---
title: Add Simple Properties in XMP using Java
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
description: Unlock Aspose.Page for Java's potential with our guide on adding properties to XMP metadata in EPS files. Elevate document processing effortlessly!
type: docs
weight: 14
url: /java/xmp-metadata-manipulation/add-simple-properties/
---
## Introduction
In the ever-evolving landscape of document processing, managing metadata efficiently is crucial. Aspose.Page for Java empowers developers to manipulate Extensible Metadata Platform (XMP) data seamlessly. In this tutorial, we'll explore the process of adding simple properties to XMP using Java, providing you with a comprehensive step-by-step guide.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
- Basic knowledge of Java programming.
- Aspose.Page for Java library installed. You can download it [here](https://releases.aspose.com/page/java/).
- A sample EPS file containing metadata. If you don't have one, feel free to use the provided "xmp3.eps" file.
## Import Packages
Ensure you import the necessary packages to kickstart your project:
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
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Step 2: Add Date Property
```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Step 3: Add Integer Property
```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Step 4: Add Double Property
```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Step 5: Add String Property
```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Step 6: Save Document
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Step 7: Close Streams
```java
// Close input EPS stream
psStream.close();
```
## Conclusion
Aspose.Page for Java simplifies the process of manipulating XMP metadata in EPS files. By following this step-by-step guide, you can effortlessly add simple properties to enhance your document's metadata.
## Frequently Asked Questions
### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page primarily supports Java, but there are versions available for other languages like .NET.
### Is a free trial available for Aspose.Page for Java?
Yes, you can explore the features of Aspose.Page by obtaining a free trial [here](https://releases.aspose.com/).
### Where can I find detailed documentation for Aspose.Page for Java?
The official documentation is available [here](https://reference.aspose.com/page/java/).
### How can I obtain a temporary license for Aspose.Page for Java?
A temporary license can be acquired [here](https://purchase.aspose.com/temporary-license/).
### Where can I purchase Aspose.Page for Java?
You can purchase the product [here](https://purchase.aspose.com/buy).
