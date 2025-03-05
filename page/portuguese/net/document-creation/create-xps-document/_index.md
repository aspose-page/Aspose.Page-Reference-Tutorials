---
title: Crie um documento XPS com Aspose.Page para .NET
linktitle: Criar documento XPS
second_title: API Aspose.Page .NET
description: Explore o mundo da criação de documentos XPS com Aspose.Page for .NET. Siga nosso guia passo a passo para gerar documentos eletrônicos sem esforço.
type: docs
weight: 10
url: /pt/net/document-creation/create-xps-document/
---
## Introdução

Bem-vindo ao nosso guia passo a passo sobre como criar documentos XPS usando Aspose.Page for .NET. Neste tutorial exploraremos o processo de geração de arquivos XPS, formato amplamente utilizado para documentos eletrônicos. Quer você seja um desenvolvedor experiente ou esteja apenas começando com Aspose.Page, este guia foi feito sob medida para ajudá-lo a criar documentos XPS perfeitamente com exemplos claros e explicações detalhadas.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Biblioteca Aspose.Page para .NET: Baixe e instale a biblioteca Aspose.Page do[Link para Download](https://releases.aspose.com/page/net/).

2. Seu diretório de documentos: Escolha ou crie um diretório em seu sistema onde deseja salvar os arquivos XPS de saída.

Agora, vamos pular para o tutorial!

## Importar namespaces

Para usar Aspose.Page for .NET, você precisa importar os namespaces necessários para o seu projeto. Siga esses passos:

### Etapa 1: adicionar referência a Aspose.Page

Em seu projeto, adicione uma referência à biblioteca Aspose.Page for .NET. Você pode encontrar a DLL necessária no pacote baixado.

### Etapa 2: importar namespaces

Inclua os seguintes namespaces em seu arquivo de código:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Agora que configuramos os pré-requisitos e importamos os namespaces necessários, vamos dividir o processo de criação de um documento XPS em várias etapas.

## Etapa 1: definir diretório de documentos

```csharp
string dir = "Your Document Directory";
```

 Certifique-se de substituir`"Your Document Directory"` com o caminho real onde você deseja salvar o arquivo XPS de saída.

## Etapa 2: criar documento XPS

```csharp
XpsDocument xDocs = new XpsDocument();
```

 Inicialize um novo documento XPS usando o`XpsDocument` aula.

## Etapa 3: adicionar glifos ao documento

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

 Use o`AddGlyphs` método para adicionar glifos (texto) ao documento. Personalize a fonte, o tamanho, o estilo e a posição conforme necessário.

## Etapa 4: definir a cor de preenchimento do glifo

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Especifique a cor de preenchimento dos glifos adicionados. Neste exemplo usamos preto, mas você pode escolher qualquer cor.

## Etapa 5: salve o resultado

```csharp
xDocs.Save(dir + "output.xps");
```

Finalmente, salve o documento XPS no diretório especificado com o nome de arquivo desejado. O arquivo XPS resultante conterá a mensagem "Hello World!" texto.

Parabéns! Você criou com sucesso um documento XPS usando Aspose.Page for .NET.

## Conclusão

Neste tutorial, percorremos o processo de criação de documentos XPS usando Aspose.Page for .NET. Esta poderosa biblioteca oferece uma maneira perfeita de gerar documentos eletrônicos com facilidade. Experimente diferentes fontes, estilos e conteúdos para adaptar seus arquivos XPS às suas necessidades específicas.

## Perguntas frequentes

### P1: Posso usar fontes personalizadas em meu documento XPS?

A1: Sim, você pode especificar a família e o tamanho da fonte ao adicionar glifos ao seu documento XPS.

### P2: O Aspose.Page é compatível com .NET Core?

A2: Sim, Aspose.Page oferece suporte a .NET Core, permitindo que você o use em aplicativos de plataforma cruzada.

### Q3: Como posso adicionar imagens a um documento XPS?

A3: Aspose.Page fornece métodos para adicionar imagens ao seu documento XPS. Consulte a documentação para exemplos detalhados.

### P4: Posso criar documentos XPS de várias páginas?

A4: Com certeza! Você pode adicionar várias páginas ao seu documento XPS usando a biblioteca Aspose.Page.

### Q5: Existe uma versão de teste disponível?

 A5: Sim, você pode explorar os recursos do Aspose.Page baixando o[teste grátis](https://releases.aspose.com/).