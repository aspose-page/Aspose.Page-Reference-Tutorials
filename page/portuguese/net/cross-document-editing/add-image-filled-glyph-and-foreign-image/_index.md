---
title: Adicionar glifo preenchido com imagem e imagem estrangeira com Aspose.Page .NET
linktitle: Adicionar glifo preenchido com imagem e imagem estrangeira
second_title: API Aspose.Page .NET
description: Desbloqueie o poder do processamento de documentos em .NET com Aspose.Page. Adicione glifos cheios de imagens sem esforço. Aprimore os recursos visuais e simplifique seu fluxo de trabalho.
weight: 11
url: /pt/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar glifo preenchido com imagem e imagem estrangeira com Aspose.Page .NET

## Introdução

No mundo do desenvolvimento .NET, Aspose.Page se destaca como um poderoso kit de ferramentas para lidar com tarefas de processamento de documentos. Este tutorial irá guiá-lo através do processo de adição de glifos preenchidos com imagens e incorporação de imagens estrangeiras usando Aspose.Page for .NET. Ao final deste guia, você terá um conhecimento sólido de como aprimorar seus recursos de processamento de documentos.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Aspose.Page para .NET: Certifique-se de ter a biblioteca Aspose.Page instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/page/net/).

- Ambiente de desenvolvimento: configure um ambiente de desenvolvimento .NET funcional com o Visual Studio ou qualquer outro IDE preferido.

- Diretório de documentos: crie um diretório onde você armazenará seus documentos. Isso será chamado de "Seu diretório de documentos" nos exemplos de código.

## Importar namespaces

Na sua aplicação .NET, comece importando os namespaces necessários para acessar as classes e métodos fornecidos pelo Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 1: crie o primeiro documento XPS

Comece criando o primeiro documento XPS usando Aspose.Page. Este documento servirá de base para adicionar glifos preenchidos com imagens.

```csharp
// ExInício:1
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";

// Crie o primeiro documento XPS
XpsDocument doc1 = new XpsDocument();
```

## Etapa 2: adicionar glifos ao primeiro documento

Adicione glifos ao primeiro documento, especificando fonte, tamanho, estilo e posição.

```csharp
// Adicione glifos ao primeiro documento
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Etapa 3: preencher glifos com um pincel de imagem

Preencha os glifos com um pincel de imagem, utilizando uma imagem do seu diretório de dados.

```csharp
// Preencha os glifos com um pincel de imagem
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Etapa 4: crie o segundo documento XPS

Agora, crie o segundo documento XPS que incorporará os glifos do primeiro documento.

```csharp
// Crie o segundo documento XPS
XpsDocument doc2 = new XpsDocument();
```

## Etapa 5: adicione glifos com a fonte do primeiro documento

Adicione glifos ao segundo documento, usando a fonte do primeiro documento.

```csharp
// Adicione glifos com a fonte do primeiro documento ao segundo documento
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Etapa 6: crie um pincel de imagem a partir do preenchimento do primeiro documento

Crie um pincel de imagem a partir do preenchimento do primeiro documento e use-o para preencher os glifos do segundo documento.

```csharp
// Crie um pincel de imagem a partir do preenchimento do primeiro documento e preencha glifos no segundo documento
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Etapa 7: salve os documentos

Salve o primeiro e o segundo documentos XPS.

```csharp
// Salve o primeiro documento XPS
doc1.Save(dataDir + "out1.xps");

// Salve o segundo documento XPS
doc2.Save(dataDir + "out2.xps");
// Fim:1
```

## Conclusão

Parabéns! Você adicionou com sucesso glifos preenchidos com imagens e incorporou imagens estrangeiras usando Aspose.Page for .NET. Este tutorial fornece uma base para aprimorar suas capacidades de processamento de documentos, abrindo novas possibilidades para documentos criativos e visualmente atraentes.

## Perguntas frequentes

### Q1: Posso usar diferentes formatos de imagem para preencher glifos?

A1: Sim, Aspose.Page suporta vários formatos de imagem. Garanta a compatibilidade com o formato de imagem escolhido.

### P2: Como posso personalizar ainda mais a aparência dos glifos?

A2: Explore a documentação do Aspose.Page para obter propriedades e métodos adicionais para ajustar a aparência do glifo.

### Q3: O Aspose.Page é adequado para lidar com grandes conjuntos de documentos?

A3: Aspose.Page foi projetado para lidar com conjuntos de documentos pequenos e grandes com eficiência.

### P4: Posso aplicar estilos diferentes a glifos individuais?

A4: Sim, você pode personalizar estilos para cada glifo de forma independente, proporcionando um alto nível de flexibilidade.

### P5: Quais são os benefícios de usar Aspose.Page em relação a outras ferramentas de processamento de documentos?

R5: Aspose.Page oferece um conjunto abrangente de recursos, excelente desempenho e extensa documentação, tornando-o a escolha preferida de muitos desenvolvedores.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
