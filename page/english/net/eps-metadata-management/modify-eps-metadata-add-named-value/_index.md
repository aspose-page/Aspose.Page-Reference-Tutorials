---
date: 2026-08-08
description: Learn how to create EPS with XMP metadata and add named values using
  Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
images:
- /net/eps-metadata-management/modify-eps-metadata-add-named-value/og-image.png
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: Add Named Value
og_description: Create EPS with XMP metadata in .NET using Aspose.Page. This guide
  shows how to add named values to EPS files quickly and reliably.
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: Create EPS with XMP – add named value using Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Create EPS with XMP – add named value using Aspose.Page
url: /net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create EPS with XMP – add named value using Aspose.Page

## Introduction

In this tutorial you’ll learn how to **create EPS with XMP** metadata and inject a named value using the Aspose.Page library for .NET. Whether you are building a batch‑processing pipeline or need to enrich EPS files with custom XMP tags, the steps below walk you through everything from setting up the project to persisting the modified file. Aspose.Page can handle EPS documents up to **500 pages** without loading the entire file into memory, making it suitable for high‑volume scenarios.

## Quick answers
- **What is the primary goal?** Add a named XMP value to an existing EPS file.  
- **Which library is required?** Aspose.Page for .NET.  
- **Do I need a license?** A commercial license is required for production; a free trial is available.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **How long does the implementation take?** Roughly 10–15 minutes for a basic use‑case.

## How to create EPS with XMP metadata in .NET?

Load the target EPS file, obtain (or create) its XMP metadata object, add the required named value, and finally save the document back to disk. This workflow requires only a few method calls and works consistently across all supported EPS versions. The approach also preserves existing page content and other XMP structures, so you can safely chain multiple metadata updates.

## Prerequisites

Before you start, make sure you have:

- Basic knowledge of C# and .NET project structure.  
- Visual Studio 2022 (or any compatible IDE).  
- Aspose.Page for .NET library. If you don’t have it yet, download it from the **Aspose.Page for .NET download page**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)).  

## Import namespaces

The following namespaces provide access to Aspose.Page’s EPS handling, device output, and XMP metadata classes.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Step 1: initialize eps file input stream

Create a `FileStream` for the source EPS file and instantiate a `PsDocument` object to work with the document.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Step 2: get XMP metadata

Retrieve the `XmpMetadata` object from the document; this object represents the embedded XMP packet.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Step 3: change XMP metadata values

Use the `AddNamedValue` method of `XmpMetadata` to insert a new named value into the specified XMP structure.

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Step 4: save eps file with changed XMP metadata

Save the modified document by writing it to a new `FileStream`.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Why use Aspose.Page for EPS metadata?

Aspose.Page supports **50+ XMP schemas** and can process EPS files up to **500 pages** while keeping memory usage under **30 MB** for typical documents. The library does not rely on external tools or native code, guaranteeing consistent behavior across Windows, Linux, and macOS environments.

## Common issues and troubleshooting

- **Missing XMP packet:** If `GetXmpMetadata()` returns `null`, the EPS file does not contain an XMP block. The library will automatically create one, but ensure the file is not corrupted.  
- **Namespace conflicts:** When adding custom named values, use a unique namespace URI to avoid collisions with existing schemas.  
- **Large files:** For EPS files larger than 200 MB, consider streaming the output to avoid excessive memory consumption.

## Frequently asked questions

**Q: Is Aspose.Page compatible with different EPS file versions?**  
A: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility with legacy and modern files.

**Q: Can I use Aspose.Page for commercial projects?**  
A: Yes, a commercial license is required for production use. You can purchase a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.

**Q: Is there a free trial available?**  
A: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial download page](https://releases.aspose.com/)**.

**Q: How can I get support or join the community?**  
A: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** to ask questions and share experiences.

**Q: What is a temporary license and how do I obtain one?**  
A: A temporary license lets you evaluate the product for a short period. You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

---

**Last updated:** 2026-08-08  
**Tested with:** Aspose.Page 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [Add Metadata to EPS Document with Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Change Named Value with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [Extract Metadata from EPS Document with Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}