---
date: 2025-12-09
description: Aprenda a criar documentos PostScript em Java e a transladar e girar
  imagens usando Aspose.Page para uma manipulação de imagens sem costura.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Criar Documento PostScript em Java – Adicionar Imagem no PostScript Java
url: /pt/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Documento PostScript em Java – Adicionar Imagem em PostScript Java

## Introdução
Neste tutorial, você aprenderá como **criar um documento PostScript Java** e incorporar imagens usando a biblioteca Aspose.Page for Java. Percorreremos cada passo, desde a configuração do documento até a aplicação de transformações como **transladar e girar a imagem**. Ao final, você será capaz de gerar arquivos PostScript ricos programaticamente e personalizar a posição das imagens para atender exatamente às necessidades do seu layout.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Page for Java  
- **Posso adicionar várias imagens?** Sim – repita as etapas de transformação e desenho  
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença é necessária para produção  
- **Qual versão do Java é suportada?** Java 8 ou superior  
- **A rotação de imagem é suportada?** Absolutamente – use `AffineTransform.rotate()`  

## O que é criar um documento PostScript em Java?
Um documento PostScript é um arquivo de linguagem de descrição de página que descreve texto, gráficos e imagens. Usando Aspose.Page, você pode gerar esses arquivos programaticamente em Java, tendo controle total sobre layout, estado gráfico e manipulação de imagens sem precisar de um interpretador PostScript.

## Por que usar Aspose.Page para manipulação de imagens?
- **API de alto nível:** Simplifica comandos PostScript complexos.  
- **Multiplataforma:** Funciona em qualquer SO que suporte Java.  
- **Controle total do estado gráfico:** Salve, restaure, translade, escale e gire gráficos com facilidade.  
- **Sem dependências externas:** Lida com carregamento e conversão de imagens internamente.

## Pré-requisitos
Antes de mergulharmos no código, certifique-se de que você tem:

- Java Development Kit (JDK) instalado no seu sistema.  
- Biblioteca Aspose.Page for Java. Você pode baixá‑la [aqui](https://releases.aspose.com/page/java/).  
- Um entendimento básico de programação Java.  

## Importar Pacotes
Para começar, importe os pacotes necessários no seu projeto Java. Use o trecho de código a seguir como referência:

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
O primeiro passo consiste em escrever o salvamento de gráficos no documento. Isso garante que quaisquer transformações ou modificações feitas posteriormente possam ser revertidas, se necessário.

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

## Etapa 2: Translacao e Transformação (transladar e girar imagem)
Em seguida, translade o documento e crie um objeto `BufferedImage` a partir do arquivo de imagem. Aplique uma série de transformações, como escala e rotação, usando `AffineTransform`. É aqui que ocorre a operação de **transladar e girar a imagem**.

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
- **FileNotFoundException:** Verifique se o caminho `dataDir` termina com um separador de arquivos (`/` ou `\\`) e se o nome do arquivo de imagem corresponde exatamente.  
- **ImageIO.read returns null:** Confirme se o formato da imagem é suportado (por exemplo, JPEG, PNG).  
- **Ângulo de rotação incorreto:** `AffineTransform.rotate` espera radianos. Converta graus para radianos (`Math.toRadians(degrees)`) se necessário.  

## Perguntas Frequentes

**Q: Posso usar Aspose.Page for Java com outras linguagens de programação?**  
A: Aspose.Page suporta principalmente Java, mas há versões disponíveis para outras linguagens de programação também.

**Q: Existe uma versão de teste gratuita do Aspose.Page for Java?**  
A: Sim, você pode acessar o teste gratuito [aqui](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para Aspose.Page for Java?**  
A: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso encontrar suporte da comunidade e discussões relacionadas ao Aspose.Page for Java?**  
A: Visite o [Aspose.Page Forum](https://forum.aspose.com/c/page/39) para suporte da comunidade.

**Q: Existem recursos adicionais para adquirir o Aspose.Page for Java?**  
A: Você pode comprar a biblioteca [aqui](https://purchase.aspose.com/buy).

## Conclusão
Parabéns! Você aprendeu com sucesso como **criar um documento PostScript Java** e incorporar imagens usando Aspose.Page for Java. Explore a [documentação](https://reference.aspose.com/page/java/) para recursos e funcionalidades avançadas, como gráficos vetoriais, renderização de texto e tamanhos de página personalizados.

---

**Última atualização:** 2025-12-09  
**Testado com:** Aspose.Page for Java 23.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}