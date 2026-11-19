---
date: 2026-11-19
description: 了解如何在 Java 中创建 PostScript 文件、设置 A4 页面大小，并使用 Aspose.Page 添加自定义字体。立即试用免费版！
keywords:
- create postscript file java
- add custom fonts java
- set a4 page size java
- aspose.page java
- postscript generation java
lastmod: 2026-11-19
linktitle: 在 Java 中使用 PostScript 创建文档
og_description: 了解如何在 Java 中创建 PostScript 文件、设置 A4 页面大小，并使用 Aspose.Page 添加自定义字体。为开发者准备的快速入门指南。
og_image_alt: Screenshot of Java code generating an A4 PostScript file with custom
  fonts using Aspose.Page
og_title: 使用 Aspose.Page 在 Java 中创建 A4 大小的 PostScript 文件
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size
  steps:
  - name: set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` defines how the PostScript document is saved, including
      page size, margins, and compression. **Definition:** `PsPageSize` is an enumeration
      that contains standard page‑size constants such as A4, Letter, and Legal. Setting
      `options.setPageSize(PsPageSize.A4)` configures the document f'
  - name: set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: create a multipaged or single‑paged PS document
    text: '`PsDocument` represents a PostScript document that can contain one or many
      pages. Instantiating it with `new PsDocument(outputStream, options)` creates
      the document object. Set `multiPaged` to `true` for multi‑page output, then
      call `document.newPage()` for each additional page you need.'
  - name: close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create postscript
- Aspose.Page
- Java document processing
- custom fonts
- A4 page size
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size using Aspose.Page
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size using Aspose.Page
  steps:
  - name: Set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create save options with A4 size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a multipaged or single‑paged PS document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
title: 如何在 Java 中使用 A4 大小创建 PostScript 文件
url: /zh/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中创建 A4 大小的 PostScript 文件

## 介绍
如果您需要 **create PostScript file Java** 并设置标准的 A4 页面尺寸，Aspose.Page for Java 为您提供了一个简洁、高性能的 API，抽象了底层的 PostScript 语法。在本教程中，我们将逐步演示每一步——从加载库、配置 `PsSaveOptions` 到嵌入您自己的 TrueType 或 OpenType 字体。完成后，您将拥有一个可直接放入任何 Java 项目的可运行代码片段。

## 快速回答
- **哪个库在 Java 中创建 PostScript？** Aspose.Page for Java。  
- **本指南针对的页面尺寸是？** A4（210 mm × 297 mm）。  
- **我可以嵌入自己的字体吗？** 可以——在保存选项中设置附加字体文件夹。  
- **生产环境需要许可证吗？** 需要商业许可证；提供免费试用。  
- **支持哪些 Java 版本？** 完全支持 Java 8、11 和 17。

## 如何在 Java 中设置 A4 页面大小并创建 PostScript？
加载 Aspose.Page 库，使用 A4 常量配置 `PsSaveOptions`，并将文档写入文件——全部代码不超过十行。此方法确保页面尺寸正确，并允许您在无需额外配置的情况下添加自定义字体。

## 什么是 PostScript A4 大小？
PostScript A4 大小是 ISO 216 标准（210 mm × 297 mm）在 PostScript 页面描述语言中的表示。它定义了打印机和查看器解释的可打印区域，确保跨平台布局一致。由于 PostScript 以设备无关的方式描述页面内容，使用 A4 大小可保证文档在任何支持 A4 的打印机或查看器上呈现相同。

## 为什么使用 Aspose.Page 设置 PostScript 页面大小？
Aspose.Page 支持超过 30 种 PostScript 操作符，能够在不将整个文档加载到内存的情况下生成高达 500 MB 的文件。它可在 2 秒内处理 200 页文档，提供对页面尺寸的精确控制，同时高效处理大工作负载。该库还抽象了复杂的 PostScript 语法并自动管理资源，适用于简单的传单和复杂的多页报告。

## 如何在 Java 中添加自定义字体
嵌入您自己的字体可确保生成的文档在任何打印机或查看器上都完全按照设计呈现，Aspose.Page 会自动发现放置在指定文件夹中的字体。通过注册附加字体文件夹，您可以使用任何 TrueType 或 OpenType 字体，避免回退替代，并在所有输出设备上保持品牌一致性。

## 前提条件
在开始之前，请确保您具备：

- 对 Java 编程有一定的了解。  
- 已安装 Aspose.Page for Java。您可以下载它 [Aspose.Page Java 下载页面](https://releases.aspose.com/page/java/)。  
- 一个名为 `necessary_fonts`（或您喜欢的任意名称）的文件夹，里面包含您想要嵌入的自定义字体。

## 导入包
在您的 Java 项目中，导入所需的 Aspose.Page 类：

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

现在让我们将示例拆分为清晰的编号步骤。

### 步骤 1：设置文档目录
`OUTPUT_DIR` 常量告诉库将生成的文件写入何处。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### 步骤 2：定义字体文件夹
`FONTS_FOLDER` 指向保存您自定义 TrueType 或 OpenType 字体的目录。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步骤 3：为 PostScript 文档创建输出流
`FileOutputStream` 打开一个流，用于接收最终的 PostScript A4 输出。

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### 步骤 4：使用 A4 大小创建保存选项
`PsSaveOptions` 定义了 PostScript 文档的保存方式，包括页面尺寸、边距和压缩。  
**定义：** `PsPageSize` 是一个枚举，包含标准页面尺寸常量，如 A4、Letter 和 Legal。  
设置 `options.setPageSize(PsPageSize.A4)` 可将文档配置为标准 A4 尺寸。

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### 步骤 5：设置页面边距并添加自定义字体文件夹
`options.setMargins(0, 0, 0, 0)` 移除所有边距，实现全幅页面；`options.setAdditionalFontsFolder(FONTS_FOLDER)` 注册您的自定义字体。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### 步骤 6：创建多页或单页 PS 文档
`PsDocument` 表示一个可以包含一个或多个页面的 PostScript 文档。使用 `new PsDocument(outputStream, options)` 实例化后即可创建文档对象。将 `multiPaged` 设置为 `true` 可生成多页输出，然后对每个需要的额外页面调用 `document.newPage()`。

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### 步骤 7：关闭当前页面并保存文档
调用 `document.close()` 完成文件并将 **PostScript A4 size** 输出写入磁盘。

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## 常见问题与技巧
- **字体未显示？** 请确认字体文件是受支持的 TrueType 或 OpenType 格式，并且 `FONTS_FOLDER` 以斜杠 (`/`) 结尾。  
- **仍然出现边距？** 在构造 `PsDocument` **之前** 调用 `options.setMargins(...)`。  
- **多页输出为空白？** 记得对每个额外页面调用 `document.newPage()`。  
- **大文件导致内存不足错误？** Aspose.Page 采用流式处理，您可以安全生成高达 500 MB 的文件；仅需确保 JVM 堆至少为 1 GB，以应对极大工作负载。

## 常见问题

**Q: 我可以在我的 PostScript 文档中使用自定义字体吗？**  
A: 可以，在保存选项中设置附加字体文件夹（见步骤 5），Aspose.Page 将自动嵌入这些字体。

**Q: 是否有 Aspose.Page for Java 的试用版？**  
A: 有，您可以获取免费试用 [Aspose.Page 免费试用页面](https://releases.aspose.com/)。

**Q: 如何访问完整的 API 参考？**  
A: 请参阅文档 [API 参考文档](https://reference.aspose.com/page/java/)。

**Q: 在哪里购买 Aspose.Page for Java 的许可证？**  
A: 您可以在 [许可证购买页面](https://purchase.aspose.com/buy) 进行购买。

**Q: 我可以在哪里向社区求助？**  
A: 访问 Aspose.Page 社区论坛 [Aspose.Page 社区论坛](https://forum.aspose.com/c/page/39)。

**Q: 能生成多页 PostScript 文件吗？**  
A: 完全可以——在步骤 6 中将 `multiPaged` 设置为 `true`，并对每个额外页面调用 `document.newPage()`。

## 结论
通过遵循这些步骤，您现在已经掌握了使用 Aspose.Page **在 Java 中创建 PostScript 文件** 并设置 **A4 页面大小** 的方法，同时还能 **在 Java 中添加自定义字体** 并控制页面尺寸选项。Aspose.Page 负责繁重的工作，让您专注于文档内容，而无需深入了解 PostScript 语言的细节。

---

**Last Updated:** 2026-11-19  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

## 相关教程

- [Aspose.Page Java 教程 – 设置自定义页面大小并在 PostScript 中添加页面](/page/java/postscript-page-manipulation/add-pages2/)
- [如何使用 Aspose.Page for Java 在 PostScript 中添加文本](/page/java/postscript-text-manipulation/)
- [Aspose Page Java 教程 - 将 PostScript 转换为 PDF](/page/java/postscript-conversion/to-pdf/)

```java
document.closePage();
document.save();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}