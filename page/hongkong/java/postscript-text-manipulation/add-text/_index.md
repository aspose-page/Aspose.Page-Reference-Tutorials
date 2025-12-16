---
date: 2025-12-14
description: 了解如何使用 Aspose.Page for Java 設定文字顏色、將文字加入 PostScript，並套用描邊文字以實現豐富的文件樣式。
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: 使用 Aspose.Page（Java）設定文字顏色 – 文字操作指南
url: /zh-hant/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 的 Java 設定文字顏色 – 文字操作指南

## Introduction
歡迎閱讀本步驟教學，內容說明在使用 Aspose.Page for Java 處理 PostScript 檔案時，如何 **set text color。Aspose.Page for Java 是一套功能強大的程式庫，讓開發者能夠建立與 **generate postscript file** 文件、操作字型、精確地為文字設定樣式。在本教學中，您將學會如何加入文字、變更顏色、調整大小，甚至 **apply stroke text**，打造更精緻的版面效果。

## Quick Answers
- **What library lets me set text color in Java?** Aspose.Page for Java.  
- **Can I use system fonts and custom fonts?** Yes, both are supported.  
- **How do I change the text size?** By specifying the font size when creating the `Font` or `DrFont`.  
- **Is it possible to outline and fill text together?** Absolutely – use `fillAndStrokeText`.  
- **What output format does this tutorial produce?** A PostScript (`.ps`) document.

## What is “set text color java”?
在 Java 中設定文字顏色，即是為渲染引擎（此處為 Aspose.Page）定義 `Color` 物件，讓它在將字元繪製到頁面時使用。此操作對於程式化產生 **postscript documents** 時，製作視覺上有區別的文件相當重要。

## Why use Aspose.Page for Java?
- **Full control** over PostScript generation without needing a native PostScript interpreter.  
- **Support for both system and external fonts**, letting you embed any typography you need.  
- **Easy API** to fill, outline, and **fill and stroke text**, giving you flexibility in styling.  
- **Cross‑platform** compatibility – write once, run anywhere Java runs.

## Prerequisites
在開始之前，請確保您已具備：

- 基本的 Java 程式開發知識。  
- 已安裝 Aspose.Page for Java 程式庫。您可從 [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) 下載。  
- 指定資料夾內已放置必要的字型。更多資訊請參閱 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)。

## Import Packages
在您的 Java 專案中，匯入 Aspose.Page for Java 所需的套件：

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
首先，建立一個新的 **PostScript document**，並設定輸出選項。

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
以下示範如何使用系統預設字型執行 **set text color java**。

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** The `fillText` method automatically uses the current color if you don’t pass a `Color` argument, which defaults to black.

## Using Custom Font and Changing Text Size
您也可以 **change text size**，並使用儲存在字型資料夾中的自訂字型。

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
為文字加上描邊可產生銳利的邊緣。此處示範使用 `BasicStroke` **apply stroke text**。

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
相同的技巧同樣適用於自訂字型。

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
最後，關閉頁面並將檔案寫入磁碟。

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
恭喜您！現在您已掌握 **set text color java**、變更字型大小、**apply stroke text**，以及使用 Aspose.Page for Java 產生 **postscript document** 檔案的技巧。可自行嘗試不同的字型、顏色與描邊樣式，製作出專業水準的 PostScript 輸出。

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}