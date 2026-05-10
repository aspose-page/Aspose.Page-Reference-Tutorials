---
date: 2026-03-13
description: Aprenda como converter XPS para JPEG em Java com Aspose.Page Java. Este
  guia passo a passo mostra como converter XPS para JPEG de forma eficiente usando
  a biblioteca Aspose.Page Java.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Como converter XPS para JPEG em Java usando Aspose.Page Java
url: /pt/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Converter XPS para JPEG em Java usando Aspose.Page Java

## Introdução ao Aspose.Page Java
Neste tutorial **você aprenderá como converter XPS para JPEG** com a biblioteca **Aspose.Page Java**. Converter arquivos XPS em imagens JPEG é uma necessidade frequente quando você precisa exibir páginas de documentos como gráficos rasterizados em portais web, visualizadores de desktop ou anexos de e‑mail. Vamos percorrer cada linha de código, explicar por que cada configuração importa e compartilhar dicas práticas para que você possa incorporar esse pipeline de conversão em suas próprias aplicações Java com confiança.

## Respostas Rápidas
- **Qual biblioteca realiza a conversão?** Aspose.Page Java  
- **Posso selecionar páginas específicas?** Sim – use `setPageNumbers` em `JpegSaveOptions`  
- **Que qualidade de imagem posso controlar?** Modo de suavização, resolução e configurações de qualidade JPEG  
- **Preciso de licença para produção?** Sim, é necessária uma licença comercial (há uma versão de avaliação disponível)  
- **O código é compatível com Java 8?** Absolutamente – a API funciona com Java 8 e versões posteriores  

## O que é XPS e Por que Converter XPS para JPEG?
XPS (XML Paper Specification) é um formato de documento de layout fixo semelhante ao PDF. Converter XPS para JPEG é útil quando você precisa de imagens rasterizadas para miniaturas, anexos de e‑mail ou ao integrar com sistemas que aceitam apenas arquivos de imagem. JPEG oferece um bom equilíbrio entre qualidade visual e tamanho de arquivo, tornando‑o ideal para pré‑visualizações baseadas na web.

## Pré‑Requisitos
Antes de mergulharmos no código, certifique‑se de que você possui o seguinte:

- **Ambiente de Desenvolvimento Java** – JDK 8 ou superior instalado e configurado.  
- **Aspose.Page para Java** – Baixe a biblioteca mais recente no site oficial [here](https://releases.aspose.com/page/java/).  
- **Documento XPS de Exemplo** – Um arquivo XPS que você deseja transformar em imagens JPEG.  

## Importar Pacotes
Comece importando as classes necessárias para o seu arquivo fonte Java:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Etapa 1: Inicializar Caminhos e Carregar o Documento XPS
Defina o diretório que contém seu arquivo XPS de origem e crie uma instância de `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Dica profissional:** Use `Paths.get()` de `java.nio.file` para manipulação de caminhos independente da plataforma.

## Etapa 2: Configurar Opções de Salvamento JPEG
Defina como as imagens JPEG devem ser renderizadas — resolução, suavização e quais páginas exportar:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` produz saída de alta resolução adequada para impressão.  
- `setPageNumbers` permite escolher apenas as páginas necessárias, economizando tempo e memória.

## Etapa 3: Criar o Dispositivo de Renderização
O `ImageDevice` captura as páginas renderizadas como arrays de bytes:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Etapa 4: Renderizar o Documento XPS para JPEG
Chame o método `save`, passando o dispositivo e as opções que você configurou:

```java
document.save(device, options);
```

Neste ponto o `device` contém um array bidimensional onde cada elemento representa uma página codificada em JPEG.

## Etapa 5: Iterar Sobre o Resultado e Gravar os Arquivos
Percorra as páginas renderizadas e grave cada array de bytes em um arquivo JPEG separado:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

Cada arquivo será nomeado `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, facilitando a identificação do documento de origem e do número da página.

## Casos de Uso Comuns
- **Gerar miniaturas** para sistemas de gerenciamento de documentos.  
- **Incorporar pré‑visualizações de páginas** em aplicações web onde apenas formatos de imagem são suportados.  
- **Processamento em lote de grandes arquivos XPS** em JPEGs para arquivamento ou geração de relatórios.  

## Problemas Comuns & Solução de Problemas
| Sintoma | Causa Provável | Solução |
|---------|----------------|---------|
| **Arquivos JPEG em branco** | Fluxo de saída não foi finalizado ou fechado corretamente | Certifique‑se de que `imageStream.close()` seja chamado dentro do loop interno (conforme mostrado). |
| **Erros de falta de memória** em arquivos XPS grandes | Renderizar todas as páginas de uma vez consome muita RAM | Processar páginas em lotes menores ou aumentar o heap da JVM (`-Xmx`). |
| **Páginas ausentes** | `setPageNumbers` não inclui a página desejada | Verifique se o array de números de página corresponde aos índices reais do XPS (baseado em 1). |

## Perguntas Frequentes

### Q: O Aspose.Page é adequado para projetos comerciais?
A: Sim, o Aspose.Page é um produto comercial com opções de licenciamento disponíveis. Consulte [here](https://purchase.aspose.com/buy) para detalhes.

### Q: Posso testar o Aspose.Page antes de comprar?
A: Sim, você pode obter uma avaliação gratuita [here](https://releases.aspose.com/).

### Q: Onde encontro a documentação do Aspose.Page?
A: A documentação está disponível [here](https://reference.aspose.com/page/java/).

### Q: Como obter suporte para o Aspose.Page?
A: Visite o [Aspose.Page Forum](https://forum.aspose.com/c/page/39) para suporte baseado na comunidade.

### Q: Preciso de uma licença temporária para testes?
A: Sim, você pode obter uma licença temporária [here](https://purchase.aspose.com/temporary-license/).

## Conclusão
Agora você domina **como converter XPS para JPEG** usando **Aspose.Page Java**. Seguindo este guia passo a passo, você pode integrar esse pipeline de conversão em qualquer aplicação Java — seja uma ferramenta de desktop, um serviço web ou um utilitário de processamento em lote. Sinta‑se à vontade para experimentar diferentes resoluções, seleções de página e formatos de imagem para atender às necessidades do seu projeto.

---

**Última Atualização:** 2026-03-13  
**Testado Com:** Aspose.Page 24.11 for Java (mais recente na data de escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}