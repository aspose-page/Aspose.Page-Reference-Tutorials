---
title: Radial Gradient Tutorial: Add Ellipse with Aspose.Page
linktitle: Add Ellipse in Java XPS
second_title: Aspose.Page Java API
description: Explore this radial gradient tutorial for adding a stroked ellipse in Java XPS using Aspose.Page for Java. Enhance your document creation effortlessly.
weight: 10
url: /java/xps-shapes/add-ellipse/
date: 2025-12-30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Radial Gradient Tutorial: Add Ellipse with Aspose.Page

## Introduction
Welcome to our **radial gradient tutorial** that shows you **how to add ellipse** graphics to an XPS document using Aspose.Page for Java. In this guide you’ll learn **how to create XPS** files, configure gradient stops, and **set stroke thickness** for a polished look. By the end of the tutorial you’ll have a fully functional XPS document containing a beautiful radial‑gradient‑stroked ellipse.

## Quick Answers
- **What does this tutorial cover?** Adding a radial gradient stroked ellipse to a Java XPS document.  
- **Which library is required?** Aspose.Page for Java (latest version).  
- **Do I need a license?** A temporary license is sufficient for testing; a full license is needed for production.  
- **How many lines of code?** Less than 30 lines of Java, split across clear steps.  
- **Can I change the colors?** Yes – simply modify the gradient stops in the code.

## What is a Radial Gradient Tutorial?
A radial gradient tutorial explains how to apply a color transition that radiates from a central point outward, creating a smooth blend that can be used for fills or strokes. In our case, the gradient is applied to the **ellipse gradient Java** stroke, giving the shape a vibrant, three‑dimensional appearance.

## Why Use Aspose.Page for Java?
Aspose.Page provides a high‑level API that abstracts the complexities of the XPS format. It lets you focus on design—like configuring gradient stops—while handling the low‑level document structure behind the scenes. This makes it ideal for developers who need to generate rich XPS graphics programmatically.

## Prerequisites
Before we begin, ensure you have the following:

- Java Development Kit (JDK) installed on your machine.  
- Aspose.Page for Java library downloaded. You can get it [here](https://releases.aspose.com/page/java/).  
- A code editor of your choice (Eclipse, IntelliJ, etc.) for writing and executing Java code.

## Import Packages
Ensure you have the necessary packages imported in your Java project to use Aspose.Page. Add the following import statements to the top of your Java file:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Step 1: Set Up Document Directory
Define the path to the folder where the XPS document will be saved:

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create XPS Document
Initialize a new XPS document instance:

```java
XpsDocument doc = new XpsDocument();
```

## Step 3: Define Radial Gradient Stops
Create a list of gradient stops that will be used to **configure gradient stops** for the ellipse’s stroke:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Step 4: Create Path Geometry
Define the geometry of the ellipse using a path string. This step answers **how to add ellipse** by describing its shape:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Step 5: Add Canvas and Path
Add a new canvas to the document and attach the path that represents the ellipse:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Step 6: Set Stroke and Gradient
Configure the stroke of the path with a radial gradient brush. This demonstrates **ellipse gradient Java** usage:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Step 7: Set Stroke Thickness
Specify how thick the ellipse outline should be—here we **set stroke thickness** to 12 points:

```java
path.setStrokeThickness(12f);
```

## Step 8: Save the Document
Persist the XPS file to disk:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Congratulations! You have successfully completed this **radial gradient tutorial** and created a radial‑gradient‑stroked ellipse in Java XPS using Aspose.Page for Java.

## Conclusion
In this tutorial we covered everything from **how to create XPS** documents to configuring gradient stops and **setting stroke thickness** for a polished ellipse. Aspose.Page for Java streamlines XPS generation, allowing you to focus on design rather than file format intricacies.

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Yes, Aspose.Page for Java can be integrated with other Java libraries seamlessly.  

### Is Aspose.Page suitable for large‑scale document processing?
Absolutely! Aspose.Page is designed to handle large‑scale document processing efficiently.  

### Where can I find more tutorials and examples for Aspose.Page for Java?
Visit the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) for comprehensive tutorials and examples.  

### How can I obtain a temporary license for Aspose.Page for Java?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).  

### Are there community forums for Aspose.Page discussions?
Yes, join the [Aspose.Page community forum](https://forum.aspose.com/c/page/39) to engage with other developers and get assistance.

## FAQ (Additional Quick Q&A)
**Q:** *Can I change the gradient colors?*  
**A:** Yes, simply modify the `doc.createColor` values in the gradient stops list.

**Q:** *What happens if I omit `setSpreadMethod`?*  
**A:** The default spread method is `Pad`, which may produce a different visual effect compared to `Reflect`.

**Q:** *Is it possible to fill the ellipse instead of stroking it?*  
**A:** Absolutely—use `path.setFill(...)` with a radial or linear gradient brush.

---

**Last Updated:** 2025-12-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}