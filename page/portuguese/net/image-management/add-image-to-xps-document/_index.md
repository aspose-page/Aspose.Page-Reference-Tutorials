---
date: 2026-02-28
description: Aprenda a criar documentos XPS em .NET e adicionar imagens usando o Aspose.Page
  para .NET. Siga este guia passo a passo para uma experiência de desenvolvimento
  tranquila.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: Criar documento XPS .NET – Adicionar imagem com Aspose.Page
url: /pt/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Imagem a Documento XPS com Aspose.Page para .NET

Neste tutorial, você aprenderá como **create XPS document .NET** e incorporar uma imagem usando a poderosa biblioteca Aspose.Page. Seja gerando relatórios, faturas ou gráficos personalizados, adicionar elementos visuais a arquivos XPS é uma necessidade frequente para desenvolvedores .NET.

## Introdução

No mundo do desenvolvimento .NET, incorporar imagens em documentos XPS é uma necessidade comum. Aspose.Page para .NET simplifica esse processo, oferecendo um conjunto de ferramentas poderoso para manipular e aprimorar documentos XPS sem esforço. Este tutorial orientará você pelos passos de adicionar uma imagem a um documento XPS usando Aspose.Page para .NET.

## Respostas Rápidas
- **Do que trata este tutorial?** Adicionar uma imagem a um documento XPS com Aspose.Page para .NET.  
- **Qual palavra‑chave principal é alvo?** *create xps document .net*  
- **Preciso de uma licença?** Uma versão de avaliação gratuita está disponível; uma licença é necessária para produção.  
- **Quais versões do .NET são suportadas?** Funciona com .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo leva a implementação?** Aproximadamente 5‑10 minutos para uma inserção básica de imagem.

## O que é “create XPS document .NET”?
Criar um documento XPS em .NET significa gerar programaticamente um arquivo XML Paper Specification (XPS) — um formato de documento de layout fixo — usando C# ou VB.NET. Aspose.Page fornece uma API fluente que abstrai os detalhes de baixo nível, permitindo que você se concentre no conteúdo, como texto, formas e imagens.

## Por que usar Aspose.Page para adicionar uma imagem?
- **Full control** sobre posicionamento, dimensionamento e recorte de imagens.  
- **No external dependencies** – a biblioteca lida com a decodificação de imagens internamente.  
- **Cross‑platform** suporte para ambientes Windows e Linux.  
- **High fidelity** renderização que preserva a qualidade da imagem no arquivo XPS final.

## Pré‑requisitos

Antes de mergulhar no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos configurados:

1. Biblioteca Aspose.Page para .NET: Baixe e instale a biblioteca a partir da [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/).
2. Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento .NET, como o Visual Studio.
3. Imagem de Exemplo: Tenha um arquivo de imagem de exemplo (por exemplo, "QL_logo_color.tif") que você deseja adicionar ao documento XPS.

## Importar Namespaces

Comece importando os namespaces necessários para o seu projeto .NET. Esses namespaces são essenciais para utilizar os recursos fornecidos pelo Aspose.Page para .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Aspose.Page Adicionar Imagem ao Documento XPS

A seguir, percorremos cada passo necessário para **create XPS document .NET** e incorporar uma imagem.

### Etapa 1: Definir Diretório do Documento

Comece especificando o caminho para o diretório do seu documento. Esta etapa garante que seu projeto saiba onde localizar e salvar arquivos.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### Etapa 2: Criar Documento XPS

Crie um novo documento XPS usando Aspose.Page para .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### Etapa 3: Adicionar Imagem ao Documento XPS

Agora, vamos adicionar a imagem ao documento XPS. Neste exemplo, usaremos uma imagem de exemplo chamada "QL_logo_color.tif".

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### Etapa 4: Salvar Documento XPS Resultante

Salve o documento XPS com a imagem adicionada.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Agora você adicionou com sucesso uma imagem a um documento XPS usando Aspose.Page para .NET!

## Problemas Comuns e Soluções

- **File not found error** – Verifique se `dataDir` aponta para a pasta correta e se o nome do arquivo de imagem corresponde exatamente, incluindo sensibilidade a maiúsculas e minúsculas no Linux.
- **Image appears distorted** – Ajuste os fatores de escala do `CreateMatrix` ou os parâmetros do `RectangleF` para controlar o tamanho e a proporção.
- **Unsupported image format** – Aspose.Page suporta formatos raster comuns (PNG, JPEG, TIFF). Converta formatos não suportados antes de usar `CreateImageBrush`.

## Perguntas Frequentes

### Q1: O Aspose.Page para .NET é compatível com as versões mais recentes do framework .NET?
A1: Aspose.Page para .NET foi projetado para ser compatível com uma ampla gama de versões do framework .NET, incluindo as versões mais recentes. Consulte a [documentation](https://reference.aspose.com/page/net/) para detalhes específicos.

### Q2: Posso usar Aspose.Page para .NET em ambientes Windows e Linux?
A2: Sim, Aspose.Page para .NET é independente de plataforma, tornando‑se adequado para uso em ambientes Windows e Linux.

### Q3: Existem opções de licenciamento para Aspose.Page para .NET?
A3: Sim, você pode explorar opções de licenciamento e fazer uma compra [here](https://purchase.aspose.com/buy).

### Q4: Há uma versão de avaliação gratuita disponível para Aspose.Page para .NET?
A4: Sim, você pode experimentar Aspose.Page para .NET gratuitamente acessando o [free trial](https://releases.aspose.com/).

### Q5: Onde posso buscar assistência ou interagir com a comunidade do Aspose.Page para .NET?
A5: Visite o [Aspose.Page for .NET forum](https://forum.aspose.com/c/page/39) para conectar‑se com a comunidade e obter suporte.

## Conclusão

Neste tutorial, exploramos como aproveitar o Aspose.Page para .NET para incorporar imagens de forma contínua em documentos XPS. Este guia passo a passo garante um processo de integração suave, aprimorando suas capacidades de desenvolvimento .NET e ajudando‑o a **create XPS document .NET** soluções com riqueza visual.

---

**Última atualização:** 2026-02-28  
**Testado com:** Aspose.Page for .NET 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}