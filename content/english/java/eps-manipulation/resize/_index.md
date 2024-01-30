---
title: Resize EPS Files in Java with Aspose.Page
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
description: Learn how to resize EPS files in Java effortlessly with Aspose.Page for Java. Follow our comprehensive guide for step-by-step instructions.
type: docs
weight: 11
url: /java/eps-manipulation/resize/
---
## Introduction
Welcome to our step-by-step guide on resizing EPS files in Java using the powerful Aspose.Page library. If you've ever needed to adjust the dimensions of your EPS images programmatically, you're in the right place. In this tutorial, we'll explore various resizing options, including points, inches, millimeters, and percentages, providing you with the flexibility you need for your specific requirements.
## Prerequisites
Before we dive into the tutorial, make sure you have the following:
- Java Development Kit (JDK) installed on your machine.
- Aspose.Page for Java library. You can download it [here](https://releases.aspose.com/page/java/).
- A basic understanding of Java programming.
## Import Packages
In your Java project, ensure you have the necessary imports to use Aspose.Page functionalities. Here's an example:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Now, let's break down the tutorial into multiple steps for each resizing option:
## Example 1: Resize EPS using Points
### Step 1: Set up the input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Step 2: Initialize PsDocument object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Step 3: Extract the current size of EPS image
```java
Dimension oldSize = doc.extractEpsSize();
```
### Step 4: Create an output stream
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Step 5: Resize and save in points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Example 2: Resize EPS using Inches
Follow similar steps as Example 1, replacing "Points" with "Inches" and adjusting the new size accordingly.
## Example 3: Resize EPS using Millimeters
Follow similar steps as Example 1, replacing "Points" with "Millimeters" and adjusting the new size accordingly.
## Example 4: Resize EPS using Percentages
Follow similar steps as Example 1, replacing "Points" with "Percentages" and adjusting the new size accordingly.
## Conclusion
Congratulations! You've successfully learned how to resize EPS files in Java using Aspose.Page. This guide provides you with versatile options, ensuring you can tailor the resizing process to meet your specific needs.

## FAQs
### Can I use this library for other image formats?
No, Aspose.Page is specifically designed for handling PostScript and EPS files.
### Is there a free trial available for Aspose.Page for Java?
Yes, you can explore the free trial [here](https://releases.aspose.com/).
### Where can I find additional help and discussions?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.
### How can I obtain a temporary license?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Are there any example projects available?
Yes, check the official documentation [here](https://reference.aspose.com/page/java/).
