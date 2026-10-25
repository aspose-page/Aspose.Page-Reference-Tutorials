---
date: 2026-10-25
description: 了解如何使用 Aspose.Page 为 Java PostScript 文档设置 custom page size 并添加页面。按照我们的
  step‑by‑step 指南，实现无缝的文档操作。
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: 在 PostScript 中添加页面
og_description: 了解如何使用 Aspose.Page for Java 在 PostScript 中设置 custom page size。按照 step‑by‑step
  说明添加页面、设置尺寸并高效保存文档。
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: 使用 Aspose.Page Java 在 PostScript 中设置 custom page size
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Aspose.Page Java 教程 – 在 PostScript 中添加页面时设置 custom page size
url: /zh/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java 教程 – 在 PostScript 中添加页面时设置自定义页面大小

## 介绍
在现代 Java 应用程序中，**set custom page size** 对于 PostScript 输出经常是必需的——无论是生成发票、票据还是自定义图形。本教程向您展示如何为每页设置自定义页面大小、添加多页，并生成符合您精确布局需求的 PostScript 文件。您将获得一个完整的可运行示例，直接放入任何 Java 8+ 项目中使用。

## 快速回答
- **我可以为每页设置不同的页面大小吗？** 是的——您可以使用 `document.openPage(width, height)` 打开具有自定义尺寸的页面。  
- **我需要许可证才能在生产环境中使用吗？** 需要有效的 Aspose.Page 许可证才能进行非评估部署。  
- **支持哪些 Java 版本？** 该库支持 Java 8 及更高版本。  
- **API 是线程安全的吗？** Document 实例不是线程安全的；请为每个线程创建单独的 `PsDocument`。  
- **PostScript 文件可以有多大？** Aspose.Page 能高效处理多兆字节的文件；内存使用随内容而增长，而不是页面数量。  
- **我可以使用 open page width/height 重载吗？** 当然可以——`openPage(double width, double height)` 允许您以点为单位指定任意尺寸。  

## 前置条件
- 对 Java 编程有基本了解。  
- 已在项目中添加 Aspose.Page for Java（Maven/Gradle 或手动 JAR）。  
- Java 开发环境（IDE、JDK 8+）。  

## 导入包
以下类是必需的：用于写入文件的 `FileOutputStream`、用于创建 PostScript 文档的 `PsDocument`，以及用于配置输出选项的 `PsSaveOptions`。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步骤 1：创建多页 PostScript 文档
`PsDocument` 是表示可以包含多页的 PostScript 文档的核心类。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## 步骤 2：向第一页添加内容
文档准备好后，您可以向第一页添加所需的任何内容。完成后，关闭页面以锁定其内容。

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## 如何设置自定义页面大小
您可以在绘制任何内容之前，通过调用 `document.openPage(width, height)` 并传入所需的点单位尺寸来设置自定义页面大小。`openPage(width, height)` 会使用指定的宽度和高度打开新页面，让您完全控制页面画布。如果默认页面大小不符合需求，您可以在打开新页面时**set custom page size**。这对于收据、标签或任何非标准布局都很有用。

## 步骤 3：添加具有不同尺寸的第二页
下面我们打开第二页，并显式提供自定义宽度和高度（以点为单位）。这演示了如何为单个页面设置自定义页面大小，使您能够在同一文档中使用**different page sizes**。

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## 步骤 4：保存文档
最后，通过保存文档来持久化更改。所有页面——包括具有自定义尺寸的页面——都会写入输出文件。

```java
// Save the document
document.save();
```

按照这些步骤，您可以使用 Aspose.Page 在 Java PostScript 文档中无缝添加页面并**set custom page size**，从而对每页的布局拥有完全控制。

## 为什么使用 Aspose.Page 来设置自定义页面大小？
Aspose.Page 提供对页面尺寸的精确控制，允许您以点为单位定义任意宽度和高度，在单个文档中混合多种页面尺寸，并高效流式传输内容，以实现高性能的 PostScript 生成。这使其非常适合发票、票据以及需要低内存使用的大规模批处理。

Aspose.Page 让您以点为单位定义精确的页面尺寸，在一个文件中混合多种尺寸，并高效流式传输内容，从而在生成 PostScript 时提供精确控制和高性能。  
- **精确度：** 尺寸以点为单位定义，您可以对页面宽度和高度进行精确控制。  
- **灵活性：** 在单个 PostScript 文件中混合使用**different page sizes**。  
- **性能：** 该库直接将内容流式写入输出文件，能够处理高达 500 MB 的文件且堆内存使用保持在 100 MB 以下，适用于大规模**generate PostScript file** 场景。  
- **丰富的 API：** 支持超过 30 种图形原语、10 种图像格式以及每页无限的文本对象——所有这些都遵循您设置的自定义尺寸。  

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **页面尺寸出现颠倒** | 记住 `openPage(width, height)` 需要先宽后高（均为点）。 |
| **内容超出页面** | 使用 `PsGraphics` 坐标系将元素定位在自定义边界内，或对绘图进行缩放。 |
| **大文档出现内存不足错误** | 通过如示例所示直接写入 `FileOutputStream` 启用流式处理，并避免一次性将大图像加载到内存中。 |

## 常见问答
### 我可以在单个 PostScript 文档中添加不同尺寸的页面吗？
是的，如本教程所示，您可以在多页 PostScript 文档中添加尺寸各异的页面。  

### 添加页面的数量有任何限制吗？
Aspose.Page 支持向文档中添加几乎无限数量的页面。  

### 我可以向页面添加自定义内容，如图像或图形吗？
当然可以！Aspose.Page 允许您添加各种内容，包括文本、图像和其他图形元素。  

### Aspose.Page 适合处理大型文档吗？
是的，Aspose.Page 旨在高效轻松地处理小型和大型文档。  

### 我在哪里可以找到 Aspose.Page 的其他资源和支持？
浏览 [Aspose.Page 文档](https://reference.aspose.com/page/java/)，或访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 获取社区支持。  

**Additional Q&A**

**Q:** *在 PostScript 页面上绘制时支持哪些图像格式？*  
**A:** 您可以使用绘图 API 直接嵌入 PNG、JPEG、BMP 和 GIF 图像。  

**Q:** *如何更改文档的默认 DPI？*  
**A:** 在创建 `PsDocument` 之前，调用 `PsSaveOptions.setResolution(int dpi)` 设置分辨率。  

**Q:** *我可以为 PostScript 文件设置密码加密吗？*  
**A:** PostScript 本身不支持加密，但您可以将输出包装为 PDF 并在需要时应用安全设置。  

---

**最后更新:** 2026-10-25  
**测试环境:** Aspose.Page for Java 24.10  
**作者:** Aspose  

## 相关教程

- [如何在 Java 中使用 Aspose.Page 设置 A4 页面大小并创建 PostScript](/page/java/document-creation/postscript/)
- [如何使用 Aspose.Page Java API 将 PostScript 转换为 PDF](/page/java/postscript-conversion/to-pdf/)
- [如何在 Java PostScript 中使用 Aspose.Page 绘制矩形](/page/java/postscript-shapes/add-rectangle/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}