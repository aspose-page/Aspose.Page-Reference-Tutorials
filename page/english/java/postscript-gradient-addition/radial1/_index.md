---
date: 2026-09-09
description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
  This step‑by‑step guide shows you how to add a color stops gradient, set radii,
  and generate a PS file quickly.
images:
- /java/postscript-gradient-addition/radial1/og-image.png
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Mastering radial gradients in Java
og_description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
  This guide explains how to add color stops gradient, set radii, and generate a PS
  file in minutes.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: How to create radial gradient in Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: How to create radial gradient in Java PostScript
url: /java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create radial gradient in Java PostScript with Aspose.Page

## Introduction
If you need to **create a radial gradient** inside a PostScript file, you’ve come to the right place. In this tutorial we’ll walk through every step required to generate a PostScript document that contains a smooth radial gradient, using **Aspose.Page for Java**. By the end you’ll understand the API, see a complete runnable example, and know how to tweak colors, positions, and radii for any design scenario.

## Quick answers
- **What library creates radial gradients in PostScript?** Aspose.Page for Java.  
- **How long does the implementation take?** About 10‑15 minutes for a basic example.  
- **Do I need a license to run the code?** A free trial works for development; a commercial license is required for production.  
- **Which Java version is supported?** Java 8 or higher.  
- **Can I change the gradient’s shape?** Yes – adjust the radius and center point in the `RadialGradientPaint` constructor.

## How to create radial gradient in Java

Load your Java project, import the required classes, and follow the step‑by‑step guide below. The core answer is that you instantiate a `RadialGradientPaint` with your color stops and then apply it to a rectangle drawn on a `PsDocument`. This two‑object approach handles all low‑level PostScript commands for you.

## What is a radial gradient?
`RadialGradientPaint` is a Java AWT class that defines a circular color transition from a central point outward. It creates a smooth blend of multiple color stops, making it ideal for spotlights, soft backgrounds, or any effect where colors radiate from a focal point.

## Why use Aspose.Page for radial gradients?
Aspose.Page gives you full programmatic control over PostScript output while handling the heavy lifting of low‑level PS syntax. It supports **50+ input and output formats**, can render multi‑hundred‑page documents without loading the entire file into memory, and runs on any operating system that supports Java 8+. This quantified capability makes it a reliable choice for enterprise‑grade graphics generation.

## Prerequisites
- **Java Development Kit (JDK) 8+** – verify with `java -version`.  
- **Aspose.Page for Java** – download the latest JAR from the official [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE of your choice** – Eclipse, IntelliJ IDEA, or VS Code with Java extensions.  
- **A writable folder** – where the generated `.ps` file will be saved.

## Import packages
First, import the classes we’ll need. The `java.awt` package provides the gradient paint objects, while `com.aspose.eps` contains the PostScript document handling classes.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step‑by‑step guide

### Step 1: create a rectangle and open a PS document
`PsDocument` is Aspose.Page's class that represents a PostScript document and provides methods to draw shapes, text, and images. We start by creating an output stream, configuring the page size (A4 by default), and defining a rectangle that will host the gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Pro tip:** Adjust the rectangle’s coordinates (`200, 100, 200, 200`) to position the gradient anywhere on the page.

### Step 2: define colors and fractions
A radial gradient is built from *color stops* (the colors) and *fractions* (the relative positions of those stops). Here we create an array of six colors and their corresponding fractions.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Why this matters:** By tweaking `fractions` you control how quickly the colors transition, enabling subtle or dramatic effects.

### Step 3: create radial gradient paint
`RadialGradientPaint` is the core class that describes a radial color gradient, including center point, radius, focus point, fractions, colors, cycle method, and color space. Now we build the `RadialGradientPaint` object using the arrays defined above.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Note:** `transform` can be `null` if you don’t need additional scaling or rotation. Feel free to experiment with `AffineTransform` for skewed gradients.

### Step 4: set paint and fill the rectangle
With the paint ready, we tell the `PsDocument` to use it and then fill the rectangle we defined earlier.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

At this point the PostScript page contains a rectangle smoothly filled with the radial gradient we configured.

### Step 5: close and save the document
Finally, close the current page and write the file to disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Open `RadialGradient1_outPS.ps` in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered exactly as defined.

## Common issues & solutions
| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Gradient appears as a solid color | `fractions` array does not start at `0.0f` or end at `1.0f` | Ensure the first fraction is `0.0f` and the last is `1.0f`. |
| Colors look washed out | Using the wrong `ColorSpaceType` | Switch to `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` for more vibrant output. |
| No output file generated | `FileOutputStream` path is invalid or not writable | Verify `dataDir` exists and the application has write permissions. |

## Frequently asked questions

**Q: Can I use Aspose.Page for Java in commercial projects?**  
A: Yes. A commercial license is required for production use. You can purchase one from the [Aspose licensing page](https://purchase.aspose.com/buy).

**Q: Where can I find the official API reference?**  
A: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Is a free trial available for testing?**  
A: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).

**Q: How do I obtain a temporary license for evaluation?**  
A: A temporary license can be requested from the [temporary license request page](https://purchase.aspose.com/temporary-license/).

**Q: Where can I get community support?**  
A: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusion
You now know **how to create radial gradient** in a Java PostScript document using Aspose.Page. By adjusting the rectangle size, color stops, and gradient radius you can create countless visual effects—from subtle background fills to bold spotlight graphics. Feel free to experiment with different `AffineTransform` values to rotate or skew the gradient, and combine this technique with text and images for richer PDF or EPS outputs.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java latest (as of writing)  
**Author:** Aspose

## Related Tutorials

- [Fill Shape with Gradient: Java PostScript Radial Example](/page/java/postscript-gradient-addition/radial2/)
- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}