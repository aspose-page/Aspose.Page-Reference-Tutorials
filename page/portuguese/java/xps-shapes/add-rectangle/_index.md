---
date: 2026-04-24
description: Aprenda como definir a cor do retângulo e adicionar um retângulo em Java
  XPS usando Aspose.Page. Este guia cobre como adicionar retângulo em Java e alterar
  o traço do retângulo.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Adicionar Retângulo no Java XPS
second_title: Aspose.Page Java API
title: Definir Cor do Retângulo e Adicionar Retângulo no Java XPS
url: /pt/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir Cor do Retângulo e Adicionar Retângulo em Java XPS

## Introdução
Neste guia, você aprenderá como **definir a cor do retângulo** e **adicionar um retângulo** em Java XPS usando a biblioteca Aspose.Page. Seja para desenhar formas simples em um relatório ou criar gráficos vetoriais complexos, dominar a estilização de retângulos oferece controle preciso sobre seus documentos XPS.  

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Page para Java  
- **Posso alterar o traçado do retângulo?** Sim, usando `setStroke` e `setStrokeThickness`  
- **Um perfil de cor CMYK é suportado?** Absolutamente – você pode carregar perfis ICC conforme mostrado  
- **Preciso de licença para produção?** Sim, uma licença comercial é necessária para uso não‑avaliativo  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutes for a basic rectangle

## O que é **definir cor do retângulo**?
Definir a cor de um retângulo significa especificar a cor de preenchimento ou de traçado que a forma terá no documento XPS final. Com Aspose.Page você pode usar RGB, CMYK ou até perfis de cor ICC personalizados para obter correspondência de cor exata.

## Por que usar Aspose.Page para **add rectangle java** e **change rectangle stroke**?
- **Full‑featured API** – supports both solid colors and gradients.  
- **Cross‑platform** – works on any Java runtime without native dependencies.  
- **Rich geometry support** – create complex paths, apply transformations, and manage stroke thickness easily.  

## Pré‑requisitos
Before we dive into the code, ensure you have:

- Basic knowledge of Java programming.  
- Aspose.Page library installed. If not, download it from the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- A working Java development environment (IDE, JDK, etc.).  

## Importar Pacotes
To get started, import the necessary packages into your Java project. Ensure that the Aspose.Page library is correctly added to your classpath. Here's a basic example:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Now, let's break down the example provided into multiple steps to **add a rectangle** and **set its color** in Java XPS.

## Etapa 1: Definir o Diretório do Documento
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Replace `"Your Document Directory"` with the absolute path where you want to read/write XPS files.

## Etapa 2: Criar um Novo Documento XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
This line initializes a fresh XPS document that will hold our shapes.

## Etapa 3: Adicionar um Retângulo Contornado com Cor Sólida CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
This step adds a **stroked rectangle** with a CMYK solid color. The `setStroke` method defines the rectangle’s outline color, while `setStrokeThickness` controls the line width—perfect for **changing rectangle stroke**.

### Pro tip:
If you prefer an RGB color, replace the `createColor` call with `doc.createColor(0, 0, 255)` for a solid blue fill.

## Etapa 4: Salvar o Documento XPS Resultante
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Finally, persist the XPS document to disk. The file `AddRectangle_out.xps` now contains a rectangle whose color and stroke you defined.

## Problemas Comuns e Soluções
| Problema | Causa | Solução |
|----------|-------|----------|
| **Rectangle not visible** | Incorrect path geometry or stroke thickness set to 0 | Verify the path string (`"M 20,10 L 220,10 220,100 20,100 Z"`) and ensure `setStrokeThickness` is greater than 0. |
| **Wrong color** | Using an ICC profile that doesn’t match the intended color space | Use `doc.createColor(r, g, b)` for RGB or double‑check the ICC file path. |
| **File not saved** | `dataDir` points to a non‑existent folder or lacks write permission | Create the folder beforehand or choose a writable location. |

## Perguntas Frequentes

**Q:** *Can I add multiple rectangles in a single XPS document?*  
A: Yes. Simply repeat the geometry creation and styling steps for each rectangle you need.

**Q:** *How can I change the rectangle’s fill color instead of the stroke?*  
A: Use `path.setFill(...)` with a solid color brush, similar to how `setStroke` is used.

**Q:** *Is Aspose.Page suitable for complex XPS document manipulations?*  
A: Absolutely. The library supports advanced features like gradients, transformations, and embedded fonts.

**Q:** *Where can I find additional examples and community support?*  
A: Explore the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for more code samples and peer assistance.

**Q:** *Can I try Aspose.Page before purchasing?*  
A: Yes, you can explore a [free trial](https://releases.aspose.com/) to evaluate the API’s capabilities.

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}