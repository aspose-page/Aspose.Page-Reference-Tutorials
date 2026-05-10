---
date: 2026-01-28
description: 了解如何使用 Aspose.Page 创建 PostScript A4 Java 文档，添加自定义字体，并设置 PostScript 页面大小。立即试用免费版！
linktitle: Create Document in Java with PostScript
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page 在 Java 中创建 A4 大小的 PostScript
url: /zh/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 创建 postscript a4 java

## 介绍
如果您需要直接在 Java 中 **创建 postscript a4 java** 文件，Aspose.Page 能让过程快速且可靠。在本教程中，我们将完整演示——如何创建 PostScript、将 PostScript 页面尺寸设置为 A4，以及在需要时 **add custom fonts**。完成后，您将拥有一段可直接放入任何 Java 项目的即用代码片段。

## 快速答案
- **主要库是什么？** Aspose.Page for Java.  
- **本指南关注的页面尺寸是？** A4（纵向）。  
- **我可以使用自己的字体吗？** 可以——通过额外的字体文件夹添加自定义字体。  
- **生产环境需要许可证吗？** 需要商业许可证；提供免费试用版。  
- **支持的 Java 版本是？** Java 8 及更高版本。

## 如何创建 postscript a4 java
本节重新阐述核心目标，并提供简明定义，以便搜索引擎能够即时显示答案。

## 什么是 **postscript a4 size**？
PostScript A4 size 指使用 PostScript 页面描述语言将页面设置为 ISO 216 A4 尺寸（210 mm × 297 mm）。它是全球众多商务文档的标准页面尺寸。

## 为什么使用 Aspose.Page 来 **set postscript page size**？
Aspose.Page 将底层的 PostScript 命令抽象化，使您能够专注于文档布局，而无需处理语言的细节。您将获得：
- 对页面尺寸（包括 A4）的精确控制。  
- 无需繁琐的系统字体路径，即可轻松集成自定义字体。  
- 支持单页和多页输出。

## 如何在 Java 中添加自定义字体
嵌入您自己的字体可确保生成的文档在任何打印机或查看器上都能呈现出预期的外观。

## 前置条件
在开始之前，请确保您已经拥有：
- 对 Java 编程的基本了解。  
- 已安装 Aspose.Page for Java。您可以在此处下载 [here](https://releases.aspose.com/page/java/)。  
- 一个名为 `necessary_fonts`（或您喜欢的任意名称）的文件夹，里面放置您想要嵌入的自定义字体。

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
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
将 `"Your Document Directory"` 替换为您希望生成文件所在的绝对路径。

### 步骤 2：定义字体文件夹
```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```
将您希望使用的所有 **custom fonts** 存放在此文件夹中。稍后在设置额外字体文件夹时，Aspose.Page 将自动加载它们。

### 步骤 3：为 PostScript 文档创建输出流
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```
此流指向将保存最终 **PostScript A4 size** 输出的文件。

### 步骤 4：使用 A4 大小创建保存选项
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```
这里我们将 **set the PostScript page size** 设置为 A4（纵向）。如果需要其他方向，只需更改常量即可。

### 步骤 5：设置页面边距并添加自定义字体文件夹
```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```
我们将所有边距设为零，以实现全幅页面，并告知 Aspose.Page 在何处查找之前添加的 **custom fonts**。

### 步骤 6：创建多页或单页 PS 文档
```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```
如果需要多于一页，请将 `multiPaged` 设置为 `true`；否则，将创建单页文档。

### 步骤 7：关闭当前页面并保存文档
```java
document.closePage();
document.save();
```
这些调用完成文档的最终化，关闭活动页面，并将 **PostScript A4 size** 文件写入磁盘。

## 常见问题与技巧
- **字体未显示？** 请确认字体文件为受支持的 TrueType 或 OpenType 格式，并且 `FONTS_FOLDER` 中的路径以斜杠 (`/`) 结尾。  
- **仍然出现边距？** 确保在创建 `PsDocument` 之前调用 `options.setMargins(...)` **before**。  
- **多页输出为空白？** 请记得为每个要添加的额外页面调用 `document.newPage()`。

## 常见问答

**Q: 我可以在我的 PostScript 文档中使用自定义字体吗？**  
A: 可以。确保在保存选项中设置额外的字体文件夹（参见步骤 5）。

**Q: 是否提供 Aspose.Page for Java 的试用版？**  
A: 有，您可以在此获取免费试用版 [here](https://releases.aspose.com/).

**Q: 我如何访问完整的 API 参考文档？**  
A: 请参阅文档 [here](https://reference.aspose.com/page/java/).

**Q: 我在哪里可以购买 Aspose.Page for Java 的许可证？**  
A: 您可以在此购买许可证 [here](https://purchase.aspose.com/buy).

**Q: 是否有 Aspose.Page 的社区论坛？**  
A: 有，加入社区 [forum](https://forum.aspose.com/c/page/39) 获取支持和最佳实践技巧。

**Q: 我可以生成多页的 PostScript 文件吗？**  
A: 当然——在步骤 6 中将 `multiPaged` 设置为 `true`，并为每个额外页面调用 `document.newPage()`。

## 结论
通过遵循这些步骤，您现在已经掌握了使用 Aspose.Page **创建 postscript a4 java** 文件的方法，同时能够 **add custom fonts java** 并控制 **set postscript page size** 选项。Aspose.Page 负责繁重的工作，让您专注于文档内容。

---

**最后更新：** 2026-01-28  
**测试环境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}