---
date: 2026-02-25
description: 学习如何使用 C# 线性渐变画刷为 PS 文件添加渐变，并使用 Aspose.Page for .NET 为矩形填充渐变。
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# 线性渐变画刷 – 使用 Aspose.Page 为 PostScript (PS) 添加垂直渐变
url: /zh/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 class name, keep it. So heading: "# c# Linear Gradient Brush – 添加垂直渐变到 PostScript (PS) 使用 Aspose.Page". Good.

Similarly subheadings.

Proceed.

Translate introduction paragraph.

Make sure to keep **bold** markers.

Translate quick answers bullet points.

Translate table.

Proceed.

Let's craft final output.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – 添加垂直渐变到 PostScript (PS) 使用 Aspose.Page

## Introduction

在文档操作和创建领域，**Aspose.Page for .NET** 是开发者的强大工具。在本指南中，您将学习如何使用 **C# linear gradient brush** 为 **PS** 文件 **添加渐变**，并 **用渐变填充矩形**。通过本教程，您将逐步了解所需代码以及为何此技术能够在 PostScript 输出中产生平滑的垂直渐变。

## Quick Answers
- **C# linear gradient brush 的作用是什么？** 它在形状之间创建多颜色的平滑过渡。
- **可以在任何 .NET 版本上使用吗？** 可以，Aspose.Page 支持 .NET Framework 4.5+ 和 .NET Core/5+。
- **生产环境需要许可证吗？** 非评估版构建需要商业许可证。
- **渐变真的垂直吗？** 画笔旋转了 90°，确保垂直方向的渐变。
- **输出保存在哪里？** 保存到您在 `dataDir` 中指定的路径（例如 `VerticalGradient_outPS.ps`）。

## What is a C# Linear Gradient Brush?
**C# linear gradient brush** 是一个 GDI+ 对象（`LinearGradientBrush`），在定义的点之间绘制线性颜色过渡。结合 Aspose.Page 的绘图 API，您可以直接在 PostScript (PS) 文档中渲染精细的渐变。

## Why Use a Linear Gradient Brush for PostScript?
- **高质量输出：** 渐变在打印机级别渲染，保持细节。
- **完全控制：** 可以自定义颜色停点、旋转和缩放。
- **代码可复用：** 相同的画笔逻辑同样适用于 PDF、SVG 等 Aspose.Page 支持的格式。

## Prerequisites

在开始教程之前，请确保具备以下条件：

- Aspose.Page for .NET：确保已安装 Aspose.Page 库。您可以在 [此处](https://reference.aspose.com/page/net/) 找到相关资源和文档。
- 开发环境：搭建合适的 .NET 开发环境，包括集成开发环境（IDE）。
- 基础了解：熟悉 .NET 开发基础，包括流、图形路径和颜色操作。

## Import Namespaces

在 C# 项目中，在代码文件开头引入所需的命名空间：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up the Document Directory

首先指定文档目录的路径，这是保存 PS 文档的位置。

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream for PostScript Document

使用 `FileStream` 类为 PostScript 文档生成输出流。

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Step 3: Create Save Options and PS Document

创建带有 A4 大小的保存选项，并初始化一个 1 页的 PS 文档。

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Define Rectangle Dimensions

指定将应用垂直渐变的矩形的尺寸和位置。

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Step 5: Create Graphics Path

根据定义的矩形构建图形路径。

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Step 6: Define Interpolation Colors

为渐变建立颜色插值数组及其位置。

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Step 7: Create Linear Gradient Brush

使用矩形边界、起始颜色和结束颜色创建线性渐变画笔。

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Step 8: Set Brush Transform

为画笔设置变换，确保 X、Y 缩放分量与矩形的宽高相匹配。

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Step 9: Set Paint and Fill the Rectangle

为文档设置画笔，并使用先前定义的路径 **fill rectangle with gradient**。

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Step 10: Close the Current Page and Save the Document

关闭当前页面并保存 PostScript 文档。

```csharp
document.ClosePage();
document.Save();
```

Congratulations! 您已成功使用 **C# linear gradient brush** 与 Aspose.Page for .NET **为 PostScript 文档添加垂直渐变**。尝试不同的参数和颜色，以在文档中实现各种视觉效果。

## Common Issues and Solutions

| Issue | Why it Happens | How to Fix |
|-------|----------------|------------|
| 渐变显示为水平 | 画笔旋转未应用 | 确保在分配给 `brush.Transform` 前调用 `brushTransform.Rotate(90);` |
| 颜色显得淡薄 | 输出流分辨率低 | 使用更高分辨率的 `PsSaveOptions` 或增大文档尺寸 |
| 输出文件为空 | 流未刷新 | 确认在 `using` 块外调用 `document.Save();` |

## Frequently Asked Questions

**Q1: 能否在同一文档的不同区域应用多个渐变？**  
A: 可以。只需为每个区域重复相应步骤，并使用各自的尺寸和配色方案。

**Q2: 如何将此代码集成到已有的 .NET 项目中？**  
A: 将代码复制粘贴到项目文件中，并确保已引用 Aspose.Page 库。

**Q3: Aspose.Page for .NET 还有其他渐变类型吗？**  
A: Aspose.Page 支持多种渐变类型，包括径向渐变和路径渐变。详情请参阅文档。

**Q4: 可以在商业项目中使用 Aspose.Page 吗？**  
A: 可以。访问 [here](https://purchase.aspose.com/buy) 了解授权选项。

**Q5: 有 Aspose.Page 的社区论坛可以求助吗？**  
A: 当然！前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 与其他开发者交流并获取帮助。

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}