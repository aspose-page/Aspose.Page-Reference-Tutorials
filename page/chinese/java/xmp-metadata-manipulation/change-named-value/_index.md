---
date: 2026-05-15
description: 了解如何使用 Aspose.Page for Java 编辑 XMP 元数据以及如何在 EPS 文件中更改 XMP 值——清晰的分步指南。
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: 使用 Java 更改 XMP 中的命名值
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何编辑 XMP – 使用 Java 更改 XMP 中的命名值
url: /zh/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何编辑 XMP – 使用 Java 更改 XMP 中的命名值

在现代文档工作流中，**Aspose.Page for Java** 使得在 EPS 文件中读取、编辑和写入 XMP 元数据变得轻而易举。**本教程展示了如何编辑 XMP** 元数据，使用 Aspose.Page API，帮助您保持文档信息的准确、可搜索并符合行业标准。无论是更新页面尺寸、作者信息还是自定义标签，下面的步骤都将引导您在 Java 中完成此过程。

## 快速答案
- **本教程涵盖什么内容？** 使用 Aspose.Page for Java 在 EPS 文件中更改命名的 XMP 值。  
- **需要哪个库版本？** 任意最近的 Aspose.Page for Java 发行版（该 API 已稳定多年）。  
- **是否需要许可证？** 生产环境需要临时或完整许可证；免费试用可用于测试。  
- **实现需要多长时间？** 对熟悉 Java I/O 的开发者大约需要 10‑15 分钟。  
- **可以在其他文件格式中使用吗？** XMP API 也可用于 PDF、SVG 以及 Aspose.Page 支持的其他格式。

## 什么是 XMP 元数据？
XMP（可扩展元数据平台）是一种基于 XML 的标准化格式，用于将丰富的元数据（如创建者、标题和自定义属性）直接嵌入文件中。在 EPS 文档中，XMP 与传统的 PostScript 注释并存，使得应用程序能够在不更改可视内容的情况下读取和修改元数据。

## 为什么使用 Aspose.Page for Java 来编辑 XMP？
Aspose.Page 为您提供对 **150 多个 XMP 架构属性的完整控制**，并在 EPS、PDF 和 SVG 等格式中保持一致的工作方式。它能够处理高达 **500 MB** 的文件而无需将整个文档加载到内存中，并且内置验证可确保生成的 EPS 符合标准。无需外部 XML 解析器或本机库。

## 介绍
Aspose.Page for Java 是一个强大的库，帮助处理和操作 EPS 文件。在这些文件中处理 XMP 元数据时，Aspose.Page 为开发者提供了全面的功能集。在本教程中，我们将重点介绍如何更改 XMP 中的命名值，为希望提升文档处理能力的开发者提供清晰简明的指南。

## 先决条件
在深入教程之前，请确保具备以下先决条件：
1. **Java 开发环境** – JDK（8 或更高）以及 IDE 或构建工具（Maven/Gradle）。  
2. **Aspose.Page for Java 库** – 下载并将 Aspose.Page for Java 库集成到项目中。您可以在[此处](https://reference.aspose.com/page/java/)找到库及详细文档。  
3. **示例 EPS 文件** – 准备好用于实验的示例 EPS 文件。如果没有，可使用提供的示例文件 **"xmp4.eps."**

## 导入包
`import` 语句将必要的 Aspose.Page 类引入作用域。

`PsDocument` 类是 Aspose.Page 的核心对象，表示内存中的 EPS 文档。  
`XmpMetadata` 类提供对嵌入 EPS 文件的 XMP 包的访问。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 如何编辑 XMP 元数据？
加载 EPS 文件，获取其 XMP 包，修改所需属性，然后保存文档——全部只需几行简洁代码。此方法适用于任何命名的 XMP 值，无论是标准的 Dublin Core 字段还是您自定义的命名空间。

## 步骤 1：初始化输入 EPS 文件流
`FileInputStream` 打开指向源 EPS 文件的只读流，使 Aspose.Page 能够在不锁定文件系统的情况下读取文档。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## 步骤 2：初始化 PsDocument
`PsDocument` 是封装 EPS 内容的主要对象，并提供对其元数据、页面和资源的访问。

```java
PsDocument document = new PsDocument(psStream);
```

## 步骤 3：获取 XMP 元数据
`XmpMetadata` 表示 EPS 文件中的 XMP 包，并提供读取、修改或删除单个属性的方法。

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 步骤 4：在 XMP 中设置新值
`setProperty` 在元数据包中设置指定 XMP 属性的值。

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## 步骤 5：初始化输出 EPS 文件流
`FileOutputStream` 创建用于保存修改后 EPS 文件的可写流。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## 步骤 6：保存带有更改 XMP 元数据的文档
`save` 将内存中的 PsDocument（包括更新后的 XMP）写入输出流。

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 步骤 7：关闭输入 EPS 流
`close` 释放文件句柄并清理与输入流关联的资源。

```java
// Close input EPS stream
psStream.close();
```

## 常见问题及解决方案
- **FileNotFoundException** – 验证 `dataDir` 指向正确的文件夹，并且 `xmp4.eps` 存在。  
- **LicenseException** – 如果出现许可证错误，请确保在创建 `PsDocument` 之前加载了有效的 Aspose.Page 许可证文件。  
- **Metadata Not Updated** – 保存后，在元数据查看器（例如 Adobe Bridge）中打开生成的 EPS，确认新值已出现。

## 常见问答
**Q: 我可以在其他编程语言中使用 Aspose.Page for Java 吗？**  
A: Aspose.Page 主要支持 Java，但 Aspose 提供了 .NET、C++ 和 Python 等等价库，具备类似的 XMP 操作功能。

**Q: Aspose.Page for Java 有免费试用吗？**  
A: 有，您可以在[此处](https://releases.aspose.com/)体验 Aspose.Page for Java 的免费试用。

**Q: 我在哪里可以找到关于 Aspose.Page for Java 的更多支持和讨论？**  
A: 请访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39)获取社区支持和讨论。

**Q: 如何获取 Aspose.Page for Java 的临时许可证？**  
A: 您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

**Q: 我在哪里可以购买 Aspose.Page for Java？**  
A: 要购买 Aspose.Page for Java，请访问 [购买页面](https://purchase.aspose.com/buy)。

---

**最后更新:** 2026-05-15  
**已测试:** Aspose.Page for Java (latest release)  
**作者:** Aspose

## 相关教程

- [如何使用 Java 读取 XMP 元数据 – Aspose.Page 指南](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java 教程 – 向 EPS 文件添加 XMP 元数据](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page 修改 xmp – 使用 Java 更改 XMP 中的值](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}