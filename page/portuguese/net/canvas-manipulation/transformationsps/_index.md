---
date: 2026-01-12
description: Aprenda como salvar arquivos PostScript e criar documentos PostScript
  usando Aspose.Page para .NET, e aplicar múltiplas transformações para gráficos dinâmicos.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Salvar arquivo PostScript com Aspose.Page Transformations (.NET)
url: /pt/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar arquivo PostScript com transformações Aspose.Page (.NET)

## Introdução

Neste tutorial você descobrirá como **salvar um arquivo PostScript** enquanto trabalha com Aspose.Page para .NET. Vamos percorrer a criação de um documento PostScript, aplicar múltiplas transformações como translação, escala, rotação e cisalhamento, e finalmente salvar o resultado. Ao final, você estará confortável em criar gráficos dinâmicos programaticamente e saberá exatamente onde colocar cada transformação no estado gráfico.

## Respostas rápidas
- **O que posso criar?** Um documento PostScript completo com gráficos transformados.  
- **Qual biblioteca é necessária?** Aspose.Page para .NET (disponível para download no site oficial).  
- **Como salvo o arquivo?** Use `PsDocument.Save()` após configurar os estados gráficos.  
- **Posso aplicar múltiplas transformações?** Sim – combine-as com `Transform` ou chamadas sequenciais.  
- **É necessária uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.

## O que é uma operação de “salvar arquivo PostScript”?

Salvar um arquivo PostScript significa persistir os comandos de desenho que você criou na memória em um arquivo `.ps` no disco. O arquivo pode então ser renderizado por qualquer interpretador PostScript, impressora ou visualizador.

## Por que usar Aspose.Page para .NET para criar documento PostScript?

Aspose.Page fornece uma API de alto nível, independente de dispositivo, que abstrai a sintaxe de baixo nível do PostScript. Você obtém:

- Objetos C# fortemente tipados para caminhos, pincéis e transformações.  
- Manipulação automática da pilha de estado gráfico (save/restore).  
- Suporte total a matrizes de transformação complexas sem cálculos manuais.

## Pré-requisitos

Antes de começar, certifique-se de que você tem:

- Biblioteca **Aspose.Page para .NET** integrada ao seu projeto. Baixe-a a partir do [link de download](https://releases.aspose.com/page/net/).  
- Uma pasta gravável onde o arquivo `.ps` gerado será armazenado. Substitua o caminho placeholder no código pelo seu diretório real.

## Importar namespaces

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora vamos explorar cada etapa de transformação passo a passo.

## Sem Transformações

### Etapa 1: Criar fluxo de saída

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Este trecho cria um **documento PostScript** com um único retângulo laranja e **salva o arquivo PostScript** sem aplicar nenhuma transformação.

## Translação

### Etapa 1: Salvar estado gráfico

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Salvar o estado gráfico permite que você volte ao estado anterior após mover objetos.

### Etapa 2: Transladar estado gráfico

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

A translação move tudo que for desenhado após esta chamada 250 unidades para a direita.

### Etapa 3: Preencher retângulo com transformação de translação

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Agora um retângulo azul aparece 250 pontos à direita do laranja.

### Etapa 4: Restaurar estado gráfico

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Restaurar devolve o sistema de coordenadas à sua posição original, de modo que desenhos subsequentes não sejam afetados pela translação.

## Escala

> *Você pode seguir o mesmo padrão — salvar estado, aplicar `Scale`, desenhar e então restaurar.*  
> **Dica profissional:** Use escala não uniforme (`Scale(sx, sy)`) para esticar objetos apenas em uma direção.

## Rotação

> *Gire em torno da origem ou de um ponto de pivô personalizado usando `Rotate(angle)`.*
> **Dica profissional:** Combine `Translate` antes da rotação para girar em torno de um ponto específico.

## Cisalhamento

> *Transformações de cisalhamento (`Shear(shx, shy)`) inclinam formas, úteis para efeitos itálicos.*

## Transformações Complexas

> *Para cenários avançados, construa uma `Matrix` personalizada e passe-a para `Transform(matrix)`.*
> É aqui que você **aplica múltiplas transformações** em um único passo.

## Conclusão

Você aprendeu como **salvar arquivo PostScript**, **criar documento PostScript** e **aplicar múltiplas transformações** usando Aspose.Page para .NET. Experimente diferentes ordens de transformação, combine-as e observe como os gráficos evoluem.

## Perguntas Frequentes

**Q: Como posso aplicar múltiplas transformações a um único objeto?**  
A: Use o método `Transform` com uma `Matrix` personalizada que combine translação, escala, rotação ou cisalhamento na ordem que você precisar.

**Q: Posso visualizar as transformações antes de salvar o documento?**  
A: Sim — renderize o `PsDocument` para uma imagem ou use um visualizador PostScript para inspecionar a saída antes de chamar `Save()`.

**Q: É possível aplicar transformações a elementos específicos em um documento?**  
A: Absolutamente. Salve o estado gráfico antes de desenhar o elemento, aplique a transformação desejada, desenhe e então restaure o estado.

**Q: Existem considerações de desempenho ao lidar com transformações complexas?**  
A: Matrizes complexas aumentam o trabalho da CPU. Mantenha as transformações o mais simples possível e reutilize estados salvos ao desenhar muitos objetos semelhantes.

**Q: Como posso obter suporte ou assistência para dúvidas relacionadas ao Aspose.Page?**  
A: Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para ajuda da comunidade, ou entre em contato diretamente com o suporte da Aspose.

---

**Última atualização:** 2026-01-12  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}