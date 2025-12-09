---
title: Create PostScript Gradient in Java – Add Vertical Gradient
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
description: Learn how to create PostScript gradient in Java using Aspose.Page. This step‑by‑step guide shows you how to add a vertical gradient to your PostScript documents effortlessly.
weight: 14
url: /java/postscript-gradient-addition/vertical/
date: 2025-12-09
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create PostScript Gradient in Java – Add Vertical Gradient

## Introduction
In this comprehensive tutorial, you'll learn how to **create PostScript gradient in Java** with Aspose.Page for Java. Adding a vertical gradient can make your documents look more vibrant and professional, and with just a few lines of code you can achieve stunning visual effects. We'll walk you through each step, explain why each piece matters, and give you practical tips to avoid common pitfalls.  
In this guide we will **create postscript gradient java** step by step.

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I customize colors?** Yes, any `java.awt.Color` can be used  
- **Is rotation supported?** Yes, you can rotate the gradient with an `AffineTransform`  
- **What output format is produced?** A standard PostScript (.ps) file  
- **Do I need a license for production?** Yes, a commercial license is required  

## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
- Java Development Kit (JDK) installed on your machine.  
- Aspose.Page for Java library. You can download it [here](https://releases.aspose.com/page/java/).

## Import Packages
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

Now, let's break down the process of adding a vertical gradient in Java PostScript into multiple steps.

## How to create PostScript gradient Java
Below is a step‑by‑step guide that shows exactly how to **create PostScript gradient in Java** using the Aspose.Page API.

### Step 1: Set up Your Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: Create Save Options with A4 Size
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New PS Document
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create a Rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: Set Up Colors and Fractions for the Gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: Create the Gradient Transform
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: Create Vertical Linear Gradient Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: Set Paint and Fill the Rectangle
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: Close Current Page and Save the Document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Congratulations! You've successfully added a vertical gradient to your Java PostScript document using Aspose.Page for Java.

## Why use vertical gradients in PostScript?
Vertical gradients give your pages depth and visual interest without increasing file size significantly. They are especially useful for:
- Report headers and footers  
- Background fills for charts or diagrams  
- Highlighting sections in technical documents  

## Common Issues and Solutions
- **Gradient appears flat:** Ensure the `AffineTransform` scaling matches the rectangle dimensions.  
- **Colors look washed out:** Verify you are using the correct `ColorSpaceType` (SRGB) and that the fractions array is ordered from 0.0 to 1.0.  
- **File not generated:** Check that the output directory (`dataDir`) exists and the application has write permissions.  

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Yes, Aspose.Page for Java is designed to work seamlessly with other Java libraries.

### Is there a free trial available for Aspose.Page for Java?
Yes, you can get a free trial [here](https://releases.aspose.com/).

### Where can I find additional documentation?
Detailed documentation is available [here](https://reference.aspose.com/page/java/).

### How can I purchase Aspose.Page for Java?
You can purchase Aspose.Page for Java [here](https://purchase.aspose.com/buy).

### Is there a forum for Aspose.Page discussions?
Yes, you can join the community forum [here](https://forum.aspose.com/c/page/39).

## Additional Frequently Asked Questions

**Q: Can I create other gradient directions (horizontal, diagonal)?**  
A: Absolutely. Adjust the start and end points in `LinearGradientPaint` and modify the rotation angle in the `AffineTransform`.

**Q: Does this work with PDF output as well?**  
A: The same gradient logic can be applied when saving to PDF by using `PdfSaveOptions` instead of `PsSaveOptions`.

**Q: How do I change the gradient size dynamically?**  
A: Calculate the rectangle dimensions at runtime and pass those values to both the `Rectangle2D` and the `AffineTransform` constructor.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}