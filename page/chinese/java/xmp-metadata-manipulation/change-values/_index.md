---
date: 2026-05-25
description: 了解如何使用 Aspose.Page 在 EPS 文档中使用 Java 修改 XMP。快速且可靠地更新元数据。
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: 使用 Java 更改 XMP 值
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page 修改 XMP – 使用 Java 更改 XMP 值
url: /zh/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 更改 XMP 中的值

## 介绍
如果您正在寻找 **how to modify xmp** 在 EPS 文件中使用 Java 的方法，您来对地方了。本教程将逐步演示——读取现有的 XMP 块，更新如 creator、title 和 modify date 等字段，最后将更改持久化回 EPS 文档。完成后，您将拥有一个可重用的代码片段，可嵌入任何自动化工作流，确保您的文件携带正确的元数据，以用于品牌、合规或搜索引擎索引。

## 快速答案
- **aspose.page modify xmp 的作用是什么？** 它允许您通过 Aspose.Page Java API 读取和写入 EPS 文件中的 XMP 元数据。  
- **需要哪个库版本？** 任何近期的 Aspose.Page for Java 发行版（API 在各版本之间保持稳定）。  
- **运行示例是否需要许可证？** 免费试用可用于评估；生产环境需要商业许可证。  
- **可以一次更改多个 XMP 字段吗？** 可以——在保存文档之前对每个字段调用 `put`。  
- **是否需要时区处理？** 设置默认时区（例如 UTC）可确保日期值一致。  

## XMP 是什么以及为何要修改它？
XMP（可扩展元数据平台）是一种标准化的基于 XML 的格式，用于将丰富的元数据直接嵌入 EPS、PDF 和图像等文件中。更新 XMP 可让您控制文档的索引、显示和搜索方式——这对于品牌一致性、法规合规以及自动化内容流水线至关重要。

## 为什么使用 Aspose.Page for Java？
Aspose.Page 提供了 **全功能、纯 Java API**，无需外部工具或本地库。它支持 **50 多种输入和输出格式**，并且能够在不将整个文档加载到内存中的情况下处理高达 **500 MB** 的 EPS 文件，在任何运行 Java 的操作系统上实现快速、低内存的元数据操作。

## 先决条件
在开始本教程之前，请确保已具备以下先决条件：
1. **Java 开发环境** – JDK（8 或更高）以及您选择的 IDE 或构建工具。  
2. **Aspose.Page for Java 库** – 下载并安装 Aspose.Page for Java 库。您可以在 [here](https://releases.aspose.com/page/java/) 找到所需的包。

## 导入包
首先在您的 Java 项目中导入所需的包。这些包对于与 EPS 文档交互和操作至关重要。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 如何使用 Java 修改 EPS 中的 XMP？
`Document` 是 Aspose.Page 中表示 EPS 文件的类，提供对其内容和元数据的访问。`XmpMetadata` 表示附加到文档的 XMP 块，允许读取和写入元数据字段。`put` 在 XmpMetadata 对象中添加或更新元数据条目。`save` 将修改后的文档（包括任何更新的 XMP 元数据）写入文件。

使用 `new Document("input.eps")` 加载 EPS 文件，获取其 `XmpMetadata` 对象，使用 `put` 更新所需的键，最后调用 `save` 将更改写回新文件。此简洁流程会自动处理缺失的 XMP 块，在需要时从 PostScript 注释创建块，并确保日期的时区一致性。

## 步骤 1：获取 XMP 元数据
`XmpMetadata` 类表示附加到 EPS 文档的 XMP 块。当调用 `document.getXmpMetadata()` 时，API 要么返回现有块，要么从 PS 注释（如 `%%Creator`、`%%CreateDate` 和 `%%Title`）构建一个新块。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## 步骤 2：更改 “ModifyDate” 值
更新 `"ModifyDate"` 条目以反映新的修改时间戳。使用 `java.util.Date` 并结合 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` 来确保存储的值不受时区影响。

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## 步骤 3：更改 “Creator” 值
`"Creator"` 键存储生成 EPS 文件的应用程序或人员的名称。调用 `xmp.put("dc:creator", "Your Company Name")` 将现有值替换为自定义标识符。

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## 步骤 4：更改 “Title” 值
`"Title"` 字段会被许多资产管理系统显示。通过 `xmp.put("dc:title", "New Document Title")` 设置，可确保文档在目录和搜索结果中正确显示。

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## 步骤 5：使用更改的 XMP 元数据保存文档
完成所有修改后，调用 `document.save("output.eps")`。库会将更新的 XMP 块写回 EPS 流，同时保持原始图形内容不变。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 常见问题及解决方案
- **缺少 XMP 块** – API 会自动从 PS 注释创建一个，但如果需要也可以手动实例化 `XmpMetadata`。  
- **时区不匹配** – 在创建 `Date` 对象之前始终设置 `TimeZone.setDefault`，以避免意外的偏移。  
- **文件访问错误** – 确保输入和输出路径正确，并且您的应用程序具有读写权限。  

## 常见问题
**Q:** 如何在修改 XMP 值时处理时区问题？  
**A:** 使用 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` 以确保时区设置的一致性。

**Q:** 我可以在一次操作中更改多个 XMP 值吗？  
**A:** 可以，通过对每个所需值使用 `put` 方法，您可以同时修改多个 XMP 值。

**Q:** 在哪里可以找到 Aspose.Page for Java 的更多文档？  
**A:** 请访问完整的文档 [here](https://reference.aspose.com/page/java/)。

**Q:** Aspose.Page for Java 是否提供免费试用？  
**A:** 有，您可以在 [here](https://releases.aspose.com/) 获取免费试用。

**Q:** 如何获取 Aspose.Page for Java 的临时许可证？  
**A:** 请在 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q:** 修改 XMP 会影响 EPS 的视觉内容吗？  
**A:** 不会。XMP 更改仅为元数据，不会改变 EPS 文件的图形元素。

**Q:** 我可以通过编程方式读取更新后的值以验证更改吗？  
**A:** 当然——在保存并关闭文档之前，只需调用 `xmp.get("dc:creator")`（或相应的键）即可。

## 结论
恭喜！您已经掌握了使用 Aspose.Page for Java 在 EPS 文档中 **how to modify xmp** 值的技巧。通过嵌入准确的 creator、title 和 modify‑date 元数据，您可以确保资产可搜索、合规，并符合品牌标准。欢迎将此模式集成到批处理流水线、CI/CD 步骤或任何自动化文档生成工作流中。

---

**最后更新：** 2026-05-25  
**测试环境：** Aspose.Page for Java (latest release)  
**作者：** Aspose

## 相关教程

- [Aspose Page Java 教程 – 向 EPS 文件添加 XMP 元数据](/page/java/xmp-metadata-manipulation/add-metadata/)
- [如何使用 Java 读取 XMP 元数据 – Aspose.Page 指南](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - 使用 Java 更改 XMP 中的数组项](/page/java/xmp-metadata-manipulation/change-array-items/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}