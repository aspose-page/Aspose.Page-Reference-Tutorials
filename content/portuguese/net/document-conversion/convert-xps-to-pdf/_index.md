---
title: Converta XPS em PDF com Aspose.Page para .NET
linktitle: Converter XPS em PDF
second_title: API Aspose.Page .NET
description: Converta facilmente XPS para PDF em .NET com Aspose.Page. Baixe a biblioteca, explore a documentação e faça uma avaliação gratuita.
type: docs
weight: 11
url: /pt/net/document-conversion/convert-xps-to-pdf/
---
## Introdução

Neste tutorial, nos aprofundaremos no processo de conversão de documentos XPS (XML Paper Specification) em PDF (Portable Document Format) usando a poderosa biblioteca Aspose.Page for .NET. Aspose.Page for .NET fornece um conjunto robusto de recursos para trabalhar com arquivos XPS, permitindo que os desenvolvedores os convertam perfeitamente para o formato PDF com várias opções de personalização.

## Pré-requisitos

Antes de embarcarmos nesta jornada de conversão, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Biblioteca Aspose.Page for .NET: certifique-se de ter a biblioteca Aspose.Page for .NET instalada em seu ambiente de desenvolvimento. Você pode baixá-lo no[Documentação Aspose.Page](https://reference.aspose.com/page/net/).

- Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento .NET com Visual Studio ou qualquer outro IDE compatível.

- Documento XPS: Prepare o documento XPS que deseja converter para PDF. Este pode ser o seu arquivo XPS de amostra armazenado em um diretório designado.

## Importar namespaces

Antes de mergulhar no código, vamos importar os namespaces necessários para tornar as funcionalidades do Aspose.Page for .NET acessíveis em nosso código:

```csharp
using Aspose.Page.XPS;
```

## Etapa 1: inicializar o diretório de documentos

```csharp
string dataDir = "Your Document Directory";
```

Substitua “Seu diretório de documentos” pelo caminho para o diretório que contém seu documento XPS.

## Etapa 2: inicializar fluxos PDF e XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Abra fluxos para o arquivo PDF de saída e para o arquivo XPS de entrada. Certifique-se de ter os caminhos de arquivo apropriados definidos.

## Etapa 3: carregar o documento XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Carregue o documento XPS usando a biblioteca Aspose.Page for .NET.

## Etapa 4: inicializar as opções de salvamento de PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Configure as opções de salvamento de PDF, incluindo parâmetros como nível de qualidade JPEG, compactação de imagem, compactação de texto e números de páginas específicos a serem incluídos.

## Passo 5: Crie um dispositivo de renderização de PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Crie um dispositivo de renderização para o formato PDF usando a biblioteca Aspose.Page for .NET.

## Etapa 6: Salvar documento em PDF

```csharp
document.Save(device, options);
```

Salve o documento XPS em PDF usando o dispositivo de renderização e as opções especificadas.

## Conclusão

Parabéns! Você converteu com sucesso um documento XPS em PDF usando Aspose.Page for .NET. Esta biblioteca versátil oferece aos desenvolvedores um conjunto de ferramentas poderoso para lidar com vários formatos de documentos sem esforço.

## Perguntas frequentes

### Q1: Posso converter vários arquivos XPS em um único PDF usando Aspose.Page for .NET?

A1: Sim, você pode percorrer vários arquivos XPS e seguir as mesmas etapas para mesclá-los em um único PDF.

### Q2: Existem outros formatos de saída suportados pelo Aspose.Page for .NET?

A2: Sim, Aspose.Page for .NET suporta vários formatos de saída, incluindo TIFF, JPEG, PNG e muito mais.

### P3: Como posso personalizar a aparência do documento PDF convertido?

A3: Você pode ajustar os parâmetros do objeto de opções, como compactação de imagem e compactação de texto, para obter a aparência desejada.

### Q4: Existe uma versão de teste disponível para Aspose.Page for .NET?

 A4: Sim, você pode explorar os recursos do Aspose.Page for .NET obtendo uma avaliação gratuita em[aqui](https://releases.aspose.com/).

### P5: Onde posso obter suporte da comunidade para Aspose.Page for .NET?

 A5: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para discussões e apoio da comunidade.