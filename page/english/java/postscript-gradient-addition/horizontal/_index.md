---
title: Add Gradient in Java PostScript using Linear Gradient Paint Java
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
description: Learn how to add a horizontal gradient in Java PostScript using Linear Gradient Paint Java with Aspose.Page for Java.
weight: 11
url: /java/postscript-gradient-addition/horizontal/
date: 2025-12-07
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Gradient in Java PostScript using Linear Gradient Paint Java

## Introduction
In this comprehensive tutorial you'll discover how to create a beautiful horizontal gradient in a PostScript document by leveraging **Linear Gradient Paint Java**. Aspose.Page for Java makes it straightforward to work with PostScript, PDF, and other vector formats, and the `LinearGradientPaint` class gives you fine‑grained control over color transitions. By the end of this guide, you’ll be able to render gradients on shapes **and** text, giving your documents a professional, eye‑catching look.

## Quick Answers
- **What library is required?** Aspose.Page for Java (supports Linear Gradient Paint Java).  
- **How long does implementation take?** About 10‑15 minutes for a basic gradient.  
- **Do I need a license?** A temporary or full license is required for production use.  
- **Which JDK version works?** Java 8 or newer.  
- **Can I use the gradient on both shapes and text?** Yes – you can fill shapes and stroke or fill text with the same gradient.

## Prerequisites
Before diving into the code, make sure you have the following:

- Java Development Kit (JDK) installed on your machine.  
- Aspose.Page for Java library. You can download it from the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Import Packages
Begin by importing the necessary packages in your Java project. These imports give you access to graphics primitives, gradient handling, and the Aspose.Page API.

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

## Step 1: Create a Rectangle
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

## Step 2: Create Horizontal Linear Gradient Paint
Here we build the **Linear Gradient Paint Java** object that defines a horizontal color transition. The `AffineTransform` scales the gradient to match the rectangle’s width and height.

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

## Step 3: Fill the Rectangle
Now fill the rectangle with the gradient we just defined.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Step 4: Fill a Text with the Gradient
You can also apply the same gradient to text, creating a striking visual effect.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Step 5: Stroke a Text with the Gradient
Finally, outline text using the gradient as the stroke color.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Common Issues and Solutions
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| Gradient appears stretched | Incorrect `AffineTransform` scaling | Ensure the transform’s width and height match the rectangle’s dimensions (200 × 100 in the example). |
| Colors look faded | Alpha values set too low | Increase the alpha component (the fourth value in `new Color(r,g,b,alpha)`). |
| Text is not visible | Paint not set before drawing text | Call `document.setPaint(paint)` **before** any `fillAndStrokeText` or `outlineText` calls. |

## Frequently Asked Questions
### Can I use Aspose.Page for Java in commercial projects?
Yes, Aspose.Page for Java can be used in commercial projects. For licensing details, visit [Aspose.Purchase](https://purchase.aspose.com/buy).

### Is there a free trial available?
Yes, you can access a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).

### Where can I find additional documentation and support?
Visit the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) for comprehensive resources. For community support, check the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

### How can I obtain a temporary license?
You can obtain a temporary license from [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### What are the system requirements for Aspose.Page for Java?
Refer to the [documentation](https://reference.aspose.com/page/java/) for detailed system requirements.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}