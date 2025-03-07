---
title: Change Named Value in XMP using Java
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
description: Discover Aspose.Page for Java - Effortlessly alter XMP metadata in EPS files with our step-by-step guide for streamlined document processing.
weight: 16
url: /java/xmp-metadata-manipulation/change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Change Named Value in XMP using Java

In the realm of document manipulation, Aspose.Page for Java stands out as a powerful tool, enabling developers to seamlessly work with XMP metadata in EPS files. This step-by-step guide will walk you through the process of changing a named value in XMP using Aspose.Page for Java. Before we delve into the details, let's set the stage with an introduction.
## Introduction
Aspose.Page for Java is a robust Java library that facilitates the manipulation and processing of EPS files. When it comes to handling XMP metadata within these files, Aspose.Page empowers developers with a comprehensive set of features. In this tutorial, we will focus on changing a named value in XMP, offering a clear and concise guide for developers looking to enhance their document processing capabilities.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
1. Java Development Environment: Make sure you have a Java development environment set up on your machine.
2. Aspose.Page for Java Library: Download and integrate the Aspose.Page for Java library into your project. You can find the library and detailed documentation [here](https://reference.aspose.com/page/java/).
3. Sample EPS File: Have a sample EPS file ready for experimentation. If you don't have one, you can use the provided example file named "xmp4.eps."
## Import Packages
To kick off the process, import the necessary packages in your Java code. These packages are essential for interacting with Aspose.Page for Java. Include the following lines at the beginning of your Java file:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
Now, let's break down the process of changing a named value in XMP using Aspose.Page for Java into multiple steps:
## Step 1: Initialize Input EPS File Stream
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```
## Step 2: Initialize PsDocument
```java
PsDocument document = new PsDocument(psStream);
```
## Step 3: Get XMP Metadata
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Step 4: Set New Value in XMP
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```
## Step 5: Initialize Output EPS File Stream
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```
## Step 6: Save Document with Changed XMP Metadata
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Step 7: Close Input EPS Stream
```java
// Close input EPS stream
psStream.close();
```
This step-by-step guide ensures a systematic approach to changing a named value in XMP using Aspose.Page for Java. By following these steps, you can seamlessly integrate this functionality into your Java applications.
## Conclusion
In conclusion, Aspose.Page for Java simplifies the process of working with XMP metadata in EPS files. This tutorial has equipped you with the knowledge to efficiently change a named value in XMP, enhancing your document processing capabilities.
## Frequently Asked Questions
### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page primarily supports Java, but Aspose provides similar libraries for various programming languages.
### Is there a free trial available for Aspose.Page for Java?
Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
### Where can I find additional support and discussions about Aspose.Page for Java?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support and discussions.
### How can I obtain a temporary license for Aspose.Page for Java?
You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Where can I purchase Aspose.Page for Java?
To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
