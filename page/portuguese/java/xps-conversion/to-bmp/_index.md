---
date: 2026-03-08
description: Aprenda como converter XPS para BMP em Java e definir a resolução do
  BMP usando a biblioteca de conversão de imagens Aspose.Page para Java. Este guia
  aborda saída de alta qualidade e dicas que economizam memória.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Converter XPS para BMP em Java – Definir Resolução para Saída de Alta Qualidade
url: /pt/java/xps-conversion/to-bmp/
weight: 10
---

Ensure proper RTL formatting if needed" - Portuguese is LTR, ignore.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter XPS para BMP em Java

## Introdução
Bem‑vindo a este guia passo a passo sobre como **converter XPS para BMP** em Java e definir a resolução para obter qualidade de imagem ideal usando Aspose.Page. Seja você quem está construindo um pipeline de impressão, gerando miniaturas ou precisando de gráficos de alta resolução, controlar o DPI oferece a flexibilidade necessária para atender a qualquer requisito.

## Respostas Rápidas
- **Qual biblioteca devo usar?** Aspose.Page for Java é a biblioteca **java image conversion library** mais completa para XPS → BMP.  
- **Posso controlar a qualidade da imagem?** Sim – use `BmpSaveOptions` para **definir a resolução BMP** e o modo de suavização.  
- **Como evito OutOfMemoryError Java ao processar arquivos XPS grandes?** Renderize as páginas em partições ou aumente o heap da JVM (`-Xmx`).  
- **Preciso converter apenas páginas específicas?** Absolutamente, `options.setPageNumbers()` permite escolher as páginas exatas.  
- **Quais versões do Java são suportadas?** Todas as versões modernas do Java (8 e superiores) funcionam perfeitamente.

## Qual é o objetivo de definir a resolução?
A resolução determina o número de pontos por polegada (DPI) na imagem BMP gerada. Um DPI maior produz imagens mais nítidas, o que é essencial para impressão ou trabalhos gráficos detalhados. Ajustar a resolução lhe dá controle total sobre a qualidade de saída do seu fluxo de **convert xps to bmp**.

## Por que usar Aspose.Page para conversão XPS → BMP?
- **Alta fidelidade** – mantém a qualidade vetorial do XPS original.  
- **Controle granular** – você pode definir DPI, suavização e até selecionar páginas específicas para conversão.  
- **Sem dependências externas** – Java puro, sem bibliotecas nativas necessárias.  
- **Escalável** – funciona tanto para documentos de página única quanto para arquivos XPS multi‑página grandes.  

## Pré‑requisitos
Antes de mergulhar no processo de conversão, certifique‑se de que você possui os seguintes pré‑requisitos:
- **Ambiente de Desenvolvimento Java** – Java 8 ou mais recente instalado na sua máquina.  
- **Aspose.Page for Java Library** – Baixe e inclua a biblioteca Aspose.Page for Java no seu projeto. Você pode encontrar a biblioteca [aqui](https://releases.aspose.com/page/java/).  
- **Arquivo XPS de Exemplo** – Prepare um documento XPS de exemplo que você deseja converter para BMP.

## Importar Pacotes
Inclua os pacotes necessários do Aspose.Page no seu código Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Como Definir a Resolução para Conversão XPS para BMP
A seguir, um passo a passo numerado que mostra exatamente onde e como definir a resolução, além de como **converter páginas específicas**.

### Etapa 1: Carregar o Documento XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Etapa 2: Inicializar Opções (Resolução e Seleção de Páginas)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Etapa 3: Criar o Dispositivo de Renderização
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Etapa 4: Salvar o Documento Usando as Opções
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Etapa 5: Iterar Sobre as Imagens Renderizadas e Gravar os Arquivos
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Repita estas etapas para qualquer personalização ou modificação adicional que você precise no processo de conversão.

## Como Evitar OutOfMemoryError Java ao Converter Arquivos XPS Grandes
- **Processar em partições** – O exemplo já renderiza o documento em partições (`device.getResult()`), o que reduz a pressão de memória.  
- **Aumentar o heap da JVM** – Use a flag `-Xmx` (por exemplo, `-Xmx2g`) para alocar mais memória para documentos grandes.  
- **Liberar recursos** – Chame `document.close()` quando terminar para liberar recursos nativos.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|---------|
| **Saída BMP de baixa qualidade** | Verifique se `options.setResolution()` está definido para um valor ≥ 300 DPI. |
| **Apenas parte do documento é convertida** | Certifique‑se de que `options.setPageNumbers()` inclui todos os índices de página desejados. |
| **OutOfMemoryError em arquivos XPS grandes** | Processar o documento em partições menores ou aumentar o tamanho do heap da JVM (`-Xmx`). |
| **Arquivo não encontrado** | Verifique novamente o caminho `dataDir` e se o arquivo XPS de entrada realmente existe. |

## Perguntas Frequentes
### P: Posso personalizar a resolução das imagens BMP?
R: Sim, você pode ajustar a resolução modificando o parâmetro `options.setResolution()` no código.

### P: O Aspose.Page é compatível com diferentes versões do Java?
R: Sim, o Aspose.Page suporta uma ampla gama de versões do Java. Certifique‑se de ter uma versão compatível instalada.

### P: Como posso converter arquivos XPS de um intervalo de páginas específico?
R: Use o método `options.setPageNumbers()` para especificar os números das páginas que deseja converter.

### P: Existem outros formatos de saída suportados pelo Aspose.Page?
R: Sim, o Aspose.Page suporta vários formatos de saída. Consulte a documentação para obter uma lista completa.

### P: Onde posso encontrar ajuda ou suporte adicional?
R: Visite o [Aspose.Page Forum](https://forum.aspose.com/c/page/39) para suporte da comunidade e discussões.

---

**Última atualização:** 2026-03-08  
**Testado com:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}