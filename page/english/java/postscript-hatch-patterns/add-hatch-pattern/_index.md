---
title: "Aspose.Page Java: Add Hatch Pattern in Java PostScript"
linktitle: "Add Hatch Pattern in Java PostScript"
second_title: "Aspose.Page Java API"
description: "Learn how to add hatch patterns to Java PostScript documents using Aspose.Page Java. This step‑by‑step guide shows you how to add hatch pattern graphics efficiently."
weight: 10
url: /java/postscript-hatch-patterns/add-hatch-pattern/
date: 2025-12-08
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Hatch Pattern in Java PostScript

## Introduction
If you’re working with **Aspose.Page Java** and need to enrich your PostScript output with textured graphics, hatch patterns are a fast and flexible solution. In this tutorial we’ll walk through **how to add hatch** designs to a PostScript document, explain why they’re useful, and give you a complete, ready‑to‑run code example. By the end, you’ll be able to create visually appealing hatch‑filled shapes and text with just a few lines of Java.

## Quick Answers
- **What library do I need?** Aspose.Page for Java (the “aspose page java” SDK).  
- **Which visual effect are we adding?** Hatch patterns (e.g., diagonal lines, crosshatch).  
- **Do I need a license to run the sample?** A free trial works for development; a license is required for production.  
- **How many lines of code?** About 70 lines, split into clear steps.  
- **Can I use the same approach for PDFs?** Yes—Aspose.Page supports multiple output formats, including PDF.

## Prerequisites
Before you start, make sure you have:

- **Java Development Environment** – JDK 8 or higher and an IDE of your choice.  
- **Aspose.Page for Java library** – Download the latest JAR from the official site [here](https://releases.aspose.com/page/java/).  
- **Write access** to a folder where the generated PostScript file will be saved.

## Import Packages
First, bring the required classes into your project. These imports give you access to drawing primitives, color handling, and the Aspose.Page API.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Initial Parameters
Create the output stream, configure the page size (A4), and define a few layout variables that will be reused when drawing each hatch‑filled square.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Step 2: Save Graphics State and Translate
Saving the graphics state lets us return to the original coordinate system later, while `translate` moves the origin to a convenient starting point.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Step 3: Create Square for Each Pattern
Define a reusable rectangle that will represent each hatch‑filled cell.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Step 4: Set Up Pen for Pattern Square Outline
A `BasicStroke` of 2 points gives a crisp outline around every square.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Step 5: Iterate Through Hatch Patterns
Loop through every value in the `HatchStyle` enum, fill each square with the corresponding texture, and then draw its outline. This is the core of **adding hatch pattern** functionality.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Step 6: Restore Graphics State
Return to the original coordinate system after we finish drawing the grid of squares.

```java
document.writeGraphicsRestore();
```

## Step 7: Fill Text with Hatch Pattern
Here we demonstrate how to paint text using a hatch texture. The example fills the word “ABC” with a diagonal‑cross pattern.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Step 8: Outline Text with Hatch Pattern
Now we outline the same text, but this time using a 70 % hatch style and a thicker stroke.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Step 9: Close and Save Document
Finalize the page, write the file to disk, and release resources.

```java
document.closePage();
document.save();
```

Follow these steps, and you’ll have a PostScript file that showcases a full set of hatch patterns applied to both shapes and text—all powered by **aspose page java**.

## Why Use Hatch Patterns with Aspose.Page Java?
- **Visual distinction** – Hatch fills work even when printers are limited to monochrome output.  
- **Performance** – Textures are generated on‑the‑fly, so you avoid large image files.  
- **Cross‑format support** – The same code can target PDF, EPS, or SVG with minimal changes.

## Common Pitfalls & Tips
- **File path errors** – Ensure `dataDir` ends with the appropriate file‑separator (`/` or `\`).  
- **Unsupported colors** – Some older PostScript interpreters may not handle certain color spaces; stick to basic RGB for maximum compatibility.  
- **License warnings** – Running the sample without a valid license will embed a watermark in the output.

## Conclusion
Incorporating hatch patterns can dramatically improve the readability and aesthetic of technical drawings, maps, or any graphics generated by Java. With **Aspose.Page Java**, you get a concise API that abstracts the low‑level PostScript commands, letting you focus on design rather than file format quirks.

## Frequently Asked Questions

**Q: Can I use Aspose.Page Java with other Java frameworks?**  
A: Yes, the library is framework‑agnostic and works with Spring, Jakarta EE, Android (limited), and plain Java SE.

**Q: Is a trial version available for Aspose.Page Java?**  
A: Absolutely. Download a free 30‑day trial [here](https://releases.aspose.com/).

**Q: How do I obtain a temporary license for development?**  
A: Request a temporary license [here](https://purchase.aspose.com/temporary-license/). It removes evaluation watermarks.

**Q: Where can I find more tutorials and community support?**  
A: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) for additional examples and Q&A.

**Q: Is there comprehensive documentation for all classes and methods?**  
A: Yes, the full API reference is available [here](https://reference.aspose.com/page/java/).

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
