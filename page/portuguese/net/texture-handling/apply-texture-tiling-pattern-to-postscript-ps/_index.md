---
date: 2026-03-26
description: Aprenda a criar documentos PostScript .NET com padrões de ladrilhos de
  textura usando o Aspose.Page. Siga nosso guia passo a passo para adicionar texturas
  ricas aos seus arquivos PS.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Criar documento PostScript .NET com ladrilhamento de textura
url: /pt/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar documento PostScript .NET com padrão de textura em mosaico

## Como criar documento PostScript .NET com padrão de textura em mosaico

Neste tutorial você aprenderá a **criar documento PostScript .NET** e enriquecê‑lo com um padrão de textura em mosaico usando a biblioteca Aspose.Page. Percorreremos cada passo, desde a configuração do projeto até o preenchimento e contorno de texto com o pincel de textura, para que você possa produzir arquivos PS visualmente atraentes em minutos.

## Respostas rápidas
- **Qual biblioteca é usada?** Aspose.Page for .NET  
- **Posso usar .NET Core?** Sim, a biblioteca suporta .NET Core e .NET 5/6  
- **Quais formatos de imagem funcionam para a textura?** Qualquer formato suportado por System.Drawing (BMP, PNG, JPEG, etc.)  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um exemplo básico  
- **Preciso de licença?** Um teste gratuito funciona para testes; uma licença é necessária para produção  

## Pré‑requisitos

- [Visual Studio](https://visualstudio.microsoft.com/) instalado na sua máquina.  
- Conhecimento básico de programação em C#.  
- Baixe e instale a [biblioteca Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Um arquivo de imagem para o padrão de textura (por exemplo, **TestTexture.bmp**).

## Importar namespaces

No seu arquivo C#, importe os namespaces necessários para que o compilador saiba onde encontrar os tipos que usaremos:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Etapa 1: Configurar diretório do documento

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Substitua **Your Document Directory** pela pasta onde você deseja que o arquivo PS gerado seja salvo.

## Etapa 2: Criar fluxo de saída para o documento PS

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Este bloco abre um fluxo de arquivo, configura o tamanho da página (A4 por padrão) e cria uma nova instância **PsDocument** que usaremos para desenhar.

## Etapa 3: Aplicar padrão de textura em mosaico

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Aqui carregamos o bitmap, o encapsulamos em um **TextureBrush**, opcionalmente esticamos horizontalmente e instruímos o **PsDocument** a usar esse pincel nas operações de desenho subsequentes.

## Etapa 4: Criar caminho retangular e preencher

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Um retângulo simples é definido e preenchido com o pincel de textura que configuramos anteriormente.

## Etapa 5: Definir contorno e desenhar

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Recuperamos a tinta atual (o pincel de textura), criamos uma caneta vermelha para o contorno e desenhamos a borda do retângulo.

## Etapa 6: Preencher e contornar texto com padrão de textura

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Esta etapa demonstra a capacidade de **preencher e contornar texto**: os caracteres “ABC” são preenchidos com o pincel de textura e depois contornados, gerando um efeito visual marcante.

## Etapa 7: Salvar e fechar o documento

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Fechar a página finaliza os comandos de desenho, e `Save()` grava o arquivo PostScript no disco.

## Problemas comuns e soluções

- **A textura aparece esticada incorretamente** – Ajuste os valores da `Matrix` para controlar a escala nas direções X/Y.  
- **Imagem não encontrada** – Verifique se `dataDir` aponta para a pasta correta e se o nome do arquivo corresponde exatamente, incluindo maiúsculas/minúsculas.  
- **Cores parecem erradas** – Lembre‑se de que o PostScript usa um espaço de cor independente de dispositivo; assegure‑se de usar objetos `Color` que mapeiem corretamente.

## Perguntas frequentes

**Q:** Posso usar outros formatos de imagem para o padrão de textura?  
**A:** Sim, qualquer formato suportado por `System.Drawing.Bitmap` (BMP, PNG, JPEG, GIF, etc.) funciona.

**Q:** O Aspose.Page é compatível com .NET Core?  
**A:** Absolutamente. A biblioteca funciona em .NET Framework, .NET Core e .NET 5/6.

**Q:** Como altero o tamanho do retângulo texturizado?  
**A:** Modifique os valores de `RectangleF` na etapa de criação do retângulo (por exemplo, `new RectangleF(0, 0, 300, 150)`).

**Q:** Posso aplicar múltiplos padrões de textura em um único documento?  
**A:** Sim. Basta criar um novo `TextureBrush` com uma imagem diferente e chamar `SetPaint` novamente antes de desenhar a próxima forma ou texto.

**Q:** Onde posso encontrar mais exemplos e referência da API?  
**A:** Visite o [Aspose.Page Forum](https://forum.aspose.com/c/page/39) para ajuda da comunidade e a [documentação oficial](https://reference.aspose.com/page/net/) para uso detalhado da API.

## Conclusão

Agora você sabe como **criar documento PostScript .NET** e aplicar um padrão de textura em mosaico, inclusive como **preencher e contornar texto** com essa textura. Experimente diferentes imagens, matrizes de escala e primitivas de desenho para produzir arquivos PS personalizados para relatórios, folhetos ou qualquer saída gráfica pesada.

---

**Última atualização:** 2026-03-26  
**Testado com:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}