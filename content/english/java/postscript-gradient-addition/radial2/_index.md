---
title: Java PostScript Radial Gradient with Aspose.Page
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
description: Explore the step-by-step guide to add Radial Gradient in Java PostScript using Aspose.Page for stunning graphics in your Java applications.
type: docs
weight: 13
url: /java/postscript-gradient-addition/radial2/
---
## Introduction
Welcome to our step-by-step guide on adding Radial Gradient 2 in Java PostScript using Aspose.Page for Java. This tutorial will walk you through the process of creating a PostScript document with a beautiful radial gradient, enhancing your Java applications with visually appealing graphics.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- A working knowledge of Java programming.
- Installed Java Development Kit (JDK) on your machine.
- Aspose.Page for Java library, which you can download from the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).
## Import Packages
In your Java project, import the necessary packages for Aspose.Page:
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
## Step 1: Set Up Document Directory
Define the path to your document directory:
```java
String dataDir = "Your Document Directory";
```
## Step 2: Create Output Stream
Create an output stream for the PostScript document:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## Step 3: Create Save Options
Create save options with A4 size:
```java
PsSaveOptions options = new PsSaveOptions();
```
## Step 4: Create PS Document
Create a new PS Document with the page opened:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Step 5: Create a Circle
Define a circle using the Ellipse2D.Float class:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Step 6: Define Gradient Colors
Create arrays of colors and fractions for the radial gradient:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Step 7: Create AffineTransform
Create an AffineTransform for the radial gradient:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Step 8: Create Radial Gradient Paint
Create a RadialGradientPaint with the specified parameters:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Step 9: Set Paint and Fill Circle
Set the paint and fill the circle with the radial gradient:
```java
document.setPaint(paint);
document.fill(circle);
```
## Step 10: Close Page and Save Document
Close the current page and save the document:
```java
document.closePage();
document.save();
```
Congratulations! You have successfully added Radial Gradient 2 in Java PostScript using Aspose.Page for Java.
## Conclusion
In this tutorial, we explored how to enhance your Java applications with radial gradients in PostScript documents. Aspose.Page for Java provides a powerful set of tools to create stunning graphics, allowing you to take your Java projects to the next level.
## FAQs
### Q: Where can I find the documentation for Aspose.Page for Java?
A: The documentation is available [here](https://reference.aspose.com/page/java/).
### Q: How can I download Aspose.Page for Java?
A: You can download it from the [releases page](https://releases.aspose.com/page/java/).
### Q: Is there a free trial available?
A: Yes, you can access the free trial [here](https://releases.aspose.com/).
### Q: Can I get a temporary license for Aspose.Page for Java?
A: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Q: Where can I seek community support and participate in discussions?
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
