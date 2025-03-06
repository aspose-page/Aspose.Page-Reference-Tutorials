---
title: Adicionar imagem lado a lado ao documento XPS com Aspose.Page para .NET
linktitle: Adicionar imagem lado a lado ao documento XPS
second_title: API Aspose.Page .NET
description: Explore a adição de imagens lado a lado a documentos XPS sem esforço com Aspose.Page for .NET. Melhore o apelo visual e crie documentos impressionantes.
weight: 12
url: /pt/net/image-management/add-tiled-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar imagem lado a lado ao documento XPS com Aspose.Page para .NET

## Introdução

Você deseja aprimorar seus documentos XPS adicionando imagens lado a lado visualmente atraentes? Aspose.Page for .NET capacita os desenvolvedores a conseguir isso perfeitamente. Neste guia passo a passo, orientaremos você no processo de adição de uma imagem lado a lado a um documento XPS usando Aspose.Page for .NET.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Aspose.Page para .NET: Certifique-se de ter a biblioteca Aspose.Page instalada. Você pode encontrar documentação detalhada e baixar a biblioteca[aqui](https://reference.aspose.com/page/net/).
- Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento .NET preferido, como Visual Studio.

## Importar namespaces

Para começar, importe os namespaces necessários para o seu projeto. Isso garante que você tenha acesso às classes e métodos necessários para trabalhar com Aspose.Page. Adicione os seguintes namespaces no início do seu código:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Agora, vamos dividir o exemplo em várias etapas.

## Etapa 1: definir o diretório de documentos

```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
```

Certifique-se de substituir “Seu diretório de documentos” pelo caminho real onde deseja salvar seu documento XPS.

## Etapa 2: crie um novo documento XPS

```csharp
// Criar novo documento XPS
XpsDocument doc = new XpsDocument();
```

 Instancie um novo documento XPS usando o`XpsDocument` aula.

## Etapa 3: adicionar uma imagem lado a lado

```csharp
// Imagem lado a lado
// Retângulo preenchido com ImageBrush no canto superior direito abaixo
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Esta etapa adiciona uma imagem lado a lado ao documento XPS. Ajuste as coordenadas e o caminho do arquivo de imagem conforme suas necessidades.

## Etapa 4: salve o documento XPS resultante

```csharp
// Salve o documento XPS resultante
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Salve o documento XPS modificado no diretório especificado.

## Conclusão

Parabéns! Você aprendeu com sucesso como adicionar uma imagem lado a lado a um documento XPS usando Aspose.Page for .NET. Este recurso simples, mas poderoso, permite aprimorar o apelo visual de seus documentos sem esforço.

## Perguntas frequentes

### Q1: O Aspose.Page é compatível com todos os ambientes de desenvolvimento .NET?

A1: Sim, o Aspose.Page foi projetado para funcionar perfeitamente com vários ambientes de desenvolvimento .NET, incluindo o Visual Studio.

### Q2: Posso ajustar a opacidade da imagem lado a lado?

A2: Certamente, conforme demonstrado no exemplo, você pode definir a opacidade do retângulo preenchido usando o`Opacity` propriedade.

### Q3: Existem outros modos de bloco disponíveis no Aspose.Page for .NET?

 A3: Sim, Aspose.Page oferece diferentes modos de bloco. Neste tutorial, usamos`XpsTileMode.Tile`, mas você pode explorar outras opções na documentação.

### P4: Como faço para lidar com licenças temporárias do Aspose.Page?

 A4: Consulte o[licença temporária](https://purchase.aspose.com/temporary-license/) página no site Aspose para orientação sobre como obter e implementar licenças temporárias.

### P5: Onde posso procurar ajuda ou me conectar com a comunidade Aspose.Page?

 A5: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para se envolver com a comunidade, fazer perguntas e encontrar soluções.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
