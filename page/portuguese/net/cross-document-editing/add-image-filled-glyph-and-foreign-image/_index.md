---
date: 2026-01-07
description: Aprenda como criar documentos XPS .NET usando Aspose.Page. Este guia
  mostra como adicionar glifos preenchidos com imagens e imagens externas para visualizações
  de documentos mais ricas.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Criar documento XPS .NET com Aspose.Page – Glifo preenchido com imagem e imagem
  estrangeira
url: /pt/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar XPS document .NET com Aspose.Page – Glifo preenchido com imagem e imagem externa

## Introdução

Se você precisa **criar XPS document .NET** aplicações que pareçam refinadas e profissionais, o Aspose.Page fornece as ferramentas para incorporar imagens diretamente em glifos e reutilizar recursos gráficos entre documentos. Neste tutorial, vamos percorrer a criação de dois arquivos XPS, preenchendo glifos com um *image brush* e, em seguida, reutilizando esse brush em um segundo documento. Ao final, você entenderá por que essa abordagem economiza memória, simplifica a estilização e abre possibilidades criativas para relatórios, faturas ou qualquer conteúdo imprimível.

## Respostas rápidas
- **O que este tutorial cobre?** Adição de glifos preenchidos com imagem e reutilização deles em documentos XPS com Aspose.Page para .NET.  
- **Qual palavra‑chave principal é alvo?** `create xps document .net`.  
- **Pré‑requisitos?** Ambiente de desenvolvimento .NET, Aspose.Page para .NET e uma pasta para seus arquivos XPS.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um protótipo funcional.  
- **Posso usar outros formatos de imagem?** Sim – qualquer formato suportado por `System.Drawing.Image` do .NET.

## Pré‑requisitos

Antes de mergulhar no código, certifique‑se de que você tem o seguinte pronto:

- **Aspose.Page for .NET** – baixe a biblioteca mais recente [aqui](https://releases.aspose.com/page/net/).  
- **Ambiente de desenvolvimento** – Visual Studio 2022 (ou qualquer IDE que suporte .NET 6+).  
- **Document Directory** – crie uma pasta na sua máquina que armazenará as imagens de entrada e os arquivos XPS gerados; nos trechos de código, nos referiremos a ela como **Your Document Directory**.

## Importar Namespaces

Comece importando os namespaces necessários para trabalhar com objetos XPS e utilitários de desenho.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Guia passo a passo

### Etapa 1: Criar o primeiro documento XPS

Iniciamos instanciando um documento XPS vazio que hospedará o glifo preenchido com imagem.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Etapa 2: Adicionar glifos ao primeiro documento

Em seguida, adicione um glifo (um caractere de texto) que será preenchido posteriormente com um *image brush*.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Etapa 3: Preencher glifos com um *Image Brush*

Aqui criamos um `ImageBrush` a partir de um arquivo TIFF localizado em nosso diretório de dados e o aplicamos ao glifo. O brush é configurado para modo *tile* para que a imagem se repita caso a área do glifo exceda o tamanho da imagem.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Etapa 4: Criar o segundo documento XPS

Agora criamos um segundo documento XPS que reutilizará o estilo de glifo e o *image brush* do primeiro.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Etapa 5: Adicionar glifos com a fonte do primeiro documento

Adicionamos um glifo ao segundo documento, reutilizando exatamente o objeto de fonte do primeiro documento. Isso garante consistência visual entre ambos os arquivos.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Etapa 6: Criar um *Image Brush* a partir do preenchimento do primeiro documento

Em vez de carregar a imagem novamente, clonamos o brush de `glyphs1` e o atribuímos a `glyphs2`. Isso demonstra como você pode **create XPS document .NET** fluxos de trabalho que compartilham recursos de forma eficiente.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Etapa 7: Salvar os documentos

Por fim, persista ambos os arquivos XPS no disco. Agora você pode abri‑los com qualquer visualizador XPS para ver o efeito de glifo preenchido com imagem.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Por que usar glifos preenchidos com imagem ao criar XPS document .NET?

- **Impacto visual** – Transforme texto simples em elementos ricos em gráficos sem rasterizar a página inteira.  
- **Reuso de recursos** – Compartilhe brushes e fontes entre vários documentos, reduzindo o consumo de memória.  
- **Flexibilidade** – Aplique *tile*, *stretch* ou rotação ao *image brush* para obter padrões personalizados ou identidade visual.

## Problemas comuns e dicas

- **Erros de caminho de arquivo** – Certifique‑se de que `dataDir` termina com um separador de caminho (`\` ou `/`) adequado ao seu SO.  
- **Formatos de imagem não suportados** – Aspose.Page funciona melhor com TIFF, PNG e JPEG. Converta outros formatos antes do uso.  
- **TileMode não aplicado** – Verifique se você faz cast para `XpsImageBrush` antes de definir `TileMode`; caso contrário, a propriedade será ignorada.

## Perguntas frequentes

### Q1: Posso usar diferentes formatos de imagem para preencher glifos?

**A:** Sim, Aspose.Page suporta TIFF, PNG, JPEG, BMP e GIF. Basta fornecer a extensão correta no chamado `CreateImageBrush`.

### Q2: Como posso personalizar ainda mais a aparência dos glifos?

**A:** Explore propriedades adicionais em `XpsGlyphs` como `Opacity`, `RenderTransform` e `Stroke` para ajustar a renderização.

### Q3: O Aspose.Page é adequado para lidar com grandes volumes de documentos?

**A:** Absolutamente. A biblioteca é otimizada para cenários de alto desempenho e pode processar milhares de arquivos XPS em trabalhos em lote.

### Q4: Posso aplicar estilos diferentes a glifos individuais?

**A:** Sim. Cada instância de `XpsGlyphs` pode ter seu próprio preenchimento, contorno e transformação, oferecendo controle granular.

### Q5: Quais são os benefícios de usar Aspose.Page em comparação com outras ferramentas de processamento de documentos?

**A:** Aspose.Page oferece uma API completa, livre de licenças, para criação, manipulação e conversão de XPS, com documentação extensa e suporte 24/7.

---

**Última atualização:** 2026-01-07  
**Testado com:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}