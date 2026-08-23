---
date: 2026-08-23
description: 了解如何使用 aspose.page image manipulation java 在 PostScript 文件中 embed 和 rotate
  图像，并提供清晰的 Java 示例。
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: 在 Java PostScript 中添加图像
og_description: 了解如何使用 aspose.page image manipulation java 在 PostScript 文件中 embed
  和 rotate 图像，并提供 step‑by‑step Java 代码示例。
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: 如何使用 aspose.page image manipulation java 添加图像
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
title: 如何使用 aspose.page image manipulation java 添加图像
url: /zh/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 aspose.page image manipulation java 添加图像

## 介绍
在本教程中，您将学习如何 **use aspose.page image manipulation java** 创建 PostScript 文件、嵌入光栅图像，并应用平移和旋转变换。完成本指南后，您将能够从 Java 生成像素级精确的 PostScript 输出——这对于自动化报告、打印流水线或任何需要在 PostScript 文档中精确放置图像的工作流都非常理想。

## 快速答案
- **需要的库是什么？** Aspose.Page for Java  
- **我可以添加多个图像吗？** Yes – repeat the transform and draw steps for each image  
- **开发是否需要许可证？** A free trial works for testing; a license is required for production  
- **支持哪个 Java 版本？** Java 8 and later  
- **是否支持图像旋转？** Absolutely – use `AffineTransform.rotate()`

## 什么是 aspose.page image manipulation java？
`aspose.page image manipulation java` 是 Aspose.Page API，允许您通过 Java 代码以编程方式构建、编辑和渲染 PostScript 文档，包括对图像放置、缩放和旋转的完整控制。使用此 API，您可以避免低层次的 PostScript 语法，让库在内部处理格式转换和嵌入。

## 为什么使用 aspose.page 进行图像操作？
Aspose.Page 提供 **50+ image formats**（包括 JPEG、PNG、BMP、TIFF），并且可以在不将整个文档加载到内存中的情况下将它们嵌入到 PostScript 中，从而能够处理包含数百页的文件，同时在典型服务器上将内存使用保持在 100 MB 以下。高级 API 抽象了复杂的 PostScript 命令，使您能够编写简洁的 Java 代码，而不是使用原始的 PS 操作符。

## 前提条件
- 已安装 Java Development Kit (JDK) 8 或更高版本。  
- Aspose.Page for Java 库 – 下载它 **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**。  
- 对 Java 语法和面向对象编程有基本了解。

## 什么是 create postscript java？
从 Java 创建 PostScript 文件意味着以编程方式生成一个 `.ps` 文档，该文档使用 PostScript 语言描述页面布局、矢量图形和光栅图像。Aspose.Page 将您的 Java 调用转换为有效的 PostScript 指令，使您能够在没有单独的 PostScript 解释器的情况下生成可打印的文件。

## 如何逐步添加带平移和旋转的图像
加载图像，应用 `AffineTransform`，并将其绘制到页面。以下步骤概述了您需要遵循的确切顺序。

### 步骤 1：写入图形保存
保存图形状态会隔离您的变换，以便稍后恢复。这相当于原始 PostScript 中的 `gsave` 操作符。

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### 步骤 2：平移和变换（平移和旋转图像）
首先，从源文件创建 `BufferedImage`，然后构建一个 `AffineTransform`，将图像平移到所需坐标并围绕其中心旋转。`AffineTransform.rotate` 需要以弧度为单位的角度，因此请使用 `Math.toRadians(degrees)` 将度数转换为弧度。

**AffineTransform** 是一个 Java 类，表示 2‑D 仿射变换，例如平移、旋转、缩放或剪切。  
**BufferedImage** 是一个 Java 类，以像素光栅的形式在内存中存储图像。

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

### 步骤 3：将图像添加到文档
配置好变换后，将图像绘制到当前页面。库会自动将 `BufferedImage` 转换为适当的 PostScript 图像流。

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

### 步骤 4：写入图形恢复
调用恢复 (`grestore`) 将图形状态返回到保存前的状态，确保后续的绘图命令不受之前变换的影响。

```java
document.drawImage(image, transform, null);
```

### 步骤 5：关闭当前页面并保存
完成页面，关闭文档，并将输出文件写入磁盘。

```java
document.writeGraphicsRestore();
```

您可以重复上述序列以嵌入更多图像，每次调整平移坐标和旋转角度。

## 常见问题及解决方案
- **FileNotFoundException:** 验证 `dataDir` 以文件分隔符（`/` 或 `\\`）结尾，并确保图像文件名完全匹配。  
- **ImageIO.read returns null:** 确保图像格式在支持列表中（JPEG、PNG、BMP、GIF、TIFF）。  
- **Incorrect rotation angle:** `AffineTransform.rotate` 使用弧度；使用 `Math.toRadians(degrees)` 将度数转换为弧度。  
- **Memory spikes on large pages:** 使用 `Document.save` 并设置 `saveOptions.setCompress(true)` 以降低内存占用。

## 常见问答

**Q: 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？**  
A: 核心库仅限 Java，但 Aspose 为 .NET、C++ 和 Python 提供了等效的 API，均针对各自平台进行定制。

**Q: 是否有 Aspose.Page for Java 的免费试用？**  
A: 是的，您可以访问免费试用 **[Aspose.Page free trial page](https://releases.aspose.com/)**。

**Q: 如何获取 Aspose.Page for Java 的临时许可证？**  
A: 您可以获取临时许可证 **[temporary license request page](https://purchase.aspose.com/temporary-license/)**。

**Q: 在哪里可以找到与 Aspose.Page for Java 相关的社区支持和讨论？**  
A: 请访问 **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** 获取社区帮助。

**Q: 是否有购买 Aspose.Page for Java 的其他资源？**  
A: 您可以购买库 **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**。

## 结论
您现在拥有一个完整的、端到端的 **aspose.page image manipulation java** 示例，能够创建 PostScript 文件、平移并旋转图像，并保存结果。探索完整的 **[documentation](https://reference.aspose.com/page/java/)**，了解诸如矢量图形、自定义页面尺寸和文本渲染等高级功能。

---

**最后更新：** 2026-08-23  
**测试环境：** Aspose.Page for Java 23.11  
**作者：** Aspose  








```java
document.closePage();
document.save();
```

## 相关教程

- [如何使用 Aspose.Page Java API 将 PostScript 转换为 PDF](/page/java/postscript-conversion/to-pdf/)
- [如何在 Java PostScript 中使用 Aspose.Page Java 添加渐变：对角线渐变](/page/java/postscript-gradient-addition/diagonal/)
- [如何在 Java PostScript 中使用 Aspose.Page 添加填充图案](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}