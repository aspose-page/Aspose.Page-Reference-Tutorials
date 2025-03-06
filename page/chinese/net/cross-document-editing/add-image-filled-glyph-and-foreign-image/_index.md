---
title: 使用 Aspose.Page .NET 添加图像填充字形和外部图像
linktitle: 添加图像填充字形和外部图像
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page 释放 .NET 中文档处理的强大功能。轻松添加图像填充的字形。增强视觉效果并简化您的工作流程。
weight: 11
url: /zh/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page .NET 添加图像填充字形和外部图像

## 介绍

在 .NET 开发领域，Aspose.Page 作为处理文档处理任务的强大工具包脱颖而出。本教程将指导您完成使用 Aspose.Page for .NET 添加图像填充字形和合并外部图像的过程。读完本指南后，您将对如何增强文档处理能力有深入的了解。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Page for .NET：确保您已安装 Aspose.Page 库。您可以从以下位置下载：[这里](https://releases.aspose.com/page/net/).

- 开发环境：使用 Visual Studio 或任何其他首选 IDE 设置工作 .NET 开发环境。

- 文档目录：创建一个用于存储文档的目录。在代码示例中，这将被称为“您的文档目录”。

## 导入命名空间

在您的 .NET 应用程序中，首先导入必要的命名空间以访问 Aspose.Page 提供的类和方法：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 步骤 1：创建第一个 XPS 文档

首先使用 Aspose.Page 创建第一个 XPS 文档。本文档将作为添加图像填充字形的基础。

```csharp
//开始时间：1
//文档目录的路径。
string dataDir = "Your Document Directory";

//创建第一个 XPS 文档
XpsDocument doc1 = new XpsDocument();
```

## 步骤 2：将字形添加到第一个文档

将字形添加到第一个文档，指定字体、大小、样式和位置。

```csharp
//将字形添加到第一个文档
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 第 3 步：使用图像画笔填充字形

使用数据目录中的图像，用图像画笔填充字形。

```csharp
//使用图像画笔填充字形
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## 步骤 4：创建第二个 XPS 文档

现在，创建第二个 XPS 文档，该文档将合并第一个文档中的字形。

```csharp
//创建第二个 XPS 文档
XpsDocument doc2 = new XpsDocument();
```

## 步骤 5：使用第一个文档中的字体添加字形

使用第一个文档中的字体将字形添加到第二个文档。

```csharp
//将第一个文档中的字体的字形添加到第二个文档中
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## 第 6 步：从第一个文档的填充中创建图像画笔

从第一个文档的填充中创建图像画笔，并使用它来填充第二个文档中的字形。

```csharp
//从第一个文档的填充创建图像画笔并在第二个文档中填充字形
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## 第7步：保存文档

保存第一个和第二个 XPS 文档。

```csharp
//保存第一个 XPS 文档
doc1.Save(dataDir + "out1.xps");

//保存第二个 XPS 文档
doc2.Save(dataDir + "out2.xps");
//结束：1
```

## 结论

恭喜！您已使用 Aspose.Page for .NET 成功添加了图像填充字形并合并了外部图像。本教程为增强文档处理能力奠定了基础，为富有创意和视觉吸引力的文档开辟了新的可能性。

## 常见问题解答

### Q1：我可以使用不同的图像格式来填充字形吗？

A1：是的，Aspose.Page支持各种图像格式。确保与所选图像格式的兼容性。

### Q2：如何进一步自定义字形的外观？

A2：探索 Aspose.Page 文档以获取微调字形外观的其他属性和方法。

### Q3：Aspose.Page 适合处理大型文档集吗？

A3：Aspose.Page 旨在有效地处理小型和大型文档集。

### Q4：我可以对各个字形应用不同的样式吗？

A4：是的，您可以单独为每个字形自定义样式，提供高度的灵活性。

### Q5：与其他文档处理工具相比，使用Aspose.Page有什么好处？

A5：Aspose.Page 提供了全面的功能、出色的性能和丰富的文档，使其成为许多开发人员的首选。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
