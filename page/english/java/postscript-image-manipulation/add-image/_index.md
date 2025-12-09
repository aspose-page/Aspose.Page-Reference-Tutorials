---
title: "Create PostScript Document Java – Add Image in Java PostScript"
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
description: "Learn how to create PostScript document Java and translate and rotate image using Aspose.Page for seamless image manipulation."
weight: 10
url: /java/postscript-image-manipulation/add-image/
date: 2025-12-09
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create PostScript Document Java – Add Image in Java PostScript

## Introduction
In this tutorial, you’ll learn how to **create a PostScript document Java** and embed images using the Aspose.Page for Java library. We'll walk through each step, from setting up the document to applying transformations like **translate and rotate image** operations. By the end, you’ll be able to generate rich PostScript files programmatically and customize image placement to fit your exact layout needs.

## Quick Answers
- **What library is required?** Aspose.Page for Java  
- **Can I add multiple images?** Yes – repeat the transform and draw steps  
- **Do I need a license for development?** A free trial works for testing; a license is required for production  
- **Which Java version is supported?** Java 8 and later  
- **Is image rotation supported?** Absolutely – use `AffineTransform.rotate()`  

## What is creating a PostScript document in Java?
A PostScript document is a page description language file that describes text, graphics, and images. Using Aspose.Page, you can programmatically generate these files in Java, giving you full control over layout, graphics state, and image handling without needing a PostScript interpreter.

## Why use Aspose.Page for image manipulation?
- **High‑level API:** Simplifies complex PostScript commands.  
- **Cross‑platform:** Works on any OS that supports Java.  
- **Full graphics state control:** Easily save, restore, translate, scale, and rotate graphics.  
- **No external dependencies:** Handles image loading and conversion internally.

## Prerequisites
Before we dive into the code, make sure you have:

- Java Development Kit (JDK) installed on your system.  
- Aspose.Page for Java library. You can download it [here](https://releases.aspose.com/page/java/).  
- A basic understanding of Java programming.  

## Import Packages
To get started, import the necessary packages in your Java project. Use the following code snippet as a reference:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Write Graphics Save
The first step involves writing the graphics save to the document. This ensures that any transformations or modifications made afterward can be rolled back if needed.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Step 2: Translate and Transform (translate and rotate image)
Next, translate the document and create a `BufferedImage` object from the image file. Apply a series of transformations like scaling and rotation using `AffineTransform`. This is where the **translate and rotate image** operation happens.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Step 3: Add Image to Document
Now, add the transformed image to the document.

```java
document.drawImage(image, transform, null);
```

## Step 4: Write Graphics Restore
After adding the image, write the graphics restore to finalize the changes made.

```java
document.writeGraphicsRestore();
```

## Step 5: Close Current Page and Save
Close the current page and save the document.

```java
document.closePage();
document.save();
```

You can repeat these steps to add multiple images or customize the transformations based on your requirements.

## Common Issues and Solutions
- **FileNotFoundException:** Ensure the `dataDir` path ends with a file separator (`/` or `\\`) and that the image file name matches exactly.  
- **ImageIO.read returns null:** Verify that the image format is supported (e.g., JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` expects radians. Convert degrees to radians (`Math.toRadians(degrees)`) if needed.  

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java with other programming languages?**  
A: Aspose.Page primarily supports Java, but there are versions available for other programming languages as well.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Yes, you can access the free trial [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find community support and discussions related to Aspose.Page for Java?**  
A: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) for community support.

**Q: Are there any additional resources for purchasing Aspose.Page for Java?**  
A: You can buy the library [here](https://purchase.aspose.com/buy).

## Conclusion
Congratulations! You have successfully learned how to **create a PostScript document Java** and embed images using Aspose.Page for Java. Explore the [documentation](https://reference.aspose.com/page/java/) for more advanced features and functionalities, such as vector graphics, text rendering, and custom page sizes.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}