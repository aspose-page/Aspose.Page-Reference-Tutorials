---
title: Add Radial Gradient Ellipse with Aspose.Page
linktitle: Add Ellipse in Java XPS
second_title: Aspose.Page Java API
description: Explore the step-by-step guide on adding a radial gradient stroked ellipse in Java XPS using Aspose.Page for Java. Enhance your document creation effortlessly.
weight: 10
url: /java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Radial Gradient Ellipse with Aspose.Page

## Introduction
Welcome to our step-by-step guide on adding an ellipse in Java XPS using Aspose.Page for Java. Aspose.Page is a powerful Java library that allows developers to work with XPS documents effortlessly. In this tutorial, we will walk you through the process of creating a radial gradient stroked ellipse and saving it as an XPS document.
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
Specify the stroke thickness of the path:
```java
path.setStrokeThickness(12f);
```
## Step 8: Save the Document
Save the resulting XPS document:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Congratulations! You have successfully added a radial gradient stroked ellipse in Java XPS using Aspose.Page for Java.
## Conclusion
In this tutorial, we explored the steps to create an XPS document with a visually appealing radial gradient stroked ellipse. Aspose.Page for Java simplifies XPS document manipulation, providing developers with a powerful toolset.
## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Yes, Aspose.Page for Java can be integrated with other Java libraries seamlessly.
### Is Aspose.Page suitable for large-scale document processing?
Absolutely! Aspose.Page is designed to handle large-scale document processing efficiently.
### Where can I find more tutorials and examples for Aspose.Page for Java?
Visit the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) for comprehensive tutorials and examples.
### How can I obtain a temporary license for Aspose.Page for Java?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Are there community forums for Aspose.Page discussions?
Yes, join the [Aspose.Page community forum](https://forum.aspose.com/c/page/39) to engage with other developers and get assistance.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
