---
title: Set Text Color Java with Aspose.Page – Text Manipulation Guide
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
description: Learn how to set text color java using Aspose.Page for Java, add text to PostScript, and apply stroke text for rich document styling.
weight: 10
url: /java/postscript-text-manipulation/add-text/
date: 2025-12-14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Text Color Java with Aspose.Page – Text Manipulation Guide

## Introduction
Welcome to our step‑by‑step guide on **set text color java** while working with PostScript files using Aspose.Page for Java. Aspose.Page for Java is a powerful library that lets developers create and **generate postscript file** documents, manipulate fonts, and style text with precision. In this tutorial you’ll learn how to add text, change its color, adjust size, and even **apply stroke text** for a polished look.

## Quick Answers
- **What library lets me set text color in Java?** Aspose.Page for Java.
- **Can I use system fonts and custom fonts?** Yes, both are supported.
- **How do I change the text size?** By specifying the font size when creating the `Font` or `DrFont`.
- **Is it possible to outline and fill text together?** Absolutely – use `fillAndStrokeText`.
- **What output format does this tutorial produce?** A PostScript (`.ps`) document.

## What is “set text color java”?
Setting the text color in Java means defining the `Color` object that the rendering engine (here, Aspose.Page) uses when drawing characters onto a page. This operation is essential for creating visually distinct documents, especially when generating **postscript documents** programmatically.

## Why use Aspose.Page for Java?
- **Full control** over PostScript generation without needing a native PostScript interpreter.
- **Support for both system and external fonts**, letting you embed any typography you need.
- **Easy API** to fill, outline, and **fill and stroke text**, giving you flexibility in styling.
- **Cross‑platform** compatibility – write once, run anywhere Java runs.

## Prerequisites
Before diving in, make sure you have:

- Basic knowledge of Java programming.
- Aspose.Page for Java library installed. You can download it from the [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
- Necessary fonts available in the specified folder. Additional details are in the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## Import Packages
In your Java project, import the necessary packages for Aspose.Page for Java:

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
First, we create a new **PostScript document** and configure the output options.

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
Now we demonstrate **set text color java** with a system‑provided font.

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
You can also **change text size** and use a custom font stored in your fonts folder.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
Outlining text gives it a crisp edge. Here we **apply stroke text** using a `BasicStroke`.

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
The same technique works with custom fonts.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
Finally, close the page and write the file to disk.

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
A: Yes, you can use custom fonts by specifying the font name and size in the `DrFont` class.

**Q:** How can I change the color of the text?  
A: You can set the desired color using the `Color` class when filling or outlining the text.

**Q:** Is it possible to add multiple pages to a PostScript document?  
A: Absolutely! You can create multiple pages by repeating the document creation and saving steps.

**Q:** What is the purpose of the `ExternalFontCache` class?  
A: `ExternalFontCache` is used to fetch custom fonts, ensuring they are available for text manipulation.

**Q:** Can I apply different strokes to the outlined text?  
A: Yes, you can customize the width and color of the stroke using the `Stroke` class and `Color` class, respectively.

## Conclusion
Congratulations! You now know how to **set text color java**, change font sizes, **apply stroke text**, and **create postscript document** files using Aspose.Page for Java. Experiment with different fonts, colors, and outline styles to produce professional‑looking PostScript output.

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}