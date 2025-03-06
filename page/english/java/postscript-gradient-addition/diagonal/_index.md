---
title: Add Diagonal Gradient in Java PostScript
linktitle: Add Diagonal Gradient in Java PostScript
second_title: Aspose.Page Java API
description: Enhance your Java PostScript documents with diagonal gradients using Aspose.Page for Java. Follow our step-by-step guide to add vibrant color transitions effortlessly.
weight: 10
url: /java/postscript-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Diagonal Gradient in Java PostScript

## Introduction
Welcome to our step-by-step guide on adding a diagonal gradient in Java PostScript using Aspose.Page for Java. In this tutorial, we'll walk you through the process, breaking down each example into multiple steps. As a proficient SEO writer, I'll ensure that the content is not only informative but also optimized for search engines, making it easy for developers and enthusiasts to follow along.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- Java Development Kit (JDK) installed on your system.
- Integrated Development Environment (IDE) like Eclipse or IntelliJ.
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
## Step 1: Create Output Stream for PostScript Document
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```
## Step 2: Create Save Options with A4 Size
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```
## Step 3: Create New PS Document
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Step 4: Create a Rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Step 5: Create Gradient Transform
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
```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```
## Step 7: Set Paint and Fill the Rectangle
```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```
## Step 8: Close the Current Page and Save the Document
```java
// Close current page and save the document
document.closePage();
document.save();
```
By following these steps, you'll successfully add a diagonal gradient in Java PostScript using Aspose.Page for Java.
## Conclusion
Congratulations! You've learned how to enhance your Java PostScript documents with diagonal gradients using Aspose.Page for Java. Experiment with different parameters to achieve unique visual effects.
## Frequently Asked Questions
### Q: Can I use this library for other graphic operations in Java?
A: Yes, Aspose.Page for Java provides a range of features for working with PostScript and other graphic elements.
### Q: Is there a free trial available for Aspose.Page for Java?
A: Yes, you can get a free trial [here](https://releases.aspose.com/).
### Q: Where can I find documentation for Aspose.Page for Java?
A: The documentation is available [here](https://reference.aspose.com/page/java/).
### Q: How can I purchase a license for Aspose.Page for Java?
A: You can buy a license [here](https://purchase.aspose.com/buy).
### Q: Need assistance or have questions?
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
