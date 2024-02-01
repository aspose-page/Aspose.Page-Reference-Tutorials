---
title: Add Namespace in XMP using Java
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
description: Unlock the power of document manipulation with Aspose.Page for Java. Learn to add XMP namespaces effortlessly in this comprehensive guide.
type: docs
weight: 13
url: /java/xmp-metadata-manipulation/add-namespace/
---

## Introduction

In the realm of document manipulation, Aspose.Page for Java stands out as a robust tool, offering a wide array of functionalities. One powerful feature is the ability to add namespaces in XMP (Extensible Metadata Platform) using Java. This tutorial will guide you through the process, breaking it down into easy-to-follow steps.

## Prerequisites

Before delving into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for Java: Ensure you have the library installed. You can download it [here](https://releases.aspose.com/page/java/).

- Java Development Environment: Set up a Java environment on your system.

- Document File: Have an EPS file with XMP metadata. If it doesn't contain XMP metadata, the library will create one based on PS metadata comments.

## Import Packages

To start, import the necessary packages into your Java project:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

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
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Step 2: Register New Namespace

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## Step 3: Add New Property

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## Step 4: Save Document

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

## Step 5: Close Streams

```java
// Close input EPS stream
psStream.close();
```

Now you've successfully added a namespace in XMP using Aspose.Page for Java. Feel free to explore more features and unleash the full potential of this library.

## Conclusion

Aspose.Page for Java simplifies the complex task of manipulating XMP metadata in EPS files. By following this step-by-step guide, you've acquired a valuable skill to enhance your document processing capabilities.

## FAQs

### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page primarily supports Java, but there are versions available for other languages such as .NET.

### Is there a free trial available?
Yes, you can explore a free trial [here](https://releases.aspose.com/).

### Where can I find comprehensive documentation?
Refer to the documentation [here](https://reference.aspose.com/page/java/).

### How can I obtain a temporary license?
You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Are there community forums for Aspose.Page?
Yes, you can engage with the community on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
