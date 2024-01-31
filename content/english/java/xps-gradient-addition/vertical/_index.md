---
title: Add Vertical Gradient in Java XPS
linktitle: Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
description: Learn how to add a vertical gradient to Java XPS documents with Aspose.Page. Enhance visual appeal effortlessly. Step-by-step guide inside.
type: docs
weight: 12
url: /java/xps-gradient-addition/vertical/
---
## Introduction
In this tutorial, we will explore how to add a vertical gradient in Java XPS using Aspose.Page for Java. Adding gradients to your XPS documents can enhance the visual appeal of your content, making it more engaging and aesthetically pleasing.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- A working Java development environment.
- Aspose.Page for Java library. You can download it from [here](https://releases.aspose.com/page/java/).
- A basic understanding of Java programming.
## Import Packages
Start by importing the necessary packages for your Java project. Ensure that you have included the Aspose.Page for Java library in your project dependencies.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```
## Step 1: Initialize the Document
Begin by initializing the XPS document. This sets the foundation for adding elements such as paths and gradients to your document.
```java
// Initialize document
XpsDocument doc = new XpsDocument();
```
## Step 2: Create a Path with Vertical Gradient
Now, let's create a path with a vertical gradient. This involves defining the path geometry and specifying the gradient stops.
```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Step 3: Save the Document
Finally, save the XPS document with the added vertical gradient to your desired directory.
```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```
Congratulations! You have successfully added a vertical gradient to your Java XPS document using Aspose.Page.
## Conclusion
Enhancing your XPS documents with gradients can significantly improve their visual appeal. Aspose.Page for Java simplifies this process, allowing you to create stunning documents with ease.
---
### FAQs
### Can I use Aspose.Page for Java in commercial projects?
Yes, Aspose.Page for Java is available for commercial use. You can purchase it [here](https://purchase.aspose.com/buy).
### Is there a free trial available for Aspose.Page for Java?
Yes, you can access a free trial [here](https://releases.aspose.com/).
### Where can I find the documentation for Aspose.Page for Java?
The documentation is available [here](https://reference.aspose.com/page/java/).
### How can I get a temporary license for Aspose.Page for Java?
Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Need help or have questions?
Visit the Aspose.Page community [forum](https://forum.aspose.com/c/page/39).
