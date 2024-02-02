---
title: Mesclar documentos XPS em PDF com Aspose.Page para .NET
linktitle: Mesclar documentos XPS em PDF
second_title: API Aspose.Page .NET
description: Mescle facilmente documentos XPS em PDFs de alta qualidade usando Aspose.Page for .NET. Siga nosso guia passo a passo para uma experiência de conversão de documentos tranquila.
type: docs
weight: 11
url: /pt/net/document-merging/merge-xps-documents-into-pdf/
---
## Introdução

No cenário em constante evolução do processamento de documentos, o Aspose.Page for .NET surge como uma ferramenta poderosa para mesclar perfeitamente documentos XPS em formato PDF. Este tutorial irá guiá-lo através do processo, detalhando cada etapa para garantir uma execução tranquila e eficaz.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Aspose.Page para .NET: certifique-se de ter a biblioteca Aspose.Page instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/page/net/).

- Arquivos de documentos: Tenha o documento XPS (`input.xps`) pronto no diretório especificado.

## Importar namespaces

Em seu projeto .NET, inclua os namespaces necessários para trabalhar com Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Esta etapa garante que você tenha acesso às classes e métodos necessários para a conversão do documento.

## Etapa 1: inicializar fluxos

```csharp
// ExInício:3
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
// Inicializar fluxo de saída de PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Inicializar fluxo de entrada XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// Fim:3
```

Esta etapa envolve a configuração dos fluxos de entrada e saída para os arquivos XPS e PDF. Certifique-se de que os caminhos e nomes de arquivo corretos sejam usados.

## Etapa 2: carregar o documento XPS

```csharp
// ExInício:4
// Carregar documento XPS do fluxo
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// ou carregue o documento XPS diretamente do arquivo. Nenhum xpsStream é necessário então.
//Documento XpsDocument = new XpsDocument(inputFileName, new XpsLoadOptions());
// Fim:4
```

 Aqui, carregamos o documento XPS no`XpsDocument` objeto, preparando-o para processamento posterior.

## Etapa 3: inicializar as opções de salvamento

```csharp
// ExInício:5
// Inicialize o objeto de opções com os parâmetros necessários.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// Fim:5
```

 Personalize o`PdfSaveOptions` objeto com base em suas preferências, especificando parâmetros como compactação de imagem, compactação de texto e números de página.

## Etapa 4: criar dispositivo de renderização

```csharp
// ExInício:6
// Crie um dispositivo de renderização para formato PDF
PdfDevice device = new PdfDevice(pdfStream);
// Fim:6
```

 O`PdfDevice` é a ferramenta responsável por renderizar o documento XPS em formato PDF.

## Etapa 5: salve o documento

```csharp
// ExInício:7
document.Save(device, options);
// Fim:7
```

Finalmente, salve o documento usando o dispositivo de renderização e as opções especificadas.

## Conclusão

Parabéns! Você mesclou com sucesso documentos XPS em PDF usando Aspose.Page for .NET. Este processo contínuo garante a preservação da qualidade e formatação do documento.

## Perguntas frequentes

### P1: Posso mesclar vários arquivos XPS em um único PDF?

 A1: Sim, você pode. Basta ajustar o`PageNumbers` parâmetro no`PdfSaveOptions` para incluir as páginas desejadas de diferentes arquivos XPS.

### Q2: Há uma licença temporária disponível para Aspose.Page for .NET?

 A2: Sim, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/) para fins de teste.

### Q3: Há alguma limitação no tamanho do arquivo ao usar Aspose.Page para conversão de documentos?

A3: Aspose.Page for .NET não impõe limitações estritas ao tamanho do arquivo, mas o desempenho ideal é alcançado com tamanhos de arquivo razoáveis.

### P4: Posso personalizar ainda mais o PDF de saída, como adicionar marcas d’água ou anotações?

A4: Sim, Aspose.Page for .NET oferece amplos recursos para manipulação de PDF. Verifique a documentação para opções avançadas de personalização.

### P5: O Aspose.Page for .NET oferece suporte ao desenvolvimento de plataforma cruzada?

A5: Sim, o Aspose.Page for .NET foi projetado para funcionar perfeitamente em várias plataformas.