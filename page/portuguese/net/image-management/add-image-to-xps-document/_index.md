---
title: Adicionar imagem ao documento XPS com Aspose.Page para .NET
linktitle: Adicionar imagem ao documento XPS
second_title: API Aspose.Page .NET
description: Explore a integração perfeita de imagens em documentos XPS com Aspose.Page for .NET. Siga nosso guia passo a passo para uma experiência de desenvolvimento tranquila.
weight: 11
url: /pt/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar imagem ao documento XPS com Aspose.Page para .NET

## Introdução

No mundo do desenvolvimento .NET, incorporar imagens em documentos XPS é um requisito comum. Aspose.Page for .NET simplifica esse processo, oferecendo um kit de ferramentas poderoso para manipular e aprimorar documentos XPS sem esforço. Este tutorial irá guiá-lo pelas etapas de adição de uma imagem a um documento XPS usando Aspose.Page for .NET.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Biblioteca Aspose.Page for .NET: Baixe e instale a biblioteca em[Documentação Aspose.Page .NET](https://reference.aspose.com/page/net/).

2. Ambiente de desenvolvimento: configure um ambiente de desenvolvimento .NET, como o Visual Studio.

3. Imagem de amostra: tenha um arquivo de imagem de amostra (por exemplo, "QL_logo_color.tif") que deseja adicionar ao documento XPS.

## Importar namespaces

Comece importando os namespaces necessários para o seu projeto .NET. Esses namespaces são vitais para a utilização dos recursos fornecidos pelo Aspose.Page for .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 1: definir diretório de documentos

Comece especificando o caminho para o diretório do seu documento. Esta etapa garante que seu projeto saiba onde localizar e salvar os arquivos.

```csharp
// ExInício:1
string dataDir = "Your Document Directory";
// Fim:1
```

## Etapa 2: criar documento XPS

Crie um novo documento XPS usando Aspose.Page for .NET.

```csharp
// ExInício:1
XpsDocument doc = new XpsDocument();
// Fim:1
```

## Etapa 3: adicionar imagem ao documento XPS

Agora, vamos adicionar a imagem ao documento XPS. Neste exemplo, usaremos uma imagem de amostra chamada "QL_logo_color.tif".

```csharp
// ExInício:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// Fim:1
```

## Etapa 4: salvar o documento XPS resultante

Salve o documento XPS com a imagem adicionada.

```csharp
// ExInício:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// Fim:1
```

Agora você adicionou com sucesso uma imagem a um documento XPS usando Aspose.Page for .NET!

## Conclusão

Neste tutorial, exploramos como aproveitar o Aspose.Page for .NET para incorporar imagens perfeitamente em documentos XPS. Este guia passo a passo garante um processo de integração tranquilo, aprimorando seus recursos de desenvolvimento .NET.

## Perguntas frequentes

### Q1: O Aspose.Page for .NET é compatível com as versões mais recentes do .NET framework?

 A1: Aspose.Page for .NET foi projetado para ser compatível com uma ampla variedade de versões do .NET framework, incluindo os lançamentos mais recentes. Consulte o[documentação](https://reference.aspose.com/page/net/) para detalhes específicos.

### Q2: Posso usar Aspose.Page for .NET em ambientes Windows e Linux?

A2: Sim, o Aspose.Page for .NET é independente de plataforma, tornando-o adequado para uso em ambientes Windows e Linux.

### Q3: Existe alguma opção de licenciamento para Aspose.Page for .NET?

 A3: Sim, você pode explorar opções de licenciamento e fazer uma compra[aqui](https://purchase.aspose.com/buy).

### Q4: Existe uma avaliação gratuita disponível para Aspose.Page for .NET?

 A4: Sim, você pode experimentar o Aspose.Page for .NET gratuitamente acessando o[teste grátis](https://releases.aspose.com/).

### P5: Onde posso procurar assistência ou interagir com a comunidade do Aspose.Page for .NET?

 A5: Visite o[Fórum Aspose.Page para .NET](https://forum.aspose.com/c/page/39) para se conectar com a comunidade e obter suporte.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
