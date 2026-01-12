---
date: 2026-01-12
description: Aprenda a criar documentos XPS com Aspose.Page para .NET – um guia passo
  a passo para gerar documentos eletrônicos de alta qualidade.
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: Criar documento XPS com Aspose.Page para .NET
url: /pt/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Documento XPS com Aspose.Page para .NET

## Introdução

Bem-vindo ao nosso guia passo a passo sobre **como criar documento XPS** usando Aspose.Page para .NET. Neste tutorial, exploraremos o processo de geração de arquivos XPS, um formato amplamente usado para documentos eletrônicos. Seja você um desenvolvedor experiente ou esteja começando com Aspose.Page, este guia foi elaborado para ajudá-lo a criar documentos XPS de forma fluida, com exemplos claros e explicações detalhadas.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.Page for .NET  
- **Posso executar isso no .NET Core?** Sim, a biblioteca suporta totalmente .NET Core e .NET 5/6  
- **Quantas linhas de código?** Menos de 20 linhas para produzir um arquivo XPS básico  
- **Preciso de licença para testes?** Um teste gratuito está disponível; uma licença é necessária para produção  
- **Qual formato tem a saída?** XPS (XML Paper Specification)  

## Como criar documento XPS usando Aspose.Page para .NET

Abaixo você encontrará tudo o que precisa antes de começar a programar, seguido de um passo a passo conciso e numerado.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de que você tem os seguintes pré-requisitos em vigor:

1. Biblioteca Aspose.Page para .NET: Baixe e instale a biblioteca Aspose.Page a partir do [link de download](https://releases.aspose.com/page/net/).

2. Seu Diretório de Documentos: Escolha ou crie um diretório em seu sistema onde você deseja salvar os arquivos XPS de saída.

Agora, vamos ao tutorial!

## Importar Namespaces

Para usar Aspose.Page para .NET, você precisa importar os namespaces necessários em seu projeto. Siga estas etapas:

### Etapa 1: Adicionar Referência ao Aspose.Page

Em seu projeto, adicione uma referência à biblioteca Aspose.Page para .NET. Você pode encontrar o DLL necessário no pacote baixado.

### Etapa 2: Importar Namespaces

Inclua os seguintes namespaces em seu arquivo de código:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Agora que configuramos os pré-requisitos e importamos os namespaces necessários, vamos dividir o processo de criação de um documento XPS em várias etapas.

## Etapa 1: Definir Diretório do Documento

```csharp
string dir = "Your Document Directory";
```

Certifique-se de substituir `"Your Document Directory"` pelo caminho real onde você deseja salvar o arquivo XPS de saída.

## Etapa 2: Criar Documento XPS

```csharp
XpsDocument xDocs = new XpsDocument();
```

Inicialize um novo documento XPS usando a classe `XpsDocument`.

## Etapa 3: Adicionar Glyphs ao Documento

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Use o método `AddGlyphs` para adicionar glyphs (texto) ao documento. Personalize a fonte, tamanho, estilo e posição conforme necessário.

## Etapa 4: Definir Cor de Preenchimento do Glyph

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Especifique a cor de preenchimento para os glyphs adicionados. Neste exemplo, usamos preto, mas você pode escolher qualquer cor.

## Etapa 5: Salvar o Resultado

```csharp
xDocs.Save(dir + "output.xps");
```

Finalmente, salve o documento XPS no diretório especificado com o nome de arquivo desejado. O arquivo XPS resultante conterá o texto "Hello World!".

Parabéns! Você criou com sucesso um documento XPS usando Aspose.Page para .NET.

## Dicas Comuns & Armadilhas

- **Caminho do Diretório** – Use `Path.Combine(dir, "output.xps")` para evitar a falta de separadores de caminho em diferentes SOs.  
- **Disponibilidade de Fonte** – A fonte que você especificar deve estar instalada na máquina onde o código é executado; caso contrário, o Aspose substituirá por uma fonte padrão.  
- **Múltiplas Páginas** – Para criar arquivos XPS de várias páginas, instancie objetos `XpsPage` adicionais e adicione conteúdo a cada página antes de salvar.

## Conclusão

Neste tutorial, percorremos o processo de criação de documentos XPS usando Aspose.Page para .NET. Esta poderosa biblioteca oferece uma maneira fluida de gerar documentos eletrônicos com facilidade. Experimente diferentes fontes, estilos e conteúdo para adaptar seus arquivos XPS às suas necessidades específicas.

## Perguntas Frequentes

### Q1: Posso usar fontes personalizadas no meu documento XPS?

R1: Sim, você pode especificar a família e o tamanho da fonte ao adicionar glyphs ao seu documento XPS.

### Q2: O Aspose.Page é compatível com .NET Core?

R2: Sim, o Aspose.Page suporta .NET Core, permitindo que você o use em aplicações multiplataforma.

### Q3: Como posso adicionar imagens a um documento XPS?

R3: O Aspose.Page fornece métodos para adicionar imagens ao seu documento XPS. Consulte a documentação para exemplos detalhados.

### Q4: Posso criar documentos XPS de várias páginas?

R4: Absolutamente! Você pode adicionar várias páginas a um documento XPS usando a biblioteca Aspose.Page.

### Q5: Existe uma versão de avaliação disponível?

R5: Sim, você pode explorar os recursos do Aspose.Page baixando o [teste gratuito](https://releases.aspose.com/).

---

**Última Atualização:** 2026-01-12  
**Testado com:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}