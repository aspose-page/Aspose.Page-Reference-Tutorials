---
date: 2026-06-30
description: 了解如何使用 Aspose.Page for .NET 在几步简易操作中创建 XPS Document .NET 并添加 Image Filled
  Glyph 或 Foreign Image。
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: 添加 Image Filled Glyph & Foreign Image
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: 创建 XPS Document .NET – Add Image Filled Glyph & Foreign Image with Aspose.Page
url: /zh/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 XPS 文档 .NET – 使用 Aspose.Page 添加图像填充字形和外部图像

## 简介

在 .NET 开发中，当需要高质量、分辨率无关的图形时，**create XPS document .NET** 任务非常常见。Aspose.Page for .NET 使这一过程变得简便，并允许您使用图像填充字形来丰富 XPS 文件，或从另一个 XPS 文档中提取图像。通过本教程，您将了解如何创建两个 XPS 文档、使用图像填充字形，并在文档之间复用这些图像——非常适合生成发票、证书或任何视觉丰富的输出。

## 快速回答
- **Aspose.Page 支持什么？** 超过 25 种图像格式，并且能够在不完整加载内存的情况下处理高达 500 MB 的 XPS 文件。  
- **添加图像填充字形需要多少行代码？** 只需两行：创建一个 `ImageBrush` 并将其分配给 `Glyph`。  
- **生产环境是否需要许可证？** 是的，商业许可证可去除评估水印。  
- **兼容哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **我可以复用另一个 XPS 的字体吗？** 当然可以——您可以将第一个文档的字体集合导入到第二个文档中。

## 如何使用 Aspose.Page .NET 创建 XPS 文档？

加载 Aspose.Page 库，实例化 `XpsDocument`，添加页面，然后调用 `Save` —— 这三个简洁的语句就完成了完整的工作流。API 会自动处理页面尺寸、DPI 和资源管理，您无需自行管理底层 XPS 结构。这种方法可从单页宣传单扩展到数百页的目录。

## 先决条件

在开始之前，请确保您拥有：

- **Aspose.Page for .NET** – 从 [here](https://releases.aspose.com/page/net/) 下载。  
- **.NET IDE** – Visual Studio、Rider 或带 C# 扩展的 VS Code。  
- **文档文件夹** – 在代码片段中我们将其称为 **Your Document Directory**。

## 导入命名空间

`Aspose.Page.XPS` 命名空间提供核心 XPS 文档类，而 `Aspose.Page.XPS.XpsModel` 包含字形和画刷等模型元素。请在文件顶部导入它们：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 什么是图像填充字形？

字形是一种向量形状，可使用纯色、渐变或图像画刷进行渲染。当您应用 `ImageBrush` 时，字形的内部会被提供的图像填充，从而在不对整页进行光栅化的情况下实现复杂的视觉效果。

## 步骤 1：创建第一个 XPS 文档

`XpsDocument` 表示一个 XPS 包，是创建和保存 XPS 文件的入口点。首先创建将承载图像填充字形的第一个 XPS 文档。

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## 步骤 2：向第一个文档添加字形

`XpsGlyphs` 定义了一组可以放置在页面上的字形（文本字符）。向第一个文档添加字形，指定字体、大小、样式和位置。

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 步骤 3：使用图像画刷填充字形

`ImageBrush` 用图像绘制区域，允许图案或图片填充形状。使用图像画刷填充字形，图像来源于您的数据目录。

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## 步骤 4：创建第二个 XPS 文档

`XpsDocument` 用于创建可以包含页面、资源和内容的新 XPS 文件。现在，创建将合并来自第一个文档字形的第二个 XPS 文档。

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## 步骤 5：使用第一个文档的字体添加字形

`Font` 表示用于在 XPS 文档中渲染文本的字体。向第二个文档添加字形，使用从第一个文档提取的字体。通过共享字体集合，您可以保持文件体积小并确保视觉一致性。

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## 步骤 6：从第一个文档的填充创建图像画刷

`ImageBrush` 可以从已有的填充创建，以在文档之间复用相同的图像。从第一个文档的填充创建图像画刷，并用它填充第二个文档中的字形。这种“外部图像”技术让您在不复制源文件的情况下复用艺术作品。

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## 步骤 7：保存文档

`Save` 将 XPS 包写入文件，嵌入所有资源。将第一个和第二个 XPS 文档都保存到输出文件夹。`Save` 方法写入 XPS 包，嵌入所有资源并保留图像填充字形。

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## 常见问题及解决方案

| 问题 | 为什么会发生 | 解决方案 |
|------|--------------|----------|
| **图像未出现在字形内部** | `ImageBrush` 使用了错误的 URI，或图像尺寸超出字形边界。 | 核实图像路径，必要时设置 `ImageBrush.Stretch = Stretch.Uniform`。 |
| **第二个文档缺少字体** | 字体资源未从第一个 XPS 导出。 | 在添加字形前使用 `firstDoc.Fonts.SaveTo(secondDoc.Fonts)`。 |
| **大文件导致性能下降** | 为每个字形加载大型图像到内存。 | 重用单个 `ImageBrush` 实例，或在使用前对图像进行降采样。 |

## 常见问题

### 问 1：我可以使用不同的图像格式来填充字形吗？

**答：** 是的，Aspose.Page 支持 PNG、JPEG、BMP、GIF、TIFF 等等——共计超过 25 种格式。

### 问 2：我如何进一步自定义字形的外观？

**答：** 可以探索 `Glyph.Stroke`、`Glyph.FillOpacity`、`Glyph.Transform` 等属性，以调整轮廓、透明度和旋转。

### 问 3：Aspose.Page 适合处理大型文档集吗？

**答：** 当然可以。该库使用流式处理多百页的 XPS 文件，即使是 500 页的文档，内存使用也保持在 100 MB 以下。

### 问 4：我可以对单个字形应用不同的样式吗？

**答：** 是的，每个 `Glyph` 实例都有自己的 `Fill`、`Stroke` 和 `Transform` 属性，支持对单个字形进行样式设置。

### 问 5：使用 Aspose.Page 相比其他 XPS 工具有哪些优势？

**答：** Aspose.Page 支持 25 种以上的图像格式，能够在不完整加载内存的情况下处理高达 500 MB 的文件，并提供 100 % .NET 原生 API——无需 COM 互操作或外部工具。

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [创建 XPS 文档 – Aspose.Page for .NET](/page/net/document-creation/)
- [使用 Aspose.Page for .NET 向 XPS 文档添加图像](/page/net/image-management/add-image-to-xps-document/)
- [使用 Aspose.Page for .NET 添加字形克隆并更改颜色](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}