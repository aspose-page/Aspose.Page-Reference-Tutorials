---
date: 2026-02-25
description: 使用 Aspose.Page for .NET 为 PostScript 文档添加线性渐变矩形。按照我们的分步指南，学习渐变填充文本和轮廓文本渐变。
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 向 PostScript (PS) 添加线性渐变矩形
url: /zh/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

 sure to keep all markdown formatting.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 PostScript (PS) 中使用 Aspose.Page 添加线性渐变矩形

## 介绍

欢迎阅读本综合教程，了解如何使用 Aspose.Page for .NET 向 PostScript (PS) 文档添加 **线性渐变矩形**。Aspose.Page 是一个强大的库，可让您创建、修改和渲染多种格式的文档，今天我们将重点介绍如何在您的 PS 文件中加入引人注目的渐变效果。

### 快速回答
- **线性渐变矩形的作用是什么？** 它在矩形区域内填充从一侧到另一侧的平滑颜色过渡。  
- **哪个 API 处理渐变填充文本？** `LinearGradientBrush` 与 `SetPaint` 和 `FillAndStrokeText` 结合使用。  
- **我可以使用渐变描边文本吗？** 可以——使用带有渐变画刷的 `SetStroke` 并调用 `OutlineText`。  
- **生产环境是否需要许可证？** 非评估使用需要商业 Aspose.Page 许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 前提条件

在开始之前，请确保您拥有：

- Aspose.Page for .NET 库：确保在项目中引用了该库。您可以从 [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) 下载。
- 文档目录：在磁盘上创建一个文件夹用于保存生成的 PS 文件，并在代码中将 **“Your Document Directory”** 替换为该路径。

## 导入命名空间

要开始，请导入能够访问绘图和 PS 特定类的命名空间：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 什么是线性渐变矩形？

**线性渐变矩形** 简单来说就是一种内部使用线性渐变填充的矩形形状——颜色沿直线平滑过渡，通常是从左到右（水平）或从上到下（垂直）。在 Aspose.Page 中，您可以通过组合定义矩形的 `GraphicsPath` 与描述颜色过渡的 `LinearGradientBrush` 来实现。

## 为什么使用渐变填充文本和描边文本渐变？

- **视觉吸引力：** 渐变填充的文本为报告、发票或宣传材料增添深度和现代感。  
- **品牌一致性：** 使用精确的 ARGB 值匹配企业颜色。  
- **多功能性：** 同一画刷可重复用于形状填充、文本填充和描边渐变，减少代码重复。

## 步骤 1：设置文档

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步骤 2：定义渐变矩形和颜色

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## 步骤 3：设置画刷的变换

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## 步骤 4：设置 Paint 并填充矩形

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## 如何应用渐变填充文本

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## 使用描边文本渐变

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## 步骤 7：关闭当前页面并保存文档

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

恭喜！您已成功向 PostScript 文档添加 **线性渐变矩形**，并使用同一画刷实现 **渐变填充文本** 和 **描边文本渐变**。

## 常见使用场景与技巧

- **报告标题：** 使用渐变填充大块文本以突出章节标题。  
- **品牌标志：** 使用渐变填充形状重新创建标志形状，实现一致的品牌形象。  
- **专业提示：** 对多个绘图调用重复使用同一 `LinearGradientBrush` 实例，以确保形状和文本之间的颜色完美对齐。

## 常见问题

### 问题 1：我可以将渐变应用于除矩形之外的其他形状吗？

**答：** 可以，您可以对由 `GraphicsPath` 定义的任何形状应用渐变。在调用 `document.Fill(path)` 之前，只需添加圆形、多边形或自定义路径即可。

### 问题 2：如何更改渐变颜色？

**答：** 在构造 `LinearGradientBrush` 时修改 `Color.FromArgb` 的值。第一个颜色为起始色，第二个为渐变结束色。

### 问题 3：Aspose.Page 是否兼容不同的文档格式？

**答：** 当然。Aspose.Page 支持 XPS、PS、PDF 以及其他多种矢量格式。请查阅官方文档获取完整列表。

### 问题 4：我可以在商业项目中使用 Aspose.Page 吗？

**答：** 可以，提供商业授权。详情请参阅购买页面：[here](https://purchase.aspose.com/buy)。

### 问题 5：在哪里可以找到社区支持？

**答：** 加入 Aspose.Page 社区论坛：[Aspose.Page Forum](https://forum.aspose.com/c/page/39)。

---

**最后更新：** 2026-02-25  
**测试环境：** Aspose.Page 24.10 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}