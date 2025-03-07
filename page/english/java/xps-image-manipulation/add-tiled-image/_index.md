---
title: Add Tiled Image in Java XPS
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
description: Explore seamless Java XPS document manipulation with Aspose.Page. Learn to add tiled images effortlessly using this step-by-step guide.
weight: 11
url: /java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Tiled Image in Java XPS

## Introduction
In the dynamic world of Java development, the need for efficient document manipulation and creation is ever-growing. Aspose.Page for Java emerges as a powerful tool, providing developers with the capability to work with XPS documents seamlessly. This tutorial focuses on a specific task – adding a tiled image to a Java XPS document.
## Prerequisites
Before diving into the tutorial, ensure that you have the following prerequisites in place:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system.
2. Aspose.Page for Java: Download and install Aspose.Page for Java from the [website](https://releases.aspose.com/page/java/).
3. Your Document Directory: Choose or create a directory where you want to save your XPS document.
## Import Packages
In your Java project, import the necessary packages to utilize Aspose.Page functionalities:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Now, let's break down the process of adding a tiled image to a Java XPS document into clear, manageable steps.
## Step 1: Set Up Your Project
Start by setting up your Java project, ensuring that Aspose.Page for Java is properly integrated.
## Step 2: Create XPS Document
Initialize a new XPS document using the following code:
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
## Step 3: Define Tiled Image Path
Specify the path to the tiled image you want to add to the XPS document.
## Step 4: Add Tiled Image
Utilize the code snippet below to add a tiled image to the XPS document:
```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Step 5: Save the Document
Finally, save the resultant XPS document using the code below:
```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Repeat these steps to effortlessly incorporate a tiled image into your Java XPS document using Aspose.Page.
## Conclusion
Aspose.Page for Java streamlines the process of working with XPS documents, offering developers an efficient solution for document manipulation. By following this step-by-step guide, you can effortlessly add a tiled image to your Java XPS document.

## FAQs
### Is Aspose.Page compatible with all Java versions?
Aspose.Page is designed to work with various Java versions. Ensure compatibility by checking the documentation [here](https://reference.aspose.com/page/java/).
### Can I use Aspose.Page for commercial projects?
Yes, Aspose.Page offers commercial licenses. Purchase them [here](https://purchase.aspose.com/buy).
### Is there a free trial available?
Yes, explore Aspose.Page features with a free trial [here](https://releases.aspose.com/).
### Where can I find community support and discussions?
Engage with the Aspose.Page community on the [forum](https://forum.aspose.com/c/page/39).
### How can I obtain a temporary license for Aspose.Page?
Acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
