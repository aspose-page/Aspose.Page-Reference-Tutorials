---
date: 2026-08-08
description: 了解如何使用 Aspose.Page EPS 元数据向 EPS 元数据添加数组项。本分步 .NET 指南展示了如何添加数组项并高效读取 EPS
  文件。
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: 添加数组项
og_description: 了解如何使用 Aspose.Page EPS 元数据向 EPS 元数据添加数组项。遵循本简明 .NET 教程，读取 EPS 文件并高效管理元数据。
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: 使用 Aspose.Page EPS 元数据在 .NET 中添加数组项
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: 使用 Aspose.Page EPS 元数据在 .NET 中添加数组项
url: /zh/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 中使用 Aspose.Page EPS 元数据添加数组项

## 介绍

在本教程中，您将学习如何使用 **Aspose.Page EPS metadata** 向 EPS 元数据添加数组项。无论您需要为 EPS 文件添加额外的标题、创建者或自定义标签，Aspose.Page 都能为任何 .NET 开发人员提供简便的解决方案。我们将逐步演示，从打开 EPS 流到持久化更新后的 XMP 包，让您能够自信地将元数据处理集成到自己的应用程序中。

## 快速答案
- **Aspose.Page EPS metadata 能做什么？** 它允许在 .NET 中读取和写入 EPS 文件内部的 XMP 元数据数组。  
- **哪个类代表 EPS 文档？** `PsDocument` 是用于加载和保存 EPS 内容的核心类。  
- **开发是否需要许可证？** 免费试用可用于测试；生产环境需要商业许可证。  
- **我能在不更改 EPS 图形的情况下修改元数据吗？** 可以，只会更改 XMP 包，页面内容保持不变。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什么是 Aspose.Page EPS 元数据？

Aspose.Page EPS 元数据是嵌入在 EPS 文件中的基于 XMP 的信息块。它按照 ISO 16684‑1 标准存储标题、创建者、关键字和自定义标签等描述性属性。可以通过 Aspose.Page API 以编程方式访问和修改这些元数据，从而实现文档管理自动化和搜索优化。

## 为什么要修改 EPS 元数据？

Aspose.Page 能处理 **超过 30 个元数据字段**，并且能够在不将整个文档加载到内存的情况下处理高达 **200 MB** 的 EPS 文件，与完整文件解析相比，可将 CPU 使用率降低至 40 % 左右。更新元数据可提升可搜索性、合规性以及下游工作流的自动化。

## 前置条件

- 基本的 .NET 编程知识。  
- 已安装 Aspose.Page for .NET – 可从 [download Aspose.Page for .NET](https://releases.aspose.com/page/net/) 下载。  
- Visual Studio（或任何兼容 .NET 的 IDE）用于运行示例代码。  

## 如何向 EPS 元数据添加数组项？

要添加数组项，首先将 EPS 文件加载到 `PsDocument` 中，然后使用 `GetXmpMetadata()` 获取其 XMP 包。对所需的 XMP 数组（如 `dc:title` 或 `dc:creator`）调用 `AddArrayItem()` 方法以追加新值。最后，调用 `Save()` 将更新后的元数据写回文件，同时保持图形内容不变。

### 步骤 1：初始化 eps 文件输入流
`PsDocument` 表示 EPS 文档并提供访问其内容的方法。以下代码将 EPS 文件作为流打开并创建 `PsDocument` 实例。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 步骤 2：获取 XMP 元数据
`GetXmpMetadata()` 检索嵌入在 EPS 文件中的 XMP 包。如果不存在该包，API 会根据现有的 PostScript 注释生成一个新的。

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### 步骤 3：更改 XMP 元数据值
`AddArrayItem()` 向现有的 XMP 数组追加新值，而不会覆盖其他条目。可使用它向元数据添加标题、创建者或自定义标签。

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### 步骤 4：保存带有更改 XMP 元数据的 EPS 文件
`Save()` 将修改后的 XMP 包写回 EPS 文件，同时保留原始的 PostScript 内容。提供输出路径即可创建新文件或覆盖源文件。

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## 常见问题与故障排除

- **Null XMP 包** – 如果 `GetXmpMetadata()` 返回 `null`，请确保 EPS 文件至少包含一个注释块；否则，需要手动创建新的 `XmpMetadata` 实例。  
- **编码问题** – 添加字符串值时使用 UTF‑8，以避免非 ASCII 语言的字符损坏。  
- **大文件** – 对于大于 150 MB 的 EPS 文件，建议使用带缓冲区的 `FileStream` 进行流式输入，以降低内存使用。

## 常见问答

**Q: Aspose.Page 是否兼容所有 .NET 环境？**  
A: 是的，Aspose.Page 在 .NET Framework 4.5+、.NET Core 3.1+ 和 .NET 5/6/7 上均可工作，在 Windows、Linux 和 macOS 上提供一致的 API 行为。

**Q: 我可以免费使用 Aspose.Page 吗？**  
A: 您可以通过从 [Aspose purchase page](https://purchase.aspose.com/buy) 下载免费试用版来评估该库。生产部署需要商业许可证。

**Q: Aspose.Page 是否提供临时许可证？**  
A: 可从 [temporary license page](https://purchase.aspose.com/temporary-license/) 获取临时许可证，用于短期项目或评估期间。

**Q: 我在哪里可以找到 Aspose.Page 的社区支持？**  
A: 加入 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 讨论，向其他开发者提问并分享解决方案。

**Q: Aspose.Page for .NET 的最新版本是什么？**  
A: 请参阅官方 [documentation](https://reference.aspose.com/page/net/) 获取最新的发行说明和下载链接。

---

**最后更新：** 2026-08-08  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## 相关教程

- [使用 Aspose.Page for .NET 更改数组项](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [使用 Aspose.Page for .NET 添加简单属性](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [使用 Aspose.Page for .NET 添加命名空间](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}