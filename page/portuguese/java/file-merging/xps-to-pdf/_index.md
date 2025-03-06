---
title: Converta XPS para PDF em Java
linktitle: Converta XPS para PDF em Java
second_title: API Java Aspose.Page
description: Aprenda como converter XPS para PDF em Java sem esforço com Aspose.Page. Siga nosso guia passo a passo para uma conversão eficiente de documentos.
weight: 11
url: /pt/java/file-merging/xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converta XPS para PDF em Java

## Introdução
No domínio do desenvolvimento Java, converter XPS em PDF é uma tarefa comum, e ter uma ferramenta confiável para fazer isso perfeitamente é fundamental. Aspose.Page for Java é uma biblioteca exemplar que oferece funcionalidade robusta para lidar com documentos XPS. Este tutorial irá guiá-lo através do processo de conversão de XPS em PDF usando Aspose.Page, garantindo simplicidade e eficiência.
## Pré-requisitos
Antes de mergulhar no processo de conversão, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Java Development Kit (JDK): certifique-se de ter o JDK mais recente instalado em seu sistema.
2.  Biblioteca Aspose.Page para Java: Baixe e inclua a biblioteca Aspose.Page para Java em seu projeto. Você pode encontrar a biblioteca e sua documentação[aqui](https://reference.aspose.com/page/java/).
## Importar pacotes
Depois de configurar seu projeto, importe os pacotes necessários para trabalhar com Aspose.Page. Aqui está um trecho para orientá-lo:
```java

import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Etapa 1: definir o caminho do diretório do documento
```java
String dataDir = "Your Document Directory";
```
Certifique-se de substituir “Seu diretório de documentos” pelo caminho real para o seu documento XPS.
## Etapa 2: inicializar o fluxo de saída de PDF
```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```
Crie um objeto FileOutputStream para o arquivo PDF, especificando o caminho de saída desejado.
## Etapa 3: carregar o documento XPS
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
Carregue o documento XPS usando a classe XpsDocument.
## Etapa 4: inicializar as opções de salvamento de PDF
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
Configure as opções de salvamento de PDF com base em seus requisitos, como configurações de compactação de imagem e texto.
## Etapa 5: Criar dispositivo de renderização para formato PDF
```java
PdfDevice device = new PdfDevice(pdfStream);
```
Inicialize um objeto PdfDevice para renderizar o documento XPS em PDF.
## Etapa 6: salve o documento
```java
document.save(device, options);
```
Por fim, salve o documento XPS em PDF usando o método salvar.
Seguindo essas etapas simples, você pode converter perfeitamente XPS em PDF em Java usando Aspose.Page, fornecendo uma solução confiável e eficiente para suas necessidades de conversão de documentos.
## Conclusão
Concluindo, Aspose.Page for Java simplifica o processo de conversão de XPS para PDF, permitindo que os desenvolvedores Java integrem perfeitamente essa funcionalidade em seus aplicativos. O guia passo a passo garante uma experiência tranquila, tornando-o acessível tanto para iniciantes quanto para desenvolvedores experientes.
## Perguntas frequentes
### P: O Aspose.Page é compatível com diferentes versões do Java?
R: Sim, Aspose.Page foi projetado para ser compatível com várias versões Java.
### P: Posso personalizar as configurações de compactação do PDF convertido?
R: Com certeza, Aspose.Page oferece opções para personalizar as configurações de compactação de imagem e texto.
### P: Onde posso encontrar suporte adicional ou discussões na comunidade?
 R: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para discussões e apoio da comunidade.
### P: Existe uma avaliação gratuita disponível para Aspose.Page?
 R: Sim, você pode explorar uma avaliação gratuita[aqui](https://releases.aspose.com/).
### P: Como posso obter uma licença temporária para Aspose.Page?
 R: Você pode adquirir uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
