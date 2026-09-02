---
date: 2026-05-20
description: 了解如何使用 Aspose.Page for Java 向 EPS 文件添加 XMP 元数据。一步一步的指南，帮助您以编程方式嵌入简单的
  XMP 属性。
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: 使用 Java 在 XMP 中添加简单属性
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: 使用 Java 为 EPS 文件添加 XMP 元数据
url: /zh/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 向 EPS 文件添加 XMP 元数据

## 介绍
在现代图形流水线中，能够以编程方式 **添加 XMP 元数据** 到 EPS 文件，使您能够完全控制插图的描述、搜索和归档方式。使用 Aspose.Page for Java，您可以在不离开 Java 生态系统的情况下读取、修改和写入 EPS 文档中的 XMP 包。本文教程将逐步演示如何向 EPS 文件添加简单的 XMP 属性，让您能够快速、可靠地为图形添加自定义元数据。

## 快速答案
- **“add XMP metadata to EPS” 是什么意思？** 将 XMP 包（基于 XML 的元数据）嵌入 EPS 文件中。  
- **需要哪个库？** Aspose.Page for Java（可从 Aspose 网站下载）。  
- **测试是否需要许可证？** 免费试用可用于开发；生产环境需要商业许可证。  
- **代码行数是多少？** 少于 30 行 Java 代码，加上一些 import 语句。  
- **可以添加其他数据类型吗？** 可以——支持日期、整数、双精度、字符串，甚至数组。  

## 如何使用 Java 向 EPS 文件添加 XMP 元数据？
使用 `new PsDocument("input.eps")` 加载 EPS 文件，获取或创建其 XMP 包，插入所需属性，然后将文档保存回磁盘——全部代码不超过十行 Java。此方法可让您在不手动编辑 EPS 源文件的情况下嵌入可搜索、符合标准的元数据。

## EPS 中的 XMP 元数据是什么？
EPS 中的 XMP 元数据是位于 EPS 文件内部的 XML 包，用于存储作者、创建日期和自定义标签等信息。嵌入此包可让下游工具读取并利用这些数据，而无需单独的伴随文件。

## 为什么要向 EPS 文件添加 XMP 元数据？
嵌入 XMP 元数据可使 EPS 资产立即可搜索，通过在文件中存储许可信息确保合规性，使自动化流水线能够根据嵌入的标签做出决策，并保证元数据随图形在所有平台上一起传递。Aspose.Page 能在不将整个文档加载到内存的情况下处理高达 500 MB 的文件，为大规模工作负载提供快速性能。

## 先决条件
在开始之前，请确保您拥有：

- 对 Java 编程的基本了解。  
- Aspose.Page for Java 库已安装。您可以在 **[here](https://releases.aspose.com/page/java/)** 下载。  
- 一个包含元数据的示例 EPS 文件。如果没有，可使用提供的 **`xmp3.eps`** 文件。

## 导入包
首先，导入所需的类。导入语句与原示例完全相同：

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

## 步骤 1：加载 EPS 文档并获取 XMP 元数据
`PsDocument` 类表示 EPS 文件，并提供访问其内容和元数据的方法。  
`XmpMetadata` 对象保存与文档关联的 XMP 包。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 步骤 2：添加 Date 属性
`Date` 类表示具有毫秒精度的特定时间点。

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## 步骤 3：添加 Integer 属性
`Integer` 类将原始的 `int` 值包装为对象。

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## 步骤 4：添加 Double 属性
`Double` 类将原始的 `double` 值包装为对象。

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## 步骤 5：添加 String 属性
`String` 类表示字符序列。

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## 步骤 6：保存更新后的 EPS 文件
`save` 方法将修改后的文档写回磁盘，保持 EPS 结构。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 步骤 7：清理资源
始终关闭流以避免文件句柄泄漏，并确保所有缓冲区被刷新。

```java
// Close input EPS stream
psStream.close();
```

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **空的 XMP 元数据** | EPS 文件没有 XMP 包，库无法推断 PS 注释。 | 确保源 EPS 至少包含一个 PS 注释（例如 `%%Creator`）。库将自动生成最小的 XMP 包。 |
| **时区不匹配** | 在其他应用程序中打开时日期出现偏移。 | 在创建 `Date` 对象之前，设置 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`，如步骤 2 所示。 |
| **许可证异常** | 运行时抛出 `LicenseException`。 | 在使用 API 前应用有效的 Aspose.Page 许可证，或以试用模式运行进行评估。 |

## 常见问题
**Q: 我可以在其他编程语言中使用 Aspose.Page for Java 吗？**  
A: Aspose.Page 主要支持 Java，但 .NET、C++ 和 Python 也有相应的库。

**Q: Aspose.Page for Java 有免费试用吗？**  
A: 有，您可以通过获取免费试用 **[here](https://releases.aspose.com/)** 来探索 Aspose.Page 的功能。

**Q: 在哪里可以找到 Aspose.Page for Java 的详细文档？**  
A: 文档可在 **[here](https://reference.aspose.com/page/java/)** 获取。

**Q: 如何获取 Aspose.Page for Java 的临时许可证？**  
A: 可在 **[here](https://purchase.aspose.com/temporary-license/)** 获取临时许可证。

**Q: 在哪里可以购买 Aspose.Page for Java？**  
A: 您可以在 **[here](https://purchase.aspose.com/buy)** 购买该产品。

**最后更新：** 2026-05-20  
**测试环境：** Aspose.Page for Java 24.12 (latest at time of writing)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Java 读取 XMP 元数据 – Aspose.Page 指南](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page XMP 教程 – 使用 Java 在 XMP 中添加命名空间](/page/java/xmp-metadata-manipulation/add-namespace/)
- [使用 Java 向 XMP 元数据添加数组项](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}