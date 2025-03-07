---
title: Get Metadata from XMP using Java
linktitle: Get Metadata from XMP using Java
second_title: Aspose.Page Java API
description: Unlock the power of Aspose.Page for Java to effortlessly extract XMP metadata. Elevate document analysis with our step-by-step guide!
weight: 18
url: /java/xmp-metadata-manipulation/get-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Get Metadata from XMP using Java

## Introduction
Welcome to our step-by-step guide on utilizing Aspose.Page for Java to extract metadata from XMP files. XMP (Extensible Metadata Platform) provides a standardized way of storing metadata in files. This tutorial focuses on retrieving essential information from XMP using Java, offering insights into document details.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
- Java Development Kit (JDK): Make sure you have Java installed on your machine.
- Aspose.Page for Java: Download and install the Aspose.Page library, which you can find [here](https://releases.aspose.com/page/java/).
## Import Packages
In your Java project, import the necessary packages:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Step 1: Initialize Input EPS File Stream
Begin by setting the path to your document directory and initializing the input EPS file stream.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Step 2: Get XMP Metadata
Retrieve XMP metadata from the EPS file. If the file lacks XMP metadata, a new one will be generated with values from PS metadata comments.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Step 3: Extract CreatorTool Information
Check and print the "CreatorTool" value from the XMP metadata.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Step 4: Extract CreateDate Information
Check and print the "CreateDate" value from the XMP metadata.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Step 5: Retrieve Thumbnail Width
If thumbnails exist, extract and print the width of the first thumbnail.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Step 6: Extract Format Information
Check and print the "format" value from the XMP metadata.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Step 7: Get DocumentID
Check and print the "DocumentID" value from the XMP metadata.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Conclusion
Congratulations! You've successfully learned how to extract XMP metadata using Aspose.Page for Java. This guide provides a comprehensive overview of the process, ensuring you can effectively retrieve essential information from your documents.
## Frequently Asked Questions
### Can I use Aspose.Page for Java with other programming languages?
Yes, Aspose.Page supports multiple languages, including Java, .NET, and more. Check the [documentation](https://reference.aspose.com/page/java/) for details.
### Is a free trial available for Aspose.Page for Java?
Yes, you can access the free trial [here](https://releases.aspose.com/).
### Where can I find support for Aspose.Page for Java?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.
### How do I obtain a temporary license for Aspose.Page for Java?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Are there additional resources for Aspose.Page for Java?
Explore the complete [documentation](https://reference.aspose.com/page/java/) and download the library [here](https://releases.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
