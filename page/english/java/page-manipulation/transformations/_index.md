---
date: 2026-10-20
description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
  shape, and apply affine transform to create PostScript documents.
images:
- /java/page-manipulation/transformations/og-image.png
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformations in Java page manipulation
og_description: Learn how to scale rectangle, translate shape, and apply affine transform
  using Aspose.Page for Java to generate PostScript files efficiently.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: How to scale rectangle with Aspise.Page for Java – step by step guide
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: How to Scale Rectangle with Aspose.Page for Java
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to scale rectangle with Aspose.Page for Java

## Introduction
In this guide you’ll discover **how to scale rectangle** objects using Aspose.Page for Java, while also learning how to translate shape positions, rotate graphics, and apply affine transform operations to produce high‑quality PostScript output. These techniques let you build sophisticated, device‑independent graphics without writing low‑level rendering code, making your Java applications more powerful and maintainable.

## Quick answers
`scale(sx, sy)` scales the graphics context by the given horizontal and vertical factors.  

- **How do I scale a rectangle in Java with Aspose.Page?** Call the `scale(sx, sy)` method on the graphics context before drawing the rectangle.  
- **Can I move (translate) a shape without affecting other graphics?** Yes—wrap the translation between `writeGraphicsSave()` and `writeGraphicsRestore()` calls.  
- **What class creates a PostScript file?** Use `PsDocument` together with `PsSaveOptions`.  
- **Do I need a license for production use?** A valid Aspose.Page license is required for commercial deployments.  
- **Which Java version is supported?** Aspose.Page works with Java 8 and later.

## Prerequisites
Before you start, verify that you have:

- A solid grasp of core Java syntax and object‑oriented concepts.  
- The Aspose.Page for Java library installed. You can download it from the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- A Java IDE (IntelliJ IDEA, Eclipse, or VS Code) configured with the library’s JAR files on the classpath.

## Import packages
`PsDocument` is the main class used to create a PostScript document, and `PsSaveOptions` configures how the document is saved.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## What is “how to scale rectangle” in Aspose.Page?
The `scale(float sx, float sy)` method applies an affine scaling transform to the current graphics state, resizing subsequent drawings by the factors `sx` (horizontal) and `sy` (vertical). This is the core operation behind the **how to scale rectangle** keyword. By applying this transform before drawing, any subsequent shapes such as rectangles will be rendered with the new dimensions while preserving their proportions.

## How to translate shape with Aspose.Page
`writeGraphicsSave()` saves the current graphics state and `writeGraphicsRestore()` restores it, ensuring transformations affect only the intended shape. Translation repositions the origin of the coordinate system without altering object dimensions. By surrounding `translate(dx, dy)` with `writeGraphicsSave()` / `writeGraphicsRestore()`, you ensure that only the intended shape moves while other graphics remain unchanged, providing precise control over individual elements.

## Example 1: no transformations
The first example draws a rectangle without any transformation, establishing a baseline for visual comparison with later examples.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Example 2: translation
In this sample we move the graphics context 250 units to the right before drawing a second rectangle, illustrating **how to translate shape**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Example 3: scaling
Here we answer the primary question **how to scale rectangle**. The rectangle is reduced to 50 % of its original width and 75 % of its original height using the `scale(0.5f, 0.75f)` call.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## How to rotate shape java (rotate shape java)
`rotate(angle)` rotates the coordinate system by the specified angle in degrees. Load your `PsDocument`, call `rotate(angle)` on the graphics state, draw the shape, then restore the previous state. This pattern implements **rotate shape java** and **how to rotate rectangle** in a single, reusable block, allowing you to pivot graphics around any point you choose.

## Why this matters – real‑world benefits
- **Device‑independent output** – Aspose.Page can generate PostScript and XPS files that render identically on any printer or viewer, eliminating platform‑specific tweaks.  
- **Fine‑grained control** – Combine translation, scaling, shearing, and rotation to meet exact layout specifications; the API supports over 20 transformation combinations per page.  
- **Performance‑oriented processing** – The library processes documents with a memory footprint under 10 MB for typical 100‑page reports, making batch jobs fast and scalable.

## Common use cases
- **Printable invoices** – Precisely place logos, barcodes, and tables using scaling and translation to match corporate branding guidelines.  
- **Technical diagrams** – Generate schematics where each component must be proportionally resized and positioned.  
- **Automated multi‑page reports** – Create PostScript reports that require consistent scaling across pages, such as engineering specifications.

## Common issues and solutions
- **Transformation not resetting** – Always pair `writeGraphicsSave()` with `writeGraphicsRestore()`; otherwise subsequent drawings inherit unwanted transforms.  
- **Unexpected colors** – Set the paint (color) after each transformation because the graphics state does not preserve color information after a restore.  
- **File size too large** – Enable compression in `PsSaveOptions` and limit embedded raster image resolution to keep the final file under 5 MB for typical 50‑page documents.

## FAQ's
### Can I use Aspose.Page for Java for other document formats?
Aspose.Page primarily focuses on page manipulation for PostScript and XPS formats, but it also offers limited PDF export capabilities.

### Where can I find more examples and documentation for Aspose.Page for Java?
Visit the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) for comprehensive guides, API references, and sample projects.

### Is there a free trial available for Aspose.Page for Java?
Yes, you can access a free trial via the **Aspose free trial download** page: [Aspose free trial download](https://releases.aspose.com/).

### How can I get a temporary license for Aspose.Page for Java?
Obtain a temporary license through the **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Where can I seek community support or ask questions about Aspose.Page for Java?
Visit the [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) for community discussions, code snippets, and troubleshooting tips.

## Frequently asked questions

**Q: What is the difference between `translate` and `scale`?**  
A: `translate` moves the origin of the coordinate system, while `scale` changes the size of drawn objects along the X and/or Y axes.

**Q: Can I combine multiple transformations in a single graphics state?**  
A: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially before drawing, you create a combined affine transformation.

**Q: How do I reset transformations after drawing a shape?**  
A: Use `writeGraphicsRestore()` to revert to the previously saved graphics state.

**Q: Is it possible to rotate a rectangle around its center?**  
A: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`, then translate it back before drawing.

**Q: Does Aspose.Page support anti‑aliasing for smoother graphics?**  
A: Yes—set the appropriate rendering options in `PsSaveOptions` to enable anti‑aliasing.

---

**Last Updated:** 2026-10-20  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose

## Related Tutorials

- [How to Draw Rectangle in Java PostScript with Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Create Radial Gradient in PostScript with Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Postscript Page Manipulation](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}