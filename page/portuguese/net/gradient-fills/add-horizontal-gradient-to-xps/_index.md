---
title: Adicione gradiente horizontal ao XPS com Aspose.Page para .NET
linktitle: Adicionar gradiente horizontal ao XPS
second_title: API Aspose.Page .NET
description: Aprenda como adicionar gradientes horizontais impressionantes aos seus documentos XPS usando Aspose.Page for .NET. Aumente o apelo visual sem esforço.
type: docs
weight: 13
url: /pt/net/gradient-fills/add-horizontal-gradient-to-xps/
---
## Introdução

Neste tutorial, exploraremos como aprimorar documentos XPS adicionando um gradiente horizontal usando Aspose.Page for .NET. Aspose.Page for .NET é uma biblioteca poderosa que fornece manipulação perfeita de documentos XPS (XML Paper Specification) em aplicativos .NET. Adicionar gradientes pode trazer apelo visual aos seus documentos, e este guia irá guiá-lo passo a passo pelo processo.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Biblioteca Aspose.Page for .NET: certifique-se de ter a biblioteca Aspose.Page for .NET instalada em seu ambiente de desenvolvimento. Você pode baixá-lo no[Documentação Aspose.Page para .NET](https://reference.aspose.com/page/net/).

2. Ambiente de desenvolvimento: configure um ambiente de desenvolvimento adequado, incluindo um editor de código como o Visual Studio.

## Importar namespaces

Comece importando os namespaces necessários para o seu projeto. Esses namespaces são essenciais para trabalhar com Aspose.Page for .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Agora, vamos dividir o exemplo fornecido em várias etapas.

## Etapa 1: definir o caminho do diretório do documento

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

## Etapa 3: inicializar paradas de gradiente

```csharp
// ExInício:5
// Inicializar lista de XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// Fim:5
```

## Etapa 4: crie um novo caminho

```csharp
// ExInício:6
//Crie um novo caminho definindo a geometria em forma abreviada
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// Fim:6
```

## Etapa 5: salve o documento XPS resultante

```csharp
// ExInício:7
// Salve o documento XPS resultante
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// Fim:7
```

Agora, você adicionou com sucesso um gradiente horizontal ao seu documento XPS usando Aspose.Page for .NET.

## Conclusão

Aprimorar seus documentos XPS com gradientes não apenas melhora seu apelo visual, mas também proporciona uma experiência de usuário mais envolvente. Aspose.Page for .NET simplifica esse processo, permitindo que você obtenha resultados profissionais sem esforço.

## Perguntas frequentes

### Q1: Onde posso encontrar a documentação do Aspose.Page for .NET?

 A1: Você pode encontrar a documentação[aqui](https://reference.aspose.com/page/net/).

### Q2: Como faço o download do Aspose.Page para .NET?

 A2: Você pode baixar a biblioteca do[Página de download do Aspose.Page para .NET](https://releases.aspose.com/page/net/).

### Q3: Onde posso comprar Aspose.Page para .NET?

 A3: Você pode comprar Aspose.Page para .NET no[página de compra](https://purchase.aspose.com/buy).

### Q4: Existe um teste gratuito disponível?

 A4: Sim, você pode obter uma avaliação gratuita em[aqui](https://releases.aspose.com/).

### Q5: Como obtenho uma licença temporária do Aspose.Page for .NET?

 A5: Você pode obter uma licença temporária de[esse link](https://purchase.aspose.com/temporary-license/).