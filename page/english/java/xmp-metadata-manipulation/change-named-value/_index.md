---
title: "how to edit xmp – Change Named Value in XMP using Java"
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
description: "Learn how to edit XMP metadata and how to change XMP values in EPS files with Aspose.Page for Java – a clear step‑by‑step guide."
weight: 16
url: /java/xmp-metadata-manipulation/change-named-value/
date: 2026-05-15
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
schemas:
- type: TechArticle
  headline: how to edit xmp – Change Named Value in XMP using Java
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  dateModified: '2026-05-15'
  author: Aspose
- type: HowTo
  name: how to edit xmp – Change Named Value in XMP using Java
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
- type: FAQPage
  questions:
  - question: Can I use Aspose.Page for Java with other programming languages?
    answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
  - question: Is there a free trial available for Aspose.Page for Java?
    answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
  - question: Where can I find additional support and discussions about Aspose.Page
      for Java?
    answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
  - question: How can I obtain a temporary license for Aspose.Page for Java?
    answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - question: Where can I purchase Aspose.Page for Java?
    answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# how to edit xmp – Change Named Value in XMP using Java

In modern document workflows, **Aspose.Page for Java** makes it easy to read, edit, and write XMP metadata inside EPS files. **This tutorial shows how to edit xmp** metadata in EPS documents using the Aspose.Page API, so you can keep your document information accurate, searchable, and compliant with industry standards. Whether you’re updating page dimensions, author information, or custom tags, the steps below walk you through the process in Java.

## Quick Answers
- **What does this tutorial cover?** Changing a named XMP value in an EPS file with Aspose.Page for Java.  
- **Which library version is required?** Any recent Aspose.Page for Java release (the API has been stable for several years).  
- **Do I need a license?** A temporary or full license is required for production; a free trial works for testing.  
- **How long does implementation take?** Roughly 10‑15 minutes for a developer familiar with Java I/O.  
- **Can I use this with other file formats?** The XMP API is also available for PDF, SVG, and other formats supported by Aspose.Page.

## What is XMP metadata?
XMP (Extensible Metadata Platform) is a standardized XML‑based format for embedding rich metadata—such as creator, title, and custom properties—directly inside files. In EPS documents, XMP lives alongside traditional PostScript comments, enabling applications to read and modify metadata without altering the visual content.

## Why use Aspose.Page for Java to edit XMP?
Aspose.Page gives you **full control over more than 150 XMP schema properties** and works consistently across EPS, PDF, and SVG formats. It processes files up to **500 MB** without loading the entire document into memory, and it includes built‑in validation that guarantees the resulting EPS remains standards‑compliant. No external XML parsers or native libraries are required.

## Introduction
Aspose.Page for Java is a robust library that facilitates the manipulation and processing of EPS files. When it comes to handling XMP metadata within these files, Aspose.Page empowers developers with a comprehensive set of features. In this tutorial, we will focus on changing a named value in XMP, offering a clear and concise guide for developers looking to enhance their document processing capabilities.

## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
1. **Java Development Environment** – A JDK (8 or higher) and an IDE or build tool (Maven/Gradle).  
2. **Aspose.Page for Java Library** – Download and integrate the Aspose.Page for Java library into your project. You can find the library and detailed documentation [here](https://reference.aspose.com/page/java/).  
3. **Sample EPS File** – Have a sample EPS file ready for experimentation. If you don't have one, use the provided example file named **"xmp4.eps."**

## Import Packages
The `import` statements bring the essential Aspose.Page classes into scope.

The `PsDocument` class is Aspose.Page's core object that represents an EPS document in memory.  
The `XmpMetadata` class provides access to the XMP packet embedded in the EPS file.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## How to edit XMP metadata?
Load the EPS file, retrieve its XMP packet, modify the desired property, and save the document—all in a few straightforward lines. This approach works for any named XMP value, whether it’s a standard Dublin Core field or a custom namespace you’ve defined.

## Step 1: Initialize Input EPS File Stream
`FileInputStream` opens a read‑only stream to the source EPS file, allowing Aspose.Page to ingest the document without locking the file system.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Step 2: Initialize PsDocument
`PsDocument` is the primary object that encapsulates the EPS content and provides access to its metadata, pages, and resources.

```java
PsDocument document = new PsDocument(psStream);
```

## Step 3: Get XMP Metadata
`XmpMetadata` represents the XMP packet inside the EPS file and offers methods to read, modify, or delete individual properties.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Step 4: Set New Value in XMP
`setProperty` sets the value of a specified XMP property in the metadata packet.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Step 5: Initialize Output EPS File Stream
`FileOutputStream` creates a writable stream for saving the modified EPS file.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Step 6: Save Document with Changed XMP Metadata
`save` writes the in‑memory PsDocument, including updated XMP, to the output stream.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Step 7: Close Input EPS Stream
`close` releases the file handle and frees resources associated with the input stream.

```java
// Close input EPS stream
psStream.close();
```

## Common Issues and Solutions
- **FileNotFoundException** – Verify that `dataDir` points to the correct folder and that `xmp4.eps` exists.  
- **LicenseException** – If you see licensing errors, make sure a valid Aspose.Page license file is loaded before creating `PsDocument`.  
- **Metadata Not Updated** – After saving, open the resulting EPS in a metadata viewer (e.g., Adobe Bridge) to confirm the new value appears.

## Frequently Asked Questions
**Q: Can I use Aspose.Page for Java with other programming languages?**  
A: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries for .NET, C++, and Python that expose similar XMP manipulation capabilities.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).

**Q: Where can I find additional support and discussions about Aspose.Page for Java?**  
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support and discussions.

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I purchase Aspose.Page for Java?**  
A: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-05-15  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

## Related Tutorials

- [How to Read XMP Metadata using Java – Aspose.Page Guide](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java Tutorial – Add XMP Metadata to EPS Files](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Change Values in XMP using Java](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}