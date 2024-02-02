---
title: Recortando XPS com Aspose.Page para .NET
linktitle: Recorte XPS
second_title: API Aspose.Page .NET
description: Explore o poder do Aspose.Page for .NET neste guia passo a passo sobre como recortar documentos XPS. Crie, manipule e salve arquivos XPS sem esforço.
type: docs
weight: 11
url: /pt/net/canvas-manipulation/clippingxps/
---
## Introdução

Bem-vindo a este tutorial abrangente sobre Clipping XPS usando Aspose.Page for .NET! Neste guia, orientaremos você no processo de criação, manipulação e salvamento de documentos XPS usando Aspose.Page for .NET. XPS, ou XML Paper Specification, é um formato de documento padronizado e aberto, e Aspose.Page for .NET fornece ferramentas poderosas para trabalhar com documentos XPS em seus aplicativos .NET.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos:

- Visual Studio instalado em sua máquina.
-  Biblioteca Aspose.Page for .NET adicionada ao seu projeto. Você pode baixá-lo[aqui](https://releases.aspose.com/page/net/).
- Conhecimento básico da linguagem de programação C#.

## Importar namespaces

Para usar as funcionalidades do Aspose.Page for .NET, você precisa importar os namespaces necessários para o seu projeto. Siga esses passos:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Agora, vamos dividir o código de exemplo fornecido em várias etapas.

## Etapa 1: Defina o caminho do diretório do documento.

```csharp
string dataDir = "Your Document Directory";
```

Certifique-se de substituir "Seu diretório de documentos" pelo caminho real para o diretório de documentos.

## Etapa 2: Crie um novo documento XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

Isso cria um novo documento XPS com o qual você trabalhará.

## Etapa 3: Crie a tela principal.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Esta etapa cria a tela principal, que é comum a todos os elementos da página.

## Etapa 4: defina os deslocamentos esquerdo e superior na tela principal.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Ajuste os deslocamentos esquerdo e superior de acordo com suas necessidades.

## Etapa 5: Crie uma geometria de caminho retangular.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Isso cria uma geometria de caminho para um retângulo.

## Etapa 6: Crie um preenchimento para retângulos.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Defina a cor de preenchimento dos retângulos.

## Passo 7: Adicione outra tela com clipe à tela principal.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Esta etapa adiciona outra tela à tela principal.

## Etapa 8: Crie uma geometria circular para o clipe.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Isso cria uma geometria de clipe circular e a aplica à segunda tela.

## Passo 9: Crie um retângulo na segunda tela e preencha-o.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Esta etapa cria um retângulo na segunda tela e o preenche.

## Etapa 10: Adicione a segunda tela com um retângulo traçado à tela principal.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Isso adiciona outra tela à tela principal.

## Passo 11: Crie um retângulo na terceira tela e trace-o.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Isso cria um retângulo na terceira tela e aplica um traço a ele.

## Etapa 12: Salve o documento XPS resultante.

```csharp
doc.Save(dataDir + "output2.xps");
```

Isso salva o documento XPS no diretório especificado.

## Conclusão

Parabéns! Você aprendeu com sucesso como recortar XPS usando Aspose.Page for .NET. Este guia forneceu um passo a passo detalhado das etapas envolvidas no processo.

## Perguntas frequentes

### Q1: Posso usar Aspose.Page for .NET com outros formatos de documento?

A1: Aspose.Page for .NET concentra-se principalmente em documentos XPS, mas Aspose fornece outras bibliotecas para vários formatos de documentos.

### Q2: O Aspose.Page for .NET é adequado para iniciantes?

A2: Sim, o Aspose.Page for .NET foi projetado para ser fácil de usar e os iniciantes podem compreender rapidamente suas funcionalidades com a documentação adequada.

### P3: Onde posso encontrar mais exemplos e recursos?

 A3: Visite o[documentação](https://reference.aspose.com/page/net/) e[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para recursos e exemplos extensos.

### Q4: Como posso obter uma licença temporária para Aspose.Page for .NET?

 A4: Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Existe uma avaliação gratuita disponível para Aspose.Page for .NET?

 A5: Sim, você pode explorar a avaliação gratuita[aqui](https://releases.aspose.com/).