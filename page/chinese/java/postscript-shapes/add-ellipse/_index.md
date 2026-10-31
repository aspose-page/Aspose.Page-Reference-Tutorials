---
date: 2026-10-31
description: 了解如何在 Java PostScript 中使用 Aspose.Page 设置 paint color 并填充 ellipse。本文指南展示了如何填充
  ellipse、绘制 ellipse 边框，以及使用清晰的代码步骤设置 stroke thickness。
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: 在 Java PostScript 中添加 ellipse
og_description: 了解如何在 Java PostScript 中使用 Aspose.Page 填充 ellipse 并设置 paint color。按照一步一步的代码，在几秒钟内绘制填充和描边的
  ellipses。
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: 如何在 Java PostScript 中填充 ellipse 并设置 paint color
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: 如何在 Java PostScript 中填充 ellipse 并设置 paint color
url: /zh/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中填充椭圆并设置绘图颜色

## 介绍
如果您在绘制矢量图形时需要**设置绘图颜色**，Aspose.Page for Java 库可让您对每一次描边和填充拥有完整控制。在本教程中，您将学习如何**设置绘图颜色**、**填充椭圆**以及**绘制椭圆轮廓**，采用简单的逐步方法。完成后，您即可在发票、报告或任何可打印文档中添加高质量的 PostScript 椭圆。

## 快速答案
- **在 Java 中绘制 PostScript 图形的最佳库是什么？** Aspose.Page for Java.  
- **我可以使用纯色填充椭圆吗？** 是的 – 在 `fill` 之前使用 `document.setPaint(Color.YOUR_COLOR)`。  
- **如何仅绘制椭圆的轮廓？** 设置绘图颜色和笔触，然后调用 `document.draw(...)`。  
- **生产使用是否需要许可证？** 需要商业许可证；可获取临时许可证用于测试。  
- **支持哪个 Java 版本？** 任何 Java 8+ 运行时均可与当前的 Aspose.Page 发行版配合使用。

## 什么是 PostScript 椭圆？
PostScript 椭圆是一种由边界矩形定义的矢量形状。与光栅图像不同，它可以在不失真的情况下缩放，非常适合高分辨率打印和 PDF 转换。由于形状是通过数学方式描述的，它可以在任何尺寸或分辨率下渲染，同时保持边缘清晰、曲线平滑。

## 为什么使用 Aspose.Page 创建 PostScript 椭圆？
Aspose.Page 为每个绘图原语提供确定性的控制。它支持**3 大操作系统（Windows、Linux、macOS）**，**0 原生依赖**，并且在典型服务器上每秒可渲染**50+ 矢量原语**。该库纯 Java 实现，可在任何 Java 8+ 应用中嵌入，无需额外的本地库。

## 前置条件
在开始之前，请确保您具备：

1. 一个可用的 Java 开发环境（JDK 8 或更高）。  
2. 将 Aspose.Page for Java 库添加到您的项目中。您可以**[从 Aspose.Page for Java 发布页面](https://releases.aspose.com/page/java/)**下载它。  

## 导入包
在您的 Java 源文件中，导入绘制和保存 PostScript 内容所需的类。

`java.awt` 包提供基本的图形类型，如 `Color`、`Ellipse2D` 和 `BasicStroke`。`com.aspose.page` 包提供用于写入 PostScript 输出的 `PsDocument` 类。

- **`Color`** – 表示用于绘图的 sRGB 颜色。  
- **`Ellipse2D`** – 描述由边界矩形定义的椭圆形状。  
- **`BasicStroke`** – 指定绘制轮廓的线宽、虚线模式和端帽样式。  
- **`PsDocument`** – 表示 PostScript 文档，并提供绘图和页面管理的方法。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 如何为椭圆设置绘图颜色
第一步是告诉文档在接下来的绘制操作中使用哪种颜色。`setPaint` 方法设置一种固体颜色，该颜色将应用于填充或描边，取决于后续的调用。

### 步骤 1：设置 PostScript 文档
创建输出流，配置页面尺寸，并实例化一个 `PsDocument`。

`PsDocument` 是表示内存中 PostScript 文件的核心类。所有绘图命令都通过该对象路由，它负责页面布局、资源管理以及最终文件生成。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步骤 2：填充椭圆 – 使用设置绘图颜色
要**填充椭圆**，必须先使用所需的填充颜色调用 `setPaint`，然后使用 `Ellipse2D` 实例调用 `fill`。

`setPaint` 设置后续填充或描边操作使用的当前绘图颜色。  
`Ellipse2D` 定义椭圆的几何边界；其构造函数接受左上角的 X‑Y 坐标以及宽度和高度。

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 步骤 3：绘制椭圆轮廓并设置笔触粗细
填充后，您可以将绘图颜色更改为其他颜色，定义 `BasicStroke` 以控制线宽，然后绘制椭圆轮廓。

`BasicStroke` 指定绘制轮廓的线宽、虚线模式和端帽样式。通过调整其 `width` 属性，您可以控制椭圆边框的粗细程度。

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 步骤 4：关闭并保存文档
完成页面并将 PostScript 文件写入磁盘。

调用 `document.close()` 会刷新所有未完成的绘图命令并释放资源。生成的 `.ps` 文件可使用任何 PostScript 查看器打开或转换为 PDF。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

现在您拥有一个包含两个椭圆的 PostScript 文件——一个填充橙色，另一个以红色描边。请随意尝试不同的坐标、尺寸和颜色，以满足您的设计需求。

## 常见陷阱与故障排除
- **文件路径不正确** – 确保 `dataDir` 以适合您操作系统的分隔符（`/` 或 `\\`）结尾。  
- **缺少许可证** – 没有有效许可证时，库会以评估模式运行，可能会添加水印。  
- **颜色未应用** – 请记得在每次 `fill` 或 `draw` 调用*之前*设置 `document.setPaint(...)`；绘图颜色设置不会自动跨操作保持。

## 常见问题

**问：我可以将 Aspose.Page for Java 与其他 Java 库一起使用吗？**  
答：可以，Aspose.Page for Java 旨在与其他 Java 库无缝集成。

**问：如何获取 Aspose.Page for Java 的临时许可证？**  
答：可从 **[Aspose 临时许可证页面](https://purchase.aspose.com/temporary-license/)** 获取临时许可证用于测试。

**问：Aspose.Page 适用于商业项目吗？**  
答：当然！请访问 **[Aspose 购买页面](https://purchase.aspose.com/buy)** 了解商业使用的授权选项。

**问：我可以在哪里寻求帮助或讨论 Aspose.Page 相关问题？**  
答：加入 **[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)** 社区进行讨论和获取帮助。

**问：有没有免费资源可以进一步了解 Aspose.Page for Java？**  
答：可使用 **[Aspose 免费试用页面](https://releases.aspose.com/)** 并在文档中查看示例。

## 结论
Aspose.Page for Java 使**设置绘图颜色**、**填充椭圆**和**绘制椭圆轮廓**变得直观，无论是简单的填充形状还是复杂的描边图形。通过上述步骤，您可以快速将专业级矢量图形添加到任何可打印文档中。若需更深入的探索——如组合多个形状、应用渐变或转换为 PDF——请参考官方 **[Aspose.Page Java 文档](https://reference.aspose.com/page/java/)**。

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## 相关教程

- [如何使用 Aspose.Page 在 Java PostScript 中绘制矩形](/page/java/postscript-shapes/add-rectangle/)
- [如何在 Java PostScript 中使用 Aspose.Page 添加 Unicode 文本](/page/java/postscript-text-manipulation/add-text-unicode/)
- [在 PostScript 中使用 Aspose.Page for Java 创建径向渐变](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}