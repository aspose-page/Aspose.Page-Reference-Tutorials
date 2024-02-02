---
title: Adicione gradiente vertical ao XPS com Aspose.Page para .NET
linktitle: Adicionar gradiente vertical ao XPS
second_title: API Aspose.Page .NET
description: Aprenda como aprimorar documentos XPS com gradientes verticais usando Aspose.Page for .NET. Siga nosso guia passo a passo para uma integração perfeita.
type: docs
weight: 15
url: /pt/net/gradient-fills/add-vertical-gradient-to-xps/
---
## Introdução

Bem-vindo a este tutorial passo a passo sobre como adicionar um gradiente vertical a um documento XPS usando Aspose.Page for .NET. Aspose.Page é uma API poderosa que permite trabalhar com arquivos XPS (XML Paper Specification) em seus aplicativos .NET. Neste tutorial, orientaremos você no processo de criação de um novo documento XPS, adição de um gradiente vertical a um caminho e salvamento do resultado.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos:

-  Biblioteca Aspose.Page for .NET: certifique-se de ter a biblioteca Aspose.Page for .NET instalada em seu ambiente de desenvolvimento. Você pode baixá-lo[aqui](https://releases.aspose.com/page/net/).

- Ambiente de desenvolvimento: configure um ambiente de desenvolvimento .NET com seu IDE preferido, como o Visual Studio.

Agora, vamos começar a adicionar um gradiente vertical a um documento XPS usando Aspose.Page for .NET.

## Importar namespaces

Em seu aplicativo .NET, inclua os namespaces necessários para acessar classes e métodos Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Etapa 1: configure seu diretório de documentos

Antes de começar, defina o caminho para o diretório do documento onde deseja salvar o documento XPS resultante.

```csharp
// ExInício:3
string dataDir = "Your Document Directory";
// Fim:3
```

## Etapa 2: crie um novo documento XPS

Inicialize um novo documento XPS usando o seguinte código:

```csharp
// ExInício:4
XpsDocument doc = new XpsDocument();
// Fim:4
```

## Etapa 3: definir paradas de gradiente

Crie uma lista de pontos de gradiente, especificando a cor e a posição de cada ponto. Neste exemplo, definimos um gradiente vertical com cinco pontos.

```csharp
// ExInício:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// Fim:5
```

## Etapa 4: crie um caminho com gradiente

Defina um caminho especificando sua geometria e aplique um pincel de gradiente linear nele.

```csharp
// ExInício:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Fim:6
```

## Etapa 5: salve o documento XPS resultante

Salve o documento XPS modificado no diretório especificado.

```csharp
// ExInício:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// Fim:7
```

Parabéns! Você adicionou com sucesso um gradiente vertical a um documento XPS usando Aspose.Page for .NET.

## Conclusão

Neste tutorial, exploramos como aproveitar o Aspose.Page for .NET para aprimorar documentos XPS com gradientes verticais. Aspose.Page simplifica tarefas complexas, fornecendo aos desenvolvedores uma maneira perfeita de manipular arquivos XPS em seus aplicativos .NET.

## Perguntas frequentes

### Q1: O Aspose.Page é compatível com o Visual Studio 2019?

A1: Sim, Aspose.Page é compatível com Visual Studio 2019. Certifique-se de ter a versão correta da biblioteca instalada.

### Q2: Posso usar Aspose.Page para projetos comerciais?

 A2: Sim, Aspose.Page pode ser usado para projetos comerciais. Visita[aqui](https://purchase.aspose.com/buy) para explorar opções de licenciamento.

### Q3: Existe um teste gratuito disponível?

 A3: Sim, você pode obter uma avaliação gratuita do Aspose.Page[aqui](https://releases.aspose.com/).

### Q4: Onde posso encontrar a documentação do Aspose.Page?

 A4: A documentação está disponível[aqui](https://reference.aspose.com/page/net/).

### P5: Como posso obter suporte ou fazer perguntas?

 A5: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio comunitário.