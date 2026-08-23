---
date: 2026-08-23
description: Aprenda como usar a manipulação de imagens aspose.page java para incorporar
  e girar imagens em arquivos PostScript com exemplos claros em Java.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Adicionar imagem em PostScript Java
og_description: Aprenda como usar a manipulação de imagens aspose.page java para incorporar
  e girar imagens em arquivos PostScript, com exemplos de código Java passo a passo.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Como usar a manipulação de imagens aspose.page java para adicionar imagem
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Como usar a manipulação de imagens aspose.page java para adicionar imagem
url: /pt/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar aspose.page manipulação de imagem java para adicionar imagem

## Introdução
Neste tutorial você aprenderá a **use aspose.page image manipulation java** para criar arquivos PostScript, incorporar imagens raster e aplicar transformações de translação‑e‑rotação. Ao final do guia, você será capaz de gerar saída PostScript pixel‑perfect a partir do Java — ideal para relatórios automatizados, pipelines de impressão ou qualquer fluxo de trabalho que exija posicionamento preciso de imagens dentro de um documento PostScript.

## Respostas rápidas
- **Qual biblioteca é necessária?** Aspose.Page for Java  
- **Posso adicionar várias imagens?** Sim – repita as etapas de transformação e desenho para cada imagem  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença é necessária para produção  
- **Qual versão do Java é suportada?** Java 8 e posteriores  
- **A rotação de imagem é suportada?** Absolutamente – use `AffineTransform.rotate()`

## O que é aspose.page manipulação de imagem java?
`aspose.page image manipulation java` é a API Aspose.Page que permite construir, editar e renderizar documentos PostScript programaticamente a partir de código Java, incluindo controle total sobre posicionamento, dimensionamento e rotação de imagens. Com essa API você evita a sintaxe de baixo nível do PostScript e deixa que a biblioteca trate a conversão de formatos e incorporação internamente.

## Por que usar aspose.page para manipulação de imagem?
Aspose.Page fornece **50+ image formats** (incluindo JPEG, PNG, BMP, TIFF) e pode incorporá‑los ao PostScript sem carregar todo o documento na memória, permitindo o processamento de arquivos com centenas de páginas enquanto mantém o uso de memória abaixo de 100 MB em um servidor típico. A API de alto nível abstrai comandos complexos do PostScript, de modo que você escreve código Java conciso em vez de operadores PS brutos.

## Pré-requisitos
- Java Development Kit (JDK) 8 ou mais recente instalado.  
- Biblioteca Aspose.Page para Java – faça o download **[página de download do Aspose.Page para Java](https://releases.aspose.com/page/java/)**.  
- Familiaridade básica com a sintaxe Java e programação orientada a objetos.

## O que é criar postscript java?
Criar um arquivo PostScript a partir do Java significa gerar programaticamente um documento `.ps` que descreve o layout da página, gráficos vetoriais e imagens raster usando a linguagem PostScript. Aspose.Page traduz suas chamadas Java em instruções PostScript válidas, permitindo produzir arquivos prontos para impressão sem um interpretador PostScript separado.

## Como adicionar uma imagem com tradução e rotação passo a passo

Carregue sua imagem, aplique um `AffineTransform` e desenhe-a na página. As etapas a seguir descrevem a sequência exata que você deve seguir.

### Etapa 1: salvar estado gráfico
Salvar o estado gráfico isola suas transformações para que você possa reverter mais tarde. Isso equivale ao operador `gsave` no PostScript puro.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Etapa 2: traduzir e transformar (traduzir e girar imagem)
Primeiro, crie um `BufferedImage` a partir do arquivo de origem, depois construa um `AffineTransform` que translada a imagem para as coordenadas desejadas e a gira ao redor de seu centro. `AffineTransform.rotate` espera um ângulo em radianos, portanto converta graus com `Math.toRadians(degrees)`.

**AffineTransform** é uma classe Java que representa uma transformação afim 2‑D, como translação, rotação, escala ou cisalhamento.  
**BufferedImage** é uma classe Java que armazena uma imagem na memória como uma raster de pixels.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Etapa 3: adicionar imagem ao documento
Depois de configurar a transformação, desenhe a imagem na página atual. A biblioteca converte automaticamente o `BufferedImage` em um fluxo de imagem PostScript adequado.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Etapa 4: restaurar estado gráfico
Chamar restore (`grestore`) devolve o estado gráfico ao que era antes do save, garantindo que comandos de desenho subsequentes não sejam afetados pela transformação anterior.

```java
document.drawImage(image, transform, null);
```

### Etapa 5: fechar página atual e salvar
Finalize a página, feche o documento e grave o arquivo de saída no disco.

```java
document.writeGraphicsRestore();
```

Você pode repetir a sequência acima para incorporar imagens adicionais, ajustando as coordenadas de translação e o ângulo de rotação a cada vez.

## Problemas comuns e soluções
- **FileNotFoundException:** Verifique se o `dataDir` termina com um separador de arquivos (`/` ou `\\`) e se o nome do arquivo de imagem corresponde exatamente.  
- **ImageIO.read returns null:** Certifique-se de que o formato da imagem está na lista de suportados (JPEG, PNG, BMP, GIF, TIFF).  
- **Ângulo de rotação incorreto:** `AffineTransform.rotate` funciona com radianos; use `Math.toRadians(degrees)` para converter de graus.  
- **Picos de memória em páginas grandes:** Use `Document.save` com `saveOptions.setCompress(true)` para reduzir o uso de memória.

## Perguntas frequentes

**Q: Posso usar Aspose.Page para Java com outras linguagens de programação?**  
A: A biblioteca principal é apenas para Java, mas a Aspose fornece APIs equivalentes para .NET, C++ e Python, cada uma adaptada à sua plataforma.

**Q: Existe um teste gratuito disponível para Aspose.Page para Java?**  
A: Sim, você pode acessar o teste gratuito **[página de teste gratuito do Aspose.Page](https://releases.aspose.com/)**.

**Q: Como posso obter uma licença temporária para Aspose.Page para Java?**  
A: Você pode obter uma licença temporária **[página de solicitação de licença temporária](https://purchase.aspose.com/temporary-license/)**.

**Q: Onde posso encontrar suporte da comunidade e discussões relacionadas ao Aspose.Page para Java?**  
A: Visite o **[Fórum Aspose.Page](https://forum.aspose.com/c/page/39)** para assistência da comunidade.

**Q: Existem recursos adicionais para comprar Aspose.Page para Java?**  
A: Você pode comprar a biblioteca **[página de compra do Aspose.Page](https://purchase.aspose.com/buy)**.

## Conclusão
Agora você tem um exemplo completo, de ponta a ponta, de **aspose.page image manipulation java** que cria um arquivo PostScript, traduz e gira uma imagem e salva o resultado. Explore a **[documentação](https://reference.aspose.com/page/java/)** completa para descobrir recursos avançados como gráficos vetoriais, tamanhos de página personalizados e renderização de texto.

---

**Last Updated:** 2026-08-23  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  








```java
document.closePage();
document.save();
```

## Tutoriais Relacionados

- [Como converter PostScript para PDF usando a API Aspose.Page Java](/page/java/postscript-conversion/to-pdf/)
- [Como adicionar gradiente: gradiente diagonal em PostScript Java usando Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Como adicionar padrão de hachura em PostScript Java com Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}