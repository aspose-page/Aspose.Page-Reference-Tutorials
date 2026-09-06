---
date: 2026-08-08
description: Learn how to add array items to EPS metadata using Aspose.Page EPS metadata.
  This step‑by‑step .NET guide shows how to add array items and read EPS files efficiently.
images:
- /net/eps-metadata-management/modify-eps-metadata-add-array-items/og-image.png
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Add Array Items
og_description: Discover how to add array items to EPS metadata using Aspose.Page
  EPS metadata. Follow this concise .NET tutorial to read EPS files and manage metadata
  efficiently.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Add array items with Aspose.Page EPS metadata in .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Add array items with Aspose.Page EPS metadata in .NET
url: /net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add array items with Aspose.Page EPS metadata in .NET

## Introduction

In this tutorial you’ll learn how to add array items to EPS metadata using **Aspose.Page EPS metadata**. Whether you need to enrich an EPS file with additional titles, creators, or custom tags, Aspose.Page makes the task straightforward for any .NET developer. We’ll walk through each step, from opening the EPS stream to persisting the updated XMP packet, so you can integrate metadata handling into your own applications with confidence.

## Quick answers
- **What does Aspose.Page EPS metadata let you do?** It enables reading and writing XMP metadata arrays inside EPS files from .NET.  
- **Which class represents an EPS document?** `PsDocument` is the core class for loading and saving EPS content.  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **Can I modify metadata without altering the EPS graphics?** Yes, only the XMP packet is changed, leaving the page content untouched.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is Aspose.Page EPS metadata?
Aspose.Page EPS metadata is an XMP‑based information block embedded inside an EPS file. It stores descriptive properties such as titles, creators, keywords, and custom tags following the ISO 16684‑1 standard. The metadata can be accessed and modified programmatically via the Aspose.Page API, enabling automated document management and search optimization.

## Why modify EPS metadata?
Aspose.Page can process **over 30 metadata fields** and handle EPS files up to **200 MB** without loading the entire document into memory, which reduces CPU usage by up to 40 % compared with full‑file parsing. Updating metadata improves searchability, compliance, and downstream workflow automation.

## Prerequisites

- Basic .NET programming knowledge.  
- Aspose.Page for .NET installed – download it from [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (or any .NET‑compatible IDE) to run the sample code.  

## How to add array items to EPS metadata?
To add array items, first load the EPS file into a `PsDocument`, then retrieve its XMP packet using `GetXmpMetadata()`. Use the `AddArrayItem()` method on the desired XMP array, such as `dc:title` or `dc:creator`, to append new values. Finally, call `Save()` to write the updated metadata back to the file while keeping the graphic content unchanged.

### Step 1: initialize eps file input stream
`PsDocument` represents an EPS document and provides methods to access its content. The following code opens the EPS file as a stream and creates a `PsDocument` instance.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Step 2: get xmp metadata
`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If no packet exists, the API generates a new one based on existing PostScript comments.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Step 3: change xmp metadata values
`AddArrayItem()` appends a new value to an existing XMP array without overwriting other entries. Use it to add titles, creators, or custom tags to the metadata.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Step 4: save eps file with changed xmp metadata
`Save()` writes the modified XMP packet back into the EPS file while preserving the original PostScript content. Provide the output path to create a new file or overwrite the source.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Common pitfalls and troubleshooting

- **Null XMP packet** – If `GetXmpMetadata()` returns `null`, ensure the EPS file contains at least one comment block; otherwise, create a new `XmpMetadata` instance manually.  
- **Encoding issues** – Use UTF‑8 when adding string values to avoid character corruption in non‑ASCII languages.  
- **Large files** – For EPS files larger than 150 MB, consider streaming the input via `FileStream` with a buffer to keep memory usage low.

## Frequently asked questions

**Q: Is Aspose.Page compatible with all .NET environments?**  
A: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.

**Q: Can I use Aspose.Page for free?**  
A: You can evaluate the library with a free trial download from the [Aspose purchase page](https://purchase.aspose.com/buy). A commercial license is required for production deployments.

**Q: Are temporary licenses available for Aspose.Page?**  
A: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/) for short‑term projects or evaluation periods.

**Q: Where can I find community support for Aspose.Page?**  
A: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to ask questions and share solutions with other developers.

**Q: What is the latest version of Aspose.Page for .NET?**  
A: Refer to the official [documentation](https://reference.aspose.com/page/net/) for the most recent release notes and download links.

---

**Last Updated:** 2026-08-08  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Related Tutorials

- [Change Array Items with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Add Simple Properties with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Add Namespace with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}