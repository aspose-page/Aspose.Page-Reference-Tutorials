---
date: 2026-09-14
description: Learn how to create postscript gradient java with Aspose.Page. This step‑by‑step
  guide shows you how to add a vertical gradient to a PostScript file in just a few
  lines of Java code.
images:
- /java/postscript-gradient-addition/vertical/og-image.png
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Add Vertical Gradient in Java PostScript
og_description: Learn how to create postscript gradient java with Aspose.Page. This
  step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
  in just a few lines of Java code.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Create postscript gradient java – vertical gradient
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Create postscript gradient java – vertical gradient
url: /java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create postscript gradient java – vertical gradient

## Introduction
Aspose.Page for Java is a library that enables creation and manipulation of PostScript and PDF files programmatically. In this comprehensive tutorial you’ll learn how to **create postscript gradient java** using that library. Adding a vertical gradient can make your documents look more vibrant and professional, and with just a few lines of code you can achieve stunning visual effects. We’ll walk you through each step, explain why each piece matters, and give you practical tips to avoid common pitfalls. By the end of this guide you’ll be able to generate PostScript files that have smooth, eye‑catching vertical color transitions.

## Quick answers
- **What library is needed?** Aspose.Page for Java  
- **Can I customize colors?** Yes, any `java.awt.Color` can be used  
- **Is rotation supported?** Yes, you can rotate the gradient with an `AffineTransform`  
- **What output format is produced?** A standard PostScript (.ps) file  
- **Do I need a license for production?** Yes, a commercial license is required  

## Why add a vertical gradient to a PostScript document?
Adding a vertical gradient gives your pages depth, improves visual hierarchy, and keeps file size low because the gradient is defined in vector form rather than raster images. This technique is perfect for report headers, technical manuals, or any flyer that needs a modern look without sacrificing scalability.

## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
- Java Development Kit (JDK) installed on your machine.  
- Aspose.Page for Java library. You can download it from the [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).

## Import packages
In your Java project, import the necessary packages to get started:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Now, let’s walk through the process of adding a vertical gradient step by step.

## How to create postscript gradient java
Load your Java environment, create a `PsSaveOptions` instance, and call `Document.save` – that’s the core sequence that creates a PostScript file with a vertical gradient. The API handles color interpolation, coordinate transforms, and page flushing for you, so you only need to focus on defining the rectangle and the gradient parameters.

### Step 1: set up your document directory
`File` objects represent the folder where the output will be written. The directory must exist before the stream is opened, otherwise an `IOException` is thrown.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: create output stream for PostScript document
`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources` block guarantees that the stream is closed even if an exception occurs.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: create save options with A4 size
`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts. Setting the size to A4 (595 × 842 points) matches most printable documents.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: create a new PS document
`Document` is the top‑level object that represents a single PostScript file in memory. All drawing commands are issued against this object.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: create a rectangle
`Rectangle2D.Double` defines the area that will be filled with the gradient. The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: set up colors and fractions for the gradient
A `float[]` array defines the position of each color stop (from 0.0 to 1.0). `Color` objects hold the actual RGB values. You can use any `java.awt.Color` you like.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: create the gradient transform
`AffineTransform` scales and rotates the gradient. For a pure vertical gradient you only need to scale the Y‑axis; rotation can be added later if desired.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: create vertical linear gradient paint
`LinearGradientPaint` ties together the rectangle, the color stops, and the transform. This object is later passed to the graphics context.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: set paint and fill the rectangle
`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside the rectangle you defined earlier.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: close current page and save the document
Calling `document.save` writes the entire PostScript stream to the output file and releases all native resources.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Congratulations! You’ve successfully added a vertical gradient to your Java PostScript document using Aspose.Page for Java.

## Common issues and solutions
- **Gradient appears flat:** Ensure the `AffineTransform` scaling matches the rectangle dimensions.  
- **Colors look washed out:** Verify you are using the correct `ColorSpaceType` (SRGB) and that the fractions array is ordered from 0.0 to 1.0.  
- **File not generated:** Check that the output directory (`dataDir`) exists and the application has write permissions.  

## Frequently asked questions
**Q: Can I use Aspose.Page for Java with other Java libraries?**  
A: Yes, Aspose.Page for Java is designed to work seamlessly alongside other Java libraries such as Apache Commons or Spring.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).

**Q: Where can I find additional documentation?**  
A: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: How can I purchase Aspose.Page for Java?**  
A: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).

**Q: Is there a forum for Aspose.Page discussions?**  
A: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

## Additional frequently asked questions

**Q: Can I create other gradient directions (horizontal, diagonal)?**  
A: Absolutely. Adjust the start and end points in `LinearGradientPaint` and modify the rotation angle in the `AffineTransform`.

**Q: Does this work with PDF output as well?**  
A: The same gradient logic can be applied when saving to PDF by using `PdfSaveOptions` instead of `PsSaveOptions`.

**Q: How do I change the gradient size dynamically?**  
A: Calculate the rectangle dimensions at runtime and pass those values to both the `Rectangle2D` and the `AffineTransform` constructor.

---

**Last Updated:** 2026-09-14  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose

## Related Tutorials

- [Create Radial Gradient in PostScript with Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [How to Convert PostScript to PDF Using Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}