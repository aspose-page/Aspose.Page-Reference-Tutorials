---
title: Aspose.Page Java Text Manipulation
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
description: Explore the power of Aspose.Page for Java in our tutorial on adding text to PostScript documents. Learn to use system and custom fonts with ease.
weight: 10
url: /java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Text Manipulation

## Introduction
Welcome to our step-by-step guide on adding text in Java PostScript using Aspose.Page for Java. Aspose.Page for Java is a powerful library that allows developers to manipulate PostScript documents with ease. In this tutorial, we will walk you through the process of adding text, using system and custom fonts, outlining text, and incorporating strokes for a visually appealing result.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
- Basic knowledge of Java programming.
- Aspose.Page for Java library installed. You can download it from the [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
- Necessary fonts available in the specified folder. You can find additional information in the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).
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
## Step 2: Using System Font for Filling Text
```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Step 3: Using Custom Font for Filling Text
```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Step 4: Outlining Text with System Font
```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue-violet colored 2-points width pen
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2-points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Step 5: Outlining Text with Custom Font
```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue-violet colored 2-points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2-points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Step 6: Save the Document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```
## Conclusion
Congratulations! You've successfully learned how to add text in Java PostScript using Aspose.Page for Java. Experiment with different fonts, colors, and outlining options to enhance your document further.
## Frequently Asked Questions
### Can I use my own custom fonts with Aspose.Page for Java?
Yes, you can use custom fonts by specifying the font name and size in the `DrFont` class.
### How can I change the color of the text?
You can set the desired color using the `Color` class when filling or outlining the text.
### Is it possible to add multiple pages to a PostScript document?
Absolutely! You can create multiple pages by repeating the document creation and saving steps.
### What is the purpose of the `ExternalFontCache` class?
`ExternalFontCache` is used to fetch custom fonts, ensuring they are available for text manipulation.
### Can I apply different strokes to the outlined text?
Yes, you can customize the width and color of the stroke using the `Stroke` class and `Color` class, respectively.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
