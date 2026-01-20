---
date: 2026-01-20
description: 使用 Aspose.Page for .NET，轻松在合并 XPS 文档为高质量 PDF 的同时添加页码。请按照我们的分步指南将 XPS
  转换为 PDF。
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: 在 PDF 中添加页码 – 使用 Aspose.Page 合并 XPS 为 PDF
url: /zh/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 添加页码 PDF – 使用 Aspose.Page 合并 XPS 为 PDF

## 介绍

如果您在合并 XPS 文件时需要 **添加页码 PDF**，Aspose.Page for .NET 可以让整个过程轻松无忧。在本教程中，我们将演示一个完整的、可投入生产的示例，展示如何将 XPS 文档转换为高质量 PDF，控制图像压缩，并自动在最终 PDF 中插入页码。完成后，您将拥有一个可在任何 C# 项目中直接使用的代码片段。

## 快速回答
- **合并 XPS 为 PDF 时可以添加页码吗？** 可以 – `PdfSaveOptions.PageNumbers` 属性正是为此设计的。  
- **哪个库负责转换？** Aspose.Page for .NET。  
- **生产环境需要许可证吗？** 需要有效的 Aspose.Page 许可证；测试时可使用临时许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6+。  
- **可以输出高质量图像吗？** 完全可以 – 将 `JpegQualityLevel` 设置为 100 并选择 `PdfImageCompression.Jpeg`。

## 前置条件

在开始教程之前，请确保已满足以下前置条件：

- Aspose.Page for .NET：确保已安装 Aspose.Page 库。您可以从 [here](https://releases.aspose.com/page/net/) 下载。  
- 文档文件：准备好位于指定目录下的 XPS 文档（`input.xps`）。

## 导入命名空间

在您的 .NET 项目中，添加使用 Aspose.Page 所需的命名空间：

```csharp
using Aspose.Page.XPS;
```

此步骤确保您能够访问文档转换所需的类和方法。

## 如何在合并 XPS 文档时添加页码 PDF

`PdfSaveOptions.PageNumbers` 集合允许您精确指定哪些页面（或页面范围）应出现在输出的 PDF 中。只需将所需的页码填入集合，Aspose.Page 即会自动插入相应的页码。

### 步骤 1：初始化流

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

此步骤用于为 XPS 和 PDF 文件设置输入输出流。请确保使用正确的路径和文件名。

### 步骤 2：加载 XPS 文档

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

在这里，我们将 XPS 文档加载到 `XpsDocument` 对象中，为后续处理做好准备。

### 步骤 3：初始化保存选项（合并 XPS 为 PDF）

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

根据您的需求自定义 `PdfSaveOptions` 对象，指定图像压缩、文本压缩以及希望在最终 PDF 中出现的 **页码**。将 `JpegQualityLevel` 设置为 100 可确保 **高质量 PDF 图像**。

### 步骤 4：创建渲染设备

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` 是负责将 XPS 文档渲染为 PDF 格式的工具。

### 步骤 5：保存文档（C# XPS 转 PDF）

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

最后，使用渲染设备和指定的选项保存文档。输出的 PDF 将包含选定的页面，并自动添加页码。

## 为什么选择 Aspose.Page 进行此转换？

- **可靠性** – 处理复杂的 XPS 特性而不失真。  
- **性能** – 基于流的处理避免将整个文件加载到内存。  
- **灵活性** – 对图像质量、压缩和页码提供细粒度控制。  
- **跨平台** – 在 Windows、Linux 和 macOS 上均可使用 .NET Core。

## 常见问题及解决方案

| 问题 | 解决方案 |
|-------|----------|
| **输出的 PDF 为白页** | 确认 XPS 文件路径正确且文件未损坏。 |
| **页码未出现** | 确保 `PageNumbers` 设置了正确的零基页索引（例如 `new int[] {1,2,6}`）。 |
| **图像质量低** | 提高 `JpegQualityLevel` 并选择 `PdfImageCompression.Jpeg`。 |
| **大型 XPS 文件导致内存压力** | 将 XPS 分块处理或增加应用程序的内存限制。 |

## 常见问答

### Q1: 能否将多个 XPS 文件合并为一个 PDF？

A1: 可以。只需在 `PdfSaveOptions` 的 `PageNumbers` 参数中包含不同 XPS 文件的所需页面，或顺序加载每个 XPS 并在同一个 `PdfDevice` 上调用 `document.Save`。

### Q2: 是否提供 Aspose.Page for .NET 的临时许可证？

A2: 是的，您可以在 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证用于测试。

### Q3: 使用 Aspose.Page 进行文档转换时对文件大小有何限制？

A3: Aspose.Page for .NET 对文件大小没有严格限制，但在文件尺寸适中的情况下可获得最佳性能。对于非常大的 XPS 文档，建议使用流式处理以降低内存消耗。

### Q4: 我可以进一步自定义输出的 PDF，例如添加水印或批注吗？

A4: 可以，Aspose.Page for .NET 提供丰富的 PDF 操作功能。转换后，您可以使用 Aspose.PDF 库添加水印、批注或其他增强功能。

### Q5: Aspose.Page for .NET 是否支持跨平台开发？

A5: 支持，Aspose.Page for .NET 设计为可在 Windows、Linux 和 macOS 上无缝运行，配合 .NET Core 或 .NET 5/6 使用。

---

**最后更新：** 2026-01-20  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}