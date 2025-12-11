---
title: "Aspose.Page Java Tutorial – set custom page size while Adding Pages in PostScript"
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
description: "Learn how to set custom page size and add pages to Java PostScript documents using Aspose.Page. Follow our step‑by‑step guide for seamless document manipulation."
weight: 11
url: /java/postscript-page-manipulation/add-pages2/
date: 2025-12-11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – set custom page size while Adding Pages in PostScript

## Introduction
In modern Java applications, **setting a custom page size** for PostScript output is often required—whether you’re generating invoices, tickets, or custom graphics. Aspose.Page for Java makes this task straightforward. In this tutorial you’ll learn how to add pages and set custom page sizes in a PostScript document, step by step, so you can produce exactly‑the‑right layout every time.

## Quick Answers
- **Can I set different page sizes for each page?** Yes, you can open pages with custom dimensions using `document.openPage(width, height)`.  
- **Do I need a license for production use?** A valid Aspose.Page license is required for non‑evaluation deployments.  
- **Which Java versions are supported?** The library works with Java 8 and newer.  
- **Is the API thread‑safe?** Document instances are not thread‑safe; create a separate `PsDocument` per thread.  
- **How large can a PostScript file be?** Aspose.Page handles multi‑megabyte files efficiently; memory usage scales with content, not page count.

## Prerequisites
Before we dive in, make sure you have:

- A basic understanding of Java programming.  
- Aspose.Page for Java added to your project (Maven/Gradle or manual JAR).  
- A Java development environment (IDE, JDK 8+).  

## Import Packages
To start, import the necessary classes from the Aspose.Page library.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Multipaged PostScript Document
First, create a new `PsDocument` configured for multiple pages. This sets up the output stream and tells the library we’ll be working with a multipage file.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Step 2: Add Content to the First Page
With the document ready, you can add any content you need to the first page. When you’re done, close the page to lock its content.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## How to set custom page size
If the default page size isn’t what you need, you can **set a custom page size** when opening a new page. This is useful for receipts, labels, or any non‑standard layout.

## Step 3: Add a Second Page with Different Size
Below we open a second page and explicitly provide a custom width and height (in points). This demonstrates how to set a custom page size for individual pages.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Step 4: Save the Document
Finally, persist the changes by saving the document. All pages—including those with custom sizes—are written to the output file.

```java
// Save the document
document.save();
```

By following these steps, you can seamlessly add pages and **set custom page sizes** in a Java PostScript document using Aspose.Page, giving you full control over the layout of each page.

## Conclusion
Aspose.Page for Java provides a robust, developer‑friendly API for handling PostScript documents. You now know how to add multiple pages, apply custom dimensions, and save the result—empowering you to generate precisely formatted output for any Java‑based solution.

## Frequently Asked Questions
### Can I add pages of different sizes in a single PostScript document?
Yes, as demonstrated in this tutorial, you can add pages with varying sizes in a multipaged PostScript document.  
### Are there any limitations on the number of pages I can add?
Aspose.Page supports adding a virtually unlimited number of pages to a document.  
### Can I add custom content, such as images or graphics, to the pages?
Absolutely! Aspose.Page allows you to add a wide range of content, including text, images, and other graphical elements.  
### Is Aspose.Page suitable for handling large documents?
Yes, Aspose.Page is designed to efficiently handle both small and large documents with ease.  
### Where can I find additional resources and support for Aspose.Page?
Explore the [Aspose.Page documentation](https://reference.aspose.com/page/java/), or visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.  

**Additional Q&A**

**Q:** *What image formats are supported when drawing on a PostScript page?*  
**A:** You can embed PNG, JPEG, BMP, and GIF images directly using the drawing API.  

**Q:** *How do I change the default DPI for the document?*  
**A:** Set the `PsSaveOptions.setResolution(int dpi)` before creating the `PsDocument`.  

**Q:** *Can I encrypt a PostScript file with a password?*  
**A:** PostScript itself does not support encryption, but you can wrap the output in a PDF and apply security settings if needed.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

---