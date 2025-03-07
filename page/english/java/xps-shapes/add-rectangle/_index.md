---
title: Add Rectangle in Java XPS
linktitle: Add Rectangle in Java XPS
second_title: Aspose.Page Java API
description: Learn how to add rectangles in Java XPS using Aspose.Page. Follow our step-by-step guide for seamless document manipulation. #JavaXPS #AsposePage
weight: 11
url: /java/xps-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Rectangle in Java XPS

## Introduction
Welcome to this comprehensive guide on adding rectangles in Java XPS using Aspose.Page! Whether you are a seasoned developer or just starting with Java XPS, this tutorial will walk you through the process with step-by-step instructions, ensuring you gain a deep understanding of the topic.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- Basic knowledge of Java programming language.
- Aspose.Page library installed. If not, you can download it from the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).
- A working Java development environment.
## Import Packages
To get started, import the necessary packages into your Java project. Ensure that the Aspose.Page library is correctly added to your classpath. Here's a basic example:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Now, let's break down the example provided into multiple steps to add a rectangle in Java XPS.
## Step 1: Set the Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Replace "Your Document Directory" with the path to your desired directory.
## Step 2: Create a New XPS Document
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
This initializes a new XPS document.
## Step 3: Add a CMYK Solid Color Stroked Rectangle
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
This step adds a stroked rectangle with a CMYK solid color.
## Step 4: Save the Resultant XPS Document
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Finally, save the modified XPS document with the added rectangle.
Repeat these steps, adjusting parameters as needed, to customize your rectangles further.
## Conclusion
Congratulations! You've successfully learned how to add rectangles in Java XPS using Aspose.Page. This tutorial provides a solid foundation for your XPS document manipulation endeavors.
## FAQs
### Can I add multiple rectangles in a single XPS document?
Yes, you can add as many rectangles as needed by repeating the steps outlined in the tutorial.
### How can I change the color of the rectangle?
Modify the color values in the `createColor` method to achieve the desired color.
### Is Aspose.Page suitable for handling complex XPS document manipulations?
Absolutely! Aspose.Page provides a robust set of features for handling various XPS document tasks.
### Where can I find additional examples and support?
Explore the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for more examples and seek assistance from the community.
### Can I try Aspose.Page before purchasing?
Yes, you can explore a [free trial](https://releases.aspose.com/) to experience the capabilities of Aspose.Page.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
