---
date: 2026-09-04
description: 了解如何使用 Aspose.Page for Java 的 Linear Gradient Paint Java 在 PostScript
  文件中创建 horizontal gradient java。提供逐步代码、常见陷阱和常见问答。
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: 使用 Aspose 在 PostScript 中创建 horizontal gradient java
og_description: 使用 Linear Gradient Paint Java 在 PostScript 中创建 horizontal gradient
  java。此 Aspose.Page 教程在 15 分钟内向您展示完整步骤、前置条件和故障排除技巧。
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: 使用 Aspose 在 PostScript 中创建 horizontal gradient java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: 使用 Aspose 在 PostScript 中创建 horizontal gradient java
url: /zh/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用线性渐变画笔添加水平渐变

## 介绍
在本综合教程中，您将学习 **如何在 PostScript 文档中使用 Java 创建水平渐变**，方法是使用随 Aspose.Page for Java 提供的 **Linear Gradient Paint Java** 类。我们将逐步演示——从项目设置到在形状和文本上渲染渐变——帮助您在几分钟内生成精致、可打印的图形。无论您是在构建报表引擎、设计自动化工具，还是自定义打印机驱动，本指南都提供了所需的完整代码。

## 快速答案
- **需要哪个库？** Aspose.Page for Java（包括 Linear Gradient Paint Java）。  
- **实现需要多长时间？** 基本水平渐变大约需要 10‑15 分钟。  
- **我需要许可证吗？** 生产使用需要临时或完整许可证。  
- **哪个 JDK 版本可用？** Java 8 或更高版本。  
- **我可以在形状和文本上都使用渐变吗？** 是的，同一个 `LinearGradientPaint` 实例可以填充形状，也可用于文本描边或填充。

## 什么是水平渐变以及为何使用它？
水平渐变将颜色从对象的左边缘平滑过渡到右边缘，创造出深度和视觉兴趣。它非常适合现代 UI 组件、突出标题或 PDF / PostScript 报表中的细微背景阴影。使用 **Linear Gradient Paint Java** 可精确控制起始和结束颜色、不透明度以及缩放，确保在任何设备或打印机上都呈现清晰的效果。

## 先决条件
在开始编写代码之前，请确保具备以下条件：

- 在您的机器上已安装 Java Development Kit (JDK)。  
- Aspose.Page for Java 库。您可以从 [Aspose.Page Java 文档](https://reference.aspose.com/page/java/) 下载。

## 导入包
在 Java 项目中导入必要的包。这些导入为您提供图形原语、渐变处理以及 Aspose.Page API 的访问权限。

`PsDocument` 类表示一个可以绘制图形的 PostScript 文档。  

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步骤 1：创建矩形
首先，设置输出流、文档以及将承载渐变的矩形。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## 步骤 2：创建水平线性渐变画笔
`LinearGradientPaint` 是定义线性颜色过渡的核心类。  
`LinearGradientPaint` 类表示一种绘画对象，可沿直线渲染渐变；您需要指定起止点、颜色停靠点，以及可选的 `AffineTransform` 将其缩放到形状上。

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## 步骤 3：填充矩形
现在使用刚才定义的渐变填充矩形。

```java
// Fill the rectangle
document.fill(rectangle);
```

## 步骤 4：使用渐变填充文本
您也可以将相同的渐变应用于文本，创造出醒目的视觉效果。

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## 步骤 5：使用渐变描边文本
最后，使用渐变作为描边颜色来描绘文本轮廓。

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## 常见问题及解决方案
| 问题 | 产生原因 | 解决方案 |
|-------|----------------|-----|
| 渐变出现拉伸 | `AffineTransform` 缩放不正确 | 确保变换的宽度和高度与矩形的尺寸（示例中为 200 × 100）匹配。 |
| 颜色看起来褪色 | Alpha 值设置得太低 | 增加 alpha 分量（`new Color(r,g,b,alpha)` 中的第四个值）。 |
| 文本不可见 | 在绘制文本之前未设置 Paint | 调用 `document.setPaint(paint)` **之前** 任何 `fillAndStrokeText` 或 `outlineText` 调用。 |

## 常见问题
**Q:** 我可以在商业项目中使用 Aspose.Page for Java 吗？  
**A:** 可以，Aspose.Page for Java 可用于商业项目。有关许可证详情，请访问 [Aspose.Purchase](https://purchase.aspose.com/buy) 页面。

**Q:** 是否提供免费试用？  
**A:** 是的，您可以在 [Aspose.Page for Java 免费试用](https://releases.aspose.com/) 页面获取免费试用版。

**Q:** 哪里可以找到更多文档和支持？  
**A:** 请访问 [Aspose.Page Java 文档](https://reference.aspose.com/page/java/) 获取完整资源。社区帮助请查看 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39)。

**Q:** 如何获取临时许可证？  
**A:** 您可以在 [Aspose.Purchase 临时许可证页面](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q:** Aspose.Page for Java 的系统要求是什么？  
**A:** 请参阅 [Aspose.Page Java 文档](https://reference.aspose.com/page/java/) 了解详细的系统要求。

---

**最后更新：** 2026-09-04  
**测试环境：** Aspose.Page for Java 24.11  
**作者：** Aspose

## 相关教程

- [在 Java 中创建 PostScript 渐变 – 添加垂直渐变](/page/java/postscript-gradient-addition/vertical/)
- [如何在 Java PostScript 中使用 Aspose.Page Java 添加渐变：对角线渐变](/page/java/postscript-gradient-addition/diagonal/)
- [创建 PostScript 渐变 – Java 中的径向渐变](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}