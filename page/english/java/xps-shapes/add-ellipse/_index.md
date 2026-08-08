---
title: Create XPS Document Java – Add Radial Gradient Ellipse
linktitle: Add Ellipse in Java XPS
second_title: Aspose.Page Java API
description: Learn how to create XPS document Java with a radial gradient ellipse. This step‑by‑step guide shows how to set stroke thickness and define path geometry using Aspose.Page.
weight: 10
url: /java/xps-shapes/add-ellipse/
date: 2026-04-24
keywords:
- create xps document java
- set stroke thickness
- define path geometry
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Radial Gradient Ellipse with Aspose.Page

## Introduction
In this tutorial, you’ll learn how to **create XPS document Java** with a beautiful radial gradient stroked ellipse using Aspose.Page for Java. Aspose.Page is a robust library that abstracts the low‑level XPS details, letting you focus on design rather than file format intricacies. By the end of this guide you’ll have a ready‑to‑use XPS file that you can embed in reports, invoices, or any document‑generation workflow.

## Quick Answers
- **What does this code produce?** A single‑page XPS file containing an ellipse stroked with a multi‑color radial gradient.  
- **Which primary API is used?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **Do I need a license to run the sample?** A temporary license works for evaluation; a full license is required for production.  
- **What are the key properties we set?** Stroke brush (radial gradient), spread method, gradient stops, and stroke thickness.  
- **Can I change the ellipse size?** Yes – modify the path geometry string or the gradient brush coordinates.

## What is “create XPS document Java”?
Creating an XPS document in Java means programmatically generating an XML Paper Specification (XPS) file—a fixed‑layout document format similar to PDF—directly from Java code. Aspose.Page provides a high‑level object model (`XpsDocument`, `XpsCanvas`, etc.) that abstracts the XML markup, making the process as simple as working with standard Java objects.

## Why use a radial gradient ellipse?
A radial gradient gives a three‑dimensional feel, perfect for visual highlights, logos, or decorative elements in reports. Compared with a solid‑color stroke, the gradient adds depth without increasing file size significantly, and the XPS format preserves the vector quality for any scaling.

## Prerequisites
Before we begin, make sure you have the following prerequisites in place:
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
Define the path to your document directory where the XPS document will be saved:

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create XPS Document
Initialize a new XPS document using the following code:

```java
XpsDocument doc = new XpsDocument();
```

## Step 3: Define Radial Gradient Stops
Create a list of gradient stops for the radial gradient stroked ellipse:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Step 4: Create Path Geometry
Define a radial gradient stroked ellipse using path geometry:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Step 5: Add Canvas and Path
Add a new canvas to the document and append the path with the defined geometry:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Step 6: Set Stroke and Gradient
Configure the stroke of the path with a radial gradient brush:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Step 7: Set Stroke Thickness
Specify the **set stroke thickness** of the path:

```java
path.setStrokeThickness(12f);
```

## Step 8: Save the Document
Save the resulting XPS document:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Congratulations! You have successfully added a radial gradient stroked ellipse while **creating an XPS document Java** with Aspose.Page.

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Ellipse appears flat** | Using `XpsSpreadMethod.Pad` instead of `Reflect` | Change the spread method to `XpsSpreadMethod.Reflect` as shown in Step 6. |
| **No output file** | `dataDir` points to a non‑existent folder | Ensure the directory exists or use an absolute path. |
| **Gradient colors look off** | Incorrect order of gradient stops | Verify the `offset` values (0 → 1) increase monotonically. |
| **Compilation errors** | Missing Aspose.Page JARs on classpath | Add `aspose-page-xx.jar` to your project dependencies. |

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java with other Java libraries?**  
A: Yes, Aspose.Page for Java can be integrated with other Java libraries seamlessly.

**Q: Is Aspose.Page suitable for large‑scale document processing?**  
A: Absolutely! Aspose.Page is designed to handle large‑scale document processing efficiently.

**Q: Where can I find more tutorials and examples for Aspose.Page for Java?**  
A: Visit the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) for comprehensive tutorials and examples.

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Are there community forums for Aspose.Page discussions?**  
A: Yes, join the [Aspose.Page community forum](https://forum.aspose.com/c/page/39) to engage with other developers and get assistance.

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}