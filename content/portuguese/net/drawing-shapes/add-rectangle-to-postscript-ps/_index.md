---
title: Adicione retângulo ao PostScript (PS) com Aspose.Page para .NET
linktitle: Adicionar retângulo ao PostScript (PS)
second_title: API Aspose.Page .NET
description: Aprimore a criação de documentos em .NET com Aspose.Page. Aprenda a adicionar retângulos a arquivos PostScript (PS) passo a passo.
type: docs
weight: 12
url: /pt/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## Introdução

Se você deseja aprimorar seus recursos de criação de documentos em .NET, Aspose.Page oferece uma solução poderosa para lidar com documentos PostScript. Neste tutorial, iremos guiá-lo através do processo de adição de retângulos a um documento PostScript usando Aspose.Page for .NET.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Biblioteca Aspose.Page for .NET: Baixe e instale a biblioteca Aspose.Page for .NET em[aqui](https://releases.aspose.com/page/net/).

- Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento .NET configurado em sua máquina.

## Importar namespaces

Antes de começar a codificar, importe os namespaces necessários para acessar as classes e métodos necessários:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora, vamos dividir o exemplo em várias etapas:

## Etapa 1: configure seu diretório de documentos

```csharp
// ExInício:1
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
```

Nesta etapa, substitua “Seu diretório de documentos” pelo caminho onde deseja salvar seu documento PostScript.

## Etapa 2: Criar fluxo de saída para documento PostScript

```csharp
//Crie fluxo de saída para documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Aqui, criamos um fluxo de saída para o documento PostScript e especificamos o nome do arquivo ("AddRectangle_outPS.ps"). Ajuste o nome e a localização do arquivo de acordo com suas preferências.

## Etapa 3: definir opções para salvar e criar documento PS

```csharp
//Crie opções de salvamento com tamanho A4
PsSaveOptions options = new PsSaveOptions();

// Crie um novo documento PS de 1 página
PsDocument document = new PsDocument(outPsStream, options, false);
```

Defina as opções de salvamento, especificando o tamanho de página desejado (A4 neste caso). Em seguida, crie um novo documento PostScript de página única.

## Etapa 4: adicionar retângulo e preenchimento

```csharp
//Crie um caminho gráfico a partir do primeiro retângulo
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Definir pintura
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Preencha o retângulo
document.Fill(path);
```

Aqui, criamos um caminho gráfico representando o primeiro retângulo, definimos a cor da tinta (neste caso, laranja) e preenchemos o retângulo.

## Etapa 5: adicione outro retângulo e traço

```csharp
//Crie um caminho gráfico a partir do segundo retângulo
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Definir curso
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Trace (contorne) o retângulo
document.Draw(path);
```

Semelhante à etapa anterior, criamos um caminho gráfico para o segundo retângulo, definimos a cor do traço (vermelho com espessura 3) e contornamos o retângulo.

## Etapa 6: feche a página e salve o documento

```csharp
//Fechar página atual
document.ClosePage();

//Salve o documento
document.Save();
```

Por fim, feche a página atual e salve o documento inteiro.

## Conclusão

Parabéns! Você adicionou retângulos com sucesso a um documento PostScript usando Aspose.Page for .NET. Este tutorial abordou as etapas essenciais, desde a configuração do ambiente de desenvolvimento até salvar o documento final.

## Perguntas frequentes

### Q1: Posso personalizar as cores dos retângulos?

A1: Sim, você pode personalizar as cores ajustando os parâmetros no`SolidBrush` e`Pen` Aulas.

### Q2: O Aspose.Page é compatível com outros formatos de documento?

A2: Sim, Aspose.Page oferece suporte a vários formatos de documento, incluindo XPS e PostScript.

### Q3: Como posso adicionar texto ao documento?

 A3: Você pode usar o`TextFragment` class em Aspose.Page para adicionar texto ao seu documento.

### P4: Onde posso encontrar exemplos e documentação adicionais?

 A4: Explore a documentação[aqui](https://reference.aspose.com/page/net/) e visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio comunitário.

### Q5: Posso experimentar o Aspose.Page antes de comprar?

 A5: Sim, você pode obter uma versão de avaliação gratuita[aqui](https://releases.aspose.com/) , e para uso prolongado, considere um[licença temporária](https://purchase.aspose.com/temporary-license/).
