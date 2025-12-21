---
title: How to Read XMP Metadata using Java – Aspose.Page Guide
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
description: Learn how to read XMP metadata using Java with Aspose.Page. This step‑by‑step guide shows you how to read document format XMP and extract key properties.
weight: 18
url: /java/xmp-metadata-manipulation/get-metadata/
date: 2025-12-21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Get Metadata from XMP using Java

## How to Read XMP Metadata using Java

Welcome to our step‑by‑step tutorial that shows **how to read XMP** metadata with Java and the Aspose.Page library. XMP (Extensible Metadata Platform) is a widely adopted standard for embedding rich metadata inside documents. By the end of this guide you’ll be able to read document format XMP, pull out creator information, timestamps, thumbnails, and more—empowering you to build smarter document‑analysis solutions.

## Quick Answers
- **What does “how to read xmp” mean?** It refers to extracting XMP metadata from files programmatically.  
- **Which library is required?** Aspose.Page for Java (available from the Aspose download page).  
- **Do I need a license?** A temporary or full license is required for production use; a free trial is available.  
- **What Java version is supported?** Java 8 or higher.  
- **Can I read XMP from other formats?** Yes, Aspose.Page can handle EPS, PDF, and several image types that embed XMP.

## Prerequisites
Before diving into the code, make sure you have:

- **Java Development Kit (JDK)** – Java 8+ installed and configured on your machine.  
- **Aspose.Page for Java** – Download the library from the official site [here](https://releases.aspose.com/page/java/).  
- An EPS file that contains XMP metadata (e.g., `xmp1.eps`).  

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

## Why This Matters
Reading XMP metadata lets you programmatically discover the origin, creation date, and other essential attributes of a document without opening it in a viewer. This is especially useful for batch processing, content management systems, and digital asset pipelines where metadata drives indexing and search.

## Common Pitfalls & Tips
- **Missing XMP:** Some EPS files may not contain XMP. The `getXmpMetadata()` call will synthesize a minimal set based on existing PS comments, but you won’t get full metadata unless it’s embedded.  
- **Thumbnail Arrays:** The `xmp:Thumbnails` key can hold multiple entries. The example extracts only the first one; iterate the array if you need all thumbnails.  
- **Namespace Awareness:** XMP keys use namespaces (e.g., `xmp:`, `dc:`). Ensure you reference the exact key name; otherwise `containsKey` will return false.

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

## Additional FAQ
**Q: Does this approach work with PDF files that contain XMP?**  
A: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.

**Q: Can I modify XMP metadata after reading it?**  
A: Absolutely. The `XmpMetadata` object is mutable; you can add, update, or remove keys and then save the document.

**Q: Is there a way to extract all thumbnail images, not just dimensions?**  
A: You can retrieve the binary data from the `xmpGImg:data` property of each thumbnail entry and write it to a file.

## Conclusion
You've now mastered **how to read XMP** metadata using Java and Aspose.Page. By following these steps you can extract creator tools, timestamps, thumbnails, format information, and document IDs—giving you full insight into the embedded metadata of your EPS files. Feel free to experiment with additional XMP namespaces to pull even richer data for your applications.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose