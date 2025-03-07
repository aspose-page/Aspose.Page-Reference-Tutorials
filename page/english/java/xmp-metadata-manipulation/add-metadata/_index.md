---
title: Add Metadata in XMP using Java
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
description: Explore the seamless integration of Aspose.Page for Java and learn how to add XMP metadata to your EPS files effortlessly. Elevate your document management game today!
weight: 11
url: /java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Metadata in XMP using Java

## Introduction
Are you looking to enhance your document's metadata by adding XMP information using Java? Look no further! This step-by-step guide will walk you through the process of adding metadata to an EPS file using the Aspose.Page for Java library. Aspose.Page is a powerful tool that simplifies document manipulation tasks in Java applications.
## Prerequisites
Before we dive into the tutorial, ensure you have the following prerequisites:
- Basic knowledge of Java programming.
- Aspose.Page for Java library installed. You can download it [here](https://releases.aspose.com/page/java/).
- An EPS file that you want to modify.
## Import Packages
Firstly, import the necessary packages to your Java program:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Step 1: Get XMP Metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Ensure to replace "Your Document Directory" with the actual path where your documents are stored.

## Step 2: Retrieve CreatorTool Value
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Step 3: Retrieve CreateDate Value
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Step 4: Retrieve Title Value
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Step 5: Retrieve Format Value
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Step 6: Retrieve Creator Value
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Step 7: Retrieve MetadataDate Value
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Step 8: Save Document with New XMP Metadata
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Finally, don't forget to close the input EPS stream:
```java
// Close input EPS stream
psStream.close();
```
Now, you have successfully added metadata to your EPS file using Aspose.Page for Java!
## Conclusion
In this tutorial, we explored the process of adding XMP metadata to an EPS file using the Aspose.Page for Java library. This powerful tool enables you to manipulate documents seamlessly, enhancing your overall document management experience.
## FAQs
### Q: Is Aspose.Page for Java free to use?
A: Aspose.Page for Java is a commercial product. You can explore its features through a free trial [here](https://releases.aspose.com/).
### Q: Where can I find the documentation for Aspose.Page for Java?
A: The documentation is available [here](https://reference.aspose.com/page/java/).
### Q: How can I obtain a temporary license for Aspose.Page for Java?
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Q: What file formats does Aspose.Page for Java support?
A: Aspose.Page for Java supports various formats, including EPS, PDF, and XPS.
### Q: Can I purchase Aspose.Page for Java?
A: Yes, you can purchase Aspose.Page for Java [here](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
