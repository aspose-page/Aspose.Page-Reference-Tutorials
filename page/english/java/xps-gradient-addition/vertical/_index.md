---
title: How to Add Gradient: Vertical Gradient in Java XPS
linktitle: How to Add Gradient: Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
description: Learn how to add gradient to shape in Java XPS using Aspose.Page. Follow this step‑by‑step guide to create vertical gradients and enhance visual appeal.
weight: 12
url: /java/xps-gradient-addition/vertical/
date: 2026-03-13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Add Gradient: Vertical Gradient in Java XPS

## Introduction
In this tutorial you’ll discover **how to add gradient**—specifically a vertical gradient—to XPS documents when working with Java. Applying a vertical gradient can dramatically improve the visual impact of reports, invoices, or any printable content. We’ll walk through each step, from setting up the project to saving the final XPS file, using the powerful Aspose.Page for Java library.

## Quick Answers
- **What does a vertical gradient do?** It creates a smooth color transition from top to bottom of a shape.  
- **Which library is required?** Aspose.Page for Java (downloadable from the official site).  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Is this compatible with Java 8+?** Yes, the API supports Java 8 and later versions.  
- **How long does implementation take?** Typically under 10 minutes once the environment is set up.

## What is a Vertical Gradient?
A vertical gradient is a linear color blend that runs along the Y‑axis of a shape. It starts with one color at the top edge and gradually transitions to another color at the bottom edge, giving a three‑dimensional feel to flat graphics.

## Why Use a Vertical Gradient in XPS?
- **Improved aesthetics:** Gradients add depth and a modern look to static shapes.  
- **Brand consistency:** Match corporate colors smoothly across pages.  
- **Easy customization:** Change colors or stop positions without redesigning graphics.  

## Prerequisites
Before we dive into the code, make sure you have the following:

- A working Java development environment (JDK 8 or newer).  
- Aspose.Page for Java library. You can download it from [here](https://releases.aspose.com/page/java/).  
- A basic understanding of Java programming concepts.  

## Import Packages
Start by importing the necessary packages for your Java project. Ensure that the Aspose.Page for Java library is added to your project’s classpath.

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

## How to Add Gradient to XPS Documents
Below is a concise, step‑by‑step guide that shows exactly how to create an XPS document and **add gradient to shape** objects.

### Step 1: Initialize the Document
Begin by creating a new XPS document. This object will hold all the drawing elements you add later.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

### Step 2: Create a Path with a Vertical Gradient
Next, define a rectangular path and apply a vertical linear gradient. The gradient stops determine the colors and their positions along the vertical axis.

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

### Step 3: Save the Document
Finally, write the XPS file to disk. The resulting file will contain the rectangle filled with the vertical gradient you defined.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

Congratulations! You have successfully learned **how to add gradient** to a Java XPS document using Aspose.Page.

## Common Issues & Troubleshooting
- **Gradient not visible:** Verify that the start and end points of the `LinearGradientBrush` are correctly set for a vertical orientation.  
- **File not saved:** Ensure `dataDir` points to a writable folder and that you have permission to write files.  
- **Library not found:** Double‑check that the Aspose.Page JAR is included in your project’s build path.

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java in commercial projects?**  
A: Yes, Aspose.Page for Java is available for commercial use. You can purchase it [here](https://purchase.aspose.com/buy).

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Yes, you can access a free trial [here](https://releases.aspose.com/).

**Q: Where can I find the documentation for Aspose.Page for Java?**  
A: The documentation is available [here](https://reference.aspose.com/page/java/).

**Q: How can I get a temporary license for Aspose.Page for Java?**  
A: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Need help or have questions?**  
A: Visit the Aspose.Page community [forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}