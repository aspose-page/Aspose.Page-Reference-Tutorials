---
title: How to Draw Rectangle in Java PostScript with Aspose.Page
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
description: Learn how to draw rectangle shapes in Java PostScript using Aspose.Page. This step‑by‑step guide shows how to set paint, set rectangle color java, and create vibrant graphics.
weight: 11
url: /java/postscript-shapes/add-rectangle/
date: 2025-12-11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Draw Rectangle in Java PostScript with Aspose.Page

## Introduction
If you need to **how to draw rectangle** shapes inside a Java PostScript file, you’ve come to the right place. In this tutorial we’ll walk through using Aspose.Page for Java to add colorful rectangles, control their fill and stroke, and save the result as a PostScript document. You’ll see exactly **how to set paint**, how to define the rectangle’s geometry, and why this approach is ideal for generating printable graphics programmatically.

## Quick Answers
- **What library is required?** Aspose.Page for Java  
- **Can I change rectangle colors?** Yes – use `setPaint` with any `java.awt.Color`  
- **Do I need a license for development?** A free trial works for testing; a license is required for production  
- **Which page size is used in the example?** A4 (default `PsSaveOptions`)  
- **Is the code compatible with Java 8+?** Absolutely – it uses standard AWT classes  

## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
- Basic understanding of Java programming.  
- Aspose.Page for Java library installed. If not, download it from the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- A Java development environment set up on your machine.

## Import Packages
In your Java project, start by importing the necessary packages:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## How to Draw Rectangle in Java PostScript
Below is the complete workflow broken into clear steps. Each step includes a short explanation followed by the original code block (unchanged).

### Step 1: Set Paint for Filling Rectangle  
**How to set paint** – we choose an orange fill color for the first rectangle.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Step 2: Set Paint for Stroking Rectangle  
**Set rectangle color java** – now we change the paint to red and define a stroke width.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Step 3: Close Current Page and Save Document  
After drawing, we close the page and persist the file.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Why Use Aspose.Page for Rectangle Graphics?
- **Cross‑platform**: Generates standard PostScript that works on any printer.  
- **Fine‑grained control**: You can set fill colors, stroke colors, and line widths independently.  
- **No external dependencies**: Uses only the built‑in AWT geometry classes.  

## Common Issues & Tips
- **File path errors** – ensure `dataDir` ends with a file separator (`/` or `\\`).  
- **License exceptions** – the trial version adds a watermark; obtain a full license for production use.  
- **Color visibility** – some printers may interpret certain RGB values differently; test with a simple black rectangle first.

## Conclusion
In this guide we demonstrated **how to draw rectangle** shapes in a Java PostScript document, covered **how to set paint**, and showed how to **set rectangle color java** using Aspose.Page. Feel free to experiment with different shapes, colors, and line styles to create rich printable graphics for reports, invoices, or custom prints.

## Frequently Asked Questions

### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page primarily supports Java, but similar libraries are available for other languages.

### Is there a trial version of Aspose.Page for Java available?
Yes, you can explore the features of Aspose.Page for Java with the [free trial version](https://releases.aspose.com/).

### Where can I find additional help and discussions?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to engage with the community and get assistance.

### How can I obtain a temporary license for Aspose.Page for Java?
Get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Where can I purchase a licensed version of Aspose.Page for Java?
Buy a licensed version [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Can I change the rectangle size dynamically?*  
**A:** Yes – simply modify the `Rectangle2D.Float(x, y, width, height)` parameters before calling `fill` or `draw`.

**Q:** *Is it possible to add text inside the rectangle?*  
**A:** Absolutely. After drawing the rectangle, use `document.drawString(...)` with the desired font and position.

**Q:** *Does Aspose.Page support other shapes like circles or polygons?*  
**A:** Yes, the API provides methods such as `drawEllipse` and `drawPolygon` for a variety of vector graphics.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}