---
date: 2025-12-21
description: 学习如何使用 Java 和 Aspose.Page 读取 XMP 元数据。本分步指南向您展示如何读取文档格式的 XMP 并提取关键属性。
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: 如何使用 Java 读取 XMP 元数据 – Aspose.Page 指南
url: /zh/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 获取 XMP 元数据

## 如何使用 Java 读取 XMP 元数据

欢迎阅读我们的分步教程，展示 **如何使用 Java 和 Aspose.Page 库读取 XMP** 元数据。XMP（可扩展元数据平台）是一项广泛采用的标准，用于在文档中嵌入丰富的元数据。阅读完本指南后，您将能够读取文档格式的 XMP，提取创建者信息、时间戳、缩略图等，从而构建更智能的文档分析解决方案。

## 快速答疑
- **“how to read xmp” 是什么意思？** 指的是以编程方式从文件中提取 XMP 元数据。  
- **需要哪个库？** Aspose.Page for Java（可从 Aspose 下载页面获取）。  
- **是否需要许可证？** 生产环境需要临时或正式许可证；提供免费试用。  
- **支持的 Java 版本？** Java 8 或更高。  
- **可以读取其他格式的 XMP 吗？** 可以，Aspose.Page 能处理 EPS、PDF 以及多种嵌入 XMP 的图像格式。

## 前置条件
在编写代码之前，请确保您已具备：

- **Java Development Kit (JDK)** – 已在机器上安装并配置 Java 8+。  
- **Aspose.Page for Java** – 从官方站点[此处](https://releases.aspose.com/page/java/)下载库。  
- 一个包含 XMP 元数据的 EPS 文件（例如 `xmp1.eps`）。  

## 导入包
在您的 Java 项目中导入必要的包：
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 步骤 1：初始化输入 EPS 文件流
设置文档目录路径并初始化输入 EPS 文件流。
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## 步骤 2：获取 XMP 元数据
从 EPS 文件中检索 XMP 元数据。如果文件缺少 XMP 元数据，将根据 PS 元数据注释生成一个新的 XMP。
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## 步骤 3：提取 CreatorTool 信息
检查并打印 XMP 元数据中的 “CreatorTool” 值。
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## 步骤 4：提取 CreateDate 信息
检查并打印 XMP 元数据中的 “CreateDate” 值。
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## 步骤 5：获取缩略图宽度
如果存在缩略图，提取并打印第一张缩略图的宽度。
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## 步骤 6：提取 Format 信息
检查并打印 XMP 元数据中的 “format” 值。
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## 步骤 7：获取 DocumentID
检查并打印 XMP 元数据中的 “DocumentID” 值。
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## 为什么这很重要
读取 XMP 元数据可以让您在不打开查看器的情况下，程序化地发现文档的来源、创建日期以及其他关键属性。这对于批量处理、内容管理系统和数字资产流水线尤为重要，因为元数据驱动索引和搜索。

## 常见陷阱与技巧
- **缺失 XMP：** 某些 EPS 文件可能不包含 XMP。`getXmpMetadata()` 调用会基于现有的 PS 注释合成一个最小集合，但除非嵌入完整的 XMP，否则无法获得全部元数据。  
- **缩略图数组：** `xmp:Thumbnails` 键可以包含多个条目。示例仅提取第一张，如需全部缩略图，请遍历该数组。  
- **命名空间意识：** XMP 键使用命名空间（例如 `xmp:`、`dc:`），请确保引用完整的键名，否则 `containsKey` 将返回 false。

## 常见问题解答
### 我可以在其他编程语言中使用 Aspose.Page for Java 吗？
可以，Aspose.Page 支持多种语言，包括 Java、.NET 等。详情请查阅[文档](https://reference.aspose.com/page/java/)。

### Aspose.Page for Java 是否提供免费试用？
是的，您可以在[此处](https://releases.aspose.com/)获取免费试用。

### 在哪里可以找到 Aspose.Page for Java 的支持？
访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)获取社区支持。

### 如何获取 Aspose.Page for Java 的临时许可证？
您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### 是否有其他资源可供 Aspose.Page for Java 使用？
请浏览完整的[文档](https://reference.aspose.com/page/java/)并在[此处](https://releases.aspose.com/page/java/)下载库。

## 其他 FAQ
**问：此方法能否用于包含 XMP 的 PDF 文件？**  
答：可以，Aspose.Page 能读取 PDF、EPS 以及多种图像格式中的 XMP。

**问：读取后我可以修改 XMP 元数据吗？**  
答：完全可以。`XmpMetadata` 对象是可变的，您可以添加、更新或删除键，然后保存文档。

**问：有没有办法提取所有缩略图图像，而不仅仅是尺寸？**  
答：可以从每个缩略图条目的 `xmpGImg:data` 属性中获取二进制数据并写入文件。

## 结论
您已经掌握了使用 Java 和 Aspose.Page **读取 XMP** 元数据的全部步骤。通过这些操作，您可以提取创建工具、时间戳、缩略图、格式信息和文档 ID，从而全面了解 EPS 文件中嵌入的元数据。欢迎尝试更多 XMP 命名空间，以获取更丰富的数据来服务您的应用。

---

**最后更新：** 2025-12-21  
**测试环境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
