---
title: "How to Create XPS Document with a Tiled Image in Java"
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
description: "Learn how to create XPS document in Java using Aspose.Page and add tiled image effortlessly with this step‑by‑step guide."
weight: 11
url: /java/xps-image-manipulation/add-tiled-image/
date: 2025-12-28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS Document and Add a Tiled Image in Java

## Introduction
In modern Java development, the ability to **create XPS document** files programmatically is a valuable skill, especially when you need to enrich them with graphics such as tiled images. Aspose.Page for Java makes this process straightforward, allowing you to focus on the visual design rather than low‑level file handling. In this tutorial you'll learn exactly how to create an XPS document, **add tiled image**, and save the result, all with clear, step‑by‑step code examples.

## Quick Answers
- **What does Aspose.Page do?** It provides a high‑level API to generate and manipulate XPS documents in Java.  
- **Can I tile an image?** Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.  
- **Do I need a license?** A temporary or commercial license is required for production use.  
- **What Java version is supported?** Any JDK 8+ is compatible.  
- **How long does implementation take?** Roughly 10–15 minutes for a basic tiled‑image scenario.

## What is “create XPS document”?
An XPS (XML Paper Specification) file is a fixed‑layout document format similar to PDF. Creating an XPS document programmatically lets you generate printable, device‑independent files directly from Java code.

## Why add a tiled image?
Tiling an image repeats the graphic across a defined area, which is perfect for backgrounds, watermarks, or pattern fills. Using Aspose.Page’s `XpsTileMode.Tile` you can achieve this with just a few lines of code.

## Prerequisites
Before diving in, make sure you have:

1. **Java Development Kit (JDK)** – JDK 8 or newer installed.  
2. **Aspose.Page for Java** – download from the [website](https://releases.aspose.com/page/java/).  
3. **A writable directory** – where the generated XPS file will be saved.

## Import Packages
In your Java project, import the necessary classes:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Project
Add the Aspose.Page JAR files to your project’s classpath and verify the import statements compile without errors.

### Step 2: Create XPS Document
Instantiate a new `XpsDocument` object. This is the core container that will hold all pages, paths, and resources.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Step 3: Define the Tiled Image Path
Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory referenced by `dataDir`. The image will be used as a brush pattern.

### Step 4: Add Tiled Image
Create a rectangular path and fill it with an `XpsImageBrush`. By setting the tile mode to `Tile`, the image repeats across the rectangle.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Step 5: Save the Document
Persist the XPS file to disk. The output file will contain the tiled image you just defined.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Repeat these steps whenever you need to **add tiled image** to other pages or shapes within the same XPS document.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| Image not showing | Verify the file path (`dataDir + "R08LN_NN.jpg"`) is correct and the image is accessible. |
| Tile pattern appears stretched | Adjust the source and destination `Rectangle2D` values to control the tile size. |
| Opacity has no effect | Ensure the brush’s opacity is set **after** the tile mode configuration. |

## Frequently Asked Questions

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

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
