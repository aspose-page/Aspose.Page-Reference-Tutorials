---
title: How to Add Metadata – Add Array Items in XMP (Java)
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
description: Learn how to add metadata by inserting array items into XMP metadata of EPS files using Aspose.Page for Java. Follow our step‑by‑step guide.
date: 2025-12-18
weight: 10
url: /java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Array Items in XMP Metadata using Java

## How to Add Metadata
Welcome to our step‑by‑step guide on **how to add metadata** to EPS files with Aspose.Page for Java. In this tutorial we’ll walk you through adding array items to XMP metadata—a common requirement when you need to enrich document information such as titles or creators. By the end, you’ll understand why XMP is valuable, how to manipulate it programmatically, and how to save the updated EPS file.

## Quick Answers
- **What library is used?** Aspose.Page for Java  
- **Which file format is targeted?** EPS (Encapsulated PostScript)  
- **Can I add multiple titles?** Yes, use `xmp.addArrayItem("dc:title", ...)` repeatedly  
- **Do I need a license for production?** Yes, a valid Aspose.Page license is required  
- **Is the code compatible with Java 8+?** Absolutely, it works with all modern Java versions  

## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites:
- Aspose.Page for Java library installed.
- Basic understanding of Java programming.
- A valid EPS file with existing XMP metadata or PS metadata comments.

## Import Packages
To get started, you need to import the necessary packages for working with Aspose.Page. Include the following lines at the beginning of your Java file:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Step 1: Get XMP Metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
In this step, we retrieve the existing XMP metadata from the EPS file. If the EPS file doesn't already contain XMP metadata, Aspose.Page generates a new one and fills it with values from PS metadata comments.

## Step 2: Add "dc:title" Array Item
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Now, we add a new array item to the **dc:title** property in the XMP metadata. Replace `"NewTitle"` with the desired title.

## Step 3: Add "dc:creator" Array Item
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Similarly, we add a new array item to the **dc:creator** property in the XMP metadata. Replace `"NewCreator"` with the desired creator information.

## Step 4: Initialize Output EPS File Stream
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Prepare the output EPS file stream where the modified document with updated XMP metadata will be saved.

## Step 5: Save Document with Changed XMP Metadata
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Save the document with the updated XMP metadata to the output EPS file.

## Conclusion
Congratulations! You've successfully learned **how to add metadata** by inserting array items in XMP metadata using Aspose.Page for Java. This powerful library simplifies the process of manipulating EPS files and provides extensive functionality for document processing.

## Frequently Asked Questions

### Can I use Aspose.Page for Java with other document formats?
Yes, Aspose.Page supports various document formats, including EPS, PDF, and XPS.

### Is there a free trial available for Aspose.Page for Java?
Yes, you can access the free trial [here](https://releases.aspose.com/).

### Where can I find the documentation for Aspose.Page for Java?
The documentation is available [here](https://reference.aspose.com/page/java/).

### How can I purchase Aspose.Page for Java?
You can buy the product [here](https://purchase.aspose.com/buy).

### Are temporary licenses available for Aspose.Page for Java?
Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

## Additional Frequently Asked Questions

**Q: Can I add more than one array item to the same property?**  
A: Absolutely. Call `xmp.addArrayItem` multiple times for the same property to build a list of values.

**Q: Does this approach work with existing XMP schemas other than Dublin Core?**  
A: Yes, you can add array items to any XMP property as long as the namespace is correctly referenced.

**Q: How can I verify that the metadata was added correctly?**  
A: Open the resulting EPS file in a viewer that supports XMP (e.g., Adobe Bridge) or extract the metadata programmatically using `XmpMetadata` methods.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}