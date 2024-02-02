---
title: Add Horizontal Gradient in Java XPS
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
description: Learn how to add a stunning horizontal gradient to XPS documents in Java using Aspose.Page. Follow our step-by-step guide for seamless integration.
type: docs
weight: 11
url: /java/xps-gradient-addition/horizontal/
---
## Introduction
Welcome to this step-by-step guide on adding a horizontal gradient in Java XPS using Aspose.Page for Java. Aspose.Page for Java is a powerful library that allows developers to work with XPS (XML Paper Specification) documents seamlessly.
In this tutorial, we will walk you through the process of creating a Java application to add a horizontal gradient to an XPS document. Follow the steps below to achieve this with ease.
## Prerequisites
Before you begin, make sure you have the following prerequisites in place:
1. Java Development Environment: Ensure that you have Java installed on your system. If not, download and install the latest version of Java from [java.com](https://www.java.com).
2. Aspose.Page for Java Library: You need to have the Aspose.Page for Java library. You can download it from the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).
## Import Packages
Start by importing the necessary packages for your Java application. Include the Aspose.Page for Java library in your project. You can do this by adding the following lines of code:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Step 1: Initialize Document
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```
## Step 2: Create Horizontal Gradient
```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Step 3: Add Path with Gradient
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Step 4: Save the Document
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Repeat these steps as needed, adjusting parameters based on your specific requirements.
## Conclusion
Congratulations! You've successfully added a horizontal gradient to an XPS document using Aspose.Page for Java. This tutorial provided a comprehensive guide for developers seeking to enhance their Java applications with gradient effects.
## FAQs
### Q: Can I apply multiple gradients in a single XPS document?
Yes, you can add multiple paths with different gradients to create complex designs.
### Q: Is Aspose.Page compatible with the latest Java versions?
Aspose.Page for Java is regularly updated to ensure compatibility with the latest Java releases.
### Q: Are there other gradient types available in Aspose.Page?
Yes, besides linear gradients, Aspose.Page supports radial gradients for more diverse effects.
### Q: Can I customize the colors and positions of gradient stops?
Absolutely! You have full control over the colors and positions of each gradient stop.
### Q: Is there a community forum for Aspose.Page where I can seek help?
Yes, you can visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with the community and get assistance.
