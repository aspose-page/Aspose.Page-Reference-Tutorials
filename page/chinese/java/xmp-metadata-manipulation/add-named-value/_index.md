---
date: 2026-09-19
description: 了解如何使用 Aspose.Page for Java 将 XMP 命名值添加到 EPS 文件中——一步一步的指南，附带代码示例。
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: 使用 Java 在 XMP 中添加命名值
og_description: 如何使用 Aspose.Page for Java 将 XMP 命名值添加到 EPS 文件中。遵循此简明指南，即可在几分钟内注入自定义元数据。
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: 如何使用 Java 在 EPS 文件中添加 XMP 命名值
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: 如何使用 Java 在 EPS 文件中添加 XMP 命名值
url: /zh/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中向 XMP 元数据添加命名值

## 介绍
在现代 Java 开发中，学习 **如何添加 XMP** 元数据到 EPS 文件中对于保留文档来源并提升可搜索性至关重要。使用 **Aspose.Page for Java**，您可以轻松将自定义命名值注入 XMP 包。本教程将逐步演示完整的操作步骤——包括代码片段——帮助您立即开始向 EPS 文档添加 XMP 元数据。

## 快速答案
- **需要的库是什么？** Aspose.Page for Java (Aspose)  
- **目标文件类型是什么？** 包含 XMP 元数据的 EPS 文件  
- **主要用例是什么？** 向 XMP 添加自定义命名值（例如，页面大小限制）  
- **先决条件？** JDK 8+ 和 Aspose.Page for Java 库  
- **典型实现时间？** 库设置完成后 5–10 分钟  

## 什么是 asp？
Aspose 是 Aspose 的简称，是一套 API，允许开发者创建、编辑、转换和渲染各种文档格式，而无需外部软件。Aspose.Page for Java 组件专注于 PostScript 和 EPS 处理，提供对页面内容、图形和元数据（如 XMP）的编程访问。

## 为什么向 XMP 元数据添加命名值？
命名值允许您直接在 XMP 包中存储任意键‑值对，使下游工具能够即时读取。这提升了搜索引擎友好性，支持工作流自动化，并通过嵌入合规信息而不改变视觉内容，满足合规要求。

## 为什么这很重要
向 XMP 添加命名值可让您存储任意键‑值对，而无需解析整个 EPS 文件即可读取。这在自动化出版流水线、数字资产管理系统以及以合规为驱动的工作流中尤为有价值，因为元数据驱动下游操作。

## 先决条件
在深入之前，请确保您具备以下条件：

- **Java Development Kit (JDK)：** 在您的机器上已安装的近期 JDK（8 或更高）。  
- **Aspose.Page for Java 库：** 从官方 [Aspose.Page for Java download](https://releases.aspose.com/page/java/) 下载。将 JAR 添加到项目的 classpath 中。  
- **EPS 文件**，该文件已包含 XMP 元数据或将自动生成。

## 导入包
首先导入必要的 Java 包。这些导入为您提供对文件流、EPS 文档模型以及 XMP 处理类的访问。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 如何在 Java 中使用 EPS 文件添加 XMP 命名值
要添加命名值，使用 `FileInputStream` 加载 EPS 文件，获取或创建其 `XmpMetadata` 对象，将所需的 `NamedValue` 插入相应的命名空间，然后使用 `FileOutputStream` 将修改后的文档写回。Aspose.Page 会自动处理缺失的 XMP 包创建，确保新元数据正确嵌入。

### 步骤 1：初始化输入 EPS 文件流
**FileInputStream** 是一个 Java I/O 类，用于从文件读取原始字节。将源 EPS 文件加载到 `FileInputStream` 中。该流将文档传递给 Aspose 的 API。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **专业提示：** 保持 `dataDir` 变量可配置，以便相同代码在不同环境中均可运行。

### 步骤 2：获取 XMP 元数据
**XmpMetadata** 表示与 EPS 文档关联的 XMP 包。检索现有的 XMP 包；如果 EPS 文件缺少该包，Aspose 会从 PS 注释中创建并填充一个新的 XMP 对象。

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### 步骤 3：添加命名值
**NamedValue** 是存储在 XMP 元数据命名空间中的键‑值对。将自定义命名值插入 XMP 结构中。在本例中，我们在 `xmpTPg:MaxPageSize` 命名空间下添加一个新键。

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **为什么这很重要：** 命名值让您存储任意键‑值对，下游应用程序可以在不解析整个文档的情况下读取它们。

### 步骤 4：初始化输出 EPS 文件流
**FileOutputStream** 是一个 Java I/O 类，用于向文件写入原始字节。准备一个 `FileOutputStream` 用于保存修改后的 EPS。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### 步骤 5：保存文档
`save` 方法持久化更改。它将更新后的 XMP 包写回 EPS 文件，确保新命名值成为文档元数据的一部分。

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### 步骤 6：关闭输入 EPS 流
关闭原始文件句柄可防止资源泄漏，并确保文件在后续操作中不被锁定。

```java
psStream.close();
```

通过遵循这六个步骤，您已成功使用 **Aspose.Page for Java** **在 XMP 元数据中添加了命名值**。

## 常见问题与解决方案
| Issue | Cause | Fix |
|-------|-------|-----|
| `xmp` 上的 NullPointerException | EPS 文件没有 XMP，且 Aspose 未能生成 | 确保 EPS 至少包含一个 PS 注释，或手动创建新的 `XmpMetadata` 实例。 |
| 输出文件为空 | 输出流未刷新/关闭 | 验证在 `finally` 块中调用 `outPsStream.close()`（如示例所示）。 |
| 键重复错误 | 相同的命名值被添加了两次 | 在添加之前使用 `xmp.containsNamedValue(...)` 检查键是否已存在。 |

## 常见问题

**Q: 我可以将 Aspose.Page for Java 与其他 Java 库一起使用吗？**  
A: 可以，Aspose.Page for Java 旨在与其他 Java 库无缝协作，为您的开发环境提供灵活性。

**Q: Aspose.Page for Java 有免费试用吗？**  
A: 有，您可以在 [Aspose releases page](https://releases.aspose.com/) 获取 Aspose.Page for Java 的免费试用。

**Q: 如何获取 Aspose.Page for Java 的临时许可证？**  
A: 请访问 [temporary license page](https://purchase.aspose.com/temporary-license/) 获取 Aspose.Page for Java 的临时许可证。

**Q: 在哪里可以找到更多 Aspose.Page for Java 的教程和示例？**  
A: 请查阅 [documentation](https://reference.aspose.com/page/java/) 获取完整的教程和示例。

**Q: Aspose.Page for Java 适合大规模项目吗？**  
A: 绝对适合，Aspose.Page for Java 旨在高效处理大规模项目，提供强大的文档操作能力。

## 结论
本指南演示了 **Aspose.Page for Java** 如何简便地在 EPS 文件的 XMP 元数据中 **添加命名值**。通过上述步骤，您可以为文档添加自定义元数据，提升可搜索性，并实现更智能的下游处理。

---

**最后更新：** 2026-09-19  
**测试环境：** Aspose.Page for Java 24.12（撰写时的最新版本）  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.Page 为 EPS 文件添加 XMP 命名空间 – Java 教程](/page/java/xmp-metadata-manipulation/add-namespace/)
- [使用 Java 向 EPS 文件添加 XMP 元数据](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [使用 Aspose.Page 读取 XMP – Java 指南](/page/java/xmp-metadata-manipulation/get-metadata/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}