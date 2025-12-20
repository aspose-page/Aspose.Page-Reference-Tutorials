---
date: 2025-12-20
description: 学习如何使用 Aspose Page Java 教程向 EPS 文件添加 XMP 元数据。按照本分步指南提升您的文档管理。
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java 教程 – 向 EPS 文件添加 XMP 元数据
url: /zh/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP 中添加元数据

## Introduction
在本 **aspose page java tutorial** 中，您将学习如何使用 Java 为文档的元数据添加 XMP 信息。此分步指南将带您阅读现有的 EPS 文件，提取其 XMP 元数据，并使用 Aspose.Page for Java 库将更改保存回磁盘。教程结束时，您将拥有一个在任何 EPS 工作流中处理 XMP 的可靠、可复用模式。

## Quick Answers
- **需要的库是什么？** Aspose.Page for Java  
- **我可以向任何 EPS 文件添加 XMP 吗？** 是的——如果不存在，API 会创建一个新的 XMP 块。  
- **开发是否需要许可证？** 免费试用可用于评估；生产环境需要商业许可证。  
- **支持哪个 Java 版本？** Java 8 及更高版本。  
- **实现大约需要多长时间？** 对于基本的元数据更新，通常在 10 分钟以内。

## Aspose Page Java Tutorial Overview
本教程演示了在 EPS 文件中操作 XMP 元数据所需的核心步骤。了解这些步骤将帮助您将元数据处理集成到更大的文档处理流水线中，提高可检索性，并符合数字资产管理的行业标准。

## Prerequisites
在开始教程之前，请确保您具备以下前提条件：
- 基本的 Java 编程知识。  
- 已安装 Aspose.Page for Java 库。您可以在[此处](https://releases.aspose.com/page/java/)下载。  
- 您想要修改的 EPS 文件。

## Import Packages
首先，将必要的包导入到您的 Java 程序中：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Step 1: Get XMP Metadata
步骤 1：获取 XMP 元数据

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

将 `"Your Document Directory"` 替换为实际存放文档的路径。

## Step 2: Retrieve CreatorTool Value
步骤 2：检索 CreatorTool 值

```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Step 3: Retrieve CreateDate Value
步骤 3：检索 CreateDate 值

```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Step 4: Retrieve Title Value
步骤 4：检索 Title 值

```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Step 5: Retrieve Format Value
步骤 5：检索 Format 值

```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Step 6: Retrieve Creator Value
步骤 6：检索 Creator 值

```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Step 7: Retrieve MetadataDate Value
步骤 7：检索 MetadataDate 值

```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Step 8: Save Document with New XMP Metadata
步骤 8：使用新的 XMP 元数据保存文档

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

最后，别忘了关闭输入的 EPS 流：

```java
// Close input EPS stream
psStream.close();
```

现在，您已成功使用 Aspose.Page for Java 为 EPS 文件添加了元数据！

## Conclusion
在本 **aspose page java tutorial** 中，我们探讨了如何使用 Aspose.Page for Java 库向 EPS 文件添加 XMP 元数据。这个强大的 API 让您能够以编程方式操作文档元数据，帮助您保持资产的组织性和可检索性。

## Frequently Asked Questions

**Q: Aspose.Page for Java 可以免费使用吗？**  
A: Aspose.Page for Java 是商业产品。您可以通过免费试用[此处](https://releases.aspose.com/)了解其功能。

**Q: 在哪里可以找到 Aspose.Page for Java 的文档？**  
A: 文档可在[此处](https://reference.aspose.com/page/java/)获取。

**Q: 如何获取 Aspose.Page for Java 的临时许可证？**  
A: 您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

**Q: Aspose.Page for Java 支持哪些文件格式？**  
A: Aspose.Page for Java 支持多种格式，包括 EPS、PDF 和 XPS。

**Q: 我可以购买 Aspose.Page for Java 吗？**  
A: 可以，您可在[此处](https://purchase.aspose.com/buy)购买。

**Q: 在添加元数据时，如何处理大型 EPS 文件？**  
A: 如示例所示，以流式方式处理文件以降低内存使用，并及时关闭流。

**Q: 我可以修改已有的 XMP 字段，而不仅仅是读取它们吗？**  
A: 当然可以——您可以在保存前使用 `xmp.put(key, value)` 来更新或添加新条目。

---

**最后更新：** 2025-12-20  
**测试环境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}