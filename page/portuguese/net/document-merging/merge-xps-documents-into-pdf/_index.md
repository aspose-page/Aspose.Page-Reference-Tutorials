---
date: 2026-01-20
description: Adicione números de página a PDFs sem esforço ao mesclar documentos XPS
  em PDFs de alta qualidade usando Aspose.Page para .NET. Siga nosso guia passo a
  passo para converter XPS em PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Adicionar Números de Página ao PDF – Mesclar XPS em PDF usando Aspose.Page
url: /pt/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Números de Página PDF – Mesclar XPS em PDF usando Aspose.Page

## Introdução

Se você precisa **adicionar números de página PDF** ao mesclar arquivos XPS, o Aspose.Page para .NET torna o processo simples. Neste tutorial vamos percorrer um exemplo completo, pronto para produção, que converte um documento XPS em um PDF de alta qualidade, permite controlar a compressão de imagens e insere automaticamente números de página no PDF final. Ao final, você terá um trecho reutilizável que pode ser inserido em qualquer projeto C#.

## Respostas Rápidas
- **Posso adicionar números de página ao mesclar XPS em PDF?** Sim – a propriedade `PdfSaveOptions.PageNumbers` faz exatamente isso.  
- **Qual biblioteca realiza a conversão?** Aspose.Page para .NET.  
- **Preciso de licença para uso em produção?** É necessária uma licença válida do Aspose.Page; uma licença temporária está disponível para testes.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6+.  
- **É possível obter saída de imagem de alta qualidade?** Absolutamente – defina `JpegQualityLevel` como 100 e escolha `PdfImageCompression.Jpeg`.

## Pré‑requisitos

Antes de mergulhar no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos:

- Aspose.Page para .NET: Garanta que a biblioteca Aspose.Page esteja instalada. Você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).

- Arquivos de Documento: Tenha o documento XPS (`input.xps`) pronto no diretório especificado.

## Importar Namespaces

No seu projeto .NET, inclua os namespaces necessários para trabalhar com Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Esta etapa garante que você tenha acesso às classes e métodos necessários para a conversão do documento.

## Como adicionar números de página PDF ao mesclar documentos XPS

A coleção `PdfSaveOptions.PageNumbers` permite especificar exatamente quais páginas (ou intervalos de páginas) devem aparecer no PDF de saída. Ao preenchê‑la com os números de página desejados, o Aspose.Page insere automaticamente a numeração correta.

### Etapa 1: Inicializar Streams

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Esta etapa envolve a configuração dos streams de entrada e saída para os arquivos XPS e PDF. Certifique‑se de usar os caminhos e nomes de arquivos corretos.

### Etapa 2: Carregar Documento XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Aqui, carregamos o documento XPS no objeto `XpsDocument`, preparando‑o para processamento adicional.

### Etapa 3: Inicializar Opções de Salvamento (mesclar xps em pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Personalize o objeto `PdfSaveOptions` de acordo com suas preferências, especificando parâmetros como compressão de imagem, compressão de texto e os **números de página** que você deseja que apareçam no PDF final. Definir `JpegQualityLevel` como 100 garante **imagens PDF de alta qualidade**.

### Etapa 4: Criar Dispositivo de Renderização

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

O `PdfDevice` é a ferramenta responsável por renderizar o documento XPS no formato PDF.

### Etapa 5: Salvar o Documento (c# xps para pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Por fim, salve o documento usando o dispositivo de renderização e as opções especificadas. O PDF de saída conterá as páginas selecionadas com números de página adicionados automaticamente.

## Por que usar Aspose.Page para esta conversão?

- **Confiabilidade** – Lida com recursos complexos do XPS sem perda de fidelidade.  
- **Desempenho** – Processamento baseado em streams evita carregar arquivos inteiros na memória.  
- **Flexibilidade** – Controle granular sobre qualidade de imagem, compressão e numeração de páginas.  
- **Multiplataforma** – Funciona no Windows, Linux e macOS com .NET Core.

## Problemas Comuns e Soluções

| Problema | Solução |
|----------|---------|
| **PDF de saída está em branco** | Verifique se o caminho do arquivo XPS está correto e se o arquivo não está corrompido. |
| **Números de página não aparecem** | Certifique‑se de que `PageNumbers` está definido com os índices de página baseados em zero corretos (por exemplo, `new int[] {1,2,6}`). |
| **Imagens de baixa qualidade** | Aumente `JpegQualityLevel` e escolha `PdfImageCompression.Jpeg`. |
| **Arquivos XPS grandes causam pressão de memória** | Processar o XPS em blocos menores ou aumentar o limite de memória da aplicação. |

## Perguntas Frequentes

### Q1: Posso mesclar vários arquivos XPS em um único PDF?

A1: Sim, você pode. Basta ajustar o parâmetro `PageNumbers` em `PdfSaveOptions` para incluir as páginas desejadas de diferentes arquivos XPS, ou carregar cada XPS sequencialmente e chamar `document.Save` no mesmo `PdfDevice`.

### Q2: Existe uma licença temporária disponível para Aspose.Page para .NET?

A2: Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/) para fins de teste.

### Q3: Há limitações de tamanho de arquivo ao usar Aspose.Page para conversão de documentos?

A3: O Aspose.Page para .NET não impõe limitações rígidas de tamanho de arquivo, mas o desempenho ideal é alcançado com arquivos de tamanho razoável. Para documentos XPS muito grandes, considere processá‑los em streams para reduzir o consumo de memória.

### Q4: Posso personalizar ainda mais o PDF de saída, como adicionar marcas d'água ou anotações?

A4: Sim, o Aspose.Page para .NET oferece recursos extensos para manipulação de PDF. Após a conversão, você pode usar a biblioteca Aspose.PDF para adicionar marcas d'água, anotações ou outras melhorias.

### Q5: O Aspose.Page para .NET suporta desenvolvimento multiplataforma?

A5: Sim, o Aspose.Page para .NET foi projetado para funcionar perfeitamente em várias plataformas, incluindo Windows, Linux e macOS, quando usado com .NET Core ou .NET 5/6.

---

**Última atualização:** 2026-01-20  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}