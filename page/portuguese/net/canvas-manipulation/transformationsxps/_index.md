---
title: Transformações XPS com Aspose.Page para .NET
linktitle: Transformações XPS
second_title: API Aspose.Page .NET
description: Transforme documentos XPS sem esforço com Aspose.Page for .NET. Siga nosso guia passo a passo para transformações perfeitas.
weight: 13
url: /pt/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Transformações XPS com Aspose.Page para .NET

## Introdução

Bem-vindo ao mundo do Aspose.Page for .NET, uma biblioteca poderosa que permite realizar várias transformações em documentos XPS sem esforço. Neste tutorial, mergulharemos no processo de transformação de documentos XPS usando Aspose.Page for .NET. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este guia orientará você em cada etapa, garantindo que você compreenda os conceitos facilmente.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte em vigor:

-  Biblioteca Aspose.Page for .NET: Baixe e instale a biblioteca em[Documentação Aspose.Page para .NET](https://reference.aspose.com/page/net/).

- Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento compatível, como Visual Studio ou qualquer outra ferramenta de desenvolvimento .NET.

- Seu diretório de documentos: substitua o espaço reservado no código pelo caminho real para o diretório de documentos.

Agora, vamos pular para o tutorial!

## Importar namespaces

Em primeiro lugar, certifique-se de importar os namespaces necessários para disponibilizar as funcionalidades do Aspose.Page for .NET em seu código. Adicione os seguintes namespaces no início do seu script:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 1: crie um novo documento XPS

```csharp
// ExInício:1
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";

// Criar novo documento XPS
XpsDocument doc = new XpsDocument();
```

## Etapa 2: crie uma tela principal

```csharp
// Crie uma tela principal, comum para todos os elementos da página
XpsCanvas canvas1 = doc.AddCanvas();

// Faça deslocamentos esquerdo e superior na tela principal
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Etapa 3: Crie uma geometria de caminho retangular

```csharp
// Criar geometria de caminho retangular
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Etapa 4: adicionar um preenchimento para retângulos

```csharp
// Crie um preenchimento para retângulos
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Etapa 5: adicionar uma nova tela sem transformações

```csharp
// Adicione uma nova tela sem nenhuma transformação na tela principal
XpsCanvas canvas2 = canvas1.AddCanvas();

// Crie um retângulo nesta tela e preencha-o
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Etapa 6: adicionar uma nova tela com a transformação Translate

```csharp
// Adicionar nova tela com transformação de tradução à tela principal
XpsCanvas canvas3 = canvas1.AddCanvas();

// Traduza esta tela para posicionar um novo retângulo abaixo do retângulo anterior
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Traduza esta tela para o lado direito da página
canvas3.RenderTransform.Translate(500, 0);

// Crie um retângulo nesta tela e preencha-o
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Etapa 7: adicionar uma nova tela com transformação de escala dupla

```csharp
//Adicione uma nova tela com transformação de escala dupla à tela principal
XpsCanvas canvas4 = canvas1.AddCanvas();

// Traduza esta tela para posicionar um novo retângulo abaixo do retângulo anterior
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Dimensione esta tela
canvas4.RenderTransform.Scale(2, 2);

// Crie um retângulo nesta tela e preencha-o
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Etapa 8: adicionar uma nova tela com transformação de rotação em torno de um ponto

```csharp
// Adicionar nova tela com rotação em torno de uma transformação de ponto à tela principal
XpsCanvas canvas5 = canvas1.AddCanvas();

// Traduza esta tela para posicionar um novo retângulo abaixo do retângulo anterior
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Gire esta tela em torno de um ponto em 45 graus
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Crie um retângulo nesta tela e preencha-o
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Etapa 9: Salvar o documento XPS resultante

```csharp
// Salve o documento XPS resultante
doc.Save(dataDir + "output1.xps");
// Fim:1
```

## Conclusão

Parabéns! Você transformou com sucesso um documento XPS usando Aspose.Page for .NET. Este guia abordou etapas essenciais, desde a configuração de pré-requisitos até a execução de diversas transformações. Experimente essas técnicas e libere todo o potencial do Aspose.Page for .NET em seus projetos.

## Perguntas frequentes

### Q1: O Aspose.Page for .NET é compatível com todos os ambientes de desenvolvimento .NET?

A1: Sim, o Aspose.Page for .NET foi projetado para funcionar perfeitamente com vários ambientes de desenvolvimento .NET, incluindo o Visual Studio.

### P2: Onde posso encontrar exemplos e documentação adicionais para Aspose.Page for .NET?

 A2: Visite o[Documentação Aspose.Page para .NET](https://reference.aspose.com/page/net/) para documentação e exemplos abrangentes.

### Q3: Posso experimentar o Aspose.Page for .NET antes de comprar?

 A3: Sim, você pode explorar uma versão de avaliação gratuita visitando[Avaliação gratuita do Aspose.Page](https://releases.aspose.com/).

### Q4: Como posso obter uma licença temporária para Aspose.Page for .NET?

 A4: Obtenha uma licença temporária visitando[Licença Temporária](https://purchase.aspose.com/temporary-license/).

### Q5: Onde posso comprar Aspose.Page para .NET?

 A5: Compre Aspose.Page para .NET em[Aspose.Página Comprar](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
