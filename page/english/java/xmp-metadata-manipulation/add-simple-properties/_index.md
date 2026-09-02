---
title: Add XMP Metadata to EPS Files Using Java
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java. Step‑by‑step guide to embed simple XMP properties programmatically.
weight: 14
url: /java/xmp-metadata-manipulation/add-simple-properties/
date: 2026-05-20
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
schemas:
- type: TechArticle
  headline: Add XMP Metadata to EPS Files Using Java
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  dateModified: '2026-05-20'
  author: Aspose
- type: FAQPage
  questions:
  - question: Can I use Aspose.Page for Java with other programming languages?
    answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
  - question: Is a free trial available for Aspose.Page for Java?
    answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
  - question: Where can I find detailed documentation for Aspose.Page for Java?
    answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
  - question: How can I obtain a temporary license for Aspose.Page for Java?
    answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
  - question: Where can I purchase Aspose.Page for Java?
    answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add XMP Metadata to EPS Files Using Java

## Introduction
In modern graphics pipelines, being able to **add XMP metadata** to EPS files programmatically gives you full control over how your illustrations are described, searched, and archived. With Aspose.Page for Java you can read, modify, and write XMP packets inside EPS documents without leaving the Java ecosystem. In this tutorial we’ll walk you through the exact steps to add simple XMP properties to an EPS file, so you can enrich your graphics with custom metadata quickly and reliably.

## Quick Answers
- **What does “add XMP metadata to EPS” mean?** Embedding an XMP packet (XML‑based metadata) inside an EPS file.  
- **Which library is required?** Aspose.Page for Java (downloadable from the Aspose site).  
- **Do I need a license for testing?** A free trial works for development; a commercial license is required for production.  
- **How many lines of code?** Fewer than 30 lines of Java plus a few import statements.  
- **Can I add other data types?** Yes – dates, integers, doubles, strings, and even arrays are supported.

## How to add XMP metadata to EPS files using Java?
Load the EPS file with `new PsDocument("input.eps")`, retrieve or create its XMP packet, insert the desired properties, and then save the document back to disk – all in under ten lines of Java code. This approach lets you embed searchable, standards‑compliant metadata without manual editing of the EPS source.

## What is XMP metadata in EPS?
XMP metadata in EPS is an XML packet that lives inside the EPS file and stores information such as author, creation date, and custom tags. Embedding this packet lets downstream tools read and act on the data without needing separate side‑car files.

## Why add XMP metadata to EPS files?
Embedding XMP metadata makes EPS assets instantly searchable, ensures compliance by storing licensing information inside the file, enables automated pipelines to make decisions based on embedded tags, and guarantees that the metadata travels with the graphic across all platforms. Aspose.Page can process files up to 500 MB without loading the entire document into memory, delivering fast performance for large‑scale workloads.

## Prerequisites
Before you start, make sure you have:

- Basic knowledge of Java programming.  
- Aspose.Page for Java library installed. You can download it **[here](https://releases.aspose.com/page/java/)**.  
- A sample EPS file containing metadata. If you don't have one, feel free to use the provided **`xmp3.eps`** file.

## Import Packages
First, import the classes you’ll need. The imports stay exactly the same as in the original example:

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

## Step 1: Load the EPS document and get XMP metadata
The `PsDocument` class represents an EPS file and provides methods to access its content and metadata.  
The `XmpMetadata` object holds the XMP packet associated with the document.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Step 2: Add a Date property
The `Date` class represents a specific instant in time, with millisecond precision.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Step 3: Add an Integer property
The `Integer` class wraps a primitive `int` value as an object.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Step 4: Add a Double property
The `Double` class wraps a primitive `double` value as an object.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Step 5: Add a String property
The `String` class represents a sequence of characters.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Step 6: Save the updated EPS file
The `save` method writes the modified document back to disk, preserving the EPS structure.

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

## Step 7: Clean up resources
Always close streams to avoid file‑handle leaks and ensure that all buffers are flushed.

```java
// Close input EPS stream
psStream.close();
```

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null XMP metadata** | The EPS file had no XMP packet and the library couldn't infer PS comments. | Ensure the source EPS contains at least one PS comment (e.g., `%%Creator`). The library will generate a minimal XMP packet automatically. |
| **Time zone mismatch** | Dates appear shifted when opened in another application. | Set `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` before creating the `Date` object, as shown in Step 2. |
| **License exception** | Runtime throws `LicenseException`. | Apply a valid Aspose.Page license before using the API, or run in trial mode for evaluation. |

## Frequently Asked Questions
**Q: Can I use Aspose.Page for Java with other programming languages?**  
A: Aspose.Page primarily supports Java, but equivalent libraries are available for .NET, C++, and Python.

**Q: Is a free trial available for Aspose.Page for Java?**  
A: Yes, you can explore the features of Aspose.Page by obtaining a free trial **[here](https://releases.aspose.com/)**.

**Q: Where can I find detailed documentation for Aspose.Page for Java?**  
A: The documentation is available **[here](https://reference.aspose.com/page/java/)**.

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Where can I purchase Aspose.Page for Java?**  
A: You can purchase the product **[here](https://purchase.aspose.com/buy)**.

---

**Last Updated:** 2026-05-20  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [How to Read XMP Metadata using Java – Aspose.Page Guide](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp tutorial – Add Namespace in XMP using Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Add Array Items in XMP Metadata using Java](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}