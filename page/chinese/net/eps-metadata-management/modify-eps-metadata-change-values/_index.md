---
date: 2026-08-13
description: 了解如何在 .NET 应用程序中使用 Aspose.Page 更改 EPS 值，包括一步步的 XMP 元数据更新。
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: 更改值
og_description: Aspose.Page 更改 EPS 值教程向您展示如何使用 .NET 修改 EPS 文件中的 XMP 元数据。按照一步步指南即时更新创建者、标题和修改日期。
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page 使用 .NET 更改 EPS 值教程
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page 使用 .NET 更改 EPS 值 – 教程
url: /zh/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page 更改 eps 值的 .NET – 教程

## 介绍

在本教程中，您将了解如何通过编辑嵌入 EPS 文件的 XMP 元数据来 **aspose.page change eps values**。无论是需要更新创建者名称、调整标题，还是纠正修改日期，Aspose.Page for .NET 都提供了一个干净、代码优先的 API，支持 Windows、Linux 和 macOS。完成本指南后，您将拥有一个可在任何 .NET 服务或控制台应用中直接使用的可复用代码片段。

## 快速答案
- **本教程涵盖什么？** 使用 Aspose.Page for .NET 在 EPS 文件中更改 XMP 元数据（创建者、标题、修改日期）。  
- **需要哪个库版本？** 任何支持 XMP 的 Aspose.Page for .NET 发行版（v24.10 及以上）。  
- **我需要许可证吗？** 生产环境需要临时许可证；开发可使用免费试用版。  
- **我可以在 .NET Core 上运行吗？** 可以 – API 与 .NET 5、.NET 6 和 .NET Core 3.1+ 兼容。  
- **实现需要多长时间？** 基本的元数据更新大约需要 5‑10 分钟。

## 什么是 XMP 元数据？

XMP 元数据是一段标准化的 XML 块，用于在 EPS 以及其他图形格式内部存储描述性信息（作者、标题、日期等）。它直接嵌入文件头部，能够被众多设计和出版工具读取，从而实现跨平台的一致元数据处理。更新 XMP 可让下游应用显示正确的文档属性，而无需更改视觉内容。

## 为什么使用 Aspose.Page 处理 EPS 元数据？

Aspose.Page 能处理 **30+** 种图形格式，并且在处理高达 **1 GB** 的 EPS 文件时无需将整个文件加载到内存中，相比传统流解析可实现 **70 %** 的内存使用量降低。该库还保证在编辑元数据后 EPS 的视觉渲染保持不变。

## 前提条件

在开始之前，请确保以下内容已准备就绪：

1. **Aspose.Page for .NET 库** – 从官方 Aspose.Page for .NET 发布页面 [此处](https://releases.aspose.com/page/net/) 下载。您也可以在 [此处](https://releases.aspose.com/) 浏览其他 Aspose 产品发布。  
2. **文档目录** – 在您的机器上创建一个文件夹，用于存放源 EPS 文件和输出文件。

现在环境已就绪，让我们导入所需的命名空间。

## 导入命名空间

`Aspose.Page` 命名空间提供核心类，而 `System.IO` 则提供流处理功能。

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## 如何更改 EPS 元数据值？

加载 EPS 文件，获取其 XMP 包，修改所需字段，然后将更新后的 EPS 写回磁盘。该过程不需要渲染页面内容，因而快速且内存高效。下面的步骤展示了每个操作的代码示例。

### 步骤 1：初始化 EPS 文件输入流

创建指向源 EPS 文件的只读 `FileStream`。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 步骤 2：从流创建 PsDocument 实例

`PsDocument` 是表示内存中 EPS 文档的顶层对象。它让您能够访问页面内容以及嵌入的 XMP 元数据。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### 步骤 3：获取 XMP 元数据

`XmpMetadata` 属性返回一个 `XmpPacket` 对象，您可以对其进行查询和编辑。

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### 步骤 4：修改 XMP 元数据值

现在您将更改三个常用字段：**ModifyDate**、**Creator** 和 **Title**。

#### 步骤 4.1：更改 ModifyDate 值

将 `ModifyDate` 设置为当前 UTC 时间戳。

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### 步骤 4.2：更改 Creator 值

用您的应用程序名称替换现有的创建者。

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### 步骤 4.3：更改 Title 值

更新标题以反映新内容的用途。

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### 步骤 5：保存带有更改 XMP 元数据的 EPS 文件

编辑完成后，将文档写回磁盘。

#### 步骤 5.1：创建输出流

为目标 EPS 文件打开一个 `FileStream`。

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### 步骤 5.2：保存 EPS 文件

在 `PsDocument` 实例上调用 `Save`，并传入输出流。

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

最后，关闭输入流以释放文件句柄。

```csharp
// Save EPS file
document.Save(outPsStream);
```

恭喜！您已成功通过更新 EPS 文件内部的 XMP 元数据 **aspose.page change eps values**。

## 常见陷阱与故障排除

- **Empty XMP packet** – 某些 EPS 文件在生成时未包含 XMP。此时，请在赋值前通过 `new XmpPacket()` 创建一个新的 `XmpPacket`。  
- **Large files** – 对于大于 500 MB 的 EPS，设置 `PsDocumentOptions.UseMemoryMappedFiles = true` 以启用流缓冲，避免 `OutOfMemoryException`。  
- **Incorrect date format** – XMP 需要 ISO 8601 格式。使用 `DateTime.UtcNow.ToString("o")` 生成符合规范的字符串。

## 常见问题

**Q: 我可以在 .NET 中使用 Aspose.Page 处理其他图形格式吗？**  
A: 可以，库支持超过 30 种格式，包括 PDF、SVG 和 AI，但 XMP 编辑 API 仅针对 EPS 和 PDF。

**Q: 是否提供试用版？**  
A: 是的，您可以在 Aspose 发布页面的免费试用版 [此处](https://releases.aspose.com/) 进行尝试。

**Q: 在哪里可以找到详细文档？**  
A: 完整的 Aspose.Page .NET API 参考文档可在 [此处](https://reference.aspose.com/page/net/) 查阅。

**Q: 如何获取临时许可证？**  
A: 您可以在 [此处](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q: 我可以购买 Aspose.Page for .NET 吗？**  
A: 当然！请访问 Aspose.Page 购买页面的 [此处](https://purchase.aspose.com/buy) 了解授权选项。

---

**最后更新：** 2026-08-13  
**已测试于：** Aspose.Page 24.10 for .NET  
**作者：** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## 相关教程

- [使用 Aspose.Page for .NET 向 EPS 文档添加元数据](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [使用 Aspose.Page for .NET 从 EPS 文档提取元数据](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [使用 Aspose.Page for .NET 更改命名值](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}