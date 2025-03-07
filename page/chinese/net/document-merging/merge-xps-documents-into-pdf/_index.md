---
title: 使用 Aspose.Page for .NET 将 XPS 文档合并为 PDF
linktitle: 将 XPS 文档合并为 PDF
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 轻松将 XPS 文档合并为高质量 PDF。请按照我们的分步指南获得流畅的文档转换体验。
weight: 11
url: /zh/net/document-merging/merge-xps-documents-into-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 将 XPS 文档合并为 PDF

## 介绍

在不断发展的文档处理领域，Aspose.Page for .NET 成为将 XPS 文档无缝合并为 PDF 格式的强大工具。本教程将指导您完成整个过程，分解每个步骤，以确保顺利有效地执行。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Page for .NET：确保您已安装 Aspose.Page 库。您可以从以下位置下载：[这里](https://releases.aspose.com/page/net/).

- 文档文件：具有 XPS 文档 (`input.xps`）在您指定的目录中准备好。

## 导入命名空间

在您的 .NET 项目中，包含使用 Aspose.Page 所需的命名空间：

```csharp
using Aspose.Page.XPS;
```

此步骤确保您有权访问文档转换所需的类和方法。

## 第 1 步：初始化流

```csharp
//起始时间：3
//文档目录的路径。
string dataDir = "Your Document Directory";
//初始化 PDF 输出流
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
//初始化XPS输入流
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
//结束：3
```

此步骤涉及设置 XPS 和 PDF 文件的输入和输出流。确保使用正确的路径和文件名。

## 第 2 步：加载 XPS 文档

```csharp
//起始时间：4
//从流中加载 XPS 文档
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
//或直接从文件加载 XPS 文档。则不需要 xpsStream。
//XpsDocument 文档 = new XpsDocument(inputFileName, new XpsLoadOptions());
//结束：4
```

在这里，我们将 XPS 文档加载到`XpsDocument`对象，为进一步处理做好准备。

## 第 3 步：初始化保存选项

```csharp
//起始时间：5
//使用必要的参数初始化选项对象。
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
//结束：5
```

定制`PdfSaveOptions`根据您的喜好指定对象，指定图像压缩、文本压缩和页码等参数。

## 第四步：创建渲染设备

```csharp
//起始时间：6
//创建PDF格式的渲染设备
PdfDevice device = new PdfDevice(pdfStream);
//结束：6
```

这`PdfDevice`是负责将XPS文档渲染为PDF格式的工具。

## 第 5 步：保存文档

```csharp
//起始时间：7
document.Save(device, options);
//结束：7
```

最后，使用渲染设备和指定选项保存文档。

## 结论

恭喜！您已使用 Aspose.Page for .NET 成功将 XPS 文档合并为 PDF。这个无缝过程确保了文档质量和格式的保留。

## 常见问题解答

### 问题 1：我可以将多个 XPS 文件合并为一个 PDF 吗？

 A1: 是的，可以。只需调整`PageNumbers`中的参数`PdfSaveOptions`以包含不同 XPS 文件中的所需页面。

### Q2：Aspose.Page for .NET 是否有临时许可证？

 A2：是的，您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/)用于测试目的。

### Q3：使用Aspose.Page进行文档转换时，文件大小有限制吗？

A3：Aspose.Page for .NET 对文件大小没有严格的限制，但通过合理的文件大小可以获得最佳性能。

### Q4：我可以进一步自定义输出的 PDF，例如添加水印或注释吗？

A4：是的，Aspose.Page for .NET 提供了广泛的 PDF 操作功能。检查高级自定义选项的文档。

### Q5：Aspose.Page for .NET支持跨平台开发吗？

A5：是的，Aspose.Page for .NET 旨在跨各种平台无缝工作。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
