---
title: How to create xmp metadata eps with Java
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
description: Learn how to create xmp metadata eps in EPS files using Aspose.Page for Java. Step‑by‑step guide to add simple XMP properties programmatically.
weight: 14
url: /java/xmp-metadata-manipulation/add-simple-properties/
date: 2025-12-20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Simple Properties in XMP using Java

## Introduction
In modern document workflows, being able to **create XMP metadata EPS** files programmatically gives you full control over how your graphics are described, searched, and archived. With Aspose.Page for Java you can read, modify, and write XMP packets inside EPS documents without leaving the Java ecosystem. In this tutorial we’ll walk you through the exact steps to add simple XMP properties to an EPS file, so you can enrich your graphics with custom metadata quickly and reliably.

## Quick Answers
- **What does “create xmp metadata eps” mean?** Adding an XMP packet (XML‑based metadata) to an EPS file.  
- **Which library is required?** Aspose.Page for Java (downloadable from the Aspose site).  
- **Do I need a license for testing?** A free trial works for development; a commercial license is required for production.  
- **How many lines of code?** Less than 30 lines of Java plus a few import statements.  
- **Can I add other data types?** Yes – dates, integers, doubles, strings, and even arrays are supported.

## What is create xmp metadata eps?
XMP (Extensible Metadata Platform) is a standard for embedding rich metadata inside files. When you **create XMP metadata EPS**, you embed an XML packet inside an EPS (Encapsulated PostScript) document, allowing downstream applications to read author, creation date, custom tags, and more.

## Why add XMP metadata to EPS files?
- **Searchability:** Enables automatic indexing by DAM systems.  
- **Compliance:** Stores legal or licensing information directly in the file.  
- **Automation:** Lets downstream pipelines make decisions based on embedded data.  
- **Portability:** The metadata travels with the EPS, ensuring consistency across platforms.

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
We open the EPS file, create a `PsDocument` instance, and retrieve (or create) the XMP packet.

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
Adding a date is as simple as creating a `Date` object and putting it into the XMP map.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Step 3: Add an Integer property
You can store numeric identifiers or version numbers using an integer value.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Step 4: Add a Double property
Floating‑point numbers are useful for measurements or ratings.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Step 5: Add a String property
Custom textual tags (e.g., project codes) are stored as strings.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Step 6: Save the updated EPS file
After all properties are added, write the document back to disk.

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
Always close the input stream to avoid file‑handle leaks.

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

## Conclusion
By following these steps you now know how to **create XMP metadata EPS** files using Aspose.Page for Java. Adding simple properties such as dates, integers, doubles, and strings is straightforward, and the resulting EPS files carry rich, searchable metadata that benefits any downstream workflow.

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page primarily supports Java, but there are versions available for other languages like .NET.

### Is a free trial available for Aspose.Page for Java?
Yes, you can explore the features of Aspose.Page by obtaining a free trial [here](https://releases.aspose.com/).

### Where can I find detailed documentation for Aspose.Page for Java?
The documentation is available [here](https://reference.aspose.com/page/java/).

### How can I obtain a temporary license for Aspose.Page for Java?
A temporary license can be acquired [here](https://purchase.aspose.com/temporary-license/).

### Where can I purchase Aspose.Page for Java?
You can purchase the product [here](https://purchase.aspose.com/buy).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}