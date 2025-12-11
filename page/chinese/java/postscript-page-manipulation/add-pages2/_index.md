---
date: 2025-12-11
description: 了解如何使用 Aspose.Page 设置自定义页面尺寸并向 Java PostScript 文档添加页面。请遵循我们的分步指南，实现无缝的文档操作。
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java 教程 – 在 PostScript 中添加页面时设置自定义页面大小
url: /zh/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java 教程 – 在 PostScript 中添加页面时设置自定义页面大小

## 介绍
在现代 Java 应用程序中，**设置自定义页面大小**以生成 PostScript 输出通常是必需的——无论是生成发票、票据还是自定义图形。Aspose.Page for Java 让此任务变得简单。在本教程中，您将学习如何在 PostScript 文档中添加页面并设置自定义页面大小，逐步操作，让您每次都能生成恰到好处的布局。

## 快速解答
- **我可以为每页设置不同的页面大小吗？** 可以，您可以使用 `document.openPage(width, height)` 打开具有自定义尺寸的页面。  
- **生产环境需要许可证吗？** 非评估部署需要有效的 Aspose.Page 许可证。  
- **支持哪些 Java 版本？** 该库兼容 Java 8 及更高版本。  
- **API 是否线程安全？** Document 实例不是线程安全的；请为每个线程创建单独的 `PsDocument`。  
- **PostScript 文件可以有多大？** Aspose.Page 能高效处理多兆字节的文件；内存使用随内容而增长，而不是页面数量。

## 前置条件
在深入之前，请确保您具备以下条件：

- 对 Java 编程有基本了解。  
- 已在项目中添加 Aspose.Page for Java（Maven/Gradle 或手动 JAR）。  
- Java 开发环境（IDE、JDK 8+）。  

## 导入包
首先，从 Aspose.Page 库导入所需的类。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步骤 1：创建多页 PostScript 文档
首先，创建一个配置为多页的 `PsDocument`。这将设置输出流并告知库我们将处理多页文件。

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
如果默认页面大小不符合需求，您可以在打开新页面时**设置自定义页面大小**。这对于收据、标签或任何非标准布局都很有用。

## 步骤 3：添加具有不同尺寸的第二页
下面我们打开第二页，并显式提供自定义宽度和高度（单位为点）。这演示了如何为单个页面设置自定义页面大小。

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

按照这些步骤，您可以使用 Aspose.Page 在 Java PostScript 文档中无缝添加页面并**设置自定义页面大小**，从而完全控制每页的布局。

## 结论
Aspose.Page for Java 提供了强大且开发者友好的 API 来处理 PostScript 文档。您现在已经了解如何添加多页、应用自定义尺寸并保存结果——使您能够为任何基于 Java 的解决方案生成精确格式的输出。

## 常见问题
### 我可以在单个 PostScript 文档中添加不同尺寸的页面吗？
是的，如本教程所示，您可以在多页 PostScript 文档中添加尺寸不同的页面。  
### 添加页面的数量有没有限制？
Aspose.Page 支持向文档添加几乎无限数量的页面。  
### 我可以向页面添加自定义内容，如图像或图形吗？
当然！Aspose.Page 允许您添加各种内容，包括文本、图像和其他图形元素。  
### Aspose.Page 适合处理大型文档吗？
是的，Aspose.Page 旨在轻松高效地处理小型和大型文档。  
### 我在哪里可以找到 Aspose.Page 的其他资源和支持？
浏览 [Aspose.Page 文档](https://reference.aspose.com/page/java/)，或访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 获取社区支持。  

**附加问答**

**Q:** *在 PostScript 页面上绘图时支持哪些图像格式？*  
**A:** 您可以使用绘图 API 直接嵌入 PNG、JPEG、BMP 和 GIF 图像。  

**Q:** *如何更改文档的默认 DPI？*  
**A:** 在创建 `PsDocument` 之前，调用 `PsSaveOptions.setResolution(int dpi)` 设置分辨率。  

**Q:** *我可以使用密码加密 PostScript 文件吗？*  
**A:** PostScript 本身不支持加密，但您可以将输出包装为 PDF 并在需要时应用安全设置。  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose