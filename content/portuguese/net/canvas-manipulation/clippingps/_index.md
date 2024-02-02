---
title: Recortando PS com Aspose.Page para .NET
linktitle: Recorte PS
second_title: API Aspose.Page .NET
description: Explore o poder do Aspose.Page for .NET neste tutorial passo a passo sobre como recortar documentos PostScript. Aprenda a aprimorar seus recursos de processamento de documentos sem esforço.
type: docs
weight: 10
url: /pt/net/canvas-manipulation/clippingps/
---
## Introdução

Bem-vindo ao tutorial abrangente sobre a utilização do Aspose.Page for .NET para implementar recorte em documentos PostScript (PS). Este tutorial irá guiá-lo através do processo de recorte de documentos PS usando Aspose.Page, uma biblioteca poderosa para trabalhar com vários formatos de documentos em aplicativos .NET.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Conhecimento prático da linguagem de programação C#.
-  Biblioteca Aspose.Page para .NET instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/page/net/).
- Um ambiente de desenvolvimento integrado (IDE), como o Visual Studio.

## Importar namespaces

Comece importando os namespaces necessários em seu código C#:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora, vamos dividir o exemplo em várias etapas:

## Etapa 1: definir diretório de documentos

```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
```

## Etapa 2: Criar fluxo de saída para documento PostScript

```csharp
// Crie fluxo de saída para documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

## Etapa 3: criar opções para salvar

```csharp
// Crie opções de salvamento com valores padrão
PsSaveOptions options = new PsSaveOptions();
```

## Etapa 4: crie um novo documento PS de 1 página

```csharp
// Crie um novo documento PS de 1 página
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Etapa 5: crie um caminho gráfico a partir do retângulo

```csharp
// Crie um caminho gráfico a partir do retângulo
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

## Etapa 6: recorte por forma

```csharp
// Salve o estado dos gráficos para retornar a este estado após a transformação
document.WriteGraphicsSave();

//Desloca o estado atual dos gráficos em 100 pontos para a direita e 100 pontos para baixo.
document.Translate(100, 100);

// Crie um caminho gráfico a partir do círculo
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Adicione recorte por círculo ao estado gráfico atual
document.Clip(circlePath);

// Definir pintura no estado gráfico atual
document.SetPaint(new SolidBrush(Color.Blue));

// Preencha o retângulo no estado gráfico atual (com recorte)
document.Fill(rectanglePath);

// Restaurar o estado gráfico para o nível anterior (superior)
document.WriteGraphicsRestore();
```

## Etapa 7: Deslocar estado gráfico de nível superior

```csharp
// Desloque o estado gráfico de nível superior em 100 pontos para a direita e 100 pontos para baixo.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Desenhe o retângulo no estado gráfico atual (sem recorte) acima do retângulo recortado
document.Draw(rectanglePath);
```

## Etapa 8: feche e salve o documento

```csharp
// Fechar página atual
document.ClosePage();

// Salve o documento
document.Save();
```

Agora, você implementou com sucesso o recorte em um documento PostScript usando Aspose.Page for .NET.

## Conclusão

Neste tutorial, você aprendeu como utilizar Aspose.Page for .NET para implementar recorte em documentos PostScript. Esta poderosa biblioteca fornece uma maneira eficiente e integrada de lidar com vários formatos de documentos em seus aplicativos .NET.

## Perguntas frequentes

### Q1: Posso usar Aspose.Page for .NET com outras linguagens de programação?

A1: Aspose.Page foi projetado principalmente para aplicativos .NET. No entanto, Aspose fornece bibliotecas semelhantes para outras linguagens de programação.

### P2: Onde posso encontrar exemplos e documentação adicionais para Aspose.Page for .NET?

 A2: Você pode explorar mais exemplos e documentação detalhada sobre o[Documentação Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: Existe uma avaliação gratuita disponível para Aspose.Page for .NET?

 A3: Sim, você pode acessar uma avaliação gratuita do Aspose.Page for .NET[aqui](https://releases.aspose.com/).

### Q4: Como posso obter uma licença temporária do Aspose.Page for .NET?

 A4: Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Onde posso obter suporte ou discutir dúvidas relacionadas ao Aspose.Page?

 A5: Visite o[Fóruns Aspose.Page](https://forum.aspose.com/c/page/39) para apoio e discussões da comunidade.