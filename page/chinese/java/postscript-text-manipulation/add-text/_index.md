---
date: 2026-02-20
description: 学习如何使用 Aspose.Page for Java 设置文本颜色、修改字体大小、生成 PostScript 文件、填充和描边文本，并在创建
  PostScript 文档时使用自定义字体（Java）。
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: 使用 Aspose.Page 的 Java 设置文本颜色 – 文本操作指南
url: /zh/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 设置文本颜色 Java – 文本操作指南

## 简介
欢迎阅读我们的分步指南，介绍在使用 Aspose.Page for Java 处理 PostScript 文件时 **set text color java**。Aspose.Page for Java 是一个强大的库，允许开发者 **create postscript document** 文件，操作字体，并精确地设置文本样式。在本教程中，您将学习如何添加文本、改变其颜色、**change font size java**，甚至 **apply fill and stroke text**，以获得精致的效果。

## 快速回答
- **什么库可以让我在 Java 中设置文本颜色？** Aspose.Page for Java。  
- **我可以使用系统字体和自定义字体吗？** 是的，两者都受支持，您可以轻松 **use custom fonts java**。  
- **如何更改文本大小？** 通过在创建 `Font` 或 `DrFont` 时指定字体大小。  
- **是否可以同时描边和填充文本？** 当然——使用 `fillAndStrokeText`。  
- **本教程生成的输出格式是什么？** 一个 PostScript（`.ps`）文档，您可以通过编程 **generate postscript file**。

## 什么是 “set text color java”？
在 Java 中设置文本颜色意味着定义渲染引擎（此处为 Aspose.Page）在页面上绘制字符时使用的 `Color` 对象。此操作对于创建视觉上区分度高的文档至关重要，尤其是在需要通过编程 **generate postscript file** 时。

## 为什么使用 Aspose.Page for Java？
- **完全控制** PostScript 生成，无需本地解释器。  
- **支持系统字体和外部字体**，让您可以嵌入所需的任何排版。  
- **简易 API** 用于填充、描边以及 **fill and stroke text**，提供样式上的灵活性。  
- **跨平台** 兼容性——一次编写，随处运行 Java。

## 先决条件
在开始之前，请确保您拥有：

- Java 编程的基础知识。  
- 已安装 Aspose.Page for Java 库。您可以从 [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) 下载。  
- 在指定文件夹中提供必要的字体。更多细节请参阅 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)。

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

## 步骤 1：设置文档
首先，我们创建一个新的 **PostScript document** 并配置输出选项。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 如何使用系统字体设置文本颜色 Java
现在我们演示使用系统提供的字体进行 **set text color java**。

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **提示：**如果未传递 `Color` 参数，`fillText` 方法会自动使用当前颜色，默认是黑色。

## 使用自定义字体并更改文本大小
您还可以 **change font size java** 并使用存放在字体文件夹中的自定义字体。

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## 描边（Stroke）文本 – 应用描边文本
描边文本可以获得清晰的边缘。这里我们使用 `BasicStroke` **apply stroke text**。

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## 使用自定义字体描边文本
相同的技术同样适用于自定义字体。

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## 步骤 6：保存文档
最后，关闭页面并将文件写入磁盘。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 为什么这很重要
能够 **set text color java** 并将填充与描边结合，使您对最终的 PostScript 输出拥有完整的艺术控制。无论是生成发票、证书还是自定义图形，能够使用精确样式 **create postscript document** 文件都能减少在图形编辑器中后期处理的需求。

## 常见问题与解决方案

| 问题 | 解决方案 |
|-------|----------|
| **未找到字体** | 确保字体文件放置在 `necessary_fonts` 中，并通过 `options.setAdditionalFontsFolders` 正确添加文件夹路径。 |
| **颜色未应用** | 确认您调用的 `fillText` 或 `outlineText` 重载包含 `Color` 参数。 |
| **描边太细** | 增加 `BasicStroke` 的宽度（例如 `new BasicStroke(3)`）。 |
| **文档无法打开** | 确认生成的 `.ps` 文件已使用正确的扩展名保存，并且您的查看器支持 PostScript。 |

## 常见问题

**Q:** 我可以在 Aspose.Page for Java 中使用自己的自定义字体吗？  
A: 是的，您可以通过在 `DrFont` 类中指定字体名称和大小来 **use custom fonts java**。

**Q:** 我如何更改文本颜色？  
A: 在填充或描边文本时，您可以使用 `Color` 类设置所需颜色。

**Q:** 是否可以向 PostScript 文档添加多个页面？  
A: 当然！您可以通过重复文档创建和保存步骤来创建多个页面。

**Q:** `ExternalFontCache` 类的作用是什么？  
A: `ExternalFontCache` 用于获取自定义字体，确保它们可用于文本操作。

**Q:** 我可以为描边文本应用不同的描边吗？  
A: 可以，您可以使用 `Stroke` 类和 `Color` 类分别自定义描边的宽度和颜色。

## 结论
恭喜！您现在已经掌握了使用 Aspose.Page for Java **set text color java**、**change font size java**、**apply fill and stroke text** 以及 **create postscript document** 文件的方法。尝试不同的字体、颜色和描边样式，以生成专业外观的 PostScript 输出。

---

**最后更新：** 2026-02-20  
**测试环境：** Aspose.Page for Java 23.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}