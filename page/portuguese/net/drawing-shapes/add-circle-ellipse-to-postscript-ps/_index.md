---
date: 2026-07-19
description: Aprenda o tutorial Aspose.Page postscript para adicionar elipses circulares
  a arquivos PostScript (PS) usando Aspose.Page para .NET – como gerar saída postscript
  rapidamente.
keywords:
- asp page postscript tutorial
- how to generate postscript
- write postscript output
lastmod: 2026-07-19
linktitle: Adicionar Elipse Circular ao PostScript (PS)
og_description: tutorial Aspose.Page postscript que mostra como gerar saída postscript
  adicionando elipses circulares com Aspose.Page para .NET. Siga o guia passo a passo
  para integração rápida.
og_image_alt: 'Guide: Add circle ellipse to PostScript using Aspose.Page .NET'
og_title: tutorial Aspose.Page postscript – Adicionar Elipse Circular (PS)
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn the asp page postscript tutorial for adding circle ellipses to
    PostScript (PS) files using Aspose.Page for .NET – how to generate postscript
    output quickly.
  headline: asp page postscript tutorial – Add Circle Ellipse (PS)
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily focuses on PostScript, but Aspose provides other
      libraries for various formats. Check the [Aspose documentation](https://reference.aspose.com/page/net/)
      for a full list.
    question: Can I use Aspose.Page for .NET with other document formats?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community discussions and support.
    question: Where can I find additional support and community discussions?
  - answer: Yes, you can access the [free trial](https://releases.aspose.com/) to
      explore the features of Aspose.Page for .NET.
    question: Is there a free trial available for Aspose.Page for .NET?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  - answer: Purchase Aspose.Page for .NET from the [buy page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- Aspose.Page
- .NET drawing
- circle ellipse
title: tutorial Aspose.Page postscript – Adicionar Elipse Circular (PS)
url: /pt/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# tutorial de asp page postscript – Adicionar Elipse Circular (PS)

## Introdução

Neste **asp page postscript tutorial** você descobrirá como adicionar elipses circulares perfeitas a um documento PostScript (PS) usando a biblioteca Aspose.Page para .NET. Seja gerando desenhos técnicos, gráficos vetoriais ou relatórios personalizados, o Aspose.Page permite que você escreva saída PostScript sem lidar com a sintaxe de PS de baixo nível. Vamos percorrer cada passo, desde a configuração do ambiente até a renderização de duas elipses — uma preenchida e outra contornada — para que você possa integrar essa capacidade em suas próprias aplicações imediatamente.

## Respostas Rápidas

- **O que este tutorial cobre?** Adicionar elipses circulares preenchidas e contornadas a um arquivo PS com Aspose.Page para .NET.  
- **Quantos passos de código são necessários?** Oito passos concisos, cada um ilustrado com um fragmento de código pronto‑para‑executar.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET 5, .NET 6, .NET Core 3.1 e .NET Framework 4.6+.  
- **Posso reutilizar o mesmo caminho gráfico?** Sim — crie um `GraphicsPath` uma vez e desenhe ou preencha‑o várias vezes.

## O que é o asp page postscript tutorial?

O **asp page postscript tutorial** é um guia passo a passo que demonstra como gerar conteúdo PostScript programaticamente com Aspose.Page para .NET. Ele foca em código prático, casos de uso do mundo real e dicas de boas práticas para que você possa produzir arquivos PS confiáveis rapidamente.

## Por que usar Aspose.Page para geração de PostScript?

O Aspose.Page suporta **mais de 30 formatos de saída** (incluindo PDF, SVG e EPS) e pode renderizar **documentos com centenas de páginas** sem carregar o arquivo inteiro na memória, proporcionando uma **redução da pegada de memória de até 70 %** em comparação com a construção manual de strings PS. Sua API de alto nível elimina a necessidade de escrever comandos PS brutos, reduzindo o tempo de desenvolvimento em **80 %** em média.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos em vigor:

1. Biblioteca Aspose.Page para .NET: Baixe e instale a biblioteca Aspose.Page para .NET a partir de [here](https://releases.aspose.com/page/net/).  
2. Ambiente de Desenvolvimento: Certifique‑se de que você tem um ambiente de desenvolvimento .NET configurado em sua máquina.

Agora, vamos começar com o guia passo a passo.

## Importar Namespaces

As diretivas `using` trazem as classes do Aspose.Page para o escopo, permitindo que você trabalhe diretamente com gráficos, cores e documentos PS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Agora, vamos dividir o exemplo fornecido em várias etapas para guiá‑lo através do processo de adição de elipses circulares a um documento PostScript.

## Como definir o diretório do documento?

Para informar ao programa onde armazenar o arquivo PS gerado, você precisa especificar um caminho de pasta que a aplicação possa gravar. Use uma variável como `dataDir` e atribua a ela um caminho completo ou relativo; esse caminho será combinado com o nome do arquivo de saída mais tarde no código.  
> **Dica profissional:** Use `Path.Combine(Environment.CurrentDirectory, "output")` para construir um caminho multiplataforma e evitar separadores codificados.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Como criar o fluxo de saída para o documento PostScript?

Criar um fluxo de saída abre um manipulador de arquivo que o motor Aspose.Page escreverá os dados PostScript. Ao usar um `FileStream` com `FileMode.Create`, o arquivo é criado novamente a cada execução, sobrescrevendo qualquer versão anterior. Esse fluxo é então passado ao construtor `PsDocument`.

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

## Como configurar opções de salvamento e inicializar um documento PS?

`PsSaveOptions` permite especificar o tamanho da página, resolução e outras configurações de renderização. Aqui usamos o tamanho de página padrão A4 e um documento de página única. `PsDocument` representa o documento PostScript que está sendo criado; ele recebe o fluxo de saída e as opções de salvamento, e gerencia os eventos do ciclo de vida da página.

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Como criar um caminho gráfico para a primeira elipse?

`GraphicsPath` representa uma forma vetorial que pode ser desenhada ou preenchida em uma página PostScript. O construtor recebe as coordenadas X/Y do canto superior esquerdo, seguidas da largura e altura, permitindo definir o tamanho e a posição exatos da elipse na página.

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

## Como definir a pintura e preencher a primeira elipse?

`SolidBrush` define uma cor de preenchimento sólido para operações de desenho. Ao criar um `SolidBrush` com um `Color` específico e passá‑lo para `graphics.FillPath`, a elipse é renderizada com essa cor sólida.

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

## Como criar um caminho gráfico para a segunda elipse?

Um segundo `GraphicsPath` é definido para ilustrar como você pode desenhar um contorno (stroke) separado de um preenchimento. O mesmo padrão de construtor é usado, mas você pode alterar as dimensões do retângulo para produzir uma elipse de tamanho diferente.

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

## Como definir o traço e desenhar a segunda elipse?

`SolidPen` especifica a cor e a largura para traçar formas. Ao fornecer um `SolidPen` para `graphics.DrawPath`, o contorno da elipse é desenhado sem preenchimento, proporcionando uma forma contornada limpa.

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

## Como fechar a página atual e salvar o documento?

Depois que todos os comandos de desenho são emitidos, você deve fechar a página ativa com `document.ClosePage()` para finalizar seu conteúdo. Por fim, chamar `document.Save()` grava os dados PostScript acumulados no fluxo previamente aberto, produzindo o arquivo de saída no disco.

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

## Problemas Comuns e Soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| **Arquivo não encontrado** | Caminho de diretório incorreto | Verifique se a pasta existe ou crie‑a com `Directory.CreateDirectory`. |
| **Saída em branco** | Esquecer de chamar `document.ClosePage()` | Certifique‑se de fechar a página antes de salvar. |
| **Cores incorretas** | Usar `Color.FromArgb` com ordem errada | Use `Color.FromRgb(red, green, blue)` para clareza. |
| **Desempenho reduzido em arquivos grandes** | Carregar o documento inteiro na memória | Use `PsSaveOptions` com `EnableMemorySaving = true` para transmitir páginas grandes. |

## Perguntas Frequentes

**Q: Posso usar Aspose.Page para .NET com outros formatos de documento?**  
A: O Aspose.Page foca principalmente em PostScript, mas a Aspose fornece outras bibliotecas para vários formatos. Consulte a [documentação da Aspose](https://reference.aspose.com/page/net/) para a lista completa.

**Q: Onde posso encontrar suporte adicional e discussões da comunidade?**  
A: Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para discussões da comunidade e suporte.

**Q: Existe um teste gratuito disponível para Aspose.Page para .NET?**  
A: Sim, você pode acessar o [teste gratuito](https://releases.aspose.com/) para explorar os recursos do Aspose.Page para .NET.

**Q: Como posso obter uma licença temporária para Aspose.Page?**  
A: Obtenha uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/) para fins de teste e avaliação.

**Q: Onde posso comprar Aspose.Page para .NET?**  
A: Compre o Aspose.Page para .NET na [página de compra](https://purchase.aspose.com/buy).

## Conclusão

Parabéns! Você concluiu com sucesso o **asp page postscript tutorial** para adicionar elipses circulares a documentos PostScript usando Aspose.Page para .NET. Seguindo os oito passos claros, você agora pode gerar arquivos PS de alta qualidade com elipses preenchidas e contornadas, prontas para serem integradas a motores de relatórios, exportadores CAD ou qualquer pipeline gráfico personalizado.

---

**Última atualização:** 2026-07-19  
**Testado com:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Aspose.Page .NET – Desenhando Formas](/page/net/drawing-shapes/)
- [Criar documento postscript .net – Adicionar Retângulo com Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Como Criar Documento PostScript com Aspose.Page para .NET](/page/net/document-creation/create-postscript-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}