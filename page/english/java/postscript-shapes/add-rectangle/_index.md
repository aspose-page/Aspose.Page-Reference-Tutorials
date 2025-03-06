---
title: Customize Java PostScript - Adding Rectangles with Aspose.Page
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
description: Explore the step-by-step guide on adding vibrant rectangles to Java PostScript documents using Aspose.Page for Java. Enhance your document customization effortlessly!
weight: 11
url: /java/postscript-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Customize Java PostScript - Adding Rectangles with Aspose.Page

## Introduction
Are you looking to enhance your Java PostScript documents with vibrant rectangles? Look no further! In this step-by-step guide, we'll explore how to use Aspose.Page for Java to add rectangles to your PostScript documents. Aspose.Page is a powerful library that provides robust features for working with PostScript files, making it an ideal choice for developers seeking to manipulate and customize their documents.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
- Basic understanding of Java programming.
- Aspose.Page for Java library installed. If not, download it from the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).
- A Java development environment set up on your machine.
## Import Packages
In your Java project, start by importing the necessary packages:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Tutorial: Adding Rectangles in Java PostScript
## Step 1: Set Paint for Filling Rectangle
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Step 2: Set Paint for Stroking Rectangle
```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Step 3: Close Current Page and Save Document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```
Congratulations! You have successfully added vibrant rectangles to your Java PostScript document using Aspose.Page.
## Conclusion
In this tutorial, we've explored the process of enhancing your Java PostScript documents with rectangles using Aspose.Page for Java. This powerful library opens up a world of possibilities for developers seeking to customize and manipulate their documents effortlessly.
Have fun experimenting with different shapes and colors to make your documents visually appealing!
## Frequently Asked Questions

### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page primarily supports Java, but similar libraries are available for other languages.
### Is there a trial version of Aspose.Page for Java available?
Yes, you can explore the features of Aspose.Page for Java with the [free trial version](https://releases.aspose.com/).
### Where can I find additional help and discussions?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to engage with the community and get assistance.
### How can I obtain a temporary license for Aspose.Page for Java?
Get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Where can I purchase a licensed version of Aspose.Page for Java?
Buy a licensed version [here](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
