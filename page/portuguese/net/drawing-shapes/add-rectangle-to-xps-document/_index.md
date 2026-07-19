---
date: 2026-07-19
description: Aprenda como criar um documento XPS .NET e adicionar um retângulo usando
  Aspose.Page para .NET em um guia conciso passo a passo.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Adicionar retângulo ao documento XPS
og_description: Crie rapidamente um documento XPS .NET. Este tutorial mostra como
  adicionar um retângulo a um arquivo XPS usando Aspose.Page para .NET, com código
  claro e dicas.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Criar documento XPS .NET – Adicionar retângulo com Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Criar documento XPS .NET – Adicionar retângulo com Aspose.Page
url: /pt/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Documento XPS .NET – Adicionar Retângulo com Aspose.Page

## Introdução

Neste tutorial você aprenderá a **create XPS document .NET** e a desenhar um retângulo dentro dele usando Aspose.Page para .NET. Seja construindo um motor de relatórios, uma fatura imprimível ou uma camada gráfica personalizada, a capacidade de gerar arquivos XPS programaticamente lhe dá controle total sobre o layout e a fidelidade. Siga os passos abaixo e você terá um arquivo XPS pronto‑para‑uso em minutos.

## Respostas Rápidas
- **Qual é o objetivo principal?** Criar um documento XPS .NET e adicionar uma forma de retângulo.  
- **Qual biblioteca é necessária?** Aspose.Page para .NET (disponível para download no site oficial).  
- **Preciso de uma licença para testes?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo leva a implementação?** Cerca de 5‑10 minutos para um retângulo básico.

## O que é Aspose.Page para .NET?
Aspose.Page para .NET é uma API de alto desempenho, totalmente gerenciada, que permite que desenvolvedores criem, editem e renderizem documentos XPS (XML Paper Specification) programaticamente sem depender de componentes externos. Ela oferece um modelo de objetos rico para desenhar formas, texto e imagens, e suporta recursos avançados como gerenciamento de cores, compressão e conversão para PDF, tornando-a adequada para uma ampla variedade de cenários de geração de documentos.

## Por que usar Aspose.Page para criar documento XPS .NET?
Aspose.Page suporta **30+ XPS features** — incluindo gráficos vetoriais, layout de texto e gerenciamento de cores — e pode gerar arquivos de até **500 MB** sem carregar todo o documento na memória. Essa capacidade quantificada garante desempenho suave mesmo para trabalhos de impressão em grande escala.

## Pré-requisitos

Antes de começar este tutorial, certifique‑se de que você tem os seguintes pré‑requisitos configurados:

1. Biblioteca Aspose.Page para .NET: Certifique‑se de que a biblioteca Aspose.Page para .NET está instalada em seu ambiente de desenvolvimento. Você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).
2. Diretório de Documentos: Configure um diretório onde você deseja armazenar seus documentos XPS.

## Importar Namespaces

Em sua aplicação .NET, inclua os namespaces necessários para usar as funcionalidades do Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Como adicionar um retângulo a um documento XPS no .NET?

Carregue o documento XPS, crie um objeto `Graphics`, defina um `RectangleF` com o tamanho desejado e chame `DrawRectangle`. Essa sequência desenha um retângulo em uma única linha de código e lida automaticamente com a escala DPI. Para páginas típicas tamanho A4, um retângulo de 200 × 100 pt aparece centralizado sem cálculos adicionais.

### Passo 1: Definir o Diretório de Documentos

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Passo 2: Criar um Novo Documento XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Passo 3: Adicionar um Retângulo

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Passo 4: Salvar o Documento

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Parabéns! Você adicionou com sucesso um retângulo a um documento XPS usando Aspose.Page para .NET.

## Problemas Comuns e Dicas

- **Fontes ausentes:** Certifique‑se de que as fontes que você referencia estejam instaladas no servidor; caso contrário, o Aspose.Page substitui por uma fonte padrão, o que pode alterar o layout.  
- **Documentos grandes:** Ao gerar arquivos maiores que 200 MB, considere chamar `document.SaveOptions.Compress = true` para reduzir o uso de memória.  
- **Sistema de coordenadas:** O XPS usa pontos (1/72 polegada). Lembre‑se de converter pixels para pontos se estiver trabalhando com dimensões baseadas na tela.

## Perguntas Frequentes

**Q: O Aspose.Page é compatível com todas as aplicações .NET?**  
A: Sim, o Aspose.Page funciona perfeitamente com aplicações .NET desktop, web e em nuvem.

**Q: Onde posso encontrar a documentação do Aspose.Page para .NET?**  
A: A referência completa da API está disponível [aqui](https://reference.aspose.com/page/net/).

**Q: Posso experimentar o Aspose.Page para .NET gratuitamente antes de comprar?**  
A: Sim, você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para Aspose.Page para .NET?**  
A: Visite [este link](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária.

**Q: Onde posso buscar suporte da comunidade ou fazer perguntas relacionadas ao Aspose.Page para .NET?**  
A: Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para suporte da comunidade.

---

**Última Atualização:** 2026-07-19  
**Testado com:** Aspose.Page for .NET 24.9  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar Documento XPS com Aspose.Page para .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Desenhando Formas](/page/net/drawing-shapes/)
- [Adicionar Texto ao Documento XPS com Aspose.Page para .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}