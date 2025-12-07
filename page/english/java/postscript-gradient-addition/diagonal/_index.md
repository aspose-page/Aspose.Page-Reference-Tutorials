---
title: "Add Diagonal Gradient in Java PostScript using Aspose.Page Java"
linktitle: "Add Diagonal Gradient in Java PostScript using Aspose.Page Java"
second_title: "Aspose.Page Java API"
description: "Enhance your Java PostScript documents with diagonal gradients using Aspose.Page Java. Learn how to add gradient effects with LinearGradientPaint in Java and create vibrant color transitions effortlessly."
weight: 10
url: /java/postscript-gradient-addition/diagonal/
date: 2025-12-07
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Diagonal Gradient in Java PostScript using Aspose.Page Java

## Introduction
If you’re looking to enrich a PostScript file with a smooth diagonal color transition, **Aspose.Page Java** makes it surprisingly easy. In this tutorial we’ll walk through **how to add gradient** effects step‑by‑step, using the `LinearGradientPaint` class from Java 2D. By the end you’ll have a ready‑to‑run snippet that creates a PostScript document with a vibrant diagonal gradient.

## Quick Answers
- **What library is required?** Aspose.Page for Java.  
- **Which class creates the gradient?** `LinearGradientPaint`.  
- **Can I change the colors?** Yes – modify the `Color[]` array.  
- **Do I need a license for production?** A commercial license is required; a free trial is available.  
- **How long does the implementation take?** Around 10 minutes for a basic gradient.

## What is Aspose.Page Java?
Aspose.Page Java is a powerful API that lets developers generate, edit, and convert PostScript and PDF files without needing any external software. It exposes the full graphics capabilities of the PostScript language through a clean, object‑oriented Java interface.

## Why use a diagonal gradient?
A diagonal gradient adds depth and visual interest to charts, banners, or any graphic element that needs a modern look. Because the gradient runs from one corner to the opposite, it works well for backgrounds, button skins, and decorative shapes.

## Prerequisites
Before you start, make sure you have:

- Java Development Kit (JDK) 8 or higher.  
- An IDE such as Eclipse, IntelliJ IDEA, or VS Code.  
- **Aspose.Page for Java** library – download the latest version from the [official download page](https://releases.aspose.com/page/java/).

## Import Packages
First, import the Java 2D and Aspose classes you’ll need. These imports give you access to color definitions, geometric shapes, gradient painting, and the PostScript document API.

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

## Step 1: Create Output Stream for PostScript Document
We start by defining the folder where the file will be saved and opening a `FileOutputStream`. This stream will receive the generated PostScript data.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Step 2: Create Save Options with A4 Size
`PsSaveOptions` lets you specify page size, resolution, and other output settings. Here we use the default A4 size.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Step 3: Create New PS Document
Instantiate a `PsDocument` using the output stream and the save options. The `false` flag tells the constructor not to automatically open a new page – we’ll do that later.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Create a Rectangle
Define the rectangle that will receive the gradient fill. The rectangle’s position (200, 100) and size (200 × 100) are chosen to make the gradient clearly visible.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 5: Create Gradient Transform
A `AffineTransform` lets us rotate, scale, and translate the gradient so that it runs diagonally across the rectangle. The math below calculates the hypotenuse and adjusts the scaling ratio accordingly.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Step 6: Create Diagonal Linear Gradient Paint
Here’s the core of **how to add gradient** – we build a `LinearGradientPaint` that spans from the rectangle’s top‑left to its bottom‑right, using the previously defined transform. The `MultipleGradientPaint.CycleMethod.NO_CYCLE` ensures the gradient does not repeat.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Step 7: Set Paint and Fill the Rectangle
Apply the gradient paint to the document and fill the rectangle shape. This step renders the diagonal color transition onto the PostScript page.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Step 8: Close the Current Page and Save the Document
Finally, close the page, flush the stream, and save the file. The resulting `DiagonalGradient_outPS.ps` file can be opened with any PostScript viewer.

```java
// Close current page and save the document
document.closePage();
document.save();
```

By following these eight steps you’ve successfully added a diagonal gradient to a PostScript document using **Aspose.Page Java**. Feel free to experiment with different colors, angles, and rectangle sizes to create custom visual effects.

## Common Issues & Tips
- **Gradient appears flat** – double‑check the rotation angle; a 45° rotation creates a true diagonal.
- **Colors look washed out** – ensure you’re using `MultipleGradientPaint.ColorSpaceType.SRGB` for accurate color rendering.
- **File not found error** – verify that `dataDir` points to an existing folder and that the application has write permissions.

## Frequently Asked Questions

**Q: Can I use this library for other graphic operations in Java?**  
A: Yes, Aspose.Page for Java provides a full set of drawing primitives, text rendering, and image handling capabilities.

**Q: Is there a free trial available for Aspose.Page Java?**  
A: Absolutely. You can download a fully functional trial from the [Aspose free trial page](https://releases.aspose.com/).

**Q: Where can I find documentation for Aspose.Page Java?**  
A: The official API reference is available [here](https://reference.aspose.com/page/java/).

**Q: How can I purchase a license for Aspose.Page Java?**  
A: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).

**Q: Need assistance or have questions?**  
A: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39) for help from both Aspose engineers and fellow developers.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}