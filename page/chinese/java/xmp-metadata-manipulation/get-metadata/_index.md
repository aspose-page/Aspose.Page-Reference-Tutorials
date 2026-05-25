---
date: 2026-05-25
description: 了解如何使用 Aspose.Page 在 Java 中读取 XMP。本分步指南展示了提取 XMP 元数据、创建者信息、时间戳、缩略图等内容。
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: 如何使用 Java 读取 XMP 元数据
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: 使用 Aspose.Page 读取 XMP – Java 指南
url: /zh/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 获取 XMP 元数据

## 如何使用 Aspose.Page (Java) 读取 XMP？

使用 `new Document("file.eps")` 加载 EPS 文件——`Document` 类表示已加载的文件。调用 `getXmpMetadata()`，它会提取 XMP 包，然后查询返回的 `XmpMetadata` 对象——一个类似映射的 XMP 属性接口，以获取所需的键。这就是使用 Aspose.Page 读取 XMP 所需的全部步骤。API 抽象了底层解析，因此只需两行代码即可获得可直接使用的属性映射。

欢迎阅读我们的分步教程，展示如何使用 Java 和 Aspose.Page 库 **读取 XMP** 元数据。XMP（可扩展元数据平台）是广泛采用的在文档中嵌入丰富元数据的标准。阅读完本指南后，您将能够读取文档格式的 XMP，提取创建者信息、时间戳、缩略图等——帮助您构建更智能的文档分析解决方案。

## 快速答案
- **“读取 XMP” 是什么意思？** 它指的是以编程方式提取存储在文件中的 XMP 包。  
- **需要哪个库？** Aspose.Page for Java（从官方页面[here](https://releases.aspose.com/page/java/)下载）。  
- **我需要许可证吗？** 在生产环境中需要临时或完整许可证；免费试用可用于评估。  
- **支持哪个 Java 版本？** Java 8 或更高版本。  
- **我可以从其他格式读取 XMP 吗？** 可以——Aspose.Page 可从 EPS、PDF、JPEG、PNG 以及超过 20 种其他格式中提取 XMP。  

## 前提条件
在深入代码之前，请确保您拥有：

- **Java Development Kit (JDK)** – 已在您的机器上安装并配置 Java 8+。  
- **Aspose.Page for Java** – 从官方站点[here](https://releases.aspose.com/page/java/)下载库。  
- 包含 XMP 元数据的 EPS 文件（例如 `xmp1.eps`）。  

## 导入包
`XmpMetadata` 类位于 `com.aspose.page.xmp` 命名空间，而 `Document` 类位于 `com.aspose.page`。导入两者以便处理 EPS 文件及其元数据。  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 步骤 1：初始化输入 EPS 文件流
首先设置文档目录的路径并初始化输入 EPS 文件流。  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## 步骤 2：获取 XMP 元数据
`XmpMetadata` 是 Aspose.Page 用于保存从文档中提取的 XMP 包的对象。使用 `document.getXmpMetadata()` 获取它。如果文件缺少 XMP，API 会根据现有的 PostScript 注释合成一个最小的包。  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## 步骤 3：提取 CreatorTool 信息
`CreatorTool` 键位于 `xmp` 命名空间下，记录生成文件的应用程序。检查其是否存在并打印其值。  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## 步骤 4：提取 CreateDate 信息
`CreateDate` 保存文档最初创建的时间戳。使用相同的 `containsKey`/`get` 模式读取它。  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## 步骤 5：获取缩略图宽度
如果存在缩略图，`xmp:Thumbnails` 数组会包含一个或多个条目。每个条目包含 `width`、`height` 和二进制数据。示例提取第一个缩略图的宽度。  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## 步骤 6：提取格式信息
`format` 键告诉您原始文件格式（例如 “application/postscript”）。在需要记录或验证源类型时，这非常有用。  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## 步骤 7：获取 DocumentID
`DocumentID` 是由创建应用程序分配的唯一标识符。它可用于大型资产库中的去重。  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## 为什么这很重要
Aspose.Page 能够从 **20+** 种文件格式读取 XMP，并且在处理高达 **500 MB** 的文档时无需将整个文件加载到内存中，为您提供快速、低开销的关键元数据访问。此功能对于批处理流水线、数字资产管理系统以及任何依赖可搜索、机器可读文档属性的解决方案都至关重要。

## 常见陷阱与技巧
- **缺少 XMP：** 某些 EPS 文件可能不包含 XMP。`getXmpMetadata()` 调用会根据现有的 PS 注释合成一个最小集合，但除非嵌入了完整的元数据，否则您无法获得全部元数据。  
- **缩略图数组：** `xmp:Thumbnails` 键可以包含多个条目。示例仅提取第一个；如果需要所有缩略图，请遍历数组。  
- **命名空间意识：** XMP 键使用命名空间（例如 `xmp:`、`dc:`）。确保引用准确的键名，否则 `containsKey` 将返回 false。  

## 常见问题
### 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？
是的，Aspose.Page 支持 Java、.NET 以及其他多种语言。完整列表请参阅[文档](https://reference.aspose.com/page/java/)。

### Aspose.Page for Java 是否提供免费试用？
是的，您可以在[此处](https://releases.aspose.com/)获取免费试用。

### 在哪里可以找到 Aspose.Page for Java 的支持？
请访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)获取社区帮助和官方支持。

### 如何获取 Aspose.Page for Java 的临时许可证？
您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### 是否有 Aspose.Page for Java 的其他资源？
请查阅完整的[文档](https://reference.aspose.com/page/java/)，并在[此处](https://releases.aspose.com/page/java/)下载库。

## 附加常见问题
**Q: 这种方法适用于包含 XMP 的 PDF 文件吗？**  
A: 是的，Aspose.Page 可以从 PDF、EPS 以及多种图像格式中读取 XMP。

**Q: 读取后我可以修改 XMP 元数据吗？**  
A: 当然可以。`XmpMetadata` 对象是可变的；您可以添加、更新或删除键，然后保存文档。

**Q: 有办法提取所有缩略图图像，而不仅仅是尺寸吗？**  
A: 您可以从每个缩略图条目的 `xmpGImg:data` 属性中获取二进制数据并写入文件。

## 结论
您现在已经掌握了使用 Java 和 Aspose.Page **读取 XMP** 元数据的方法。通过遵循这些步骤，您可以提取创建工具、时间戳、缩略图、格式信息和文档 ID——全面了解 EPS 文件中嵌入的元数据。欢迎尝试使用其他 XMP 命名空间，以获取更丰富的数据用于您的应用程序。

---

**最后更新：** 2026-05-25  
**测试环境：** Aspose.Page for Java 24.12 (latest)  
**作者：** Aspose

## 相关教程

- [Aspose Page Java 教程 – 向 EPS 文件添加 XMP 元数据](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page XMP 教程 – 使用 Java 在 XMP 中添加命名空间](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page XMP 教程 – 使用 Java 更改 XMP 中的命名值](/page/java/xmp-metadata-manipulation/change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}