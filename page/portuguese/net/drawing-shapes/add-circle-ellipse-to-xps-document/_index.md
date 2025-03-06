---
title: Adicione Circle Ellipse ao documento XPS com Aspose.Page para .NET
linktitle: Adicionar círculo elipse ao documento XPS
second_title: API Aspose.Page .NET
description: Aprimore documentos XPS com gradientes radiais vibrantes usando Aspose.Page para .NET. Siga nosso guia passo a passo para obter efeitos visuais impressionantes.
weight: 11
url: /pt/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicione Circle Ellipse ao documento XPS com Aspose.Page para .NET

## Introdução

A criação de documentos XPS visualmente atraentes é um requisito comum em vários aplicativos. Aspose.Page for .NET fornece um poderoso conjunto de recursos para manipular documentos XPS com eficiência. Neste tutorial, vamos nos concentrar em adicionar uma elipse circular a um documento XPS usando Aspose.Page for .NET. Siga as etapas abaixo para aprimorar seus documentos XPS com gradientes radiais vibrantes.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Biblioteca Aspose.Page for .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/page/net/).
- Um ambiente de desenvolvimento, de preferência Visual Studio ou qualquer outra ferramenta de desenvolvimento .NET.
- Conhecimento básico de programação C#.

## Importar namespaces

Para começar, inclua os namespaces necessários em seu código C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Agora, vamos dividir o exemplo em várias etapas:

## Etapa 1: configurar o documento

```csharp
// ExInício:1
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
// Criar novo documento XPS
XpsDocument doc = new XpsDocument();
```

Aqui, inicializamos um novo documento XPS usando Aspose.Page for .NET.

## Etapa 2: definir a elipse do gradiente radial

```csharp
// Elipse com gradiente radial no canto inferior esquerdo
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Esta etapa envolve a definição de uma elipse de gradiente radial com vários limites de cores.

## Etapa 3: definir o pincel gradiente radial

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Aqui, definimos o traço da elipse como um pincel de gradiente radial, fornecendo-lhe os parâmetros necessários.

## Etapa 4: ajustar a espessura do traço

```csharp
path.StrokeThickness = 12f;
```

Esta etapa envolve ajustar a espessura do traço para melhor visualização.

## Etapa 5: salve o documento XPS resultante

```csharp
// Salve o documento XPS resultante
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// Fim:1
```

Por fim, salve o documento XPS modificado no local desejado.

## Conclusão

Parabéns! Você adicionou com sucesso uma elipse circular com gradientes radiais ao seu documento XPS usando Aspose.Page for .NET. Experimente diferentes parâmetros e cores para obter os efeitos visuais desejados em seus documentos.

## Perguntas frequentes

### Q1: Posso usar Aspose.Page for .NET com outros formatos de documento?

A1: Aspose.Page for .NET lida especificamente com a manipulação de documentos XPS. Para outros formatos, considere usar bibliotecas Aspose relacionadas.

### P2: Existe uma licença temporária disponível para fins de teste?

 A2: Sim, você pode obter uma licença temporária para testes visitando[esse link](https://purchase.aspose.com/temporary-license/).

### P3: Onde posso encontrar ajuda e discussões adicionais?

 A3: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio e discussões da comunidade.

### Q4: Há algum documento de amostra disponível para referência?

 A4: Explore o[documentação](https://reference.aspose.com/page/net/) para obter exemplos e diretrizes abrangentes.

### Q5: Posso comprar Aspose.Page para .NET?

 A5: Sim, você pode comprar a biblioteca[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
