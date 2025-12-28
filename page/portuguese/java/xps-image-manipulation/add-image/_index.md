---
date: 2025-12-28
description: Aprenda como adicionar imagens a documentos XPS em Java usando Aspose.Page.
  Este guia passo a passo mostra como inserir imagens de forma simples e aprimorar
  o processamento de documentos.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: Como adicionar imagem a documentos XPS em Java – Um guia simples com Aspose.Page
url: /pt/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Imagem a Documentos XPS Java com Aspose.Page

Adicionar imagens a arquivos XPS é uma necessidade comum para desenvolvedores Java que precisam enriquecer relatórios, faturas ou qualquer documento visual. Neste tutorial você descobrirá **como adicionar imagem** a um documento XPS usando a poderosa biblioteca Aspose.Page for Java. Vamos percorrer cada passo, explicar por que cada linha é importante e oferecer dicas para evitar armadilhas típicas.

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I add multiple images?** Yes – repeat the image‑adding steps for each picture  
- **Supported image formats?** TIFF, JPEG, PNG, GIF (and others supported by .NET)  
- **Do I need a license?** A free trial works for evaluation; a commercial license is required for production  
- **Typical implementation time?** About 10‑15 minutes for a basic image insertion

## Introduction
Adicionar imagens a documentos XPS é uma necessidade comum em muitas aplicações Java, desde a geração de relatórios até o processamento de documentos. Aspose.Page for Java simplifica essa tarefa, oferecendo métodos eficientes para integrar imagens aos seus arquivos XPS de forma transparente. Neste tutorial, demonstraremos como adicionar uma imagem a um documento XPS usando Aspose.Page for Java.

## Prerequisites
Antes de iniciar o tutorial, certifique‑se de que você possui os seguintes pré‑requisitos:
1. **Aspose.Page for Java Library** – Baixe e instale a biblioteca Aspose.Page for Java a partir do [website](https://releases.aspose.com/page/java/).  
2. **Java Development Environment** – Garanta que você tenha um ambiente de desenvolvimento Java configurado em sua máquina.

Agora, vamos para os próximos passos.

## Import Packages
No seu projeto Java, importe os pacotes necessários do Aspose.Page for Java para acessar as classes e métodos requeridos.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Step 1: Set Up Document Directory
Defina o caminho para o diretório onde o documento XPS e os arquivos de imagem serão armazenados.

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create a New XPS Document
Inicialize um novo documento XPS usando o trecho de código a seguir:

```java
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Image to XPS Document
Para adicionar uma imagem, crie um caminho no documento XPS e defina o pincel de imagem usando o arquivo de imagem fornecido e as coordenadas.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Step 4: Save Resultant XPS Document
Salve o documento XPS modificado no diretório especificado.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Repita estas etapas para adicionar mais imagens ou personalizar as existentes de acordo com os requisitos do seu projeto.

## Conclusion
Parabéns! Você aprendeu com sucesso **como adicionar imagem** a um documento XPS usando Aspose.Page for Java. Essa habilidade é valiosa para melhorar o apelo visual das suas aplicações e documentos Java.

### Frequently Asked Questions
### Can I add multiple images to the same XPS document using Aspose.Page for Java?
Sim, você pode adicionar várias imagens repetindo as etapas descritas neste tutorial para cada imagem.

### What image formats are supported by Aspose.Page for Java?
Aspose.Page for Java suporta diversos formatos de imagem, incluindo TIFF, JPEG, PNG e GIF.

### Is there a trial version of Aspose.Page for Java available?
Sim, você pode obter uma versão de avaliação gratuita do Aspose.Page for Java através deste [link](https://releases.aspose.com/).

### How can I get a temporary license for Aspose.Page for Java?
Você pode obter uma licença temporária neste [link](https://purchase.aspose.com/temporary-license/).

### Where can I find additional support or discuss issues related to Aspose.Page for Java?
Visite o [forum Aspose.Page](https://forum.aspose.com/c/page/39) para obter ajuda, compartilhar experiências e conectar‑se com a comunidade Aspose.Page.

## Additional Tips & Common Pitfalls
- **Path Geometry Accuracy** – Certifique‑se de que a string de caminho no estilo SVG corresponda às dimensões da sua imagem; caso contrário, a imagem pode aparecer esticada ou cortada.  
- **Image Brush Scaling** – O método `createImageBrush` recebe retângulos de origem e destino; ajustar esses valores permite controlar posicionamento e dimensionamento com precisão.  
- **License Activation** – Se você executar o código sem uma licença válida, a Aspose adicionará uma marca d'água ao arquivo XPS gerado.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}