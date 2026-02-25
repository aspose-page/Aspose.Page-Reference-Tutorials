---
date: 2026-02-25
description: Aprenda a criar gradiente XPS com preenchimento horizontal usando Aspose.Page
  para .NET. Eleve a atratividade visual dos seus documentos sem esforço.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Criar gradiente XPS: preenchimento horizontal com Aspose.Page para .NET'
url: /pt/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Gradiente XPS – Adicionar Gradiente Horizontal ao XPS com Aspose.Page para .NET

## Introdução

Neste tutorial você **criará preenchimentos de gradiente XPS** que se estendem horizontalmente pelas suas páginas. Adicionar um gradiente horizontal pode instantaneamente deixar um documento XPS mais polido e atraente, especialmente para relatórios, brochuras ou qualquer saída visualmente rica. Vamos percorrer todo o processo usando Aspose.Page para .NET, desde a configuração do ambiente até a gravação do arquivo XPS final.

## Respostas Rápidas
- **O que este tutorial cobre?** Adicionar um gradiente horizontal a um documento XPS com Aspose.Page para .NET.  
- **Qual biblioteca é necessária?** Aspose.Page para .NET (qualquer versão recente).  
- **Preciso de licença?** Uma versão de avaliação funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quanto tempo leva a implementação?** Cerca de 5–10 minutos para um gradiente básico.  
- **Posso mudar a direção do gradiente?** Sim – modifique os pontos de início/fim do `LinearGradientBrush`.

## Como criar gradiente XPS com Aspose.Page para .NET

Abaixo você encontrará um guia passo a passo que explica **por que** cada linha de código existe, não apenas **o que** ela faz. Sinta-se à vontade para seguir no Visual Studio ou no seu editor .NET preferido.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem os seguintes pré‑requisitos configurados:

1. Biblioteca Aspose.Page para .NET: Garanta que a biblioteca Aspose.Page para .NET esteja instalada no seu ambiente de desenvolvimento. Você pode baixá‑la na [Documentação do Aspose.Page para .NET](https://reference.aspose.com/page/net/).

2. Ambiente de Desenvolvimento: Configure um ambiente adequado, incluindo um editor de código como o Visual Studio.

## Importar Namespaces

Comece importando os namespaces necessários para o seu projeto. Esses namespaces são essenciais para trabalhar com Aspose.Page para .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Agora, vamos dividir o exemplo fornecido em várias etapas.

## Etapa 1: Definir o Caminho do Diretório do Documento

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Etapa 2: Criar um Novo Documento XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Etapa 3: Inicializar os Stops do Gradiente

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Etapa 4: Criar um Novo Caminho

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Etapa 5: Salvar o Documento XPS Resultante

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Agora, você adicionou com sucesso um gradiente horizontal ao seu documento XPS usando Aspose.Page para .NET.

## Problemas Comuns e Soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| O gradiente aparece como cor sólida | Stops do gradiente não foram adicionados corretamente | Certifique‑se de que `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` seja executado após definir o brush. |
| Arquivo salvo está vazio | `dataDir` aponta para uma pasta inexistente | Verifique se a pasta existe ou use um caminho absoluto. |
| Erro de compilação em `PointF` | Falta a referência `System.Drawing` | Adicione uma referência a `System.Drawing.Common` (para .NET Core/5+). |

## Perguntas Frequentes

### Q1: Onde posso encontrar a documentação do Aspose.Page para .NET?

A1: Você pode encontrar a documentação [aqui](https://reference.aspose.com/page/net/).

### Q2: Como faço o download do Aspose.Page para .NET?

A2: Você pode baixar a biblioteca na [página de download do Aspose.Page para .NET](https://releases.aspose.com/page/net/).

### Q3: Onde posso comprar o Aspose.Page para .NET?

A3: Você pode comprar o Aspose.Page para .NET na [página de compra](https://purchase.aspose.com/buy).

### Q4: Existe uma versão de avaliação gratuita disponível?

A4: Sim, você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Q5: Como obtenho uma licença temporária para o Aspose.Page para .NET?

A5: Você pode obter uma licença temporária neste [link](https://purchase.aspose.com/temporary-license/).

## Perguntas Frequentes Adicionais

**P: Posso usar esta técnica de gradiente em documentos XPS que já contêm imagens?**  
R: Absolutamente. O gradiente é aplicado a uma camada de caminho, portanto as imagens existentes permanecem intactas.

**P: É possível criar um gradiente vertical em vez de horizontal?**  
R: Sim. Altere os pontos de início e fim do `LinearGradientBrush` para ter coordenadas Y diferentes enquanto mantém X constante.

**P: O Aspose.Page suporta .NET Core?**  
R: A biblioteca é totalmente compatível com .NET Core, .NET 5 e versões posteriores.

**P: Como reutilizo o mesmo gradiente em várias páginas?**  
R: Crie o `XpsLinearGradientBrush` uma única vez, armazene‑o em uma variável e atribua‑o aos caminhos em cada página.

## Conclusão

Aprimorar seus documentos XPS com gradientes não só melhora o apelo visual, mas também oferece uma experiência de usuário mais envolvente. Com Aspose.Page para .NET, você pode **criar preenchimentos de gradiente XPS** de forma rápida e confiável, conferindo aos seus relatórios, brochuras ou e‑books um acabamento profissional.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-02-25  
**Testado com:** Aspose.Page para .NET 24.11  
**Autor:** Aspose  

---