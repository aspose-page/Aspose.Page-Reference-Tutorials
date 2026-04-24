---
date: 2026-01-05
description: Aprenda como adicionar caminho de recorte no PostScript usando Aspose.Page
  para .NET – guia passo a passo com técnicas de definir pincel de pintura e desenhar
  retângulo tracejado.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Adicionar caminho de recorte ao PS com Aspose.Page para .NET
url: /pt/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Clipping Path ao PS com Aspose.Page para .NET

## Introdução

Neste tutorial abrangente, você descobrirá como **adicionar clipping path** a um documento PostScript (PS) usando Aspose.Page para .NET. Vamos percorrer cada etapa, mostrar como **definir o pincel de pintura** e demonstrar como **desenhar um retângulo tracejado** ao redor do conteúdo recortado. Ao final, você terá um arquivo PS totalmente funcional que ilustra o recorte por forma, tornando seus gráficos mais dinâmicos e profissionais.

## Respostas Rápidas
- **O que faz “adicionar clipping path”?** Ele restringe as operações de desenho a uma forma definida, ocultando tudo que estiver fora dessa forma.  
- **Qual biblioteca lida com clipping no .NET?** Aspose.Page para .NET fornece uma API rica para manipulação de PS/EPS.  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso mudar a cor do pincel?** Sim, use `SetPaint` com qualquer `SolidBrush` ou gradiente que preferir.  
- **É possível desenhar um retângulo tracejado?** Absolutamente – crie um `Pen` com `DashStyle.Dash` e use `Draw`.  

## O que é um clipping path no PostScript?
Um clipping path define a região visível dos comandos de desenho subsequentes. Qualquer coisa desenhada fora do caminho é ignorada, permitindo criar gráficos mascarados complexos sem alterar o conteúdo original.

## Por que usar Aspose.Page para clipping?
- **Sem dependências externas** – biblioteca .NET pura.  
- **Controle total** sobre o estado gráfico (save/restore, translate, rotate).  
- **Primitivas de desenho avançadas** como `SetPaint`, `Clip` e `Draw` com canetas e pincéis personalizáveis.  

## Pré‑requisitos

- Conhecimento básico de programação em C#.  
- Biblioteca Aspose.Page para .NET instalada – você pode baixá‑la [aqui](https://releases.aspose.com/page/net/).  
- Visual Studio ou qualquer IDE .NET de sua preferência.  

## Importar Namespaces

Primeiro, importe os namespaces necessários para a manipulação gráfica:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora vamos dividir o exemplo em etapas claras e numeradas.

### Etapa 1: Definir Diretório do Documento

Defina a pasta onde seus arquivos de origem e saída serão armazenados.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Etapa 2: Criar Stream de Saída para o Documento PostScript

Crie um stream gravável que conterá o arquivo PS gerado.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Etapa 3: Criar Opções de Salvamento

Instancie `PsSaveOptions` com as configurações padrão. Você pode personalizar mais tarde, se necessário.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Etapa 4: Criar um Novo Documento PS de 1 Página

Inicialize o objeto `PsDocument` que representa seu arquivo PS.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Etapa 5: Criar Caminho Gráfico a partir do Retângulo

Usaremos um retângulo como forma base que será recortada posteriormente.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Etapa 6: Recorte por Forma

Aqui nós **adicionamos clipping path** usando um círculo, **definimos o pincel de pintura** para azul e preenchemos o retângulo dentro da região recortada.

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

### Etapa 7: Deslocar o Estado Gráfico de Nível Superior e Desenhar Retângulo Tracejado

Após restaurar o estado anterior, movemos o cursor gráfico novamente, **desenhamos um retângulo tracejado** e aplicamos um traço azul.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Etapa 8: Fechar e Salvar o Documento

Finalize a página e grave o arquivo PS no disco.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Você adicionou com sucesso um **clipping path**, definiu um pincel de pintura personalizado e desenhou um retângulo tracejado ao redor dos seus gráficos usando Aspose.Page para .NET.

## Problemas Comuns e Soluções

- **Clipping não visível:** Certifique‑se de chamar `WriteGraphicsSave()` antes de traduzir e `WriteGraphicsRestore()` após o preenchimento.  
- **Cores incorretas:** Verifique se `SetPaint` é chamado após `Clip` e antes de `Fill`.  
- **Linhas tracejadas aparecem sólidas:** Garanta que o `DashStyle` da `Pen` esteja definido como `DashStyle.Dash` antes de `SetStroke`.  

## Perguntas Frequentes

### Q1: Posso usar Aspose.Page para .NET com outras linguagens de programação?
R: Aspose.Page foi projetado principalmente para aplicações .NET. Contudo, a Aspose oferece bibliotecas semelhantes para outras linguagens de programação.

### Q2: Onde encontro exemplos adicionais e documentação para Aspose.Page para .NET?
R: Você pode explorar mais exemplos e documentação detalhada na [documentação do Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: Existe uma avaliação gratuita disponível para Aspose.Page para .NET?
R: Sim, você pode acessar uma avaliação gratuita do Aspose.Page para .NET [aqui](https://releases.aspose.com/).

### Q4: Como obter uma licença temporária para Aspose.Page para .NET?
R: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Q5: Onde posso obter suporte ou discutir dúvidas relacionadas ao Aspose.Page?
R: Visite os [fóruns do Aspose.Page](https://forum.aspose.com/c/page/39) para suporte da comunidade e discussões.

---

**Última atualização:** 2026-01-05  
**Testado com:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}