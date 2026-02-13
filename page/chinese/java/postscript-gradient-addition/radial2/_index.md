---
date: 2026-02-13
description: 学习如何在 Java PostScript 中使用 Aspose.Page 用渐变填充形状并绘制渐变圆形。一步一步的指南，包含代码和技巧。
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 使用渐变填充形状：Java PostScript 径向示例
url: /zh/java/postscript-gradient-addition/radial2/
weight: 13
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 填充形状渐变：Java PostScript 径向示例

## Introduction
在本教程中，您将学习如何通过使用 Aspose.Page for Java 为 PostScript 文档构建径向渐变示例来**填充形状渐变**。我们将逐步演示——从项目设置到渲染一个填充平滑径向渐变的圆形——让您立即在 Java 应用程序中添加引人注目的图形。

## Quick Answers
- **本教程创建了什么？** 一个包含径向渐变填充圆形的 PostScript 文件（`.ps`）。  
- **需要哪个库？** Aspose.Page for Java（最新版本）。  
- **实现需要多长时间？** 大约 10‑15 分钟即可得到可运行的示例。  
- **是否需要许可证？** 生产使用需要临时或完整许可证；免费试用可用于开发。  
- **代码能否复用于 PDF 或 SVG？** 可以——Aspose.Page 支持多种输出格式，只需少量修改。

## How to Fill Shape with Gradient in PostScript
在深入代码之前，让我们先说明为什么“填充形状渐变”很重要。使用渐变可以让您的图形呈现专业的三维感，而无需栅格图像。使用 Aspose.Page，您可以将相同的渐变逻辑应用于任何矢量形状——圆形、矩形或自定义路径——在所有受支持的输出格式（PostScript、PDF、SVG）中保持一致。

## What Is a Radial Gradient?
径向渐变是从中心点向外过渡颜色，形成平滑的圆形混合。它非常适合用于高光、按钮背景或任何需要自然“发光”效果的视觉元素。

## Why Use Aspose.Page for Radial Gradients?
- **设备无关渲染**——在 PostScript、PDF、SVG 等平台上表现一致。  
- **完整的 Java 集成**——无需本地代码，仅使用纯 Java API。  
- **高质量输出**——支持抗锯齿和色彩空间控制。

## Prerequisites
在开始之前，请确保您具备以下条件：

- 对 Java 编程有基本了解。  
- 已在机器上安装 JDK 8 或更高版本。  
- Aspose.Page for Java 库（可从 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) 下载）。

## Import Packages
首先，导入我们需要的类。这些包括标准的 AWT 图形类型和 Aspose.Page API。

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Document Directory
定义生成的 PostScript 文件将保存的文件夹。将占位符替换为系统上的实际路径。

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream
打开指向目标 `.ps` 文件的 `FileOutputStream`。该流用于写入 Aspose.Page 生成的二进制数据。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Step 3: Create Save Options
实例化 `PsSaveOptions`。您可以自定义页面大小、压缩等，但默认设置已足够本示例使用。

```java
PsSaveOptions options = new PsSaveOptions();
```

## Step 4: Create PS Document
创建 `PsDocument` 对象，传入输出流和保存选项。`false` 标志告诉 Aspose.Page 不要自动打开页面（我们将手动打开）。

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Create a Circle
我们将使用 `Ellipse2D.Float` 绘制一个圆。参数为 `(x, y, width, height)`。将 width = height 设置为相等即可得到完美的圆形。

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## How to Draw Circle with Gradient
现在我们已有形状，下一步是**使用渐变绘制圆**。通过将 `RadialGradientPaint` 应用于圆，填充操作会自动使用我们定义的渐变。

## Step 6: Define Gradient Colors
准备两个数组：一个用于渐变中的颜色，另一个用于对应的分数位置（0 = 中心，1 = 边缘）。

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Step 7: Create AffineTransform
`AffineTransform` 用于缩放和平移渐变以适配我们的圆。矩阵 `(scaleX, 0, 0, scaleY, translateX, translateY)` 完成此工作。

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Step 8: Create Radial Gradient Paint
现在我们构建 `RadialGradientPaint` 对象。它接受中心点、半径、焦点、颜色分数、颜色数组、循环方式、颜色空间以及我们刚才定义的变换。

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Step 9: Set Paint and Fill Circle
将渐变画笔应用到文档并填充先前定义的圆。这是我们**径向渐变示例**的核心，演示了如何**填充形状渐变**。

```java
document.setPaint(paint);
document.fill(circle);
```

## Step 10: Close Page and Save Document
完成页面，写入磁盘并关闭流。您的 PostScript 文件现在可以使用任何 PS 查看器打开。

```java
document.closePage();
document.save();
```

恭喜！您已成功使用 Aspose.Page 在 Java PostScript 中创建了径向渐变示例。您现在拥有一个可复用的**填充形状渐变**模式，可适配其他形状和输出格式。

## Common Issues and Solutions
| 问题 | 解决方案 |
|---------|----------|
| **FileNotFoundException** 在打开输出流时 | 确认 `dataDir` 指向已存在的文件夹且您拥有写入权限。 |
| 渐变显示平坦或缺失 | 确保 `fractions` 数组长度与 `colors` 数组相匹配，并且 `AffineTransform` 正确缩放。 |
| 颜色显示颠倒 | 调换 `colors` 数组中的颜色顺序或调整 `focus` 点坐标。 |

## Frequently Asked Questions

**问：在哪里可以找到 Aspose.Page for Java 的文档？**  
答：完整的 API 参考可在[此处](https://reference.aspose.com/page/java/)获取。

**问：如何下载 Aspose.Page for Java？**  
答：从[发布页面](https://releases.aspose.com/page/java/)获取最新的 JAR。

**问：是否提供免费试用？**  
答：是的——在[此处](https://releases.aspose.com/)下载试用版。

**问：我可以获取临时许可证用于测试吗？**  
答：当然，可从[临时许可证页面](https://purchase.aspose.com/temporary-license/)申请。

**问：在哪里可以获得社区支持？**  
答：加入[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)的讨论。

## Conclusion
在本指南中，我们使用 Aspose.Page for Java 为 PostScript 文档构建了完整的**径向渐变示例**。通过遵循这些步骤，您现在拥有一个可复用的**填充形状渐变**模式，可适配 PDF、SVG 或 Aspose.Page 支持的任何其他格式。尝试不同的颜色、半径和形状，以丰富您的 Java 图形项目。

---

**最后更新：** 2026-02-13  
**测试环境：** Aspose.Page for Java 24.11（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}