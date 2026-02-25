---
date: 2026-02-25
description: Aprimore documentos PostScript com um retângulo de gradiente linear usando
  Aspose.Page para .NET. Siga nosso guia passo a passo para aprender preenchimento
  de texto com gradiente e contorno de texto com gradiente.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Adicionar um Retângulo com Gradiente Linear ao PostScript (PS) usando Aspose.Page
url: /pt/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

 ensure we keep code block placeholders unchanged.

Also keep markdown formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar um Retângulo com Gradiente Linear ao PostScript (PS) com Aspose.Page

## Introdução

Bem-vindo a este tutorial abrangente sobre como adicionar um **retângulo com gradiente linear** a documentos PostScript (PS) usando Aspose.Page para .NET. Aspose.Page é uma biblioteca poderosa que permite criar, modificar e renderizar documentos em diversos formatos, e hoje vamos nos concentrar em como trazer gradientes atraentes para seus arquivos PS.

### Respostas Rápidas
- **O que o retângulo com gradiente linear faz?** Ele preenche uma área retangular com uma transição suave de cor de um lado ao outro.  
- **Qual API lida com preenchimento de texto com gradiente?** `LinearGradientBrush` combinado com `SetPaint` e `FillAndStrokeText`.  
- **Posso contornar texto com um gradiente?** Sim—use `SetStroke` com um pincel de gradiente e chame `OutlineText`.  
- **Preciso de licença para produção?** Uma licença comercial do Aspose.Page é necessária para uso não‑avaliativo.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Pré‑requisitos

Antes de começarmos, certifique-se de que você tem:

- Biblioteca Aspose.Page para .NET: Certifique-se de que a biblioteca está referenciada em seu projeto. Você pode baixá‑la na [documentação do Aspose.Page para .NET](https://reference.aspose.com/page/net/).
- Diretório de Documentos: Crie uma pasta no disco onde o arquivo PS gerado será salvo e substitua **“Your Document Directory”** no código por esse caminho.

## Importar Namespaces

Para iniciar, importe os namespaces que dão acesso às classes de desenho e específicas do PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## O que é um Retângulo com Gradiente Linear?

Um **retângulo com gradiente linear** é simplesmente uma forma retangular cujo interior é pintado com um gradiente linear—as cores transicionam suavemente ao longo de uma linha reta, tipicamente da esquerda para a direita (horizontal) ou de cima para baixo (vertical). No Aspose.Page você consegue isso combinando um `GraphicsPath` que define o retângulo com um `LinearGradientBrush` que descreve a transição de cores.

## Por que usar preenchimento de texto com gradiente e contorno de texto com gradiente?

- **Apelo Visual:** Texto preenchido com gradiente adiciona profundidade e estilo moderno a relatórios, faturas ou materiais promocionais.  
- **Consistência de Marca:** Combine cores corporativas com valores ARGB precisos.  
- **Versatilidade:** O mesmo pincel pode ser reutilizado para preenchimento de formas, preenchimento de texto e gradientes de contorno, reduzindo a duplicação de código.

## Etapa 1: Configurar o Documento

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Etapa 2: Definir o Retângulo de Gradiente e as Cores

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Etapa 3: Definir Transformação para o Pincel

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Etapa 4: Definir Pintura e Preencher o Retângulo

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Como Aplicar Preenchimento de Texto com Gradiente

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Usando Contorno de Texto com Gradiente

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Etapa 7: Fechar a Página Atual e Salvar o Documento

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Parabéns! Você adicionou com sucesso um **retângulo com gradiente linear** a um documento PostScript e usou o mesmo pincel para **preenchimento de texto com gradiente** e um **contorno de texto com gradiente**.

## Casos de Uso Comuns & Dicas

- **Cabeçalhos de Relatórios:** Preencha blocos de texto grandes com gradientes para destacar os títulos das seções.  
- **Logotipos de Marca:** Recrie formas de logotipo com formas preenchidas por gradiente para uma identidade visual consistente.  
- **Dica Profissional:** Re‑utilize a mesma instância de `LinearGradientBrush` para várias chamadas de desenho para manter as cores perfeitamente alinhadas entre formas e texto.

## Perguntas Frequentes

### Q1: Posso aplicar gradientes a outras formas além de retângulos?

**A:** Sim, você pode aplicar gradientes a qualquer forma definida por um `GraphicsPath`. Basta adicionar círculos, polígonos ou caminhos personalizados antes de chamar `document.Fill(path)`.

### Q2: Como posso mudar as cores do gradiente?

**A:** Modifique os valores `Color.FromArgb` ao construir o `LinearGradientBrush`. A primeira cor é o início, a segunda é o fim do gradiente.

### Q3: O Aspose.Page é compatível com diferentes formatos de documento?

**A:** Absolutamente. Aspose.Page suporta XPS, PS, PDF e vários outros formatos vetoriais. Consulte a documentação oficial para a lista completa.

### Q4: Posso usar o Aspose.Page em projetos comerciais?

**A:** Sim, licenciamento comercial está disponível. Veja a página de compra para detalhes: [here](https://purchase.aspose.com/buy).

### Q5: Onde posso encontrar suporte da comunidade?

**A:** Participe do fórum da comunidade Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Última Atualização:** 2026-02-25  
**Testado com:** Aspose.Page 24.10 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}