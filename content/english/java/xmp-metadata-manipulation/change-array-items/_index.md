---
title: Change Array Items in XMP using Java
linktitle: Change Array Items in XMP using Java
second_title: Aspose.Page Java API
description: Learn how to change array items in XMP using Aspose.Page for Java. Modify metadata effortlessly with our step-by-step guide. Enhance your EPS documents now!
type: docs
weight: 15
url: /java/xmp-metadata-manipulation/change-array-items/
---
## Introduction
Welcome to our comprehensive guide on changing array items in XMP using Aspose.Page for Java! Aspose.Page is a powerful Java library that allows you to work with XMP metadata in EPS files seamlessly. In this tutorial, we'll walk you through the process of modifying array items within XMP metadata, helping you enhance and customize your EPS documents.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- Java Development Kit (JDK) installed on your system.
- Aspose.Page library for Java. You can download it from [here](https://releases.aspose.com/page/java/).
## Import Packages
To get started, let's import the necessary packages in your Java project. Ensure you have the Aspose.Page library included in your project.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## Step 1: Get XMP Metadata
Firstly, retrieve the XMP metadata from your EPS file. If the EPS file doesn't already contain XMP metadata, a new one will be created with values from PS metadata comments such as %%Creator, %%CreateDate, %%Title, etc.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```
## Step 2: Set "dc:title" Array Item
Now, let's set the "dc:title" array item at index 0 with a new value.
```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## Step 3: Set "dc:creator" Array Item
Similarly, set the "dc:creator" array item at index 0 with a new creator value.
```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## Step 4: Initialize Output EPS File Stream
Prepare the output EPS file stream where the modified document will be saved.
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## Step 5: Save Document with Changed XMP Metadata
Save the document with the updated XMP metadata.
```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Conclusion
Congratulations! You've successfully learned how to change array items in XMP using Aspose.Page for Java. This tutorial provided step-by-step guidance, ensuring you can effortlessly enhance your EPS documents with customized metadata.
---
## FAQs
### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page is primarily designed for Java, but Aspose provides similar libraries for other languages.
### Where can I find detailed documentation for Aspose.Page for Java?
The documentation is available [here](https://reference.aspose.com/page/java/).
### Is there a free trial available for Aspose.Page for Java?
Yes, you can get a free trial [here](https://releases.aspose.com/).
### How can I obtain a temporary license for Aspose.Page for Java?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Where can I purchase the full version of Aspose.Page for Java?
You can buy the full version [here](https://purchase.aspose.com/buy).
