---
title: How to Add dc:title Array Items in XMP Metadata using Java
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
description: Learn how to add dc:title array items in XMP metadata of EPS files using Aspose.Page for Java. Follow this step‑by‑step guide for quick results.
weight: 10
url: /java/xmp-metadata-manipulation/add-array-items/
date: 2026-03-05
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Array Items in XMP Metadata using Java

## Introduction
In this tutorial you'll discover **how to add dc:title** (and other array items) to XMP metadata inside an EPS file with Aspose.Page for Java. Updating XMP metadata is useful when you need to embed searchable information—such as titles, creators, or keywords—directly into your graphics files. We'll walk through each step, explain why each line matters, and show you how to verify the changes.

## Quick Answers
- **What does “dc:title” represent?** It’s the Dublin Core title property stored as an XMP array.  
- **Why modify XMP metadata?** It enables better asset management, searchability, and compliance with standards.  
- **Do I need an existing XMP block?** No—Aspose.Page will generate one from PS comments if missing.  
- **Which library version is required?** Any recent Aspose.Page for Java release (tested with the latest 2026 build).  
- **Can I add other array properties?** Yes—use the same `addArrayItem` method for properties like `dc:creator`.

## Prerequisites
Before we dive in, make sure you have:

- Aspose.Page for Java library installed (add the JAR to your project’s classpath).  
- Basic Java development experience (JDK 8+ recommended).  
- An EPS file that already contains XMP metadata or at least PS metadata comments (e.g., `%%Title`, `%%Creator`).  

## Import Packages
To start, import the classes required for reading, manipulating, and saving EPS files:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Step 1: Load the EPS Document and Retrieve XMP Metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Here we open the EPS file and ask Aspose.Page for its XMP block. If the file lacks XMP, the library auto‑creates one using existing PS comments, ensuring you always have a metadata container to work with.

## Step 2: Add a New **dc:title** Array Item  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

This line demonstrates **how to add dc:title**. Replace `"NewTitle"` with the actual title you want to embed. The method appends the value to the existing title array, preserving any previous titles.

## Step 3: Add a New **dc:creator** Array Item  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Similarly, you can enrich the `dc:creator` property. Multiple creators can be stored; each call adds another entry.

## Step 4: Prepare the Output Stream  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

We create a stream for the modified EPS file. Using a different filename (`xmp3_changed.eps`) keeps the original file untouched.

## Step 5: Save the Document with Updated XMP Metadata  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

The `save` call writes the EPS data together with the updated XMP block. The `finally` block guarantees the file handle is released even if an exception occurs.

## Why This Matters
Embedding accurate `dc:title` and `dc:creator` values improves:

- **Searchability** in digital asset management (DAM) systems.  
- **Compliance** with publishing standards that require metadata.  
- **Collaboration**, as teammates can quickly identify file contents without opening the EPS.

## Common Pitfalls & Tips
- **Pitfall:** Overwriting existing array items unintentionally.  
  **Tip:** Use `xmp.getArrayItems("dc:title")` to inspect current values before adding new ones.  
- **Pitfall:** Forgetting to close streams, leading to file locks.  
  **Tip:** Always wrap I/O in try‑with‑resources or a `finally` block as shown.  
- **Tip:** You can chain multiple `addArrayItem` calls to add several titles or creators in one pass.

## Frequently Asked Questions

### Can I use Aspose.Page for Java with other document formats?
Yes, Aspose.Page supports various document formats, including EPS, PDF, and XPS.

### Is there a free trial available for Aspose.Page for Java?
Yes, you can access the free trial [here](https://releases.aspose.com/).

### Where can I find the documentation for Aspose.Page for Java?
The documentation is available [here](https://reference.aspose.com/page/java/).

### How can I purchase Aspose.Page for Java?
You can buy the product [here](https://purchase.aspose.com/buy).

### Are temporary licenses available for Aspose.Page for Java?
Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest 2026 release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}