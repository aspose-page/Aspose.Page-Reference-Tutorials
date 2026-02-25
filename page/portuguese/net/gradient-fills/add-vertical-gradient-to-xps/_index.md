---
date: 2026-02-25
description: Aprenda como criar um documento XPS e aplicar gradiente linear com Aspose.Page
  para .NET. Siga nosso guia passo a passo para salvar o arquivo XPS.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Criar documento XPS com gradiente vertical usando Aspose.Page
url: /pt/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

step-by-step in order - do not skip sections". So keep order.

Also note "For Portuguese, ensure proper RTL formatting if needed" - not needed.

Let's translate.

Start with shortcodes.

Then heading "# Add Vertical Gradient to XPS with Aspose.Page for .NET" translate to Portuguese: "Adicionar Gradiente Vertical ao XPS com Aspose.Page para .NET". Keep same heading level.

Similarly other headings.

Translate bullet list items.

Translate paragraphs.

Translate table.

Translate FAQ.

Make sure to keep markdown syntax.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Gradiente Vertical ao XPS com Aspose.Page para .NET

## Introdução

Neste tutorial você **criará um documento XPS** que apresenta um gradiente vertical suave. Adicionar gradientes é uma maneira comum de tornar arquivos XPS mais profissionais — perfeito para relatórios, brochuras ou quaisquer gráficos imprimíveis. Vamos percorrer cada passo, desde a configuração do projeto até a gravação do arquivo XPS final, para que você possa aplicar rapidamente um gradiente linear a qualquer caminho.

## Respostas Rápidas
- **O que este tutorial cobre?** Adicionar um gradiente linear vertical a um caminho em um documento XPS.  
- **Qual biblioteca é necessária?** Aspose.Page para .NET.  
- **Preciso de licença?** Uma versão de avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um exemplo básico.  
- **Posso salvar o resultado como um arquivo XPS?** Sim, o método `Save` grava o arquivo no disco.

## O que é um gradiente vertical no XPS?

Um gradiente vertical é uma transição de cores que vai do topo de uma forma até a base. No XPS, isso é conseguido com um **pincel de gradiente linear** que define pontos de início e fim, além de uma coleção de paradas de gradiente que controlam a cor em posições específicas.

## Por que usar Aspose.Page para criar documentos XPS com gradientes?

- **Integração completa com .NET** – funciona com .NET Framework, .NET Core e .NET 5/6+.  
- **Sem dependências externas** – toda a renderização é tratada pela biblioteca.  
- **Alta fidelidade** – os gradientes são renderizados exatamente como definidos, em conformidade com a especificação XPS.  
- **Fácil de manter** – modelo de objetos claro para caminhos, pincéis e cores.

## Pré‑requisitos

- Biblioteca Aspose.Page para .NET: Certifique‑se de que a biblioteca Aspose.Page para .NET está instalada em seu ambiente de desenvolvimento. Você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).
- Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento .NET com sua IDE preferida, como o Visual Studio.

Agora que temos tudo pronto, vamos mergulhar no código.

## Importar Namespaces

Em sua aplicação .NET, inclua os namespaces necessários para acessar as classes e métodos do Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Etapa 1: Configurar o Diretório do Documento

Defina a pasta onde o arquivo XPS gerado será salvo.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Etapa 2: Criar um Novo Documento XPS

Instancie um novo documento XPS que será preenchido posteriormente com um caminho preenchido por gradiente.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Etapa 3: Definir Paradas de Gradiente

As paradas de gradiente determinam as cores e suas posições ao longo da linha do gradiente. Aqui criamos cinco paradas para produzir uma transição vertical suave.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Etapa 4: Criar um Caminho com Gradiente

Desenhamos um caminho em forma de retângulo e aplicamos um **pincel de gradiente linear** que vai verticalmente do ponto (10, 110) ao ponto (10, 200). O pincel recebe as paradas de gradiente definidas anteriormente.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Etapa 5: Salvar o Documento XPS Resultante

Por fim, grave o documento XPS no disco. Esta etapa de **salvar arquivo XPS** produz `AddVerticalGradient_outXPS.xps` na pasta que você especificou.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Dica profissional:** Verifique a saída abrindo o arquivo XPS no Visualizador XPS do Windows ou em qualquer visualizador de terceiros para garantir que o gradiente apareça como esperado.

## Problemas Comuns & Solução de Problemas

| Sintoma | Causa Provável | Solução |
|---------|----------------|---------|
| O gradiente aparece como cor sólida | Paradas de gradiente não foram adicionadas ao pincel | Certifique‑se de que `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` seja executado. |
| Arquivo não encontrado ao salvar | `dataDir` aponta para uma pasta inexistente | Crie o diretório primeiro ou use um caminho absoluto. |
| As cores parecem diferentes | Valores de cor usam ordem ARGB; verifique a ordem dos canais | Use `CreateColor(alpha, red, green, blue)` corretamente. |

## Perguntas Frequentes

**P: O Aspose.Page é compatível com o Visual Studio 2019?**  
R: Sim, o Aspose.Page é compatível com o Visual Studio 2019. Certifique‑se de ter a versão correta da biblioteca instalada.

**P: Posso usar o Aspose.Page em projetos comerciais?**  
R: Sim, o Aspose.Page pode ser usado em projetos comerciais. Visite [aqui](https://purchase.aspose.com/buy) para explorar opções de licenciamento.

**P: Existe uma versão de avaliação gratuita?**  
R: Sim, você pode obter uma avaliação gratuita do Aspose.Page [aqui](https://releases.aspose.com/).

**P: Onde encontro a documentação do Aspose.Page?**  
R: A documentação está disponível [aqui](https://reference.aspose.com/page/net/).

**P: Como obter suporte ou fazer perguntas?**  
R: Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para suporte da comunidade.

## Conclusão

Agora você sabe como **criar um documento XPS**, **aplicar um gradiente linear** e **salvar o arquivo XPS** usando Aspose.Page para .NET. Essa abordagem oferece controle total sobre o estilo visual nas saídas XPS, fazendo com que seus documentos imprimíveis se destaquem.

---  

**Última atualização:** 2026-02-25  
**Testado com:** Aspose.Page para .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}