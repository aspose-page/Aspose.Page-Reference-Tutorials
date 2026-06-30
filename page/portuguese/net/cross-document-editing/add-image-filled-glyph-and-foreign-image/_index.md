---
date: 2026-06-30
description: Aprenda como criar um documento XPS .NET e adicionar glifos preenchidos
  com imagem ou imagens externas usando Aspose.Page para .NET em alguns passos simples.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Adicionar glifo preenchido com imagem e imagem externa
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Criar documento XPS .NET – Adicionar glifo preenchido com imagem e imagem externa
  com Aspose.Page
url: /pt/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Documento XPS .NET – Adicionar Glifo Preenchido com Imagem & Imagem Estrangeira com Aspose.Page

## Introdução

Em desenvolvimento .NET, tarefas de **criar documento XPS .NET** são comuns quando você precisa de gráficos de alta qualidade e independentes de resolução. Aspose.Page para .NET torna isso simples e permite enriquecer arquivos XPS com glifos preenchidos com imagem ou inserir imagens de outro documento XPS. Ao final deste tutorial, você saberá como criar dois documentos XPS, preencher glifos com imagens e reutilizar essas imagens entre documentos — perfeito para gerar faturas, certificados ou qualquer saída visualmente rica.

## Respostas Rápidas

- **O que o Aspose.Page suporta?** Mais de 25 formatos de imagem e a capacidade de processar arquivos XPS de até 500 MB sem carregamento completo na memória.  
- **Quantas linhas de código são necessárias para adicionar um glifo preenchido com imagem?** Apenas duas linhas: crie um `ImageBrush` e atribua‑o a um `Glyph`.  
- **Preciso de uma licença para produção?** Sim, uma licença comercial remove as marcas d'água de avaliação.  
- **Quais versões do .NET são compatíveis?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso reutilizar fontes de outro XPS?** Absolutamente – você pode importar a coleção de fontes do primeiro documento para o segundo.

## Como criar um documento XPS usando Aspose.Page .NET?

Carregue a biblioteca Aspose.Page, instancie um `XpsDocument`, adicione uma página e chame `Save` – esse é o fluxo de trabalho completo em três declarações concisas. A API lida automaticamente com o tamanho da página, DPI e gerenciamento de recursos, portanto você não precisa gerenciar estruturas XPS de baixo nível. Essa abordagem escala de um folheto de página única a catálogos de várias centenas de páginas.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

- **Aspose.Page for .NET** – faça o download a partir de [aqui](https://releases.aspose.com/page/net/).  
- **Um IDE .NET** – Visual Studio, Rider ou VS Code com a extensão C#.  
- **Uma pasta para seus documentos** – nos referiremos a ela como **Your Document Directory** nos trechos de código.

## Importar Namespaces

O namespace `Aspose.Page.XPS` fornece classes centrais de documentos XPS, enquanto `Aspose.Page.XPS.XpsModel` contém elementos de modelo como glifos e pincéis. Importe‑os no início do seu arquivo:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## O que é um Glifo Preenchido com Imagem?

Um glifo é uma forma vetorial que pode ser renderizada com uma cor sólida, gradiente ou um pincel de imagem. Quando você aplica um `ImageBrush`, o interior do glifo é pintado com a imagem fornecida, permitindo efeitos visuais complexos sem rasterizar a página inteira.

## Etapa 1: Criar o Primeiro Documento XPS

`XpsDocument` representa um pacote XPS e é o ponto de entrada para criar e salvar arquivos XPS. Comece criando o primeiro documento XPS que hospedará os glifos preenchidos com imagem.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Etapa 2: Adicionar Glifos ao Primeiro Documento

`XpsGlyphs` define uma coleção de glifos (caracteres de texto) que podem ser colocados em uma página. Adicione glifos ao primeiro documento, especificando a fonte, tamanho, estilo e posição.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Etapa 3: Preencher Glifos com um Pincel de Imagem

`ImageBrush` pinta uma área com uma imagem, permitindo que padrões ou fotos preencham formas. Preencha os glifos com um pincel de imagem, usando uma imagem do seu diretório de dados.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Etapa 4: Criar o Segundo Documento XPS

`XpsDocument` é usado para criar um novo arquivo XPS que pode conter páginas, recursos e conteúdo. Agora, crie o segundo documento XPS que incorporará glifos do primeiro documento.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Etapa 5: Adicionar Glifos com a Fonte do Primeiro Documento

`Font` representa um tipo de letra usado para renderizar texto em um documento XPS. Adicione glifos ao segundo documento, usando a fonte extraída do primeiro documento. Ao compartilhar a coleção de fontes, você mantém o tamanho do arquivo baixo e garante consistência visual.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Etapa 6: Criar um Pincel de Imagem a partir do Preenchimento do Primeiro Documento

`ImageBrush` pode ser criado a partir de um preenchimento existente para reutilizar a mesma imagem em vários documentos. Crie um pincel de imagem a partir do preenchimento do primeiro documento e use‑o para preencher os glifos no segundo documento. Essa técnica de “imagem estrangeira” permite reutilizar arte sem duplicar o arquivo fonte.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Etapa 7: Salvar os Documentos

`Save` grava o pacote XPS em um arquivo, incorporando todos os recursos. Salve tanto o primeiro quanto o segundo documento XPS na pasta de saída. O método `Save` grava o pacote XPS, incorporando todos os recursos e preservando os glifos preenchidos com imagem.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Problemas Comuns e Soluções

| Problema | Por que acontece | Solução |
|----------|------------------|--------|
| **Imagem não aparece dentro do glifo** | O `ImageBrush` foi criado com um URI incorreto ou o tamanho da imagem excede os limites do glifo. | Verifique o caminho da imagem e, opcionalmente, defina `ImageBrush.Stretch = Stretch.Uniform`. |
| **Fontes ausentes no segundo documento** | Os recursos de fontes não foram exportados do primeiro XPS. | Use `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` antes de adicionar glifos. |
| **Desempenho lento em arquivos grandes** | Carregando imagens grandes na memória para cada glifo. | Reutilize uma única instância de `ImageBrush` para todos os glifos, ou reduza a amostra da imagem antes do uso. |

## Perguntas Frequentes

### Q1: Posso usar diferentes formatos de imagem para preencher glifos?

R1: Sim, Aspose.Page suporta PNG, JPEG, BMP, GIF, TIFF e mais — mais de 25 formatos no total.

### Q2: Como posso personalizar ainda mais a aparência dos glifos?

R2: Explore propriedades como `Glyph.Stroke`, `Glyph.FillOpacity` e `Glyph.Transform` para ajustar contornos, opacidade de preenchimento e rotação.

### Q3: O Aspose.Page é adequado para lidar com grandes conjuntos de documentos?

R3: Absolutamente. A biblioteca processa arquivos XPS com várias centenas de páginas usando streaming, mantendo o uso de memória abaixo de 100 MB mesmo para documentos de 500 páginas.

### Q4: Posso aplicar estilos diferentes a glifos individuais?

R4: Sim, cada instância de `Glyph` tem suas próprias propriedades `Fill`, `Stroke` e `Transform`, permitindo estilização por glifo.

### Q5: Quais são os benefícios de usar o Aspose.Page em relação a outras ferramentas XPS?

R5: Aspose.Page suporta mais de 25 formatos de imagem, processa arquivos de até 500 MB sem carregamento completo na memória e fornece uma API 100 % nativa .NET — eliminando a necessidade de interop COM ou ferramentas externas.

---

**Última Atualização:** 2026-06-30  
**Testado com:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Criar Documento XPS – Aspose.Page for .NET](/page/net/document-creation/)
- [Adicionar Imagem ao Documento XPS com Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [Adicionar Clone de Glifo e Alterar Cor com Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}