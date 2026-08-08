---
date: 2026-06-30
description: 了解如何使用 Aspose.Page for .NET 创建 postscript 文档 .NET 并添加矩形。提供代码示例的分步指南。
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: 向 PostScript (PS) 添加矩形
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: 创建 PostScript 文档 .NET – 添加矩形 Aspose.Page
url: /zh/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Page 向 PostScript (PS) 添加矩形

## 介绍

Aspose.Page for .NET 是一个库，可实现以编程方式创建和操作 PostScript、EPS 和 XPS 文件。如果您想 **create postscript document .net**，本教程将指导您使用 Aspose.Page 向 PostScript 文档添加矩形，为更丰富的图形生成奠定坚实基础。

## 快速答案
- **我需要哪个库？** Aspose.Page for .NET.  
- **我可以从头创建 PostScript 文档吗？** 是的——API 允许您以编程方式构建 PS 文件。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **开发需要许可证吗？** 免费试用可用于测试；生产环境需要许可证。  
- **实现需要多长时间？** 对于基本形状通常在 10 分钟以内。

## 什么是创建 postscript 文档 .net？

在 .NET 中创建 PostScript 文档是指使用 Aspose.Page API 以编程方式生成描述页面内容（文本、图形或形状）的 `.ps` 文件。这种方法非常适合服务器端图形生成、自动化报告创建或任何需要对输出格式进行精确控制的场景。

## 为什么使用 Aspose.Page for .NET？

Aspose.Page 支持 **30+ 图形原语**，并且能够生成高达 **500 MB** 的文件而无需将整个文档加载到内存中，在 Windows、Linux 和 macOS 上实现高性能渲染。它让您能够全面控制形状、颜色和笔触，同时无需编写低层次的 PostScript 代码。

- **Full control over graphics** – 绘制形状、设置颜色并应用笔触，无需处理低层次的 PS 语法。  
- **Cross‑platform** – 在 Windows、Linux 和 macOS 运行时上工作。  
- **No external dependencies** – 库内部处理所有 PS 生成。  
- **Rich documentation & examples** – 快速上手。

## 前提条件

- **Aspose.Page for .NET Library** – 从 [here](https://releases.aspose.com/page/net/) 下载并安装。  
- **Development Environment** – Visual Studio、VS Code 或任何兼容 .NET 的 IDE。

## 导入命名空间

`Aspose.Page` 命名空间公开了您需要的核心类，例如 `Document`、`Page`、`SolidBrush` 和 `Pen`。在开始编码之前请先导入它。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

现在让我们将示例拆分为清晰的编号步骤。

## 步骤 1：设置文档目录

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为您希望保存生成的 PS 文件的文件夹路径。

## 步骤 2：为 PostScript 文档创建输出流

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

此流指向 **AddRectangle_outPS.ps**。如有需要，随意重命名文件或更改位置。

## 步骤 3：设置保存选项并创建 PS 文档

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

在这里我们告诉 Aspose.Page 使用 A4 页面尺寸并创建单页文档。

## 步骤 4：添加填充矩形

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

我们在 (250, 100) 处定义一个宽 150、高 100 的矩形，设置橙色画刷并填充形状。

## 步骤 5：添加描边矩形

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

在页面下方创建第二个矩形，这次使用红色 3 点宽的笔触。

## 步骤 6：关闭页面并保存文档

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

关闭页面会完成绘制，`Save()` 将 PS 文件写入磁盘。

## 如何创建 postscript 文档 .net？

`Document` 是 Aspose.Page 中表示 PostScript 文件的主要类。`SaveOptions` 指定文档的页面尺寸和输出格式等设置。加载 `Document` 对象，为 A4 页面配置 `SaveOptions`，使用 `SolidBrush` 或 `Pen` 绘制形状，然后调用 `document.Save()`——整个工作流只需几行代码，并可在任何受支持的 .NET 运行时上运行。此模式使您能够生成完全符合规范的 PostScript 文件，而无需接触原始 PS 语法。

## 如何生成 postscript 文件

使用 Aspose.Page 的 `SaveOptions` 类将输出格式指定为 PostScript（`SaveFormat.PS`）。库会直接将内容流式写入文件或内存流，使您能够高效生成大型文档而不会消耗过多内存。

## 常见问题与技巧

- **Incorrect file path** – 确保 `dataDir` 以路径分隔符（`\\` 或 `/`）结尾，或使用 `Path.Combine`。  
- **Missing license** – 在生产环境中，在创建文档前应用您的 Aspose 许可证，以避免评估水印。  
- **Color visibility** – 如果矩形显示为空白，请确认画刷或笔的颜色与页面背景形成对比。

## 常见问答

**Q:** 我可以自定义矩形的颜色吗？  
**A:** 当然。将 `SolidBrush` 和 `Pen` 构造函数中的 `Color.Orange` 或 `Color.Red` 值更改为您喜欢的任何 `System.Drawing.Color`。

**Q:** Aspose.Page 与其他文档格式兼容吗？  
**A:** 是的。除了 PostScript，Aspose.Page 还支持 XPS 和 EPS 的生成。

**Q:** 我如何向同一文档添加文本？  
**A:** 使用 `TextFragment` 类在所需坐标放置文本，然后调用 `document.Draw(textFragment)`。

**Q:** 我在哪里可以找到更多示例和完整的 API 参考？  
**A:** 浏览文档 [here](https://reference.aspose.com/page/net/) 并加入 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 社区。

**Q:** 我可以在购买前试用 Aspose.Page 吗？  
**A:** 可以，下载免费试用版 [here](https://releases.aspose.com/)。如需延长评估，可考虑获取 [temporary license](https://purchase.aspose.com/temporary-license/)。

---

**最后更新：** 2026-06-30  
**测试环境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何使用 Aspose.Page for .NET 创建 PostScript 文档](/page/net/document-creation/create-postscript-document/)
- [使用 Aspose.Page 向 PostScript (PS) 文档添加图像](/page/net/image-management/add-image-to-postscript-ps-document/)
- [使用 Aspose.Page 向 PostScript (PS) 文档添加文本](/page/net/text-manipulation/add-text-to-postscript-ps-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}