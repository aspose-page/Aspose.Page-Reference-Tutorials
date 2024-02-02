---
title: Adicione texto com string Unicode ao documento XPS com Aspose.Page
linktitle: Adicionar texto com string Unicode ao documento XPS
second_title: API Aspose.Page .NET
description: Explore o poder do Aspose.Page for .NET com nosso guia passo a passo sobre como adicionar texto Unicode a documentos XPS.
type: docs
weight: 12
url: /pt/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Introdução

No cenário em constante evolução do desenvolvimento .NET, Aspose.Page se destaca como uma ferramenta poderosa para lidar com documentos XPS. Entre seus muitos recursos, a capacidade de adicionar texto com strings Unicode a um documento XPS é uma funcionalidade valiosa. Este guia passo a passo orientará você durante o processo, garantindo que você aproveite esse recurso de maneira eficaz.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Uma compreensão básica do desenvolvimento .NET.
- Visual Studio instalado em sua máquina.
-  Biblioteca Aspose.Page para .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/page/net/).

## Importar namespaces

Para começar, certifique-se de importar os namespaces necessários para o seu projeto. Isso fornecerá as classes e funcionalidades necessárias para trabalhar com Aspose.Page. Aqui estão os namespaces essenciais:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Etapa 1: configurar o documento

Em primeiro lugar, crie um novo documento XPS onde adicionará o texto Unicode. Siga o trecho de código abaixo:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
// Criar novo documento XPS
XpsDocument doc = new XpsDocument();
```

## Etapa 2: adicionar texto Unicode

Agora, vamos adicionar texto Unicode ao documento XPS. Este exemplo usa a fonte Arial, define o tamanho da fonte como 20 e posiciona o texto nas coordenadas (400f, 200f). A string Unicode neste caso é "TEN. rof SPX.esopsA". Confira o trecho de código abaixo:

```csharp
// Adicione texto
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Etapa 3: salve o documento

Depois que o texto Unicode for adicionado, salve o documento XPS resultante. Aqui está a etapa final:

```csharp
// Salve o documento XPS resultante
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Parabéns! Você adicionou com êxito texto Unicode a um documento XPS usando Aspose.Page for .NET.

## Conclusão

Neste tutorial, exploramos o processo de adição de texto Unicode a documentos XPS usando Aspose.Page for .NET. Essa funcionalidade abre portas para a criação diversificada e dinâmica de documentos no ambiente .NET.

## Perguntas frequentes

### Q1: O Aspose.Page é compatível com os frameworks .NET mais recentes?

A1: Sim, Aspose.Page é atualizado regularmente para garantir compatibilidade com os frameworks .NET mais recentes.

### Q2: Posso personalizar o estilo e o tamanho da fonte ao adicionar texto?

A2: Com certeza! O código de exemplo fornecido permite personalizar facilmente o estilo, o tamanho da fonte e outros atributos.

### Q3: Onde posso encontrar documentação adicional para Aspose.Page?

 A3: Você pode consultar a documentação[aqui](https://reference.aspose.com/page/net/) para obter informações abrangentes e exemplos.

### Q4: Existem recursos gratuitos para começar a usar o Aspose.Page?

 A4: Sim, você pode explorar o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio e discussões da comunidade.

### P5: Existe uma versão de teste disponível antes de fazer uma compra?

 A5: Certamente! Você pode acessar a versão de teste gratuita[aqui](https://releases.aspose.com/) antes de fazer uma compra.