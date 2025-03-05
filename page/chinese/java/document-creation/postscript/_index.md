---
title: 使用 PostScript 在 Java 中创建文档
linktitle: 使用 PostScript 在 Java 中创建文档
second_title: Aspose.Page Java API
description: 使用 Aspose.Page 在 Java 中轻松创建 PostScript 文档。自定义页面大小、边距和字体。立即免费试用！
type: docs
weight: 10
url: /zh/java/document-creation/postscript/
---
## 介绍
在 Java 开发领域，创建和管理文档是一个至关重要的方面。随着 Aspose.Page for Java 的出现，该过程不仅变得高效而且灵活。本教程旨在指导您完成使用 Aspose.Page 通过 PostScript 在 Java 中创建文档的步骤，确保您充分利用该工具的强大功能。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- Java 编程的实用知识。
-  Aspose.Page for Java 已安装。你可以下载它[这里](https://releases.aspose.com/page/java/).
- 需要的字体存放在指定的文件夹中。例如，在文档目录中创建一个“necessary_fonts”目录。
## 导入包
在您的 Java 项目中，导入所需的 Aspose.Page 包：
```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
现在，让我们将示例分解为多个步骤，以便无缝理解。
## 第1步：设置文档目录
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
```
将“您的文档目录”替换为您要保存文档的实际路径。
## 第 2 步：定义字体文件夹
```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```
确保此文件夹中存储有必要的字体。
## 步骤 3：为 PostScript 文档创建输出流
```java
//为 PostScript 文档创建输出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```
此步骤为 PostScript 文档建立输出流，并相应地设置文件名。
## 步骤 4：创建 A4 尺寸的保存选项
```java
//创建 A4 尺寸的保存选项
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```
根据您的文档要求自定义保存选项，指定页面大小和方向。
## 第 5 步：设置页边距和其他字体文件夹
```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```
如果字体存储在系统文件夹之外，请调整页边距并包含其他字体文件夹。
## 步骤 6：创建多页或单页 PS 文档
```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```
确定生成的 PostScript 文档是多页还是单页，并相应地创建文档。
## 第7步：关闭当前页面并保存文档
```java
document.closePage();
document.save();
```
通过关闭当前页面并保存文档来完成文档创建过程。
本分步指南确保您可以使用 Aspose.Page 通过 PostScript 无缝创建 Java 文档，从而释放这个强大工具的潜力。
## 结论
使用 Aspose.Page 可以轻松掌握 Java 文档创建。本教程提供了整个过程的全面指南，使您能够利用该库的全部功能。
## 常见问题解答
### 我可以在 PostScript 文档中使用自定义字体吗？
是的你可以。确保在保存选项中设置附加字体文件夹。
### Aspose.Page for Java 是否有试用版？
是的，您可以获得免费试用[这里](https://releases.aspose.com/).
### 如何访问 Aspose.Page for Java 的文档？
参考文档[这里](https://reference.aspose.com/page/java/).
### 在哪里可以购买 Aspose.Page for Java 的许可证？
您可以购买许可证[这里](https://purchase.aspose.com/buy).
### 有 Aspose.Page 讨论的论坛吗？
是的，您可以加入社区[论坛](https://forum.aspose.com/c/page/39)进行讨论和支持。