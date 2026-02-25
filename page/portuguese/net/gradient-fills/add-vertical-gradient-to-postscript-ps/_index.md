---
date: 2026-02-25
description: Aprenda a usar um pincel de gradiente linear em C# para adicionar gradiente
  a arquivos PS e preencher retângulos com gradiente usando o Aspose.Page para .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Pincel de Gradiente Linear – Adicionar Gradiente Vertical ao PostScript
  (PS) com Aspose.Page
url: /pt/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Adicionar Gradiente Vertical ao PostScript (PS) com Aspose.Page

## Introdução

No domínio da manipulação e criação de documentos, **Aspose.Page for .NET** destaca‑se como uma ferramenta poderosa para desenvolvedores. Neste guia você descobrirá como **adicionar gradiente a arquivos PS** usando um **C# linear gradient brush** para **preencher retângulo com gradiente**. Ao final deste tutorial, você terá uma compreensão clara, passo a passo, do código necessário e por que essa técnica produz um gradiente vertical suave na sua saída PostScript.

## Respostas Rápidas
- **O que faz um C# linear gradient brush?** Ele cria uma transição suave entre várias cores ao longo de uma forma.
- **Posso usar isso com qualquer versão do .NET?** Sim, o Aspose.Page suporta .NET Framework 4.5+ e .NET Core/5+.
- **Preciso de licença para produção?** Uma licença comercial é necessária para builds que não sejam de avaliação.
- **O gradiente é realmente vertical?** O brush é rotacionado 90°, garantindo um fluxo vertical.
- **Onde a saída é salva?** No caminho que você especificar em `dataDir` (por exemplo, `VerticalGradient_outPS.ps`).

## O que é um C# Linear Gradient Brush?
Um **C# linear gradient brush** é um objeto GDI+ (`LinearGradientBrush`) que pinta uma transição de cor linear entre pontos definidos. Quando combinado com a API de desenho do Aspose.Page, permite renderizar gradientes sofisticados diretamente em um documento PostScript (PS).

## Por que usar um Linear Gradient Brush para PostScript?
- **Saída de alta qualidade:** Os gradientes são renderizados no nível da impressora, preservando a fidelidade.
- **Controle total:** Você pode definir pontos de cor personalizados, rotação e dimensionamento.
- **Código reutilizável:** A mesma lógica de brush funciona para PDF, SVG e outros formatos suportados pelo Aspose.Page.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique‑se de que você tem o seguinte configurado:

- Aspose.Page for .NET: Certifique‑se de que a biblioteca Aspose.Page está instalada. Você pode encontrar os recursos necessários e a documentação [aqui](https://reference.aspose.com/page/net/).
- Ambiente de desenvolvimento: Configure um ambiente de desenvolvimento adequado, incluindo uma IDE (Integrated Development Environment) para desenvolvimento .NET.
- Compreensão básica: Familiarize‑se com os fundamentos do desenvolvimento .NET, incluindo trabalho com streams, caminhos gráficos (graphics paths) e manipulação de cores.

## Importar Namespaces

No seu projeto C#, inclua os namespaces necessários no início do seu arquivo de código:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Etapa 1: Configurar o Diretório do Documento

Comece especificando o caminho para o diretório do seu documento. Este é o local onde seu documento PS será salvo.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Criar Stream de Saída para o Documento PostScript

Gere um stream de saída para o documento PostScript usando a classe `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Etapa 3: Criar Opções de Salvamento e Documento PS

Crie opções de salvamento com tamanho A4 e inicialize um novo documento PS de 1 página.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Etapa 4: Definir Dimensões do Retângulo

Especifique as dimensões e a posição do retângulo onde o gradiente vertical será aplicado.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Etapa 5: Criar Graphics Path

Construa um graphics path a partir do retângulo definido.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Etapa 6: Definir Cores de Interpolação

Estabeleça um array de cores de interpolação e posições para o gradiente.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Etapa 7: Criar Linear Gradient Brush

Forme um linear gradient brush com o retângulo como limites, cores inicial e final.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Etapa 8: Definir Transformação do Brush

Estabeleça uma transformação para o brush, garantindo que os componentes de escala X e Y correspondam à largura e altura do retângulo.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Etapa 9: Definir Pintura e Preencher o Retângulo

Defina a pintura para o documento e **preencha o retângulo com gradiente** usando o caminho definido anteriormente.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Etapa 10: Fechar a Página Atual e Salvar o Documento

Feche a página atual e salve o documento PostScript.

```csharp
document.ClosePage();
document.Save();
```

Parabéns! Você adicionou com sucesso **um gradiente vertical a um documento PostScript** usando um **C# linear gradient brush** com Aspose.Page for .NET. Experimente diferentes parâmetros e cores para alcançar vários efeitos visuais em seus documentos.

## Problemas Comuns e Soluções

| Problema | Por que acontece | Como corrigir |
|----------|------------------|---------------|
| Gradiente aparece horizontal | Rotação do brush não aplicada | Certifique‑se de que `brushTransform.Rotate(90);` seja chamado antes de atribuir a `brush.Transform`. |
| Cores parecem desbotadas | Stream de saída de baixa resolução | Use um `PsSaveOptions` de resolução mais alta ou aumente o tamanho do documento. |
| Arquivo de saída está vazio | Stream não foi descarregado (flush) | Verifique se `document.Save();` é chamado fora do bloco `using`. |

## Perguntas Frequentes

**Q1: Posso aplicar múltiplos gradientes a diferentes regiões do mesmo documento?**  
A: Sim, você pode. Basta repetir as etapas para cada região com suas dimensões específicas e esquema de cores.

**Q2: Como posso integrar este código ao meu projeto .NET existente?**  
A: Copie e cole o código no seu arquivo de projeto e certifique‑se de que a biblioteca Aspose.Page está referenciada.

**Q3: Existem outros tipos de gradiente disponíveis no Aspose.Page para .NET?**  
A: O Aspose.Page suporta vários tipos de gradiente, incluindo radiais e de caminho. Consulte a documentação para mais detalhes.

**Q4: Posso usar o Aspose.Page em projetos comerciais?**  
A: Sim, pode. Visite [aqui](https://purchase.aspose.com/buy) para explorar as opções de licenciamento.

**Q5: Existe um fórum da comunidade para Aspose.Page onde eu possa buscar ajuda?**  
A: Certamente! Acesse o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para conectar‑se com outros desenvolvedores e obter assistência.

---

**Última atualização:** 2026-02-25  
**Testado com:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}