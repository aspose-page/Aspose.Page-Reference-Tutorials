---
date: 2026-09-14
description: 了解如何使用 Aspose.Page 创建 postscript gradient java。本分步指南展示了如何仅用几行 Java 代码在
  PostScript 文件中添加垂直渐变。
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: 在 Java PostScript 中添加垂直渐变
og_description: 了解如何使用 Aspose.Page 创建 postscript gradient java。本分步指南展示了如何仅用几行 Java
  代码在 PostScript 文件中添加垂直渐变。
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: 创建 postscript gradient java – 垂直渐变
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: 创建 postscript gradient java – 垂直渐变
url: /zh/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 PostScript 渐变 Java – 垂直渐变

## 介绍
Aspose.Page for Java 是一个库，可让您以编程方式创建和操作 PostScript 和 PDF 文件。在本综合教程中，您将学习如何使用该库 **create postscript gradient java**。添加垂直渐变可以让您的文档看起来更鲜活、更专业，只需几行代码即可实现惊艳的视觉效果。我们将逐步演示每一步，解释每个环节的重要性，并提供实用技巧以避免常见陷阱。完成本指南后，您将能够生成具有平滑、引人注目垂直颜色过渡的 PostScript 文件。

## 快速答案
- **需要的库是什么？** Aspose.Page for Java  
- **可以自定义颜色吗？** 可以，任何 `java.awt.Color` 都可使用  
- **支持旋转吗？** 支持，您可以使用 `AffineTransform` 旋转渐变  
- **生成的输出格式是什么？** 标准的 PostScript (.ps) 文件  
- **生产环境需要许可证吗？** 需要商业许可证  

## 为什么要在 PostScript 文档中添加垂直渐变？
添加垂直渐变可以为页面增添层次感，提升视觉层级，同时由于渐变以矢量形式定义而非光栅图像，文件大小保持低位。此技术非常适合报告页眉、技术手册或任何需要现代外观且不牺牲可伸缩性的宣传单。

## 先决条件
在开始教程之前，请确保您已具备以下条件：
- 已在机器上安装 Java Development Kit (JDK)。  
- Aspose.Page for Java 库。您可以从 [Aspose.Page for Java release page](https://releases.aspose.com/page/java/) 下载。

## 导入包
在您的 Java 项目中，导入必要的包以开始使用：
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

现在，让我们一步步演示添加垂直渐变的过程。

## 如何创建 postscript gradient java
加载 Java 环境，创建 `PsSaveOptions` 实例，并调用 `Document.save` —— 这是一套核心流程，可生成带有垂直渐变的 PostScript 文件。API 会处理颜色插值、坐标变换和页面刷新，您只需专注于定义矩形和渐变参数。

### 步骤 1：设置文档目录
`File` 对象表示输出将写入的文件夹。目录必须在打开流之前存在，否则会抛出 `IOException`。
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步骤 2：为 PostScript 文档创建输出流
`FileOutputStream` 将二进制 PostScript 数据写入磁盘。使用 `try‑with‑resources` 块可确保即使出现异常也会关闭流。
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### 步骤 3：使用 A4 大小创建保存选项
`PsSaveOptions` 允许您指定页面大小、DPI 以及是否嵌入字体。将大小设为 A4（595 × 842 points）可匹配大多数可打印文档。
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### 步骤 4：创建新的 PS 文档
`Document` 是表示单个 PostScript 文件的顶层对象。所有绘图指令均针对该对象发出。
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步骤 5：创建矩形
`Rectangle2D.Double` 定义将被渐变填充的区域。矩形坐标使用点（1 point = 1/72 英寸）表示。
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### 步骤 6：为渐变设置颜色和比例
`float[]` 数组定义每个颜色停靠点的位置（从 0.0 到 1.0）。`Color` 对象保存实际的 RGB 值。您可以使用任何 `java.awt.Color`。
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### 步骤 7：创建渐变变换
`AffineTransform` 用于缩放和旋转渐变。对于纯垂直渐变，只需在 Y 轴上缩放；如需旋转，可稍后添加。
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### 步骤 8：创建垂直线性渐变 Paint
`LinearGradientPaint` 将矩形、颜色停靠点和变换组合在一起。随后该对象会传递给图形上下文。
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### 步骤 9：设置 Paint 并填充矩形
`Graphics2D.setPaint` 应用渐变，`fill` 在您先前定义的矩形内部渲染它。
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### 步骤 10：关闭当前页面并保存文档
调用 `document.save` 将整个 PostScript 流写入输出文件并释放所有本机资源。
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

恭喜！您已成功使用 Aspose.Page for Java 为 Java PostScript 文档添加垂直渐变。

## 常见问题及解决方案
- **渐变显示平坦：** 确保 `AffineTransform` 的缩放与矩形尺寸匹配。  
- **颜色显得苍白：** 验证使用了正确的 `ColorSpaceType`（SRGB），并且 fractions 数组按 0.0 到 1.0 的顺序排列。  
- **文件未生成：** 检查输出目录（`dataDir`）是否存在且应用具有写入权限。  

## 常见问答

**Q: 可以将 Aspose.Page for Java 与其他 Java 库一起使用吗？**  
A: 可以，Aspose.Page for Java 设计为可无缝配合其他 Java 库（如 Apache Commons 或 Spring）使用。

**Q: Aspose.Page for Java 有免费试用吗？**  
A: 有，您可以在 [free trial download page](https://releases.aspose.com/) 获取免费试用。

**Q: 在哪里可以找到更多文档？**  
A: 详细文档可在 [Aspose.Page Java API reference](https://reference.aspose.com/page/java/) 查看。

**Q: 如何购买 Aspose.Page for Java？**  
A: 您可以在 [Aspose.Page purchase page](https://purchase.aspose.com/buy) 进行购买。

**Q: 是否有 Aspose.Page 讨论论坛？**  
A: 有，您可以加入社区论坛 [Aspose.Page community forum](https://forum.aspose.com/c/page/39)。

## 其他常见问答

**Q: 能创建其他方向的渐变吗（水平、对角线）？**  
A: 完全可以。只需在 `LinearGradientPaint` 中调整起止点，并在 `AffineTransform` 中修改旋转角度。

**Q: 这同样适用于 PDF 输出吗？**  
A: 可以，使用 `PdfSaveOptions` 代替 `PsSaveOptions`，相同的渐变逻辑同样适用于保存为 PDF。

**Q: 如何动态改变渐变大小？**  
A: 在运行时计算矩形尺寸，并将这些值同时传递给 `Rectangle2D` 和 `AffineTransform` 构造函数。

---

**最后更新：** 2026-09-14  
**测试环境：** Aspose.Page for Java 24.11（最新）  
**作者：** Aspose

## 相关教程

- [在 PostScript 中使用 Aspose.Page for Java 创建径向渐变](/page/java/postscript-gradient-addition/)
- [使用 Aspose.Page Java API 将 PostScript 转换为 PDF 的方法](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page 透明度教程 – 在 Java PostScript 中添加透明度](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}