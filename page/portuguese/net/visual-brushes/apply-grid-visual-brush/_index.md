---
date: 2026-04-03
description: Aprenda a adicionar um retângulo transparente e aplicar um Grid Visual
  Brush no .NET usando o Aspose.Page para documentos XPS impressionantes.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Aplicar pincel visual de grade
second_title: Aspose.Page .NET API
title: Adicionar Retângulo Transparente usando Pincel Visual de Grade (.NET)
url: /pt/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Retângulo Transparente usando Grid Visual Brush (.NET)

## Introdução

Se você está procurando **adicionar um retângulo transparente** a um documento XPS enquanto também aplica um elegante Grid Visual Brush, você está no lugar certo. Neste tutorial, vamos percorrer as etapas exatas necessárias com Aspose.Page for .NET, para que você possa criar documentos visualmente ricos que se destacam. Ao final, você terá um exemplo completo e executável que demonstra ambas as técnicas em um fluxo de trabalho único e fácil de seguir.

## Respostas Rápidas
- **O que um retângulo transparente faz?** Ele adiciona uma sobreposição semi‑opaca que permite que o conteúdo de fundo seja exibido.  
- **Qual API cria o brush?** `XpsDocument.CreateVisualBrush` cria o Grid Visual Brush.  
- **Preciso de uma licença?** Uma versão de avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um exemplo básico.

## O que é um Retângulo Transparente em XPS?

Um retângulo transparente é simplesmente uma forma cuja cor de preenchimento inclui um componente alfa menor que 1.0, permitindo que os gráficos subjacentes fiquem parcialmente visíveis. Isso é perfeito para destacar seções sem obscurecer completamente o plano de fundo.

## Por que usar um Grid Visual Brush?

Um Grid Visual Brush permite que você repita um pequeno gráfico vetorial em uma área maior, criando padrões como grades, hachuras ou texturas personalizadas. Combinar isso com um retângulo transparente oferece efeitos visuais em camadas que são leves e independentes de resolução.

## Pré-requisitos

Antes de mergulhar no código, certifique-se de que você tem:

- **Aspose.Page for .NET** – você pode baixá-lo [aqui](https://releases.aspose.com/page/net/).
- Um ambiente de desenvolvimento .NET (Visual Studio, VS Code ou qualquer IDE de sua preferência).
- Uma pasta onde os arquivos XPS gerados serão salvos.

## Importar Namespaces

No seu arquivo C#, importe os namespaces necessários:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Agora vamos dividir a solução em etapas claras e numeradas.

## Etapa 1: Inicializar XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Começamos criando uma instância de `XpsDocument`, que armazenará todas as operações de desenho subsequentes.

## Etapa 2: Criar Geometria da Grade Magenta

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Esta geometria define o contorno da grade que o visual brush preencherá.

## Etapa 3: Projetar VisualBrush da Grade Magenta

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Aqui desenhamos um pequeno bloco magenta que será repetido pela grade.

## Etapa 4: Aplicar VisualBrush à Grade

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

A chamada `CreateVisualBrush` vincula o bloco magenta à geometria da grade e habilita o padrão.

## Etapa 5: Adicionar Grade ao Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Colocamos a grade em padrão em um canvas e aplicamos uma transformação de translação para que apareça na localização desejada.

## Etapa 6: Adicionar Retângulo Transparente

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

Nesta etapa, nós **adicionamos um retângulo transparente** (a forma vermelha com `Opacity = 0.7f`). Ajuste o valor da opacidade para controlar o grau de transparência do retângulo.

## Etapa 7: Salvar o Documento

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

O arquivo XPS é gravado na pasta que você especificou anteriormente.

## Casos de Uso Comuns

- **Realce de Relatórios:** Sobrepor um retângulo semi‑transparente para enfatizar um gráfico ou tabela.  
- **Efeitos de Marca d'Água:** Combine uma grade em padrão com uma sobreposição transparente para branding sutil.  
- **PDFs/XPS Interativos:** Use o padrão como fundo para campos de formulário mantendo a interface legível.

## Dicas de Solução de Problemas

- **Opacidade Não Visível?** Certifique-se de que seu visualizador suporta transparência XPS; alguns visualizadores mais antigos podem ignorar a propriedade `Opacity`.  
- **Tamanho da Ladrilho Incorreto?** Verifique se o retângulo de origem (`new RectangleF(0f, 0f, 10f, 10f)`) corresponde às dimensões do ladrilho vetorial.  
- **Arquivo Não Salvo?** Verifique novamente se `dataDir` aponta para um diretório existente e gravável.

## Perguntas Frequentes

**Q: Posso usar Aspose.Page for .NET em aplicações web e desktop?**  
A: Sim, a biblioteca funciona em todos os tipos de aplicação .NET.

**Q: Existe uma versão de avaliação disponível antes da compra?**  
A: Absolutamente, você pode acessar a versão de avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Onde posso encontrar suporte adicional ou discussões da comunidade?**  
A: Visite o [Aspose.Page Forum](https://forum.aspose.com/c/page/39) para obter ajuda da comunidade e dos engenheiros da Aspose.

**Q: Como posso obter uma licença temporária para avaliação?**  
A: Você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Que outra documentação está disponível para Aspose.Page for .NET?**  
A: Explore a documentação completa [aqui](https://reference.aspose.com/page/net/).

---

**Última Atualização:** 2026-04-03  
**Testado com:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}