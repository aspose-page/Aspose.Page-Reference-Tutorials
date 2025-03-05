---
title: Add Horizontal Gradient in Java PostScript
linktitle: Add Horizontal Gradient in Java PostScript
second_title: Aspose.Page Java API
description: Learn how to add a horizontal gradient in Java PostScript with Aspose.Page for Java. Create visually stunning documents effortlessly.
type: docs
weight: 11
url: /java/postscript-gradient-addition/horizontal/
---
## Introduction
Welcome to this comprehensive tutorial on adding a horizontal gradient in Java PostScript using Aspose.Page for Java. Aspose.Page is a powerful Java library that allows developers to work with PostScript and other document formats. In this tutorial, we'll guide you through the process of creating a PostScript document with a horizontal gradient using step-by-step examples.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
- Java Development Kit (JDK) installed on your machine.
- Aspose.Page for Java library. You can download it from the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).
## Import Packages
Begin by importing the necessary packages in your Java project. These packages are crucial for working with Aspose.Page.
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
```java
// Fill the rectangle
document.fill(rectangle);
```
## Step 4: Fill a Text with the Gradient
```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Step 5: Stroke a Text with the Gradient
```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Conclusion
Congratulations! You have successfully added a horizontal gradient in Java PostScript using Aspose.Page for Java. This tutorial provided you with a detailed step-by-step guide to help you create visually appealing PostScript documents.
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