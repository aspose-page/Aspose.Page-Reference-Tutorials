---
title: Read XMP using Aspose.Page – Java Guide
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
description: Learn how to read xmp using aspose.page with Java. This step‑by‑step guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and more.
weight: 18
url: /java/xmp-metadata-manipulation/get-metadata/
date: 2026-05-25
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
schemas:
- type: TechArticle
  headline: Read XMP using Aspose.Page – Java Guide
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  dateModified: '2026-05-25'
  author: Aspose
- type: FAQPage
  questions:
  - question: Does this approach work with PDF files that contain XMP?
    answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
  - question: Can I modify XMP metadata after reading it?
    answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
  - question: Is there a way to extract all thumbnail images, not just dimensions?
    answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Get Metadata from XMP using Java

## How to read XMP using Aspose.Page (Java)?

Load the EPS file with `new Document("file.eps")`—the `Document` class represents a loaded file. Call `getXmpMetadata()`, which extracts the XMP packet, and then query the returned `XmpMetadata` object—a map‑like interface for XMP properties—to retrieve the keys you need. This is all required to read XMP using Aspose.Page. The API abstracts the low‑level parsing, so you get a ready‑to‑use map of properties in just two lines of code.

Welcome to our step‑by‑step tutorial that shows **how to read XMP** metadata with Java and the Aspose.Page library. XMP (Extensible Metadata Platform) is a widely adopted standard for embedding rich metadata inside documents. By the end of this guide you’ll be able to read document format XMP, pull out creator information, timestamps, thumbnails, and more—empowering you to build smarter document‑analysis solutions.

## Quick Answers
- **What does “read XMP” mean?** It means programmatically extracting the XMP packet that stores metadata inside a file.  
- **Which library is required?** Aspose.Page for Java (download from the official page [here](https://releases.aspose.com/page/java/)).  
- **Do I need a license?** A temporary or full license is required for production; a free trial works for evaluation.  
- **What Java version is supported?** Java 8 or higher.  
- **Can I read XMP from other formats?** Yes – Aspose.Page extracts XMP from EPS, PDF, JPEG, PNG and over 20 other formats.

## Prerequisites
Before diving into the code, make sure you have:

- **Java Development Kit (JDK)** – Java 8+ installed and configured on your machine.  
- **Aspose.Page for Java** – Download the library from the official site [here](https://releases.aspose.com/page/java/).  
- An EPS file that contains XMP metadata (e.g., `xmp1.eps`).  

## Import Packages
The `XmpMetadata` class lives in the `com.aspose.page.xmp` namespace, while the `Document` class is in `com.aspose.page`. Import both so you can work with the EPS file and its metadata.  
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
`XmpMetadata` is Aspose.Page's object that holds the XMP packet extracted from a document. Retrieve it with `document.getXmpMetadata()`. If the file lacks XMP, the API synthesises a minimal packet from existing PostScript comments.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Step 3: Extract CreatorTool Information
The `CreatorTool` key lives under the `xmp` namespace and records the application that generated the file. Check for its presence and print the value.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Step 4: Extract CreateDate Information
`CreateDate` stores the timestamp when the document was originally created. Use the same `containsKey`/`get` pattern to read it.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Step 5: Retrieve Thumbnail Width
If thumbnails exist, the `xmp:Thumbnails` array holds one or more entries. Each entry contains `width`, `height`, and binary data. The example extracts the width of the first thumbnail.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Step 6: Extract Format Information
The `format` key tells you the original file format (e.g., “application/postscript”). This is useful when you need to log or validate source types.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Step 7: Get DocumentID
`DocumentID` is a unique identifier assigned by the creator application. It can be used for deduplication in large asset libraries.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Why This Matters
Aspose.Page can read XMP from **20+** file formats and processes documents up to **500 MB** without loading the entire file into memory, giving you fast, low‑overhead access to essential metadata. This capability is critical for batch‑processing pipelines, digital asset management systems, and any solution that relies on searchable, machine‑readable document attributes.

## Common Pitfalls & Tips
- **Missing XMP:** Some EPS files may not contain XMP. The `getXmpMetadata()` call will synthesize a minimal set based on existing PS comments, but you won’t get full metadata unless it’s embedded.  
- **Thumbnail Arrays:** The `xmp:Thumbnails` key can hold multiple entries. The example extracts only the first one; iterate the array if you need all thumbnails.  
- **Namespace Awareness:** XMP keys use namespaces (e.g., `xmp:`, `dc:`). Ensure you reference the exact key name; otherwise `containsKey` will return false.  

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other programming languages?
Yes, Aspose.Page supports Java, .NET, and several other languages. See the full list in the [documentation](https://reference.aspose.com/page/java/).

### Is a free trial available for Aspose.Page for Java?
Yes, you can access the free trial [here](https://releases.aspose.com/).

### Where can I find support for Aspose.Page for Java?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community help and official support.

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

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## Related Tutorials

- [Aspose Page Java Tutorial – Add XMP Metadata to EPS Files](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page xmp tutorial – Add Namespace in XMP using Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page xmp tutorial – Change Named Value in XMP using Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}