---
date: 2026-01-07
description: 学习如何使用 Aspose.Page 在 .NET 中创建 XPS 文档。本指南展示了添加图像填充的字形和外部图像，以实现更丰富的文档视觉效果。
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 在 .NET 中创建 XPS 文档 – 图像填充字形与外部图像
url: /zh/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 创建 XPS 文档 .NET – 图像填充字形与外部图像

## 介绍

如果您需要 **create XPS document .NET** 应用程序看起来精致专业，Aspose.Page 为您提供将图像直接嵌入字形并在文档之间复用图形资源的工具。在本教程中，我们将演示如何构建两个 XPS 文件，将字形填充为图像画刷，然后在第二个文档中复用该画刷。完成后，您将了解此方法为何能节省内存、简化样式，并为报告、发票或任何可打印内容打开创意可能性。

## 快速答案
- **本教程涵盖什么内容？** 使用 Aspose.Page for .NET 添加图像填充字形并在 XPS 文档之间复用。  
- **目标的主要关键词是什么？** `create xps document .net`.  
- **先决条件？** .NET 开发环境、Aspose.Page for .NET，以及用于存放 XPS 文件的文件夹。  
- **实现需要多长时间？** 大约 10‑15 分钟即可完成可运行的原型。  
- **我可以使用其他图像格式吗？** 可以——任何 .NET `System.Drawing.Image` 支持的格式。

## 先决条件

在深入代码之前，请确保以下内容已准备好：

- **Aspose.Page for .NET** – 从 [here](https://releases.aspose.com/page/net/) 下载最新库。  
- **开发环境** – Visual Studio 2022（或任何支持 .NET 6+ 的 IDE）。  
- **文档目录** – 在机器上创建一个文件夹，用于保存输入图像和生成的 XPS 文件；在代码片段中我们将其称为 **Your Document Directory**。

## 导入命名空间

首先引入处理 XPS 对象和绘图工具所需的命名空间。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 步骤指南

### 步骤 1：创建第一个 XPS 文档

我们首先实例化一个空的 XPS 文档，用于承载图像填充的字形。

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### 步骤 2：向第一个文档添加字形

接下来，添加一个字形（文本字符），稍后我们将使用图像画刷填充它。

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### 步骤 3：使用图像画刷填充字形

这里我们从数据目录中的 TIFF 文件创建 `ImageBrush` 并将其应用于字形。画刷设置为平铺模式，如果字形区域大于图像尺寸，图像将重复。

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### 步骤 4：创建第二个 XPS 文档

现在我们创建第二个 XPS 文档，以复用第一个文档中的字形样式和图像画刷。

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### 步骤 5：使用第一个文档的字体添加字形

我们向第二个文档添加字形，复用第一个文档中的同一字体对象。这确保两个文件的视觉一致性。

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### 步骤 6：从第一个文档的填充创建图像画刷

我们不再重新加载图像，而是克隆 `glyphs1` 的画刷并分配给 `glyphs2`。这展示了如何在 **create XPS document .NET** 工作流中高效共享资源。

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### 步骤 7：保存文档

最后，将两个 XPS 文件保存到磁盘。现在可以使用任何 XPS 查看器打开它们，查看图像填充字形的效果。

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## 为什么在创建 XPS 文档 .NET 时使用图像填充字形？

- **视觉冲击** – 将普通文本转换为图形丰富的元素，而无需对整页进行光栅化。  
- **资源复用** – 在多个文档之间共享画刷和字体，降低内存占用。  
- **灵活性** – 平铺、拉伸或旋转图像画刷，以实现自定义图案或品牌标识。

## 常见问题与技巧

- **文件路径错误** – 确保 `dataDir` 以适合您操作系统的路径分隔符（`\` 或 `/`）结尾。  
- **不受支持的图像格式** – Aspose.Page 最适合 TIFF、PNG 和 JPEG。使用前请转换其他格式。  
- **TileMode 未生效** – 在设置 `TileMode` 前确认已将对象强制转换为 `XpsImageBrush`；否则该属性会被忽略。

## 常见问答

### 问题 1：我可以使用不同的图像格式来填充字形吗？

**答：** 可以，Aspose.Page 支持 TIFF、PNG、JPEG、BMP 和 GIF。只需在 `CreateImageBrush` 调用中提供正确的文件扩展名。

### 问题 2：我如何进一步自定义字形的外观？

**答：** 可探索 `XpsGlyphs` 的其他属性，如 `Opacity`、`RenderTransform` 和 `Stroke`，以微调渲染效果。

### 问题 3：Aspose.Page 适合处理大批量文档吗？

**答：** 绝对可以。该库针对高性能场景进行优化，能够在批处理作业中处理成千上万的 XPS 文件。

### 问题 4：我可以为单个字形应用不同的样式吗？

**答：** 可以。每个 `XpsGlyphs` 实例都可以拥有自己的填充、描边和变换，从而实现细粒度控制。

### 问题 5：使用 Aspose.Page 相比其他文档处理工具有哪些优势？

**答：** Aspose.Page 提供完整的、免许可证的 XPS 创建、操作和转换 API，拥有丰富的文档和 24/7 支持。

---

**最后更新：** 2026-01-07  
**测试环境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}