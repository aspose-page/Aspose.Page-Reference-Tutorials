---
date: 2026-07-10
description: Aprenda como criar documentos XPS com aspose.page usando Aspose.Page
  para .NET – um guia passo a passo para gerar arquivos XPS de alta qualidade.
keywords:
- aspose.page create xps
- XPS document generation
- Aspose.Page .NET
lastmod: 2026-07-10
linktitle: Criar documento XPS
og_description: Crie XPS rapidamente com aspose.page usando Aspose.Page para .NET.
  Siga este guia para produzir arquivos XPS de alta qualidade em menos de 20 linhas
  de código.
og_image_alt: 'Guide: Create XPS document using Aspose.Page for .NET'
og_title: aspose.page create xps – Gere documentos XPS com .NET
schemas:
- author: Aspose
  dateModified: '2026-07-10'
  description: Learn how to aspose.page create xps documents using Aspose.Page for
    .NET – a step‑by‑step guide to generate high‑quality XPS files.
  headline: aspose.page create xps – Generate XPS Documents with .NET
  type: TechArticle
- questions:
  - answer: Yes. Provide the exact font family name when calling `AddGlyphs`; the
      font must be installed on the runtime machine.
    question: Can I use custom fonts in my XPS document?
  - answer: Absolutely. The library works on .NET Core 3.1, .NET 5, .NET 6 and later,
      enabling cross‑platform XPS generation.
    question: Is Aspose.Page compatible with .NET Core?
  - answer: Use the `AddImage` method of the `XpsPage` class. The API accepts PNG,
      JPEG, BMP, and GIF formats.
    question: How do I add images to an XPS document?
  - answer: Yes. Instantiate multiple `XpsPage` objects, populate each with glyphs
      or images, and then save the document once.
    question: Can I create multi‑page XPS documents?
  - answer: Yes, you can explore the full feature set by downloading the [free trial](https://releases.aspose.com/).
    question: Is there a trial version available?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- create xps
- XPS document
- .NET document generation
title: aspose.page create xps – Gere documentos XPS com .NET
url: /pt/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page create xps – Criar documento XPS com Aspose.Page para .NET

## Introdução

Neste tutorial você aprenderá a criar documentos **aspose.page create xps** passo a passo usando a biblioteca Aspose.Page para .NET. Seja construindo um motor de relatórios, um gerador de faturas ou qualquer sistema que precise de documentos eletrônicos de alta fidelidade, o XPS é um formato confiável, baseado em XML, que preserva o layout em diferentes plataformas. Vamos percorrer tudo, desde os pré‑requisitos até a gravação do arquivo final, com dicas práticas que você pode aplicar imediatamente.

## Respostas rápidas
- **Qual biblioteca eu preciso?** Aspose.Page for .NET  
- **Posso executar isso no .NET Core?** Sim – totalmente suportado no .NET Core 3.1, .NET 5, .NET 6 e posteriores  
- **Quantas linhas de código?** Menos de 20 linhas para um arquivo XPS básico “Hello World”  
- **Preciso de licença para testes?** Um teste gratuito funciona para desenvolvimento; uma licença é necessária para implantações em produção  
- **Qual formato tem a saída?** XPS (XML Paper Specification)  

## Como criar um documento XPS com Aspose.Page para .NET?

Carregue a biblioteca Aspose.Page, instancie um `XpsDocument`, adicione uma única página com glifos, defina a cor de preenchimento e chame `Save`. Esse fluxo de trabalho completo requer apenas algumas chamadas de método e produz um arquivo XPS compatível com padrões que pode ser aberto no Windows Reader, Adobe Acrobat ou qualquer visualizador compatível com XPS. A abordagem funciona no Windows, Linux e macOS sem dependências adicionais.

## O que é aspose.page create xps?

`aspose.page create xps` refere‑se ao processo de gerar um arquivo XPS (XML Paper Specification) programaticamente usando a API Aspose.Page para .NET. A API abstrai estruturas de baixo nível de PDF/XPS, permitindo que você se concentre no conteúdo em vez das complexidades do formato de arquivo. Ela suporta a definição de tamanho de página, fontes, cores e incorporação de imagens, permitindo que desenvolvedores criem documentos ricos e imprimíveis diretamente a partir do código.

## Por que usar Aspose.Page para geração de XPS?

Aspose.Page suporta **mais de 30 formatos de saída** e pode renderizar arquivos XPS de até **500 MB** sem carregar o documento inteiro na memória, oferecendo alto desempenho em cargas de trabalho no servidor. A biblioteca garante fidelidade de layout pixel‑perfeito, incorporação automática de fontes e suporte total a Unicode, eliminando a necessidade de conversores de terceiros.

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem o seguinte:

1. **Aspose.Page for .NET Library** – faça o download a partir do [download link](https://releases.aspose.com/page/net/).  
2. **Target Directory** – decida onde o arquivo XPS gerado será salvo em sua máquina.  

Agora que o ambiente está pronto, vamos importar os namespaces necessários.

## Importar namespaces

Para usar Aspose.Page para .NET, você precisa importar os namespaces necessários em seu projeto. Siga estas etapas:

### Etapa 1: Adicionar referência ao Aspose.Page

Em seu projeto, adicione uma referência à biblioteca Aspose.Page para .NET. Você pode encontrar o DLL necessário no pacote baixado.

### Etapa 2: Importar namespaces

Inclua os seguintes namespaces em seu arquivo de código:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 1: Definir diretório do documento

A variável `directoryPath` informa à API onde gravar o arquivo XPS resultante.

```csharp
string dir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho real da pasta em seu sistema, por exemplo, `C:\\Docs\\Output`.

## Etapa 2: Criar documento XPS

A classe `XpsDocument` representa o objeto raiz de um arquivo XPS.

```csharp
XpsDocument xDocs = new XpsDocument();
```

Inicialize‑a com o nome de arquivo de destino e uma nova página será criada automaticamente.

## Etapa 3: Adicionar glifos ao documento

O método `AddGlyphs` insere texto (glifos) na página atual.

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Você pode controlar a família da fonte, tamanho, estilo e coordenadas exatas para posicionar o texto com precisão.

## Etapa 4: Definir cor de preenchimento dos glifos

O método `SetFillColor` define o pincel usado para pintar os glifos.

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Neste exemplo usamos preto (`Color.Black`), mas qualquer cor ARGB é suportada.

## Etapa 5: Salvar o resultado

Chamar `Save` grava o documento XPS no disco.

```csharp
xDocs.Save(dir + "output.xps");
```

O arquivo conterá o texto “Hello World!” que você adicionou nas etapas anteriores.

## Dicas comuns e armadilhas

- **Caminho do diretório** – Use `Path.Combine(dir, "output.xps")` para evitar a falta de separadores de caminho no Windows, Linux ou macOS.  
- **Disponibilidade de fontes** – A fonte especificada deve estar instalada na máquina host; caso contrário, a Aspose substitui por uma fonte de fallback, o que pode afetar o layout.  
- **Múltiplas páginas** – Para saída de múltiplas páginas, crie objetos `XpsPage` adicionais, adicione conteúdo a cada um e então chame `Save` uma única vez.  

## Perguntas frequentes

**Q: Posso usar fontes personalizadas no meu documento XPS?**  
A: Sim. Forneça o nome exato da família da fonte ao chamar `AddGlyphs`; a fonte deve estar instalada na máquina de tempo de execução.

**Q: O Aspose.Page é compatível com .NET Core?**  
A: Absolutamente. A biblioteca funciona no .NET Core 3.1, .NET 5, .NET 6 e posteriores, permitindo geração de XPS multiplataforma.

**Q: Como adicionar imagens a um documento XPS?**  
A: Use o método `AddImage` da classe `XpsPage`. A API aceita os formatos PNG, JPEG, BMP e GIF.

**Q: Posso criar documentos XPS de múltiplas páginas?**  
A: Sim. Instancie múltiplos objetos `XpsPage`, preencha cada um com glifos ou imagens e então salve o documento uma única vez.

**Q: Existe uma versão de teste disponível?**  
A: Sim, você pode explorar o conjunto completo de recursos baixando a [versão de teste gratuita](https://releases.aspose.com/).

## Conclusão

Agora você tem um fluxo de trabalho completo e pronto para produção de documentos **aspose.page create xps** usando Aspose.Page para .NET. Experimente diferentes fontes, cores e layouts de página para adaptar a saída às necessidades da sua aplicação. Para cenários mais avançados — como incorporação de gráficos vetoriais ou manipulação de grandes lotes — consulte a referência oficial da API.

---

**Last Updated:** 2026-07-10  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose

## Tutoriais relacionados

- [Add Text to XPS Document with Aspose.Page for .NET](/page/net/text-manipulation/add-text-to-xps-document/)
- [Add Image to XPS Document with Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [Add Rectangle to XPS Document with Aspose.Page for .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}