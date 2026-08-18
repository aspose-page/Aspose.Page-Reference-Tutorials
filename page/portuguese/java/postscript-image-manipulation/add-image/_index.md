---
date: 2026-02-15
description: Aprenda a criar documentos PostScript em Java e gerar arquivos de documentos
  PostScript com translação e rotação de imagens usando o Aspose.Page para Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Criar PostScript em Java – Adicionar Imagem no PostScript Java
url: /pt/java/postscript-image-manipulation/add-image/
weight: 10
---

Last Updated:** 2026-02-15" keep date.

"**Tested With:** Aspose.Page for Java 23.11" keep.

"**Author:** Aspose" keep.

Then closing shortcodes.

Also need to keep the final backtop button shortcode.

Make sure to keep all shortcodes exactly.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar PostScript Java – Adicionar Imagem em Java PostScript

## Introdução
Neste tutorial, você aprenderá como **create postscript java** documentos e incorporar imagens usando a biblioteca Aspose.Page for Java. Vamos percorrer cada passo, desde a inicialização de um novo arquivo PostScript até a aplicação de transformações **translate and rotate image**. Ao final, você será capaz de gerar arquivos PostScript programaticamente e controlar a colocação de imagens com precisão de pixel — perfeito para relatórios automatizados, fluxos de impressão ou qualquer cenário em que você precise **generate postscript document** a partir do Java.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Page for Java  
- **Posso adicionar várias imagens?** Sim – repita as etapas de transformação e desenho  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença é necessária para produção  
- **Qual versão do Java é suportada?** Java 8 e posteriores  
- **A rotação de imagem é suportada?** Absolutamente – use `AffineTransform.rotate()`  

## O que é create postscript java?
Uma operação **create postscript java** produz um arquivo de descrição de página PostScript que codifica texto, gráficos vetoriais e imagens raster. Com Aspose.Page você pode construir esses arquivos diretamente a partir de código Java, oferecendo controle programático total sobre layout, dimensionamento e rotação sem precisar de um interpretador PostScript separado.

## Por que usar Aspose.Page para manipulação de imagens?
- **API de alto nível:** Abstrai comandos de PostScript de baixo nível em métodos Java simples.  
- **Multiplataforma:** Executa em qualquer SO que suporte Java.  
- **Controle total do estado gráfico:** Salvar, restaurar, traduzir, escalar e girar gráficos à vontade.  
- **Sem dependências externas:** Lida com carregamento de imagens, conversão de formato e incorporação internamente.

## Pré-requisitos
Antes de mergulharmos no código, certifique‑se de que você tem:

- Java Development Kit (JDK) instalado no seu sistema.  
- Biblioteca Aspose.Page for Java. Você pode baixá‑la [aqui](https://releases.aspose.com/page/java/).  
- Um entendimento básico de programação Java.  

## Importar Pacotes
Para começar, importe os pacotes necessários em seu projeto Java. Use o trecho de código a seguir como referência:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Etapa 1: Escrever Salvamento de Gráficos
O primeiro passo envolve escrever o salvamento de gráficos no documento. Isso garante que quaisquer transformações ou modificações feitas posteriormente possam ser revertidas, se necessário.

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

## Etapa 2: Traduzir e Transformar (translate and rotate image)
Em seguida, traduza o documento e crie um objeto `BufferedImage` a partir do arquivo de imagem. Aplique uma série de transformações como dimensionamento e rotação usando `AffineTransform`. É aqui que a operação **translate and rotate image** ocorre.

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

## Etapa 3: Adicionar Imagem ao Documento
Agora, adicione a imagem transformada ao documento.

```java
document.drawImage(image, transform, null);
```

## Etapa 4: Escrever Restauração de Gráficos
Após adicionar a imagem, escreva a restauração de gráficos para finalizar as alterações feitas.

```java
document.writeGraphicsRestore();
```

## Etapa 5: Fechar Página Atual e Salvar
Feche a página atual e salve o documento.

```java
document.closePage();
document.save();
```

Você pode repetir essas etapas para adicionar várias imagens ou personalizar as transformações conforme suas necessidades.

## Problemas Comuns e Soluções
- **FileNotFoundException:** Certifique‑se de que o caminho `dataDir` termina com um separador de arquivos (`/` ou `\\`) e que o nome do arquivo de imagem corresponde exatamente.  
- **ImageIO.read returns null:** Verifique se o formato da imagem é suportado (ex.: JPEG, PNG).  
- **Ângulo de rotação incorreto:** `AffineTransform.rotate` espera radianos. Converta graus para radianos (`Math.toRadians(degrees)`) se necessário.  

## Perguntas Frequentes

**P: Posso usar Aspose.Page for Java com outras linguagens de programação?**  
R: Aspose.Page suporta principalmente Java, mas também há versões disponíveis para outras linguagens de programação.

**P: Existe um teste gratuito disponível para Aspose.Page for Java?**  
R: Sim, você pode acessar o teste gratuito [aqui](https://releases.aspose.com/).

**P: Como posso obter uma licença temporária para Aspose.Page for Java?**  
R: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**P: Onde posso encontrar suporte da comunidade e discussões relacionadas ao Aspose.Page for Java?**  
R: Visite o [Aspose.Page Forum](https://forum.aspose.com/c/page/39) para suporte da comunidade.

**P: Existem recursos adicionais para comprar Aspose.Page for Java?**  
R: Você pode comprar a biblioteca [aqui](https://purchase.aspose.com/buy).

## Conclusão
Parabéns! Você aprendeu com sucesso como **create postscript java** documentos e incorporar imagens usando Aspose.Page for Java. Explore a [documentação](https://reference.aspose.com/page/java/) para recursos e funcionalidades avançadas, como gráficos vetoriais, renderização de texto e tamanhos de página personalizados.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}