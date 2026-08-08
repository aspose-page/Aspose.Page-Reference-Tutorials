---
date: 2026-06-30
description: Aprenda como criar documento postscript .NET e adicionar retângulos usando
  Aspose.Page para .NET. Guia passo a passo com exemplos de código.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Adicionar Retângulo ao PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Criar Documento PostScript .NET – Adicionar Retângulo Aspose.Page
url: /pt/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Retângulo ao PostScript (PS) com Aspose.Page para .NET

## Introdução

Aspose.Page for .NET é uma biblioteca que permite a criação e manipulação de arquivos PostScript, EPS e XPS programaticamente. Se você está procurando **create postscript document .net**, este tutorial orienta você a adicionar retângulos a um documento PostScript usando Aspose.Page, proporcionando uma base sólida para a geração de gráficos mais avançados.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.Page for .NET.  
- **Posso criar um documento PostScript do zero?** Yes – the API lets you build PS files programmatically.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Preciso de uma licença para desenvolvimento?** A free trial works for testing; a license is required for production.  
- **Quanto tempo leva a implementação?** Typically under 10 minutes for basic shapes.

## O que é criar um documento postscript .net?

Criar um documento PostScript em .NET significa gerar programaticamente um arquivo `.ps` que descreve o conteúdo da página — texto, gráficos ou formas — usando a API Aspose.Page. Essa abordagem é ideal para geração de gráficos no lado do servidor, criação automatizada de relatórios ou qualquer cenário em que você precise de controle preciso sobre o formato de saída.

## Por que usar Aspose.Page para .NET?

Aspose.Page suporta **30+ primitives gráficas** e pode gerar arquivos de até **500 MB** sem carregar o documento inteiro na memória, oferecendo renderização de alto desempenho no Windows, Linux e macOS. Ele fornece controle total sobre formas, cores e traços, eliminando a necessidade de escrever código PostScript de baixo nível.

- **Controle total sobre gráficos** – desenhe formas, defina cores e aplique traços sem lidar com a sintaxe PS de baixo nível.  
- **Multiplataforma** – funciona em runtimes Windows, Linux e macOS.  
- **Sem dependências externas** – a biblioteca lida com toda a geração de PS internamente.  
- **Documentação rica e exemplos** – comece a usar rapidamente.

## Pré-requisitos

- **Aspose.Page for .NET Library** – download e instale a partir de [here](https://releases.aspose.com/page/net/).  
- **Ambiente de Desenvolvimento** – Visual Studio, VS Code ou qualquer IDE compatível com .NET.

## Importar Namespaces

O namespace `Aspose.Page` expõe as classes principais que você precisará, como `Document`, `Page`, `SolidBrush` e `Pen`. Importe-o antes de começar a codificar.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora vamos dividir o exemplo em etapas claras e numeradas.

## Etapa 1: Configurar o Diretório do Seu Documento

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pela pasta onde você deseja salvar o arquivo PS resultante.

## Etapa 2: Criar Fluxo de Saída para o Documento PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Este fluxo aponta para **AddRectangle_outPS.ps**. Sinta-se à vontade para renomear o arquivo ou alterar o local conforme necessário.

## Etapa 3: Definir Opções de Salvamento e Criar o Documento PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Aqui informamos ao Aspose.Page para usar o tamanho de página A4 e criar um documento de uma única página.

## Etapa 4: Adicionar um Retângulo Preenchido

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Definimos um retângulo em (250, 100) com largura 150 e altura 100, definimos um pincel laranja e preenchemos a forma.

## Etapa 5: Adicionar um Retângulo Contornado

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Um segundo retângulo é criado mais abaixo na página, desta vez com um traço vermelho de 3 pontos.

## Etapa 6: Fechar a Página e Salvar o Documento

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Fechar a página finaliza o desenho, e `Save()` grava o arquivo PS no disco.

## Como criar documento postscript .net?

`Document` é a classe principal que representa um arquivo PostScript no Aspose.Page. `SaveOptions` especifica configurações como tamanho da página e formato de saída para o documento. Carregue o objeto `Document`, configure `SaveOptions` para uma página A4, desenhe suas formas com `SolidBrush` ou `Pen`, então chame `document.Save()` — todo o fluxo de trabalho requer apenas algumas linhas de código e funciona em qualquer runtime .NET suportado. Esse padrão permite gerar arquivos PostScript totalmente compatíveis sem tocar na sintaxe PS bruta.

## Como gerar arquivo postscript

Use a classe `SaveOptions` do Aspose.Page para especificar o formato de saída como PostScript (`SaveFormat.PS`). A biblioteca transmite o conteúdo diretamente para um arquivo ou stream de memória, permitindo gerar documentos grandes de forma eficiente sem consumo excessivo de memória.

## Problemas Comuns & Dicas

- **Caminho de arquivo incorreto** – Certifique-se de que `dataDir` termina com um separador de caminho (`\\` ou `/`) ou use `Path.Combine`.  
- **Licença ausente** – Em um ambiente de produção, aplique sua licença Aspose antes de criar o documento para evitar marcas d'água de avaliação.  
- **Visibilidade da cor** – Se o retângulo aparecer em branco, verifique se as cores do pincel ou da caneta contrastam com o fundo da página.

## Perguntas Frequentes

**Q:** Posso personalizar as cores dos retângulos?  
**A:** Absolutamente. Altere os valores `Color.Orange` ou `Color.Red` nos construtores `SolidBrush` e `Pen` para qualquer `System.Drawing.Color` que preferir.

**Q:** O Aspose.Page é compatível com outros formatos de documento?  
**A:** Sim. Além de PostScript, o Aspose.Page também suporta geração de XPS e EPS.

**Q:** Como posso adicionar texto ao mesmo documento?  
**A:** Use a classe `TextFragment` para posicionar texto nas coordenadas desejadas, então chame `document.Draw(textFragment)`.

**Q:** Onde posso encontrar exemplos adicionais e a referência completa da API?  
**A:** Explore a documentação [here](https://reference.aspose.com/page/net/) e participe da comunidade no [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Posso experimentar o Aspose.Page antes de comprar?  
**A:** Sim, faça download de uma avaliação gratuita [here](https://releases.aspose.com/). Para avaliação prolongada, considere uma [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Última Atualização:** 2026-06-30  
**Testado com:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Criar Documento PostScript com Aspose.Page para .NET](/page/net/document-creation/create-postscript-document/)
- [Adicionar Imagem ao Documento PostScript (PS) com Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Adicionar Texto ao Documento PostScript (PS) com Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}