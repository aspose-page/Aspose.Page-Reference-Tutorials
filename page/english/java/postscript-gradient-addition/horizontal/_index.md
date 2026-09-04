---
date: 2026-09-04
description: Learn how to create horizontal gradient java in a PostScript file using
  Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
  pitfalls, and FAQs.
images:
- /java/postscript-gradient-addition/horizontal/og-image.png
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Create horizontal gradient java in PostScript using Aspose
og_description: Create horizontal gradient java in PostScript with Linear Gradient
  Paint Java. This Aspose.Page tutorial shows you the exact steps, prerequisites,
  and troubleshooting tips in under 15 minutes.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Create horizontal gradient java in PostScript using Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Create horizontal gradient java in PostScript using Aspose
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to add a horizontal gradient in Java PostScript using Linear Gradient Paint

## Introduction
In this comprehensive tutorial you’ll learn **how to create horizontal gradient java** in a PostScript document by using the **Linear Gradient Paint Java** class that ships with Aspose.Page for Java. We’ll walk through every step—from setting up the project to rendering the gradient on both shapes and text—so you can produce polished, print‑ready graphics in minutes. Whether you’re building a reporting engine, a design‑automation tool, or a custom printer driver, this guide gives you the exact code you need.

## Quick answers
- **What library is required?** Aspose.Page for Java (includes Linear Gradient Paint Java).  
- **How long does implementation take?** About 10‑15 minutes for a basic horizontal gradient.  
- **Do I need a license?** A temporary or full license is required for production use.  
- **Which JDK version works?** Java 8 or newer.  
- **Can I use the gradient on both shapes and text?** Yes – the same `LinearGradientPaint` instance can fill shapes and be applied to text strokes or fills.

## What is a horizontal gradient and why use it?
A horizontal gradient blends colors from the left edge of an object to its right edge, creating a smooth transition that adds depth and visual interest. It’s ideal for modern UI components, highlighted headings, or subtle background shadings in PDF or PostScript reports. Using **Linear Gradient Paint Java** lets you precisely control start‑and end‑colors, opacity, and scaling, ensuring the result looks crisp on any device or printer.

## Prerequisites
Before diving into the code, make sure you have the following:

- Java Development Kit (JDK) installed on your machine.  
- Aspose.Page for Java library. You can download it from the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Import packages
Begin by importing the necessary packages in your Java project. These imports give you access to graphics primitives, gradient handling, and the Aspose.Page API.

The `PsDocument` class represents a PostScript document that you can draw graphics onto.  

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: create a rectangle
First, set up the output stream, document, and a rectangle that will host the gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 2: create horizontal linear gradient paint
`LinearGradientPaint` is the core class that defines a linear color transition.  
The `LinearGradientPaint` class represents a paint object that renders a gradient along a straight line; you specify start/end points, color stops, and an optional `AffineTransform` to scale it to your shape.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Step 3: fill the rectangle
Now fill the rectangle with the gradient we just defined.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Step 4: fill a text with the gradient
You can also apply the same gradient to text, creating a striking visual effect.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Step 5: stroke a text with the gradient
Finally, outline text using the gradient as the stroke color.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Common issues and solutions
| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Gradient appears stretched | Incorrect `AffineTransform` scaling | Ensure the transform’s width and height match the rectangle’s dimensions (200 × 100 in the example). |
| Colors look faded | Alpha values set too low | Increase the alpha component (the fourth value in `new Color(r,g,b,alpha)`). |
| Text is not visible | Paint not set before drawing text | Call `document.setPaint(paint)` **before** any `fillAndStrokeText` or `outlineText` calls. |

## Frequently asked questions
**Q:** Can I use Aspose.Page for Java in commercial projects?  
**A:** Yes, Aspose.Page for Java can be used in commercial projects. For licensing details, visit the [Aspose.Purchase](https://purchase.aspose.com/buy) page.

**Q:** Is there a free trial available?  
**A:** Yes, you can access a free trial of Aspose.Page for Java on the [Aspose.Page for Java free trial](https://releases.aspose.com/) page.

**Q:** Where can I find additional documentation and support?  
**A:** Visit the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) for comprehensive resources. For community help, check the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** How can I obtain a temporary license?  
**A:** You can obtain a temporary license from the [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/).

**Q:** What are the system requirements for Aspose.Page for Java?  
**A:** Refer to the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) for detailed system requirements.

---

**Last Updated:** 2026-09-04  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Related Tutorials

- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Create PostScript Gradient – Radial Gradient in Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}