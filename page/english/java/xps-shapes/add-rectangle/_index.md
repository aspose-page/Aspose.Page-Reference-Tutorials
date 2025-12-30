---
title: "Create XPS Document Java – Add Rectangle with Aspose.Page"
linktitle: "Create XPS Document Java – Add Rectangle"
second_title: "Aspose.Page Java API"
description: "Learn how to create XPS document Java by adding rectangles using Aspose.Page. Follow this step‑by‑step guide for seamless XPS document manipulation."
weight: 11
url: /java/xps-shapes/add-rectangle/
date: 2025-12-30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS Document Java – Add Rectangle

## Introduction
In this comprehensive tutorial you'll **create XPS document Java** files and learn how to add rectangles using the Aspose.Page library. Whether you're building reports, invoices, or custom graphics, mastering rectangle creation gives you precise control over XPS layout. We'll walk through each step, explain the why behind every line of code, and show you how to customize colors and strokes for professional results.

## Quick Answers
- **What library is recommended?** Aspose.Page for Java  
- **How long does the implementation take?** About 10 minutes for a basic rectangle  
- **Do I need a license?** A free trial works for development; a commercial license is required for production  
- **Which Java version is supported?** Java 8 and later  
- **Can I add multiple shapes?** Yes – repeat the steps for each shape

## Prerequisites
Before we dive in, make sure you have:

- Basic knowledge of the Java programming language.  
- Aspose.Page library installed. If not, you can download it from the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- A working Java development environment (IDE, JDK, and Maven/Gradle if you prefer).

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

Replace `"Your Document Directory"` with the path to the folder where you want to store the XPS files.

## Step 2: Create a New XPS Document
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

This line **creates** a fresh XPS document that you can later populate with shapes, text, or images.

## Step 3: Add a CMYK Solid Color Stroked Rectangle
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

This step adds a stroked rectangle with a CMYK solid color. You can change the geometry string (`"M 20,10 L 220,10 220,100 20,100 Z"`) to modify size or position, and adjust the color values in `createColor` to suit your design.

## Step 4: Save the Resultant XPS Document
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Finally, save the modified XPS document with the added rectangle to the directory you specified earlier.

## Common Use Cases
- **Report headers** – Use rectangles as background blocks for titles.  
- **Invoice tables** – Highlight cells or sections with colored borders.  
- **Custom graphics** – Combine multiple rectangles to create complex shapes.

## Troubleshooting Tips
- **File not found error:** Verify that `dataDir` points to an existing folder and that the ICC profile (`uswebuncoated.icc`) is present.  
- **Incorrect colors:** Ensure the ICC profile matches the color space you intend to use (CMYK vs. RGB).  
- **Unexpected dimensions:** Adjust the geometry string to reflect the correct coordinates.

## Conclusion
Congratulations! You've successfully learned how to **create XPS document Java** files and add rectangles using Aspose.Page. This foundation lets you build richer XPS documents, customize graphics, and integrate shapes into larger workflows.

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

## Frequently Asked Questions

**Q: Does this approach work with Java 11 or newer?**  
A: Yes, the Aspose.Page library is compatible with Java 8 and later, including Java 11, 17, and beyond.

**Q: Can I embed images inside the rectangle area?**  
A: You can add an `XpsImage` element and position it over or inside the rectangle using the same geometry coordinates.

**Q: How do I set a fill color instead of just a stroke?**  
A: Call `path.setFill(...)` with a solid color brush created via `doc.createSolidColorBrush(...)`.

**Q: Is it possible to rotate the rectangle?**  
A: Apply a transformation matrix to the path using `path.setTransform(...)` to achieve rotation or scaling.

**Q: What licensing is required for production use?**  
A: A commercial Aspose.Page license is required for deployment; the free trial is limited to evaluation and development.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---