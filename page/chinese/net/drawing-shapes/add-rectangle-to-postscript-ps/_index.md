---
date: 2026-01-18
description: 学习如何使用 Aspose.Page for .NET 创建 PostScript 文档并添加矩形。一步一步的指南，附带代码示例。
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 在 .NET 中创建 PostScript 文档 – 添加矩形
url: /zh/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 向 PostScript (PS) 添加矩形

## Introduction

如果您想 **创建 postscript 文档 .net**，Aspose.Page 提供了强大的解决方案来处理 PostScript 文件。在本教程中，我们将演示如何使用 Aspose.Page for .NET 向 PostScript 文档添加矩形，为您提供更丰富的图形生成的坚实基础。

## Quick Answers
- **我需要哪个库？** Aspose.Page for .NET.
- **我可以从头创建 PostScript 文档吗？** 是的——API 允许您以编程方式构建 PS 文件。
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要许可证。
- **实现大约需要多长时间？** 对于基本形状通常在 10 分钟以内。

## What is creating a postscript document .net?
在 .NET 中创建 PostScript 文档是指使用 Aspose.Page API 以编程方式生成描述页面内容（文本、图形或形状）的 .ps 文件。这种方式非常适合服务器端图形生成、自动化报告创建或任何需要对输出格式进行精确控制的场景。

## Why use Aspose.Page for .NET?
- **对图形的完整控制** —— 绘制形状、设置颜色并应用笔触，而无需处理底层 PS 语法。
- **跨平台** —— 在 Windows、Linux 和 macOS 运行时均可工作。
- **无外部依赖** —— 库内部处理所有 PS 生成。
- **丰富的文档和示例** —— 快速上手。

## Prerequisites

- **Aspose.Page for .NET 库** —— 从[此处](https://releases.aspose.com/page/net/)下载并安装。
- **开发环境** —— Visual Studio、VS Code 或任何兼容 .NET 的 IDE。

## Import Namespaces

在开始编码之前，导入公开所需类的命名空间：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

现在让我们将示例拆分为清晰的编号步骤。

## Step 1: Set up Your Document Directory

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为您希望保存生成的 PS 文件的文件夹路径。

## Step 2: Create Output Stream for the PostScript Document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

此流指向 **AddRectangle_outPS.ps**。如有需要，可自由重命名文件或更改保存位置。

## Step 3: Set Save Options and Create the PS Document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

这里我们指示 Aspose.Page 使用 A4 页面尺寸并创建单页文档。

## Step 4: Add a Filled Rectangle

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

我们在 (250, 100) 处定义一个宽 150、高 100 的矩形，设置橙色画刷并填充该形状。

## Step 5: Add an Outlined Rectangle

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

在页面下方创建第二个矩形，这次使用红色 3 点宽的笔触描边。

## Step 6: Close the Page and Save the Document

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

关闭页面以完成绘制，`Save()` 将 PS 文件写入磁盘。

## Common Issues & Tips

- **文件路径不正确** —— 确保 `dataDir` 以路径分隔符（`\\` 或 `/`）结尾，或使用 `Path.Combine`。
- **缺少许可证** —— 在生产环境中，请在创建文档前应用 Aspose 许可证，以避免评估水印。
- **颜色可见性** —— 如果矩形显示为空白，请确认画刷或笔的颜色与页面背景形成对比。

## Frequently Asked Questions

**问：** 我可以自定义矩形的颜色吗？  
**答：** 当然。将 `SolidBrush` 和 `Pen` 构造函数中的 `Color.Orange` 或 `Color.Red` 值更改为您喜欢的任意 `System.Drawing.Color`。

**问：** Aspose.Page 是否兼容其他文档格式？  
**答：** 是的。除了 PostScript，Aspose.Page 还支持 XPS 和 EPS 的生成。

**问：** 我如何在同一文档中添加文本？  
**答：** 使用 `TextFragment` 类在所需坐标放置文本，然后调用 `document.Draw(textFragment)`。

**问：** 我在哪里可以找到更多示例和完整的 API 参考？  
**答：** 请在[此处](https://reference.aspose.com/page/net/)查看文档，并在 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39)加入社区。

**问：** 我可以在购买前试用 Aspose.Page 吗？  
**答：** 可以，您可以在[此处](https://releases.aspose.com/)下载免费试用版。若需延长评估，可考虑获取[临时许可证](https://purchase.aspose.com/temporary-license/)。

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}