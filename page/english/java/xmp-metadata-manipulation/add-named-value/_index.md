---
title: Add Named Value in XMP Metadata using Java
linktitle: Add Named Value in XMP using Java
second_title: Aspose.Page Java API
description: Master Java document manipulation with asp. Learn how to add XMP metadata using Aspose.Page – a step‑by‑step guide for adding named values.
weight: 12
url: /java/xmp-metadata-manipulation/add-named-value/
date: 2025-12-20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Named Value in XMP Metadata using Java

## Introduction
In modern Java development, managing **XMP metadata** inside EPS files is essential for preserving document provenance and searchability. With **asp** (Aspose.Page for Java), you can effortlessly inject custom named values into the XMP packet. This tutorial walks you through the exact steps—complete with code snippets—so you can start adding XMP metadata to your EPS documents today.

## Quick Answers
- **What library is needed?** Aspose.Page for Java (asp)
- **Which file type is targeted?** EPS files containing XMP metadata
- **Primary use case?** Add custom named values (e.g., page size limits) to XMP
- **Prerequisites?** JDK 8+ and the Aspose.Page for Java library
- **Typical implementation time?** 5–10 minutes once the library is set up

## What is asp?
*asp* is the short form for **Aspose**, a family of .NET and Java APIs that simplify document processing. The Aspose.Page for Java component lets you create, edit, and convert PostScript and EPS files while giving full programmatic access to their metadata, including XMP.

## Why add named values to XMP metadata?
- **Search engine friendliness:** Custom tags improve discoverability.
- **Workflow automation:** Downstream tools can read your custom values to make decisions.
- **Compliance:** Embed regulatory information directly into the document package.

## Prerequisites
Before we dive in, ensure you have the following:

- **Java Development Kit (JDK):** A recent JDK (8 or higher) installed on your machine.
- **Aspose.Page for Java Library:** Download it from the official [download link](https://releases.aspose.com/page/java/). Add the JAR to your project’s classpath.
- **An EPS file** that either already contains XMP metadata or will have it generated automatically.

## Import Packages
Begin by importing the necessary Java packages. These imports give you access to file streams, the EPS document model, and XMP handling classes.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Step‑by‑Step Guide

### Step 1: Initialize Input EPS File Stream
Load the source EPS file into a `FileInputStream`. This stream feeds the document into Aspose’s API.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Pro tip:** Keep the `dataDir` variable configurable so the same code works across environments.

### Step 2: Obtain XMP Metadata
Retrieve the existing XMP packet. If the EPS file lacks one, Aspose creates a fresh XMP object populated from the PS comments.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Step 3: Add Named Value
Insert a custom named value into the XMP structure. In this example we add a new key under the `xmpTPg:MaxPageSize` namespace.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Why this matters:** Named values let you store arbitrary key‑value pairs that downstream applications can read without parsing the entire document.

### Step 4: Initialize Output EPS File Stream
Prepare a `FileOutputStream` where the modified EPS will be saved.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Step 5: Save Document
Persist the changes. The `save` call writes the updated XMP packet back into the EPS file.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Step 6: Close Input EPS Stream
Release the original file handle to avoid resource leaks.

```java
psStream.close();
```

By following these six steps, you have successfully **added a named value in XMP metadata** using **asp** (Aspose.Page for Java).

## Common Issues & Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `xmp` | EPS file has no XMP and Aspose failed to generate one | Ensure the EPS contains at least one PS comment or manually create a new `XmpMetadata` instance. |
| Output file is empty | Output stream not flushed/closed | Verify `outPsStream.close()` is called in a `finally` block (as shown). |
| Duplicate key error | Same named value added twice | Check if the key already exists with `xmp.containsNamedValue(...)` before adding. |

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Yes, Aspose.Page for Java is designed to work seamlessly with other Java libraries, providing flexibility in your development environment.

### Is a free trial available for Aspose.Page for Java?
Yes, you can access a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).

### How can I obtain a temporary license for Aspose.Page for Java?
Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain a temporary license for Aspose.Page for Java.

### Where can I find more tutorials and examples for Aspose.Page for Java?
Explore the [documentation](https://reference.aspose.com/page/java/) for comprehensive tutorials and examples.

### Is Aspose.Page for Java suitable for large‑scale projects?
Absolutely, Aspose.Page for Java is designed to handle large‑scale projects efficiently, providing robust document manipulation capabilities.

## Conclusion
In this guide we demonstrated how **asp** (Aspose.Page for Java) makes it straightforward to **add named values to XMP metadata** within EPS files. With the steps above, you can enrich your documents with custom metadata, improve searchability, and enable smarter downstream processing.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}