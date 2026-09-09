---
date: 2026-09-09
description: Learn how to create gradient in Java PostScript and add gradient to shape
  using Aspose.Page. Follow this step‑by‑step guide with code and tips.
images:
- /java/postscript-gradient-addition/radial2/og-image.png
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient with Aspose.Page
og_description: Learn how to create gradient in Java PostScript and add gradient to
  shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: How to create gradient in Java PostScript with radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: How to create gradient in Java PostScript with radial fill
url: /java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create gradient in Java PostScript with radial fill

## Introduction
In this tutorial you’ll learn **how to create gradient** graphics in a PostScript document using Java and Aspose.Page. We’ll walk through every step—from project setup to rendering a circle filled with a smooth radial gradient—so you can **add gradient to shape** objects instantly and elevate the visual quality of your Java applications.

## Quick answers
- **What does this tutorial create?** A PostScript file (`.ps`) containing a circle filled with a radial gradient.  
- **Which library is required?** Aspose.Page for Java (latest version).  
- **How long does implementation take?** Approximately 10‑15 minutes for a working example.  
- **Do I need a license?** A temporary or full license is required for production use; a free trial works for development.  
- **Can I reuse the code for PDF or SVG?** Yes—Aspose.Page supports multiple output formats with minimal changes.

## How to fill shape with gradient in PostScript
You can fill a shape with a radial gradient in PostScript by creating a `PsDocument`, defining a `RadialGradientPaint`, applying it to the target shape, and finally saving the document. This concise workflow lets you produce professional‑looking vector graphics without raster images, and the same code can be reused for PDF or SVG output. The process is straightforward and works consistently across all supported formats.

## What is a radial gradient?
A radial gradient transitions colors outward from a central point, creating a smooth, circular blend. It’s ideal for highlights, button backgrounds, or any visual that needs a natural “glow” effect. By varying the color stops and radius, you can simulate lighting, depth, and material properties in pure vector form.

## Why use Aspose.Page for radial gradients?
Aspose.Page lets you generate device‑independent vector graphics with a single Java API. It supports over 50 input and output formats—including PostScript, PDF, and SVG—while preserving color accuracy and anti‑aliasing for high‑resolution output. The library also provides easy‑to‑use gradient classes, making complex visual effects simple to implement.

## Prerequisites
Before we dive in, make sure you have:

- Basic familiarity with Java programming.  
- JDK 8 or newer installed on your machine.  
- Aspose.Page for Java library (download from the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Import packages
First, import the classes we’ll need. These include standard AWT graphics types and the Aspose.Page API.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: set up document directory
Define the folder where the generated PostScript file will be saved. Replace the placeholder with an actual path on your system.

```java
String dataDir = "Your Document Directory";
```

## Step 2: create output stream
FileOutputStream writes raw bytes to a file, allowing binary data to be saved. Opening one targeting a `.ps` file lets Aspose.Page stream the generated PostScript data directly to disk.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Step 3: create save options
PsSaveOptions configures how a PostScript file is saved, including page size and compression. You can customize these settings, but the defaults are fine for this example.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Step 4: create ps document
PsDocument represents a PostScript document in memory and provides methods to add pages and graphics.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: create a circle
`Ellipse2D.Float` describes an ellipse shape; when width = height it becomes a perfect circle. This object will serve as the canvas for our gradient fill.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## How to draw circle with gradient
To draw a circle with a radial gradient, you load a `RadialGradientPaint` into the graphics context and then fill the previously defined ellipse. This single operation paints the shape with a smooth color transition from the center outward, creating a visually appealing effect.

## Step 6: define gradient colors
Prepare two arrays: one for the colors that will appear in the gradient and another for the corresponding fractional positions (0 = center, 1 = edge).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Step 7: create affinetransform
AffineTransform is a matrix that can translate, rotate, scale, or shear graphics objects. Here it scales and translates the gradient so it fits precisely inside the circle.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Step 8: create radial gradient paint
RadialGradientPaint creates a radial color gradient based on a center point, radius, and color stops.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Step 9: set paint and fill circle
Apply the gradient paint to the document and fill the previously defined circle. This is the core of our **radial gradient example** and demonstrates how to **fill shape with gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Step 10: close page and save document
Finalize the page, write the content to disk, and close the stream. Your PostScript file is now ready to view with any PS viewer.

```java
document.closePage();
document.save();
```

Congratulations! You have successfully created a radial gradient example in Java PostScript using Aspose.Page. You now have a reusable pattern for **fill shape with gradient** that can be adapted to other shapes and output formats.

## Common issues and solutions
| Problem | Solution |
|---------|----------|
| **FileNotFoundException** when opening the output stream | Verify that `dataDir` points to an existing folder and you have write permissions. |
| Gradient looks flat or missing | Ensure the `fractions` array matches the `colors` array length and that the `AffineTransform` scales correctly. |
| Colors appear inverted | Swap the order of colors in the `colors` array or adjust the `focus` point coordinates. |

## Frequently asked questions

**Q: Where can I find the documentation for Aspose.Page for Java?**  
A: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).

**Q: How can I download Aspose.Page for Java?**  
A: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).

**Q: Is there a free trial available?**  
A: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).

**Q: Can I obtain a temporary license for testing?**  
A: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Where can I get community support?**  
A: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Conclusion
In this guide we built a complete **radial gradient example** for a PostScript document using Aspose.Page for Java. By following the steps you now have a reusable pattern for **fill shape with gradient**, which you can adapt to PDF, SVG, or any other format supported by Aspose.Page. Experiment with different colors, radii, and shapes to enrich your Java graphics projects.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Related Tutorials

- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [Create Texture Pattern in PostScript with Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}