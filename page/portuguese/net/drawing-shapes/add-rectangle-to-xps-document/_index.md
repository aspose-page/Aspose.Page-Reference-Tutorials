---
title: Adicionar retângulo ao documento XPS com Aspose.Page para .NET
linktitle: Adicionar retângulo ao documento XPS
second_title: API Aspose.Page .NET
description: Aprimore a criação de documentos com Aspose.Page for .NET. Aprenda como adicionar retângulos a documentos XPS neste tutorial passo a passo.
type: docs
weight: 13
url: /pt/net/drawing-shapes/add-rectangle-to-xps-document/
---
## Introdução

Aspose.Page for .NET é uma biblioteca poderosa que fornece uma variedade de recursos para trabalhar com documentos XPS (XML Paper Specification) em aplicativos .NET. Neste tutorial, focaremos na adição de um retângulo a um documento XPS usando Aspose.Page for .NET. Siga este guia passo a passo para aprimorar seu processo de criação de documentos.

## Pré-requisitos

Antes de começar com este tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Biblioteca Aspose.Page for .NET: certifique-se de ter a biblioteca Aspose.Page for .NET instalada em seu ambiente de desenvolvimento. Você pode baixá-lo[aqui](https://releases.aspose.com/page/net/).

2. Diretório de documentos: configure um diretório onde deseja armazenar seus documentos XPS.

## Importar namespaces

Em seu aplicativo .NET, inclua os namespaces necessários para usar as funcionalidades do Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 1: definir o diretório de documentos

```csharp
// ExInício:3
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
// Fim:3
```

## Etapa 2: crie um novo documento XPS

```csharp
// ExInício:4
// Criar novo documento XPS
XpsDocument doc = new XpsDocument();
// Fim:4
```

## Etapa 3: adicione um retângulo

```csharp
// ExInício:5
// Retângulo traçado de cor sólida CMYK (azul) no canto inferior esquerdo
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// Fim:5
```

## Etapa 4: salve o documento

```csharp
// ExInício:6
// Salve o documento XPS resultante
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// Fim:6
```

Parabéns! Você adicionou com êxito um retângulo a um documento XPS usando Aspose.Page for .NET.

## Conclusão

Aspose.Page for .NET simplifica as tarefas de manipulação de documentos, permitindo que os desenvolvedores criem e modifiquem documentos XPS sem esforço. Este guia passo a passo demonstra como adicionar um retângulo ao seu documento XPS, fornecendo uma base sólida para exploração posterior.

## Perguntas frequentes

### Q1: O Aspose.Page é compatível com todos os aplicativos .NET?

A1: Sim, o Aspose.Page foi projetado para funcionar perfeitamente com todos os aplicativos .NET.

### Q2: Onde posso encontrar a documentação do Aspose.Page for .NET?

 A2: A documentação está disponível[aqui](https://reference.aspose.com/page/net/).

### Q3: Posso experimentar o Aspose.Page for .NET gratuitamente antes de comprar?

 A3: Sim, você pode obter uma avaliação gratuita[aqui](https://releases.aspose.com/).

### Q4: Como posso obter uma licença temporária para Aspose.Page for .NET?

 A4: Visita[esse link](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária.

### P5: Onde posso buscar suporte da comunidade ou fazer perguntas relacionadas ao Aspose.Page for .NET?

 A5: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio comunitário.