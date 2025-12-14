---
date: 2025-12-14
description: 学习如何使用 Aspose.Page for Java 设置文本颜色、向 PostScript 添加文本，以及应用描边文本以实现丰富的文档样式。
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: 使用 Aspose.Page 在 Java 中设置文本颜色 – 文本操作指南
url: /zh/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 设置文本颜色 Java – 文本操作指南

## Introduction
欢迎阅读本分步指南，了解在使用 Aspose.Page for Java 处理 PostScript 文件时如何 **set text color java**。Aspose.Page for Java 是一个强大的库，帮助开发者创建并 **generate postscript file** 文档、操作字体以及精准地设置文本样式。在本教程中，你将学习如何添加文本、修改颜色、调整大小，甚至 **apply stroke text**，以获得精致的效果。

## Quick Answers
- **What library lets me set text color in Java?** Aspose.Page for Java.  
- **Can I use system fonts and custom fonts?** Yes, both are supported.  
- **How do I change the text size?** By specifying the font size when creating the `Font` or `DrFont`.  
- **Is it possible to outline and fill text together?** Absolutely – use `fillAndStrokeText`.  
- **What output format does this tutorial produce?** A PostScript (`.ps`) document.

## What is “set text color java”?
在 Java 中设置文本颜色是指定 `Color` 对象，渲染引擎（此处为 Aspose.Page）在将字符绘制到页面时会使用该颜色。此操作对于创建视觉上区分度高的文档尤为重要，尤其是以编程方式 **postscript documents**。

## Why use Aspose.Page for Java?
- **Full control** over PostScript generation without needing a native PostScript interpreter.  
- **Support for both system and external fonts**, letting you embed any typography you need.  
- **Easy API** to fill, outline, and **fill and stroke text**, giving you flexibility in styling.  
- **Cross‑platform** compatibility – write once, run anywhere Java runs.

## Prerequisites
在开始之前，请确保你具备以下条件：

- 基本的 Java 编程知识。  
- 已安装 Aspose.Page for Java 库。你可以从 [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) 下载。  
- 指定文件夹中已有必要的字体。更多细节请参阅 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)。

## Import Packages
在你的 Java 项目中，导入 Aspose.Page for Java 所需的包：

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

## Step 1: Set Up the Document
首先，创建一个新的 **PostScript document** 并配置输出选项。

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

## How to Set Text Color Java Using System Font
下面演示使用系统提供的字体进行 **set text color java**。

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** `fillText` 方法在未传入 `Color` 参数时会自动使用当前颜色，默认是黑色。

## Using Custom Font and Changing Text Size
你也可以 **change text size** 并使用存放在字体文件夹中的自定义字体。

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
为文本描边可以获得更清晰的边缘。这里我们使用 `BasicStroke` **apply stroke text**。

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

## Outlining Text with Custom Font
相同的技术同样适用于自定义字体。

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
最后，关闭页面并将文件写入磁盘。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Font not found** | Ensure the font file is placed in `necessary_fonts` and the folder path is correctly added via `options.setAdditionalFontsFolders`. |
| **Color not applied** | Verify you are calling the overload of `fillText` or `outlineText` that includes a `Color` argument. |
| **Stroke appears too thin** | Increase the `BasicStroke` width (e.g., `new BasicStroke(3)`). |
| **Document not opening** | Confirm the generated `.ps` file is saved with the correct extension and that your viewer supports PostScript. |

## Frequently Asked Questions

**Q:** Can I use my own custom fonts with Aspose.Page for Java?  
**A:** Yes, you can use custom fonts by specifying the font name and size in the `DrFont` class.

**Q:** How can I change the color of the text?  
**A:** You can set the desired color using the `Color` class when filling or outlining the text.

**Q:** Is it possible to add multiple pages to a PostScript document?  
**A:** Absolutely! You can create multiple pages by repeating the document creation and saving steps.

**Q:** What is the purpose of the `ExternalFontCache` class?  
**A:** `ExternalFontCache` is used to fetch custom fonts, ensuring they are available for text manipulation.

**Q:** Can I apply different strokes to the outlined text?  
**A:** Yes, you can customize the width and color of the stroke using the `Stroke` class and `Color` class, respectively.

## Conclusion
恭喜！你现在已经掌握了如何 **set text color java**、更改字体大小、**apply stroke text**，以及使用 Aspose.Page for Java 创建 **postscript document** 文件。尝试不同的字体、颜色和描边样式，生成专业级的 PostScript 输出。

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}