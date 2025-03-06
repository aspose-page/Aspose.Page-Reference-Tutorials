---
title: Aspose.Page Java 文本操作
linktitle: 在 Java PostScript 中添加文本
second_title: Aspose.Page Java API
description: 在我们向 PostScript 文档添加文本的教程中探索 Aspose.Page for Java 的强大功能。学习轻松使用系统和自定义字体。
weight: 10
url: /zh/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java 文本操作

## 介绍
欢迎阅读我们有关使用 Aspose.Page for Java 在 Java PostScript 中添加文本的分步指南。 Aspose.Page for Java 是一个功能强大的库，允许开发人员轻松操作 PostScript 文档。在本教程中，我们将引导您完成添加文本、使用系统和自定义字体、概述文本以及合并笔划以获得视觉上吸引人的结果的过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- Java 编程的基础知识。
- 安装了 Java 库的 Aspose.Page。您可以从[Aspose.Page for Java 下载页面](https://releases.aspose.com/page/java/).
- 指定文件夹中提供必要的字体。您可以在以下位置找到更多信息[Aspose.Page 用于 Java 文档](https://reference.aspose.com/page/java/).
## 导入包
在您的 Java 项目中，导入 Aspose.Page for Java 所需的包：
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## 第 1 步：设置文档
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
//为 PostScript 文档创建输出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
//创建 A4 尺寸的保存选项
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
//要写入 PS 文件的文本
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
//创建新的 1 页 PS 文档
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 步骤2：使用系统字体填充文本
```java
//使用系统字体填充文本
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
//使用默认或已定义的颜色（黑色）填充文本
document.fillText(str, font, 50, 100);
//用蓝色填充文本
document.fillText(str, font, 50, 150, Color.BLUE);
```
## 步骤 3：使用自定义字体填充文本
```java
//使用自定义字体填充文本
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
//使用默认或已定义的颜色（黑色）填充文本
document.fillText(str, drFont, 50, 200);
//用蓝色填充文本
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## 步骤 4：使用系统字体勾画文本轮廓
```java
//使用系统字体来概述文本
document.outlineText(str, font, 50, 300);
//使用蓝紫色 2 点宽笔勾勒文本轮廓
document.outlineText(str, font, 50, 350, strokeColor, stroke);
//用橙色填充文本并用蓝色 2 点宽笔描边
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## 第 5 步：使用自定义字体勾画文本轮廓
```java
//使用自定义字体来概述文本
document.outlineText(str, drFont, 50, 450);
//使用蓝紫色 2 点宽笔勾勒文本轮廓
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
//用橙色填充文本并用蓝色 2 点宽笔描边
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## 第 6 步：保存文档
```java
//关闭当前页面
document.closePage();
//保存文档
document.save();
```
## 结论
恭喜！您已经成功学习了如何使用 Aspose.Page for Java 在 Java PostScript 中添加文本。尝试不同的字体、颜色和轮廓选项，以进一步增强您的文档。
## 经常问的问题
### 我可以在 Aspose.Page for Java 中使用我自己的自定义字体吗？
是的，您可以通过在中指定字体名称和大小来使用自定义字体`DrFont`班级。
### 如何更改文本的颜色？
您可以使用设置所需的颜色`Color`填充或概述文本时的类。
### 是否可以向 PostScript 文档添加多个页面？
绝对地！您可以通过重复文档创建和保存步骤来创建多个页面。
### 目的是什么`ExternalFontCache` class?
`ExternalFontCache`用于获取自定义字体，确保它们可用于文本操作。
### 我可以对轮廓文本应用不同的笔画吗？
是的，您可以使用以下命令自定义笔划的宽度和颜色`Stroke`类和`Color`类，分别。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
