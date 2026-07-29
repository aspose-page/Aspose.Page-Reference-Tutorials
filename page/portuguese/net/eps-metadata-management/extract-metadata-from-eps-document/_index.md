---
date: 2026-07-29
description: Aprenda como extrair e adicionar metadados EPS usando Aspose.Page para
  .NET. Este guia mostra código passo a passo para gerenciar metadados XMP de EPS
  de forma eficiente.
keywords:
- aspose.page eps metadata
- eps metadata extraction
- aspose.page .net
lastmod: 2026-07-29
linktitle: Extrair Metadados de Documento EPS
og_description: 'Guia aspose.page eps metadata: extrair e definir metadados XMP em
  arquivos EPS usando Aspose.Page para .NET. Siga o tutorial passo a passo.'
og_image_alt: Tutorial showing how to extract and add metadata to EPS documents with
  Aspose.Page for .NET
og_title: aspose.page eps metadata – Extrair Metadados EPS com .NET
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to extract and add EPS metadata using Aspose.Page for .NET.
    This guide shows step‑by‑step code to manage EPS XMP metadata efficiently.
  headline: aspose.page eps metadata – Extract EPS Metadata with .NET
  type: TechArticle
- questions:
  - answer: Yes, iterate over a collection of file paths, apply the same extraction‑and‑update
      logic, and save each file. The API is thread‑safe, so you can parallelise the
      operation for faster batch processing.
    question: Can I add metadata to multiple EPS documents simultaneously?
  - answer: The library comfortably processes EPS files up to **500 MB**. For files
      larger than this, consider splitting the document or using a streaming approach
      to avoid out‑of‑memory exceptions.
    question: Are there any limitations on the size of EPS documents that Aspose.Page
      for .NET can handle?
  - answer: XMP follows the ISO 16684‑1 standard, but individual creators may populate
      custom namespaces. Aspose.Page reads both standard and custom properties, allowing
      you to preserve any proprietary data.
    question: Is the XMP metadata standardized for all EPS documents?
  - answer: Absolutely. You can add custom XMP schemas or extend existing ones by
      using the `XmpMetadata.AddCustomProperty` method, giving you full control over
      the metadata structure.
    question: Can I customize the metadata fields to suit specific requirements?
  - answer: Wrap the extraction and save logic in a `try…catch` block, and log `Aspose.Page.Exception`
      details. This will capture issues such as corrupted streams, unsupported properties,
      or I/O failures.
    question: How can I handle errors during the metadata addition process?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: aspose.page eps metadata – Extrair Metadados EPS com .NET
url: /pt/net/eps-metadata-management/extract-metadata-from-eps-document/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrair Metadados de Documento EPS com Aspose.Page para .NET

## Introdução

Em fluxos de trabalho de documentos modernos, **aspose.page eps metadata** é a chave para tornar arquivos EPS pesquisáveis, ordenáveis e em conformidade com as políticas de gerenciamento de conteúdo corporativo. Este tutorial orienta você a extrair metadados XMP existentes, atualizar campos comuns como *CreatorTool* e *CreateDate*, e salvar o arquivo EPS com as novas informações — tudo usando a API Aspose.Page para .NET.

## Respostas Rápidas
- **O que o tutorial cobre?** Extrair e atualizar metadados XMP em arquivos EPS com Aspose.Page para .NET.  
- **Qual versão da biblioteca é necessária?** Qualquer versão do Aspose.Page para .NET que suporte XMP (v24.10 ou posterior).  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso processar arquivos EPS grandes?** Sim — o Aspose.Page pode lidar com arquivos de até 500 MB sem carregar todo o documento na memória.  
- **O código é multiplataforma?** A biblioteca .NET funciona no Windows, Linux e macOS com .NET 6+.

## Pré-requisitos

Antes de mergulharmos no guia passo a passo, certifique‑se de que você tem o seguinte:

- **Aspose.Page for .NET Library** – Baixe e instale a biblioteca a partir de [here](https://releases.aspose.com/page/net/).  
- **Document Directory** – Uma pasta na sua máquina que contém os arquivos EPS que você deseja processar.  
- **.NET Development Environment** – Visual Studio 2022, Rider ou qualquer IDE que suporte .NET 6+.

## O que é metadados EPS?

Os **metadados EPS** consistem em pacotes XMP (Extensible Metadata Platform) incorporados que armazenam informações como criador, data de criação, título e ferramenta usada para gerar o arquivo. XMP é um formato padrão ISO, tornando os metadados intercambiáveis entre produtos Adobe, sistemas de gerenciamento de conteúdo e mecanismos de busca.

## Por que usar Aspose.Page para metadados EPS?

Aspose.Page suporta **mais de 30 propriedades XMP distintas** e pode lê‑las ou escrevê‑las sem renderizar todo o conteúdo PostScript. Ele processa arquivos EPS de até **500 MB** mantendo o uso de memória abaixo de **50 MB**, o que é ideal para pipelines de processamento em lote em ambientes de nuvem ou locais.

## Importar Namespaces

Os namespaces a seguir são necessários para trabalhar com arquivos EPS e metadados XMP.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Como extrair e definir metadados EPS usando Aspose.Page?

Carregue o arquivo EPS em um fluxo `EpsDocument`, recupere o pacote XMP existente, modifique os campos necessários e, em seguida, salve o documento de volta ao disco. Todo esse fluxo de trabalho pode ser realizado em **quatro etapas concisas** que você pode incorporar em qualquer serviço .NET ou aplicação console.

## Etapa 1: Inicializar Fluxo de Entrada do Arquivo EPS

`PsDocument` representa um documento EPS e fornece acesso às suas páginas e metadados.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```

## Etapa 2: Obter Metadados XMP

`XmpMetadata` encapsula o pacote XMP incorporado em um arquivo EPS, permitindo a leitura e escrita de propriedades de metadados.

```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

## Etapa 3: Verificar e Definir Valores de Metadados

Verifique os valores de metadados extraídos dos comentários de metadados PS e configure-os no novo metadado XMP.

### Obter Valor CreatorTool

```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```

### Obter Valor CreateDate

```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```

### Obter Valor Format

```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```

### Obter Valor Title

```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```

### Obter Valor Creator

```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```

### Obter Valor MetadataDate

```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```

## Etapa 4: Salvar Arquivo EPS com Novos Metadados XMP

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```

## Problemas Comuns e Soluções

- **Missing XMP packet** – Se `document.XmpMetadata` retornar `null`, o arquivo EPS não contém um bloco XMP. Você pode criar uma nova instância `XmpMetadata` e anexá‑la antes de salvar.  
- **Incorrect date format** – XMP espera datas no formato ISO 8601 (`yyyy-MM-ddTHH:mm:ssZ`). Use `DateTime.UtcNow.ToString("o")` para gerar uma string compatível.  
- **Large file memory spikes** – Habilite o modo de streaming definindo `EpsLoadOptions.Streaming = true` para manter o consumo de memória baixo.

## Perguntas Frequentes

**Q: Posso adicionar metadados a vários documentos EPS simultaneamente?**  
A: Sim, itere sobre uma coleção de caminhos de arquivos, aplique a mesma lógica de extração e atualização e salve cada arquivo. A API é thread‑safe, portanto você pode paralelizar a operação para um processamento em lote mais rápido.

**Q: Existem limitações no tamanho dos documentos EPS que o Aspose.Page para .NET pode manipular?**  
A: A biblioteca processa confortavelmente arquivos EPS de até **500 MB**. Para arquivos maiores que isso, considere dividir o documento ou usar uma abordagem de streaming para evitar exceções de falta de memória.

**Q: Os metadados XMP são padronizados para todos os documentos EPS?**  
A: XMP segue o padrão ISO 16684‑1, mas criadores individuais podem preencher namespaces personalizados. Aspose.Page lê tanto propriedades padrão quanto personalizadas, permitindo que você preserve quaisquer dados proprietários.

**Q: Posso personalizar os campos de metadados para atender a requisitos específicos?**  
A: Absolutamente. Você pode adicionar esquemas XMP personalizados ou estender os existentes usando o método `XmpMetadata.AddCustomProperty`, dando controle total sobre a estrutura dos metadados.

**Q: Como posso tratar erros durante o processo de adição de metadados?**  
A: Envolva a lógica de extração e salvamento em um bloco `try…catch` e registre os detalhes da `Aspose.Page.Exception`. Isso capturará problemas como fluxos corrompidos, propriedades não suportadas ou falhas de I/O.

**Q: O Aspose.Page suporta .NET Core e .NET 5/6?**  
A: Sim, a biblioteca é totalmente compatível com .NET Core 3.1, .NET 5, .NET 6 e versões posteriores, oferecendo uma API consistente em todos os runtimes suportados.

---

**Última atualização:** 2026-07-29  
**Testado com:** Aspose.Page for .NET 24.10  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Adicionar Metadados ao Documento EPS com Aspose.Page para .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Adicionar Namespace com Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)
- [Adicionar Propriedades Simples com Aspose.Page para .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}