---
date: 2025-12-23
description: Aprenda como converter XPS para PDF em Java usando Aspose.Page. Este
  guia mostra a conversão passo a passo, como renderizar PDF a partir de XPS e especificar
  os números de página do PDF.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Como converter XPS para PDF em Java
url: /pt/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Converter XPS para PDF em Java

## Como Converter XPS para PDF em Java
No âmbito do desenvolvimento Java, **como converter XPS para PDF** é uma pergunta frequente. Seja construindo um sistema de gerenciamento de documentos ou precisando gerar relatórios imprimíveis, converter arquivos XPS de forma confiável pode ser um divisor de águas. Felizmente, o Aspose.Page for Java torna simples **renderizar PDF a partir de XPS** com apenas algumas linhas de código.

## Respostas Rápidas
- **Qual biblioteca lida com a conversão?** Aspose.Page for Java.
- **Quanto tempo leva a implementação?** Aproximadamente 10‑15 minutos para uma configuração básica.
- **Preciso de uma licença?** Um teste gratuito funciona para avaliação; uma licença é necessária para produção.
- **Posso converter apenas páginas selecionadas?** Sim – use a opção *specify PDF page numbers*.
- **A conversão é sem perdas?** A biblioteca preserva gráficos vetoriais e a fidelidade do texto.

## O que é a conversão de XPS para PDF?
XPS (XML Paper Specification) é o formato de documento de layout fixo da Microsoft. Convertê‑lo para PDF permite que você compartilhe, imprima ou arquive documentos usando o padrão PDF universalmente aceito.

## Por que usar Aspose.Page for Java para renderizar PDF a partir de XPS?
- **Alta fidelidade** – mantém gráficos vetoriais, fontes e layout.
- **Controle granular** – você pode definir a qualidade da imagem, compressão e até escolher páginas específicas.
- **Sem dependências externas** – Java puro, funciona em qualquer plataforma que suporte JDK.

## Prerequisites
Antes de começar, certifique‑se de que você tem:

- **Java Development Kit (JDK)** – qualquer versão recente (8+ recomendada).
- **Aspose.Page for Java** – baixe a biblioteca da [documentação](https://reference.aspose.com/page/java/).
- Um arquivo XPS que você deseja converter.

## Importar Pacotes
No seu projeto Java, importe os pacotes necessários para trabalhar com Aspose.Page for Java. Esta etapa é crucial para acessar as funcionalidades necessárias para a conversão de XPS para PDF.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Guia Passo a Passo

### Etapa 1: Definir Diretório do Documento
Defina o caminho para a pasta que contém seu arquivo XPS de origem.

```java
String dataDir = "Your Document Directory";
```

### Etapa 2: Inicializar Fluxo de Saída PDF
Crie um `FileOutputStream` que receberá o PDF gerado.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Etapa 3: Carregar Documento XPS
Carregue o arquivo XPS usando Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Etapa 4: Inicializar Opções de Salvamento PDF  
Crie opções para a conversão. Aqui você pode **specify PDF page numbers**, ajustar a qualidade da imagem e definir compressão.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Etapa 5: Criar Dispositivo de Renderização PDF  
Configure um dispositivo de renderização que escreverá a saída PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Etapa 6: Salvar o Documento  
Finalmente, salve o documento XPS como PDF usando as opções e o dispositivo configurados.

```java
document.save(device, options);
```

Repita estas etapas, ajustando os caminhos de arquivos e opções de acordo com seu cenário específico.

## Como Especificar Números de Páginas PDF ao Converter XPS
Se você precisar apenas de um subconjunto de páginas do XPS original, preencha o array `setPageNumbers` com os índices de página desejados (começando em 1). Isso ajuda a reduzir o tamanho do arquivo e o tempo de processamento.

## Problemas Comuns & Solução de Problemas
- **FileNotFoundException** – Verifique se `dataDir` aponta para a pasta correta e se o nome do arquivo XPS corresponde.
- **LicenseException** – Uma licença válida do Aspose.Page é necessária para uso em produção; caso contrário, a biblioteca funciona em modo de avaliação com marca d'água.
- **Baixa qualidade de imagem** – Aumente `setJpegQualityLevel` ou troque para compressão sem perdas, se necessário.

## Frequently Asked Questions
### Posso converter arquivos XPS com várias páginas usando Aspose.Page for Java?
Sim, você pode **specify PDF page numbers** em `PdfSaveOptions` (veja a Etapa 4) para incluir as páginas que precisar.

### Onde posso encontrar suporte adicional ou discutir dúvidas relacionadas ao Aspose.Page?
Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para suporte da comunidade e discussões.

### Existe um teste gratuito disponível para Aspose.Page for Java?
Sim, você pode explorar os recursos com um [teste gratuito](https://releases.aspose.com/).

### Como posso obter uma licença temporária para Aspose.Page for Java?
Visite [este link](https://purchase.aspose.com/temporary-license/) para detalhes da licença temporária.

### Onde posso comprar a licença do Aspose.Page for Java?
Você pode comprar a licença [aqui](https://purchase.aspose.com/buy).

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}