---
title: 使用 Aspose.Page for .NET 将 XPS 转换为 PDF
linktitle: 将 XPS 转换为 PDF
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page 在 .NET 中轻松将 XPS 转换为 PDF。下载库、浏览文档并获得免费试用。
type: docs
weight: 11
url: /zh/net/document-conversion/convert-xps-to-pdf/
---
## 介绍

在本教程中，我们将深入研究使用强大的 Aspose.Page for .NET 库将 XPS（XML 纸张规范）文档转换为 PDF（便携式文档格式）的过程。 Aspose.Page for .NET 提供了一组强大的功能来处理 XPS 文件，使开发人员能够通过各种自定义选项将其无缝转换为 PDF 格式。

## 先决条件

在我们开始此转换之旅之前，请确保您具备以下先决条件：

-  Aspose.Page for .NET 库：确保您的开发环境中安装了 Aspose.Page for .NET 库。您可以从[Aspose.Page 文档](https://reference.aspose.com/page/net/).

- 开发环境：使用 Visual Studio 或任何其他兼容的 IDE 设置 .NET 开发环境。

- XPS 文档：准备要转换为 PDF 的 XPS 文档。这可能是存储在指定目录中的示例 XPS 文件。

## 导入命名空间

在深入研究代码之前，让我们导入必要的命名空间，以使 Aspose.Page for .NET 功能可以在我们的代码中访问：

```csharp
using Aspose.Page.XPS;
```

## 第1步：初始化文档目录

```csharp
string dataDir = "Your Document Directory";
```

将“您的文档目录”替换为包含 XPS 文档的目录的路径。

## 步骤 2：初始化 PDF 和 XPS 流

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

打开输出 PDF 文件和输入 XPS 文件的流。确保您设置了适当的文件路径。

## 第 3 步：加载 XPS 文档

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

使用 Aspose.Page for .NET 库加载 XPS 文档。

## 步骤 4：初始化 PDF 保存选项

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

设置 PDF 保存选项，包括 JPEG 质量级别、图像压缩、文本压缩和要包含的特定页码等参数。

## 第5步：创建PDF渲染设备

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

使用 Aspose.Page for .NET 库创建 PDF 格式的渲染设备。

## 第 6 步：将文档保存为 PDF

```csharp
document.Save(device, options);
```

使用指定的渲染设备和选项将 XPS 文档保存为 PDF。

## 结论

恭喜！您已使用 Aspose.Page for .NET 成功将 XPS 文档转换为 PDF。这个多功能库为开发人员提供了强大的工具集，可以轻松处理各种文档格式。

## 常见问题解答

### 问题 1：我可以使用 Aspose.Page for .NET 将多个 XPS 文件转换为单个 PDF 吗？

A1：是的，您可以循环浏览多个 XPS 文件，并按照相同的步骤将它们合并为单个 PDF。

### Q2：Aspose.Page for .NET 是否支持其他输出格式？

A2：是的，Aspose.Page for .NET 支持各种输出格式，包括 TIFF、JPEG、PNG 等。

### Q3：如何自定义转换后的PDF文档的外观？

A3：您可以调整选项对象参数，例如图像压缩和文本压缩，以获得所需的外观。

### Q4：Aspose.Page for .NET 有试用版吗？

 A4：是的，您可以通过获取免费试用版来探索 Aspose.Page for .NET 的功能[这里](https://releases.aspose.com/).

### 问题 5：在哪里可以获得 Aspose.Page for .NET 的社区支持？

 A5：访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)供社区讨论和支持。