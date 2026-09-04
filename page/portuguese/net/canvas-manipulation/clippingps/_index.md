---
date: 2026-06-25
description: Aprenda a adicionar caminho de recorte no PostScript usando Aspose.Page
  for .NET – guia passo a passo com técnicas de pincel e retângulo tracejado.
keywords:
- how to add clipping path
- Aspose.Page clipping
- PostScript graphics .NET
linktitle: Recorte PS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  headline: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  name: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  steps:
  - name: Set Document Directory
    text: Define the folder where your source and output files will live. This makes
      it easy to locate the generated PS file later.
  - name: Create Output Stream for PostScript Document
    text: Create a writable stream that will hold the generated PS file. Using a `FileStream`
      ensures the file is written directly to disk.
  - name: Create Save Options
    text: '`PsSaveOptions` is Aspose.Page’s configuration object for PS output. It
      lets you control compression, version, and other rendering details.'
  - name: Create a New 1‑Paged PS Document
    text: '`PsDocument` represents a PostScript document object. You instantiate it
      with the output stream and the save options you just configured.'
  - name: Create Graphics Path from the Rectangle
    text: '`GraphicsPath` is a vector container for geometric shapes. Here we start
      with a simple rectangle that will later be clipped.'
  - name: Clipping by Shape
    text: We add a clipping path using a circle, set the paint brush to blue, and
      fill the rectangle within the clipped region. This demonstrates how clipping
      limits drawing to the circle’s interior.
  - name: Displace Upper Level Graphics State & Draw Dashed Rectangle
    text: After restoring the previous graphics state, we translate the cursor, create
      a `Pen` with `DashStyle.Dash`, and draw a dashed rectangle around the clipped
      content. The blue stroke highlights the clipping boundary. `Pen` defines stroke
      attributes such as color and dash style. `DashStyle.Dash` specifi
  - name: Close and Save Document
    text: Finish the page, flush the stream, and dispose of resources. The PS file
      is now written to disk and ready for viewing in any PostScript viewer. You have
      now successfully **added clipping path**, set a custom paint brush, and drawn
      a dashed rectangle around your graphics using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: It restricts drawing operations to a defined shape, hiding everything
      outside that shape.
    question: What does “add clipping path” do?
  - answer: Aspose.Page for .NET provides a rich API for PS/EPS manipulation.
    question: Which library handles clipping in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes, use `SetPaint` with any `SolidBrush` or gradient you prefer.
    question: Can I change the brush color?
  - answer: Absolutely – create a `Pen` with `DashStyle.Dash` and use `Draw`.
    question: Is drawing a dashed rectangle possible?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Como adicionar caminho de recorte ao PostScript com Aspose.Page for .NET
url: /pt/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Caminho de Recorte a PostScript com Aspose.Page para .NET

## Introdução

Neste tutorial abrangente, você aprenderá **como adicionar caminho de recorte** a um documento PostScript (PS) usando Aspose.Page para .NET. Vamos percorrer cada passo, mostrar como **definir um pincel de pintura**, e demonstrar como **desenhar um retângulo tracejado** ao redor do conteúdo recortado. Ao final, você terá um arquivo PS totalmente funcional que ilustra o recorte por forma, dando aos seus gráficos um aspecto mais dinâmico e profissional.

## Respostas Rápidas
- **O que faz “add clipping path”?** Ele restringe as operações de desenho a uma forma definida, ocultando tudo que está fora dessa forma.  
- **Qual biblioteca lida com recorte em .NET?** Aspose.Page para .NET fornece uma API rica para manipulação de PS/EPS.  
- **Preciso de uma licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso mudar a cor do pincel?** Sim, use `SetPaint` com qualquer `SolidBrush` ou gradiente que preferir.  
- **É possível desenhar um retângulo tracejado?** Absolutamente – crie um `Pen` com `DashStyle.Dash` e use `Draw`.  

## O que é um caminho de recorte em PostScript?

Um caminho de recorte define a região visível dos comandos de desenho subsequentes, descartando tudo que for renderizado fora de seus limites. Na prática, ele permite mascarar gráficos de modo que apenas a parte dentro do caminho seja exibida, o que é essencial para criar composições complexas sem alterar permanentemente os objetos originais.

## Como adicionar caminho de recorte a um documento PostScript com Aspose.Page?

Carregue um `PsDocument`, defina um caminho gráfico (por exemplo, um círculo), aplique `Clip()` para restringir a área de desenho e, em seguida, use `SetPaint` e `Fill` para renderizar o conteúdo dentro da região recortada. Após restaurar o estado gráfico, você pode desenhar formas adicionais — como um retângulo tracejado — sem afetar a área recortada. Essa sequência realiza o recorte em apenas algumas chamadas concisas da API.

`PsDocument` representa um objeto de documento PostScript.  
`GraphicsPath` é um contêiner vetorial para formas geométricas.  
`Clip()` define a região de recorte para desenhos subsequentes.  
`SetPaint` atribui um pincel usado para preencher formas.  
`Fill` renderiza o caminho atual usando o pincel atual.

## Por que usar Aspose.Page para recorte?

Aspose.Page suporta **mais de 50 formatos de entrada e saída**, incluindo PS, EPS, PDF, SVG e tipos de imagem, e pode processar documentos com centenas de páginas sem carregar o arquivo inteiro na memória. A biblioteca tem **zero dependências externas**, funciona em **.NET Framework 4.5+**, **.NET Core 3.1+** e **.NET 6+**, e oferece controle total sobre o estado gráfico (salvar/restaurar, transladar, girar). Esses benefícios quantificados a tornam uma escolha confiável para geração de gráficos no lado do servidor.

## Pré-requisitos

- Conhecimento básico de programação em C#.  
- Biblioteca Aspose.Page para .NET instalada – você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).  
- Visual Studio ou qualquer IDE .NET de sua preferência.  

## Importar Namespaces

Os namespaces a seguir dão acesso aos objetos gráficos principais e às opções de salvamento específicas para PS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora vamos dividir o exemplo em etapas claras e numeradas.

### Passo 1: Definir Diretório do Documento

Defina a pasta onde seus arquivos de origem e saída serão armazenados. Isso facilita localizar o arquivo PS gerado posteriormente.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Passo 2: Criar Fluxo de Saída para Documento PostScript

Crie um fluxo gravável que armazenará o arquivo PS gerado. Usar um `FileStream` garante que o arquivo seja escrito diretamente no disco.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Passo 3: Criar Opções de Salvamento

`PsSaveOptions` é o objeto de configuração do Aspose.Page para saída PS. Ele permite controlar compressão, versão e outros detalhes de renderização.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Passo 4: Criar um Novo Documento PS de 1 Página

`PsDocument` representa um objeto de documento PostScript. Você o instancia com o fluxo de saída e as opções de salvamento que acabou de configurar.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Passo 5: Criar Caminho Gráfico a partir do Retângulo

`GraphicsPath` é um contêiner vetorial para formas geométricas. Aqui começamos com um retângulo simples que será recortado posteriormente.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Passo 6: Recorte por Forma

Adicionamos um caminho de recorte usando um círculo, definimos o pincel de pintura para azul e preenchemos o retângulo dentro da região recortada. Isso demonstra como o recorte limita o desenho ao interior do círculo.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Passo 7: Deslocar o Estado Gráfico de Nível Superior e Desenhar Retângulo Tracejado

Após restaurar o estado gráfico anterior, transladamos o cursor, criamos um `Pen` com `DashStyle.Dash` e desenhamos um retângulo tracejado ao redor do conteúdo recortado. O traço azul destaca o limite do recorte.

`Pen` define atributos de traço como cor e estilo de traço.  
`DashStyle.Dash` especifica um padrão de linha tracejada.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Passo 8: Fechar e Salvar Documento

Finalize a página, descarregue o fluxo e libere os recursos. O arquivo PS agora está escrito no disco e pronto para visualização em qualquer visualizador PostScript.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Você agora adicionou com sucesso **caminho de recorte**, definiu um pincel de pintura personalizado e desenhou um retângulo tracejado ao redor de seus gráficos usando Aspose.Page para .NET.

## Problemas Comuns e Soluções

- **Recorte não visível:** Certifique-se de chamar `WriteGraphicsSave()` antes de transladar e `WriteGraphicsRestore()` após preencher.  
- **Cores incorretas:** Verifique se `SetPaint` é chamado após `Clip` e antes de `Fill`.  
- **Linhas tracejadas aparecem sólidas:** Garanta que o `DashStyle` do `Pen` esteja definido como `DashStyle.Dash` antes de `SetStroke`.  

## Perguntas Frequentes

### Q1: Posso usar Aspose.Page para .NET com outras linguagens de programação?
R: Aspose.Page é projetado principalmente para aplicações .NET, mas a Aspose oferece bibliotecas equivalentes para Java, C++ e outras plataformas.

### Q2: Onde posso encontrar exemplos adicionais e documentação para Aspose.Page para .NET?
R: Você pode explorar mais exemplos e documentação detalhada na [documentação do Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: Existe uma avaliação gratuita disponível para Aspose.Page para .NET?
R: Sim, você pode acessar uma avaliação gratuita do Aspose.Page para .NET [aqui](https://releases.aspose.com/).

### Q4: Como posso obter uma licença temporária para Aspose.Page para .NET?
R: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Onde posso obter suporte ou discutir dúvidas relacionadas ao Aspose.Page?
R: Visite os [fóruns do Aspose.Page](https://forum.aspose.com/c/page/39) para suporte da comunidade e discussões.

---

**Última Atualização:** 2026-06-25  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como Criar Documento PostScript com Aspose.Page para .NET](/page/net/document-creation/create-postscript-document/)
- [Salvar arquivo PostScript com Transformações Aspose.Page (.NET)](/page/net/canvas-manipulation/transformationsps/)
- [Criar documento postscript .net – Adicionar Retângulo com Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}