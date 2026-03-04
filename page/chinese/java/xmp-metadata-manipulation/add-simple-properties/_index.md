---
date: 2025-12-20
description: 了解如何使用 Aspose.Page for Java 在 EPS 文件中创建 XMP 元数据。一步一步的指南，教您以编程方式添加简单的
  XMP 属性。
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: 如何使用 Java 创建 XMP 元数据 EPS
url: /zh/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP 中添加简单属性

## 介绍
在现代文档工作流中，能够以编程方式 **create XMP metadata EPS** 文件，使您能够完全控制图形的描述、检索和归档方式。使用 Aspose.Page for Java，您可以在不离开 Java 生态系统的情况下读取、修改并写入 EPS 文档中的 XMP 包。本文教程将逐步演示如何向 EPS 文件添加简单的 XMP 属性，让您快速、可靠地为图形添加自定义元数据。

## 快速答案
- **What does “create xmp metadata eps” mean?** 向 EPS 文件添加一个 XMP 包（基于 XML 的元数据）。  
- **Which library is required?** Aspose.Page for Java（可从 Aspose 网站下载）。  
- **Do I need a license for testing?** 免费试用可用于开发；生产环境需要商业许可证。  
- **How many lines of code?** 少于 30 行 Java 代码，加上一些 import 语句。  
- **Can I add other data types?** 是的——支持日期、整数、双精度、字符串，甚至数组。

## 什么是 create xmp metadata eps？
XMP（可扩展元数据平台）是一种在文件内部嵌入丰富元数据的标准。当您 **create XMP metadata EPS** 时，即在 EPS（封装的 PostScript）文档中嵌入一个 XML 包，使下游应用能够读取作者、创建日期、自定义标签等信息。

## 为什么要向 EPS 文件添加 XMP 元数据？
- **Searchability（可检索性）:** 使 DAM 系统能够自动索引。  
- **Compliance（合规性）:** 将法律或许可信息直接存储在文件中。  
- **Automation（自动化）:** 让下游流水线能够基于嵌入的数据做出决策。  
- **Portability（可移植性）:** 元数据随 EPS 一起传播，确保跨平台的一致性。

## 前置条件
在开始之前，请确保您具备：

- 对 Java 编程的基本了解。  
- 已安装 Aspose.Page for Java 库。您可以在 **[here](https://releases.aspose.com/page/java/)** 下载。  
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
我们打开 EPS 文件，创建 `PsDocument` 实例，并检索（或创建）XMP 包。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 步骤 2：添加日期属性
添加日期只需创建一个 `Date` 对象并将其放入 XMP 映射中。

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## 步骤 3：添加整数属性
您可以使用整数值存储数字标识符或版本号。

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## 步骤 4：添加双精度属性
浮点数可用于测量值或评分等场景。

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## 步骤 5：添加字符串属性
自定义文本标签（例如项目代码）以字符串形式存储。

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## 步骤 6：保存更新后的 EPS 文件
所有属性添加完毕后，将文档写回磁盘。

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
始终关闭输入流以避免文件句柄泄漏。

```java
// Close input EPS stream
psStream.close();
```

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **Null XMP metadata** | EPS 文件没有 XMP 包，库无法推断 PS 注释。 | 确保源 EPS 至少包含一个 PS 注释（例如 `%%Creator`）。库会自动生成最小的 XMP 包。 |
| **Time zone mismatch** | 在其他应用中打开时日期出现偏移。 | 在创建 `Date` 对象前调用 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`，如步骤 2 所示。 |
| **License exception** | 运行时抛出 `LicenseException`。 | 在使用 API 前应用有效的 Aspose.Page 许可证，或以试用模式运行进行评估。 |

## 结论
通过上述步骤，您现在已经掌握了使用 Aspose.Page for Java **create XMP metadata EPS** 文件的方式。添加日期、整数、双精度和字符串等简单属性非常直观，生成的 EPS 文件携带丰富、可检索的元数据，能够提升任何下游工作流的效率。

## 常见问题
### 我可以在其他编程语言中使用 Aspose.Page for Java 吗？
Aspose.Page 主要支持 Java，但也提供 .NET 等其他语言的版本。

### Aspose.Page for Java 提供免费试用吗？
是的，您可以通过 [here](https://releases.aspose.com/) 获取免费试用。

### 在哪里可以找到 Aspose.Page for Java 的详细文档？
文档可在 [here](https://reference.aspose.com/page/java/) 查看。

### 如何获取 Aspose.Page for Java 的临时许可证？
可在 [here](https://purchase.aspose.com/temporary-license/) 申请临时许可证。

### 在哪里可以购买 Aspose.Page for Java？
购买链接在 [here](https://purchase.aspose.com/buy)。

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.11（撰写时的最新版本）  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}