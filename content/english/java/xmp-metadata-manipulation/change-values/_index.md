---
title: Change Values in XMP using Java
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
description: Enhance EPS documents with Aspose.Page for Java. Effortlessly modify XMP metadata for tailored and professional content. #JavaDevelopment
type: docs
weight: 17
url: /java/xmp-metadata-manipulation/change-values/
---
## Introduction
In the realm of document processing and manipulation, Aspose.Page for Java stands out as a powerful tool. This tutorial delves into the process of changing XMP (Extensible Metadata Platform) values in EPS (Encapsulated PostScript) documents using Java with the Aspose.Page library. By following the step-by-step guide provided, you'll learn how to effortlessly modify metadata, ensuring your documents are tailored to your specific requirements.
## Prerequisites
Before we embark on this tutorial, ensure you have the following prerequisites in place:
1. Java Development Environment: Make sure you have a working Java development environment on your machine.
2. Aspose.Page for Java Library: Download and install the Aspose.Page for Java library. You can find the necessary package [here](https://releases.aspose.com/page/java/).
## Import Packages
Begin by importing the required packages into your Java project. These packages are vital for interacting with and manipulating EPS documents.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Step 1: Get XMP Metadata
Retrieve XMP metadata from the EPS document. If the EPS file doesn't contain XMP metadata, a new one will be created with values from PS metadata comments such as %%Creator, %%CreateDate, and %%Title.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```
## Step 2: Change "ModifyDate" Value
Modify the "ModifyDate" value in the XMP metadata to reflect the desired date.
```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Step 3: Change "Creator" Value
Update the "Creator" value in the XMP metadata to specify the creator of the document.
```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Step 4: Change "Title" Value
Modify the "Title" value in the XMP metadata to set an appropriate title for the document.
```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Step 5: Save Document with Changed XMP Metadata
Save the document with the updated XMP metadata to a new EPS file.
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Conclusion
Congratulations! You've successfully navigated the process of changing XMP values in EPS documents using Aspose.Page for Java. This tutorial has equipped you with the knowledge to modify metadata, ensuring your documents align with your specific requirements seamlessly.
## FAQs
### Q: How can I handle time zone considerations when modifying XMP values?
Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency in time zone settings.
### Q: Can I change multiple XMP values in a single operation?
Yes, by using the `put` method for each desired value, you can modify multiple XMP values concurrently.
### Q: Where can I find additional documentation for Aspose.Page for Java?
Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
### Q: Is there a free trial available for Aspose.Page for Java?
Yes, you can access the free trial [here](https://releases.aspose.com/).
### Q: How can I obtain a temporary license for Aspose.Page for Java?
Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
