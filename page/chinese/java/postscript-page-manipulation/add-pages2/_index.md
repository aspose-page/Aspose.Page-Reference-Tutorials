---
date: 2026-02-18
description: 了解如何使用 Aspose.Page 设置自定义页面尺寸并向 Java PostScript 文档添加页面。按照我们的分步指南，实现无缝的文档操作。
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java 教程 – 在 PostScript 中添加页面时设置自定义页面大小
url: /zh/java/postscript-page-manipulation/add-pages2/
weight: 11
---

Proceed.

I'll produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java 教程 – 在 PostScript 中添加页面时设置自定义页面大小

## 介绍
在现代 Java 应用程序中，**为 PostScript 输出设置自定义页面大小** 常常是必需的——无论是生成发票、票据还是自定义图形。本文教程将教您如何为每页 **设置自定义页面大小**、添加多页，并最终 **生成符合精确布局需求的 PostScript 文件**。我们将逐步演示代码，帮助您快速在自己的项目中应用此技术。

## 快速答疑
- **可以为每页设置不同的页面大小吗？** 可以，使用 `document.openPage(width, height)` 可以打开具有自定义尺寸的页面。  
- **生产环境需要许可证吗？** 非评估部署必须使用有效的 Aspose.Page 许可证。  
- **支持哪些 Java 版本？** 该库兼容 Java 8 及更高版本。  
- **API 是否线程安全？** Document 实例不是线程安全的；请为每个线程创建单独的 `PsDocument`。  
- **PostScript 文件的大小上限是多少？** Aspose.Page 能高效处理多兆字节的文件；内存使用随内容而增长，而非页面数量。  
- **可以使用打开页面的宽度/高度重载吗？** 当然可以——`openPage(double width, double height)` 允许您以点为单位指定任意尺寸。  

## 前置条件
在开始之前，请确保您具备以下条件：

- 基本的 Java 编程知识。  
- 已在项目中添加 Aspose.Page for Java（通过 Maven/Gradle 或手动 JAR）。  
- 已配置 Java 开发环境（IDE、JDK 8+）。  

## 导入包
首先，导入 Aspose.Page 库中所需的类。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步骤 1：创建多页 PostScript 文档
首先，创建一个用于多页的 `PsDocument`。这会设置输出流并告知库我们将处理多页文件。

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
文档准备好后，您可以向第一页添加任意内容。完成后，关闭页面以锁定其内容。

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## 如何设置自定义页面大小
如果默认页面大小不符合需求，您可以在打开新页面时 **设置自定义页面大小**。这对于收据、标签或任何非标准布局都非常有用。

## 步骤 3：添加具有不同尺寸的第二页
下面我们打开第二页，并显式提供自定义宽度和高度（单位为点）。这演示了如何为单个页面设置自定义页面大小，从而在同一文档中使用 **不同页面大小**。

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## 步骤 4：保存文档
最后，通过保存文档将更改持久化。所有页面——包括自定义尺寸的页面——都会写入输出文件。

```java
// Save the document
document.save();
```

按照这些步骤，您即可在 Java PostScript 文档中使用 Aspose.Page **添加页面并设置自定义页面大小**，从而完全掌控每页的布局。

## 为什么使用 Aspose.Page 设置自定义页面大小？
- **精确度：** 尺寸以点为单位定义，能够精确控制页面宽度和高度。  
- **灵活性：** 在单个 PostScript 文件中混合使用 **不同页面大小**。  
- **性能：** 库直接将内容流式写入输出文件，适用于大规模 **生成 PostScript 文件** 场景。  
- **丰富的 API：** 支持绘制图形、嵌入图像和添加文本——同时遵循您设定的自定义尺寸。  

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **页面尺寸出现颠倒** | 请记住 `openPage(width, height)` 的参数顺序是先宽后高（均为点）。 |
| **内容超出页面范围** | 使用 `PsGraphics` 坐标系在自定义边界内定位元素，或对绘图进行缩放。 |
| **处理超大文档时出现内存不足** | 如示例所示，使用 `FileOutputStream` 直接写入以启用流式处理，避免一次性加载大型图像。 |

## 常见问答
### 我可以在同一个 PostScript 文档中添加不同尺寸的页面吗？
可以，正如本教程所示，您可以在多页 PostScript 文档中添加尺寸各异的页面。  

### 添加页面的数量有限制吗？
Aspose.Page 支持向文档中添加几乎无限数量的页面。  

### 我可以向页面添加自定义内容，如图像或图形吗？
当然可以！Aspose.Page 允许您添加包括文本、图像和其他图形元素在内的多种内容。  

### Aspose.Page 能够处理大型文档吗？
可以，Aspose.Page 旨在高效处理大小不一的文档。  

### 在哪里可以找到 Aspose.Page 的更多资源和支持？
浏览 [Aspose.Page 文档](https://reference.aspose.com/page/java/)，或访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 获取社区支持。  

**其他问答**

**问：** *在 PostScript 页面上绘制时支持哪些图像格式？*  
**答：** 您可以使用绘图 API 直接嵌入 PNG、JPEG、BMP 和 GIF 图像。  

**问：** *如何更改文档的默认 DPI？*  
**答：** 在创建 `PsDocument` 之前，调用 `PsSaveOptions.setResolution(int dpi)` 设置分辨率。  

**问：** *我可以为 PostScript 文件设置密码加密吗？*  
**答：** PostScript 本身不支持加密，但您可以将输出包装为 PDF 并在需要时应用安全设置。  

---

**最后更新：** 2026-02-18  
**测试环境：** Aspose.Page for Java 24.10  
**作者：** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}