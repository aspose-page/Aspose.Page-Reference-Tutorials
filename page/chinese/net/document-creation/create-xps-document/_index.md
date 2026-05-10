---
date: 2026-01-12
description: 学习如何使用 Aspose.Page for .NET 创建 XPS 文档——一步步指南，生成高质量的电子文档。
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 创建 XPS 文档
url: /zh/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 创建 XPS 文档

## 介绍

欢迎阅读我们的分步指南，了解如何使用 Aspose.Page for .NET **创建 XPS 文档**。在本教程中，我们将探讨生成 XPS 文件的过程，这是一种广泛使用的电子文档格式。无论您是经验丰富的开发者还是刚刚接触 Aspose.Page，本指南都旨在帮助您通过清晰的示例和详细的说明，轻松创建 XPS 文档。

## 快速答案
- **需要哪个库？** Aspose.Page for .NET  
- **可以在 .NET Core 上运行吗？** 是的，该库完全支持 .NET Core 和 .NET 5/6  
- **需要多少行代码？** 少于 20 行即可生成基本的 XPS 文件  
- **测试需要许可证吗？** 提供免费试用版；生产环境需要许可证  
- **输出的格式是什么？** XPS（XML Paper Specification）  

## 使用 Aspose.Page for .NET 创建 XPS 文档的步骤

下面您将找到开始编码前所需的所有内容，随后是一段简明的编号步骤说明。

## 前提条件

在深入教程之前，请确保已满足以下前提条件：

1. Aspose.Page for .NET 库：从[下载链接](https://releases.aspose.com/page/net/)下载并安装 Aspose.Page 库。  
2. 文档目录：在系统上选择或创建一个目录，用于保存输出的 XPS 文件。

现在，让我们开始教程！

## 导入命名空间

为了在 .NET 中使用 Aspose.Page，您需要在项目中导入必要的命名空间。请按照以下步骤操作：

### 步骤 1：添加 Aspose.Page 引用

在项目中，添加对 Aspose.Page for .NET 库的引用。所需的 DLL 位于下载的包中。

### 步骤 2：导入命名空间

在代码文件中包含以下命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

现在我们已经完成前提条件的设置并导入了必要的命名空间，接下来将把创建 XPS 文档的过程拆分为多个步骤。

## 步骤 1：设置文档目录

```csharp
string dir = "Your Document Directory";
```

请将 `"Your Document Directory"` 替换为您希望保存输出 XPS 文件的实际路径。

## 步骤 2：创建 XPS 文档

```csharp
XpsDocument xDocs = new XpsDocument();
```

使用 `XpsDocument` 类初始化一个新的 XPS 文档。

## 步骤 3：向文档添加字形

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

使用 `AddGlyphs` 方法向文档添加字形（文本）。根据需要自定义字体、大小、样式和位置。

## 步骤 4：设置字形填充颜色

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

指定已添加字形的填充颜色。在本例中使用黑色，您也可以选择其他颜色。

## 步骤 5：保存结果

```csharp
xDocs.Save(dir + "output.xps");
```

最后，将 XPS 文档保存到指定目录并使用所需的文件名。生成的 XPS 文件将包含 "Hello World!" 文本。

恭喜！您已成功使用 Aspose.Page for .NET 创建了 XPS 文档。

## 常见提示与注意事项

- **目录路径** – 使用 `Path.Combine(dir, "output.xps")` 以避免在不同操作系统上缺少路径分隔符。  
- **字体可用性** – 您指定的字体必须已安装在运行代码的机器上；否则，Aspose 将使用默认字体进行替代。  
- **多页文档** – 若要创建多页 XPS 文件，请实例化额外的 `XpsPage` 对象，并在保存之前向每页添加内容。

## 结论

在本教程中，我们演示了使用 Aspose.Page for .NET 创建 XPS 文档的整个过程。该强大的库提供了一种轻松生成电子文档的无缝方式。尝试不同的字体、样式和内容，以根据您的具体需求定制 XPS 文件。

## 常见问题

### Q1: 我可以在 XPS 文档中使用自定义字体吗？

A1: 可以，在向 XPS 文档添加字形时，您可以指定字体族和大小。

### Q2: Aspose.Page 与 .NET Core 兼容吗？

A2: 可以，Aspose.Page 支持 .NET Core，您可以在跨平台应用中使用它。

### Q3: 如何向 XPS 文档添加图像？

A3: Aspose.Page 提供了向 XPS 文档添加图像的方法。请参阅文档获取详细示例。

### Q4: 我可以创建多页 XPS 文档吗？

A4: 当然可以！您可以使用 Aspose.Page 库向 XPS 文档添加多个页面。

### Q5: 是否提供试用版？

A5: 可以，您可以通过下载[免费试用版](https://releases.aspose.com/)来体验 Aspose.Page 的功能。

---

**最后更新：** 2026-01-12  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}