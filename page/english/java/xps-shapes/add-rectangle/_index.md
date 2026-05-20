---
title: Set Rectangle Color and Add Rectangle in Java XPS
linktitle: Add Rectangle in Java XPS
second_title: Aspose.Page Java API
description: Learn how to set rectangle color and add rectangle in Java XPS using Aspose.Page. This guide covers add rectangle java and change rectangle stroke.
weight: 11
url: /java/xps-shapes/add-rectangle/
date: 2026-04-24
keywords:
  - set rectangle color
  - add rectangle java
  - change rectangle stroke
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Rectangle Color and Add Rectangle in Java XPS

## Introduction
In this guide, you'll learn how to **set rectangle color** and **add a rectangle** in Java XPS using the Aspose.Page library. Whether you need to draw simple shapes for a report or create complex vector graphics, mastering rectangle styling gives you precise control over your XPS documents.  

## Quick Answers
- **What library is required?** Aspose.Page for Java  
- **Can I change the rectangle stroke?** Yes, using `setStroke` and `setStrokeThickness`  
- **Is a CMYK color profile supported?** Absolutely – you can load ICC profiles as shown  
- **Do I need a license for production?** Yes, a commercial license is required for non‑evaluation use  
- **How long does implementation take?** Typically under 10 minutes for a basic rectangle

## What is **set rectangle color**?
Setting a rectangle’s color means defining the fill or stroke color that the shape will render with in the final XPS document. With Aspose.Page you can use RGB, CMYK, or even custom ICC color profiles to achieve exact color matching.

## Why use Aspose.Page to **add rectangle java** and **change rectangle stroke**?
- **Full‑featured API** – supports both solid colors and gradients.  
- **Cross‑platform** – works on any Java runtime without native dependencies.  
- **Rich geometry support** – create complex paths, apply transformations, and manage stroke thickness easily.  

## Prerequisites
Before we dive into the code, ensure you have:

- Basic knowledge of Java programming.  
- Aspose.Page library installed. If not, download it from the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- A working Java development environment (IDE, JDK, etc.).  

## Import Packages
To get started, import the necessary packages into your Java project. Ensure that the Aspose.Page library is correctly added to your classpath. Here's a basic example:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Now, let's break down the example provided into multiple steps to **add a rectangle** and **set its color** in Java XPS.

## Step 1: Set the Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Replace `"Your Document Directory"` with the absolute path where you want to read/write XPS files.

## Step 2: Create a New XPS Document
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
This line initializes a fresh XPS document that will hold our shapes.

## Step 3: Add a CMYK Solid Color Stroked Rectangle
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
This step adds a **stroked rectangle** with a CMYK solid color. The `setStroke` method defines the rectangle’s outline color, while `setStrokeThickness` controls the line width—perfect for **changing rectangle stroke**.

### Pro tip:
If you prefer an RGB color, replace the `createColor` call with `doc.createColor(0, 0, 255)` for a solid blue fill.

## Step 4: Save the Resultant XPS Document
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Finally, persist the XPS document to disk. The file `AddRectangle_out.xps` now contains a rectangle whose color and stroke you defined.

## Common Issues and Solutions
| Issue | Cause | Solution |
|-------|-------|----------|
| **Rectangle not visible** | Incorrect path geometry or stroke thickness set to 0 | Verify the path string (`"M 20,10 L 220,10 220,100 20,100 Z"`) and ensure `setStrokeThickness` is greater than 0. |
| **Wrong color** | Using an ICC profile that doesn’t match the intended color space | Use `doc.createColor(r, g, b)` for RGB or double‑check the ICC file path. |
| **File not saved** | `dataDir` points to a non‑existent folder or lacks write permission | Create the folder beforehand or choose a writable location. |

## Frequently Asked Questions

**Q:** *Can I add multiple rectangles in a single XPS document?*  
A: Yes. Simply repeat the geometry creation and styling steps for each rectangle you need.

**Q:** *How can I change the rectangle’s fill color instead of the stroke?*  
A: Use `path.setFill(...)` with a solid color brush, similar to how `setStroke` is used.

**Q:** *Is Aspose.Page suitable for complex XPS document manipulations?*  
A: Absolutely. The library supports advanced features like gradients, transformations, and embedded fonts.

**Q:** *Where can I find additional examples and community support?*  
A: Explore the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for more code samples and peer assistance.

**Q:** *Can I try Aspose.Page before purchasing?*  
A: Yes, you can explore a [free trial](https://releases.aspose.com/) to evaluate the API’s capabilities.

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
