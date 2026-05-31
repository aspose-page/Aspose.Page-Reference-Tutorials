---
title: "asp page eps tutorial: Add Array Items with Aspose.Page"
linktitle: Add Array Items
second_title: Aspose.Page .NET API
description: "Explore the asp page eps tutorial for adding array items in EPS files using Aspose.Page for .NET. Follow our step-by-step guide for seamless document manipulation."
weight: 11
url: /net/eps-metadata-management/modify-eps-metadata-add-array-items/
date: 2026-01-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page eps tutorial: Add Array Items with Aspose.Page

## Introduction

If you need to modify EPS metadata programmatically, the **asp page eps tutorial** is the perfect place to start. In this guide we’ll walk through adding new items to an XMP array inside an EPS file using Aspose.Page for .NET. Whether you’re updating titles, creators, or any other array‑based metadata, you’ll see exactly how to do it—step by step, with clear explanations and ready‑to‑run code.

## Quick Answers
- **What does the tutorial cover?** Adding array items to EPS XMP metadata with Aspose.Page.  
- **Which language is used?** C# (.NET).  
- **Do I need a license?** A free trial works for testing; a commercial license is required for production.  
- **What are the prerequisites?** .NET development environment and Aspose.Page for .NET installed.  
- **How long does implementation take?** About 10‑15 minutes for a basic scenario.

## What is an asp page eps tutorial?

An **asp page eps tutorial** teaches you how to leverage the Aspose.Page library to read, modify, and write EPS (Encapsulated PostScript) files. The focus here is on XMP metadata arrays—structures that store multiple values such as titles or creators.

## Why add array items to EPS metadata?

Adding items to an EPS’s XMP array lets you enrich the document with searchable, standards‑compliant information. Typical use cases include:
- Adding multiple authors to a design file.  
- Storing version history titles.  
- Embedding custom tags for downstream processing pipelines.

## Prerequisites

Before you start, make sure you have:

- A basic understanding of .NET programming.  
- Aspose.Page for .NET installed. If you haven’t downloaded it yet, get it from [here](https://releases.aspose.com/page/net/).  
- A code editor such as Visual Studio.

## Import Namespaces

In your .NET project, add the required `using` directives so the compiler knows where to find the Aspose.Page classes.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

These namespaces expose the core EPS handling, device rendering, and XMP metadata APIs.

## Step 1: Initialize EPS file input stream

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

Here we open the source EPS file and create a `PsDocument` object that represents the whole document in memory.

## Step 2: Get XMP metadata

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

The `GetXmpMetadata` call either returns the existing XMP block or creates a fresh one populated with standard PostScript comments.

## Step 3: Change XMP metadata values

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

- `dc:title` and `dc:creator` are standard Dublin Core properties.  
- The first call appends a new title.  
- The second call inserts a creator at position 0, pushing existing entries forward.

## Step 4: Save EPS file with changed XMP metadata

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

After updating the metadata, we write the modified document back to disk. The resulting EPS file now contains the new array items.

## Common Issues & Tips

- **File access errors:** Ensure the input EPS file is not locked by another process.  
- **Missing XMP block:** If the source file has no XMP, the library creates one automatically, but you may need to set additional required properties later.  
- **Encoding problems:** Use UTF‑8 strings for XMP values to avoid character corruption.

## Frequently Asked Questions

**Q1: Is Aspose.Page compatible with all .NET environments?**  
A1: Yes, Aspose.Page works across .NET Framework, .NET Core, and .NET 5/6+ platforms.

**Q2: Can I use Aspose.Page for free?**  
A2: A free trial is available for evaluation. For production use, a license must be purchased from [here](https://purchase.aspose.com/buy).

**Q3: Are temporary licenses available for Aspose.Page?**  
A3: Yes, temporary licenses can be obtained from [here](https://purchase.aspose.com/temporary-license/) for short‑term projects.

**Q4: Where can I find community support for Aspose.Page?**  
A4: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q5: What is the latest version of Aspose.Page for .NET?**  
A5: Refer to the official [documentation](https://reference.aspose.com/page/net/) for the most up‑to‑date release information.

---

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Page 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}