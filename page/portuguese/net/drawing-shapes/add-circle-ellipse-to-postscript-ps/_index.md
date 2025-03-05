---
title: Adicionar círculo elipse ao PostScript (PS) com Aspose.Page
linktitle: Adicionar círculo elipse ao PostScript (PS)
second_title: API Aspose.Page .NET
description: Aprenda como adicionar elipses circulares sem esforço a documentos PostScript (PS) usando Aspose.Page for .NET. Siga nosso guia passo a passo para uma integração perfeita.
type: docs
weight: 10
url: /pt/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## Introdução

Bem-vindo a este tutorial abrangente sobre como adicionar elipses circulares a documentos PostScript (PS) usando Aspose.Page for .NET. Aspose.Page é uma biblioteca poderosa que permite aos desenvolvedores trabalhar perfeitamente com PostScript e outros formatos de documentos. Neste guia, orientaremos você no processo de incorporação de elipses circulares em seus documentos PS com facilidade.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Biblioteca Aspose.Page for .NET: Baixe e instale a biblioteca Aspose.Page for .NET em[aqui](https://releases.aspose.com/page/net/).

2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento .NET funcional configurado em sua máquina.

Agora, vamos começar com o guia passo a passo.

## Importar namespaces

Na primeira etapa, você precisa importar os namespaces necessários para disponibilizar a funcionalidade Aspose.Page em seu código.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora, vamos dividir o exemplo fornecido em várias etapas para guiá-lo através do processo de adição de elipses circulares a um documento PostScript.

## Etapa 1: definir o diretório de documentos

```csharp
// ExInício:1
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
```

Certifique-se de substituir "Seu diretório de documentos" pelo caminho real para o diretório de documentos.

## Etapa 2: Criar fluxo de saída para documento PostScript

```csharp
//Crie fluxo de saída para documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Aqui, um FileStream é criado para gravar o documento PostScript e o modo de arquivo é definido para criar um novo arquivo.

## Etapa 3: criar opções de salvamento e documento PS

```csharp
//Crie opções de salvamento com tamanho A4
PsSaveOptions options = new PsSaveOptions();

// Crie um novo documento PS de 1 página
PsDocument document = new PsDocument(outPsStream, options, false);
```

Esta etapa envolve a criação de opções de salvamento em tamanho A4 e a inicialização de um novo documento PS de 1 página.

## Etapa 4: criar caminho gráfico para a primeira elipse

```csharp
//Crie um caminho gráfico a partir da primeira elipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Um caminho gráfico é criado para a primeira elipse, especificando sua posição e dimensões.

## Etapa 5: defina a pintura e preencha a elipse

```csharp
//Definir pintura
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Preencha a elipse
document.Fill(path);
```

Aqui a tinta é definida e a primeira elipse é preenchida com a cor especificada.

## Etapa 6: Criar caminho gráfico para a segunda elipse

```csharp
//Crie um caminho gráfico a partir da segunda elipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Da mesma forma, um caminho gráfico é criado para a segunda elipse, definindo sua posição e dimensões.

## Etapa 7: definir o traço e desenhar a elipse

```csharp
//Definir curso
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Trace (contorne) a elipse
document.Draw(path);
```

Nesta etapa, o traço é definido e a segunda elipse é contornada com a cor e espessura da linha especificadas.

## Etapa 8: feche a página atual e salve o documento

```csharp
//Fechar página atual
document.ClosePage();

//Salve o documento
document.Save();
```

Por fim, a página atual é fechada e todo o documento é salvo, finalizando o processo.

## Conclusão

Parabéns! Você aprendeu com sucesso como adicionar elipses circulares a documentos PostScript usando Aspose.Page for .NET. Este tutorial forneceu um guia passo a passo detalhado para ajudá-lo a integrar perfeitamente essa funcionalidade em seus projetos.

## Perguntas frequentes

### Q1: Posso usar Aspose.Page for .NET com outros formatos de documento?

 A1: Aspose.Page concentra-se principalmente em PostScript, mas Aspose fornece outras bibliotecas para vários formatos de documentos. Verifica a[Aspor documentação](https://reference.aspose.com/page/net/) para mais detalhes.

### P2: Onde posso encontrar suporte adicional e discussões na comunidade?

 A2: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para discussões e apoio da comunidade.

### Q3: Existe uma avaliação gratuita disponível para Aspose.Page for .NET?

 A3: Sim, você pode acessar o[teste grátis](https://releases.aspose.com/)para explorar os recursos do Aspose.Page for .NET.

### Q4: Como posso obter uma licença temporária para Aspose.Page?

 A4: Obtenha uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/) para fins de teste e avaliação.

### Q5: Onde posso comprar Aspose.Page para .NET?

 A5: Compre Aspose.Page para .NET no[página de compra](https://purchase.aspose.com/buy).