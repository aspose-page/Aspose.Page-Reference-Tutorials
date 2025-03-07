---
title: Edite o tíquete de impressão existente com Aspose.Page para .NET
linktitle: Editar ticket de impressão existente
second_title: API Aspose.Page .NET
description: Aprenda a editar tickets de impressão em documentos XPS usando Aspose.Page for .NET. Um guia passo a passo para desenvolvedores. Melhore o controle de impressão de documentos sem esforço.
weight: 11
url: /pt/net/print-ticket-management/print-ticket-management/aspose.page/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Edite o tíquete de impressão existente com Aspose.Page para .NET

## Introdução

Bem-vindo a este guia completo sobre edição de tickets de impressão existentes usando Aspose.Page for .NET! Aspose.Page é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com documentos XPS sem esforço. Neste tutorial, orientaremos você no processo de edição de tickets impressos com exemplos práticos, detalhando cada etapa para uma experiência de aprendizado perfeita.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Conhecimento básico de programação C#.
- Visual Studio instalado em sua máquina.
- Biblioteca Aspose.Page for .NET baixada e referenciada em seu projeto.

 Se você ainda não instalou o Aspose.Page for .NET, você pode baixá-lo[aqui](https://releases.aspose.com/page/net/).

## Importar namespaces

Para começar, importe os namespaces necessários para o seu projeto C#. Isso garante que você tenha acesso às funcionalidades do Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

Agora, vamos dividir o código de exemplo fornecido em várias etapas.

## Etapa 1: definir diretório de documentos

```csharp
// O caminho para o diretório de documentos.
string dir = "Your Document Directory";
```

 Aqui, substitua`"Your Document Directory"` com o caminho real onde seus documentos XPS estão localizados.

## Etapa 2: abra o documento XPS com impressão de tíquetes

```csharp
// ExInício:3
XpsDocument xDocs = new XpsDocument(dir + "input3.xps");
JobPrintTicket pt = xDocs.JobPrintTicket;
// Fim:3
```

Esta etapa envolve abrir um documento XPS e obter seu JobPrintTicket.

## Etapa 3: Remover parâmetros do tíquete de impressão do trabalho

```csharp
// ExInício:4
pt.Remove(
	"ns0000:PageDevmodeSnapshot",
	"ns0000:JobInterleaving",
	"ns0000:JobImageType");
// Fim:4
```

 Remova parâmetros indesejados do JobPrintTicket usando o`Remove`método.

## Etapa 4: adicionar parâmetros ao tíquete de impressão do trabalho

```csharp
// ExInício:5
pt.Add(
	new JobCopiesAllDocuments(2),
	new PageMediaSize(PageMediaSize.PageMediaSizeOption.ISOA4));
// Fim:5
```

 Adicione os parâmetros desejados ao JobPrintTicket usando o`Add`método.

## Etapa 5: Salvar documento com tíquete de impressão de trabalho alterado

```csharp
// ExInício:6
xDocs.Save(dir + "output3.xps");
// Fim:6
```

Salve o documento XPS modificado com o JobPrintTicket atualizado.

Repita essas etapas para um processo descomplicado de edição de tickets de impressão com Aspose.Page for .NET!

## Conclusão

Parabéns! Você aprendeu com sucesso como editar tickets de impressão existentes usando Aspose.Page for .NET. Esta poderosa biblioteca oferece flexibilidade e facilidade no manuseio de documentos XPS, tornando-a uma ferramenta inestimável para desenvolvedores.

## perguntas frequentes

### Q1: Posso usar Aspose.Page for .NET com outros formatos de documento?

A1: Sim, o Aspose.Page for .NET concentra-se principalmente em documentos XPS, mas o Aspose oferece várias bibliotecas para diferentes formatos. Verifique a documentação para obter mais detalhes.

### P2: O Aspose.Page for .NET é compatível com o .NET Core?

A2: Sim, Aspose.Page for .NET é compatível com .NET Core, proporcionando flexibilidade em seu ambiente de desenvolvimento.

### Q3: Como posso obter suporte ou fazer perguntas relacionadas ao Aspose.Page?

 A3: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39)para obter suporte da comunidade e conectar-se com outros desenvolvedores.

### Q4: Existe uma avaliação gratuita disponível para Aspose.Page for .NET?

 A4: Sim, você pode obter uma avaliação gratuita[aqui](https://releases.aspose.com/).

### Q5: Como posso obter uma licença temporária para Aspose.Page for .NET?

 A5: Visita[esse link](https://purchase.aspose.com/temporary-license/) para obter uma licença temporária.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
