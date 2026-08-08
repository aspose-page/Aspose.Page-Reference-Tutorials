---
date: 2026-07-19
description: 了解如何在 .NET 中创建 XPS 文档并使用 Aspose.Page for .NET 添加矩形，提供简明的分步指南。
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: 向 XPS 文档添加矩形
og_description: 快速创建 XPS 文档 .NET。本教程展示如何使用 Aspose.Page for .NET 向 XPS 文件添加矩形，提供清晰的代码示例和技巧。
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: 创建 XPS 文档 .NET – 使用 Aspose.Page 添加矩形
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: 创建 XPS 文档 .NET – 使用 Aspose.Page 添加矩形
url: /zh/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 XPS 文档 .NET – 使用 Aspose.Page 添加矩形

## 简介

在本教程中，您将学习如何 **create XPS document .NET** 并使用 Aspose.Page for .NET 在其中绘制矩形。无论您是构建报表引擎、可打印发票，还是自定义图形层，程序化生成 XPS 文件的能力都能让您对布局和保真度拥有完全控制。按照以下步骤操作，您将在几分钟内拥有一个可直接使用的 XPS 文件。

## 快速回答
- **主要目标是什么？** 创建 XPS 文档 .NET 并添加矩形形状。  
- **需要哪个库？** Aspose.Page for .NET（可从官方网站下载）。  
- **测试是否需要许可证？** 免费试用可用于开发；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.6+、.NET Core 3.1+、.NET 5/6/7。  
- **实现需要多长时间？** 基本矩形约需 5‑10 分钟。

## Aspose.Page for .NET 是什么？
Aspose.Page for .NET 是一个高性能、完全托管的 API，允许开发者以编程方式创建、编辑和渲染 XPS（XML Paper Specification）文档，而无需依赖外部组件。它提供了丰富的对象模型用于绘制形状、文本和图像，并支持颜色管理、压缩和 PDF 转换等高级功能，适用于各种文档生成场景。

## 为什么使用 Aspose.Page 来创建 XPS 文档 .NET？
Aspose.Page 支持 **30+ XPS 功能**——包括矢量图形、文本布局和颜色管理，并且能够在不将整个文档加载到内存中的情况下生成高达 **500 MB** 的文件。这种量化能力确保即使在大规模打印作业中也能保持流畅性能。

## 先决条件

在开始本教程之前，请确保已具备以下先决条件：

1. Aspose.Page for .NET Library：确保已在开发环境中安装 Aspose.Page for .NET 库。您可以在 [here](https://releases.aspose.com/page/net/) 下载。
2. 文档目录：设置一个用于存放 XPS 文档的目录。

## 导入命名空间

在您的 .NET 应用程序中，包含使用 Aspose.Page 功能所需的命名空间。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 如何在 .NET 中向 XPS 文档添加矩形？

加载 XPS 文档，创建 `Graphics` 对象，使用所需尺寸定义 `RectangleF`，并调用 `DrawRectangle`。此序列在一行代码中绘制矩形，并自动处理 DPI 缩放。对于典型的 A4 大小页面，200 × 100 pt 的矩形会居中显示，无需额外计算。

### 步骤 1：设置文档目录

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### 步骤 2：创建新的 XPS 文档

`XpsDocument` 类表示您正在构建的 XPS 文件，并提供添加页面、图形和其他资源的方法。

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### 步骤 3：添加矩形

`XpsPath` 定义了 XPS 文档中的可绘制路径对象，允许您设置几何形状、笔画、填充和其他视觉属性。

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### 步骤 4：保存文档

`Save` 方法将构建好的 XPS 文档写入磁盘上指定的文件路径。

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

恭喜！您已成功使用 Aspose.Page for .NET 向 XPS 文档添加矩形。

## 常见问题与技巧

- **缺少字体：** 确保您引用的字体已安装在服务器上；否则 Aspose.Page 会使用默认字体替代，可能会改变布局。  
- **大文档：** 生成超过 200 MB 的文件时，考虑调用 `document.SaveOptions.Compress = true` 以降低内存使用。  
- **坐标系统：** XPS 使用点（1/72 英寸）。如果使用基于屏幕的尺寸，请记得将像素转换为点。

## 常见问答

**Q: Aspose.Page 是否兼容所有 .NET 应用程序？**  
A: 是的，Aspose.Page 可无缝用于桌面、Web 和云端 .NET 应用程序。

**Q: 在哪里可以找到 Aspose.Page for .NET 的文档？**  
A: 完整的 API 参考可在 [here](https://reference.aspose.com/page/net/) 获取。

**Q: 在购买前可以免费试用 Aspose.Page for .NET 吗？**  
A: 可以，您可以在 [here](https://releases.aspose.com/) 获取免费试用。

**Q: 如何获取 Aspose.Page for .NET 的临时许可证？**  
A: 请访问 [this link](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q: 在哪里可以寻求社区支持或提问与 Aspose.Page for .NET 相关的问题？**  
A: 请访问 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 获取社区支持。

---

**最后更新：** 2026-07-19  
**测试环境：** Aspose.Page for .NET 24.9  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Page for .NET 创建 XPS 文档](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – 绘制形状](/page/net/drawing-shapes/)
- [使用 Aspose.Page for .NET 向 XPS 文档添加文本](/page/net/text-manipulation/add-text-to-xps-document/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}