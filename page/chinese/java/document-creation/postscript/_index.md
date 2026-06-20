---
date: 2026-06-20
description: 了解如何设置 A4 页面尺寸、在 Java 中创建 PostScript 文件，并使用 Aspose.Page 添加自定义字体。立即试用免费版！
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: 在 Java 中使用 PostScript 创建文档
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page 设置 A4 页面尺寸并创建 PostScript
url: /zh/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 设置 A4 页面尺寸并创建 PostScript

## 介绍
如果您需要在 Java 中生成 PostScript 文件时 **设置 a4 页面尺寸**，Aspose.Page 提供了快速、可靠的 API，隐藏了底层细节。在本教程中，我们将完整演示工作流——创建 PostScript 文档、配置 A4 页面尺寸，以及在需要时 **添加自定义字体**。完成后，您将拥有一段可直接放入任何 Java 项目的可用代码片段。

## 快速回答
- **什么库在 Java 中创建 PostScript？** Aspose.Page for Java.  
- **本指南针对哪种页面尺寸？** A4 (210 mm × 297 mm)。  
- **我可以嵌入自己的字体吗？** 可以——在保存选项中设置额外的字体文件夹。  
- **生产环境需要许可证吗？** 需要商业许可证；提供免费试用。  
- **支持哪些 Java 版本？** Java 8 及更高版本。

## 如何在 Java 中设置 a4 页面尺寸并创建 postscript
加载 Aspose.Page 库，使用 A4 常量配置 `PsSaveOptions`，并将文档写入文件——全部代码不超过十行。这种直接方法确保页面尺寸正确，并且可以在无需额外配置的情况下添加自定义字体。

## 什么是 postscript A4 大小？
PostScript A4 大小是 ISO 216 标准（210 mm × 297 mm）在 PostScript 页面描述语言中的表示。它定义了打印机和查看器解释的可打印区域，确保跨平台布局一致。由于 PostScript 以设备无关的方式描述页面内容，使用 A4 大小可保证文档在全球任何支持 A4 的打印机或查看器上呈现相同。

## 为什么使用 Aspose.Page 设置 postscript 页面尺寸？
Aspose.Page 支持 **30 多个 PostScript 操作符**，并且能够生成最高 **500 MB** 的文件，而无需将整个文档加载到内存中。这让您在高效处理大批量工作负载的同时，精确控制页面尺寸。该库还抽象了复杂的 PostScript 语法，自动管理资源，并提供高性能流式处理，适用于简单的单页传单和复杂的多页报告。

## 如何在 Java 中添加自定义字体
嵌入您自己的字体可确保生成的文档在任何打印机或查看器上都完全按照设计呈现，Aspose.Page 会自动发现放置在指定文件夹中的字体。通过注册额外的字体文件夹，您可以使用任何 TrueType 或 OpenType 字体，避免回退替代，并在所有输出设备上保持品牌一致性。

## 前置条件
- 具备 Java 编程的工作知识。  
- 已安装 Aspose.Page for Java。您可以在[此处](https://releases.aspose.com/page/java/)下载。  
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
`FONTS_FOLDER` 指向存放您自定义 TrueType 或 OpenType 字体的目录。

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
`PsSaveOptions` 允许您指定目标页面尺寸。  
**定义：** `PsPageSize` 是一个枚举，包含标准页面尺寸常量，如 A4、Letter 和 Legal。  
设置 `options.setPageSize(PsPageSize.A4)` 将文档配置为标准 A4 尺寸。

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### 步骤 5：设置页面边距并添加自定义字体文件夹
`options.setMargins(0, 0, 0, 0)` 移除所有边距，实现全幅页面，`options.setAdditionalFontsFolder(FONTS_FOLDER)` 注册您的自定义字体。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### 步骤 6：创建多页或单页 PS 文档
`PsDocument document = new PsDocument(outputStream, options)` 创建文档。`PsDocument` 表示一个可以包含一个或多个页面的 PostScript 文档。将 `multiPaged` 设置为 `true` 可实现多页输出。

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### 步骤 7：关闭当前页面并保存文档
调用 `document.close()` 完成文件并将 **PostScript A4 大小** 输出写入磁盘。

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## 常见问题与技巧
- **字体未显示？** 请确认字体文件是受支持的 TrueType 或 OpenType 格式，并且 `FONTS_FOLDER` 以斜杠 (`/`) 结尾。  
- **边距仍然显示？** 在构造 `PsDocument` 之前调用 `options.setMargins(...)`。  
- **多页输出为空白？** 请记得为每个需要的额外页面调用 `document.newPage()`。

## 常见问答

**问：我可以在我的 PostScript 文档中使用自定义字体吗？**  
**答：** 可以，在保存选项中设置额外的字体文件夹（见步骤 5），Aspose.Page 将自动嵌入这些字体。

**问：是否有 Aspose.Page for Java 的试用版？**  
**答：** 有，您可以在[此处](https://releases.aspose.com/)获取免费试用。

**问：如何获取完整的 API 参考？**  
**答：** 请参阅文档[此处](https://reference.aspose.com/page/java/)。

**问：在哪里购买 Aspose.Page for Java 的许可证？**  
**答：** 您可以在[此处](https://purchase.aspose.com/buy)购买许可证。

**问：我可以在哪里向社区求助？**  
**答：** 访问 Aspose.Page 论坛[forum](https://forum.aspose.com/c/page/39)。

**问：我可以生成多页 PostScript 文件吗？**  
**答：** 完全可以——在步骤 6 中将 `multiPaged` 设置为 `true`，并为每个额外页面调用 `document.newPage()`。

## 结论
通过遵循这些步骤，您现在了解了如何 **设置 a4 页面尺寸** 并使用 Aspose.Page 在 Java 中创建 **PostScript** 文件，同时还能 **在 Java 中添加自定义字体** 并控制页面尺寸选项。Aspose.Page 负责繁重的工作，让您专注于文档内容。

---

**Last Updated:** 2026-06-20  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [Aspose.Page Java 教程 – 在 PostScript 中添加页面时设置自定义页面尺寸](/page/java/postscript-page-manipulation/add-pages2/)
- [如何使用 Aspose.Page for Java 在 PostScript 中添加文本](/page/java/postscript-text-manipulation/)
- [Aspose Page Java 教程 - 将 PostScript 转换为 PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```