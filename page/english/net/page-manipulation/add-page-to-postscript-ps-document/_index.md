---
title: Set Custom Page Size in PS Document with Aspose.Page
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
description: Learn how to set custom page size and add a second PS page to a PostScript document using Aspose.Page for .NET.
weight: 10
url: /net/page-manipulation/add-page-to-postscript-ps-document/
date: 2026-03-03
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Page to PostScript (PS) Document with Aspose.Page

## Introduction

In .NET development, being able to **set custom page size** and **add second PS page** to a PostScript (PS) document gives you fine‑grained control over the layout of generated prints, reports, or graphics. Aspose.Page for .NET makes this task straightforward with a clean, object‑oriented API. In this tutorial you’ll learn how to create a multi‑page PS file, define a custom size for each page, and save the result—all with just a few lines of C# code.

## Quick Answers
- **Can I set a custom page size?** Yes – just pass width and height when opening a page.  
- **How do I add a second PS page?** Call `document.OpenPage(width, height)` a second time.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Do I need a license?** A temporary license works for testing; a full license is required for production.  
- **Where can I download Aspose.Page?** From the official download page linked below.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- A working knowledge of .NET development.  
- Visual Studio installed on your machine.  
- Aspose.Page for .NET library, which you can download [here](https://releases.aspose.com/page/net/).  
- Your preferred document directory for testing.

## Import Namespaces

Ensure that you include the necessary namespaces in your project to access the functionalities provided by Aspose.Page. In the given example, the namespaces are implicitly included, but it's essential to double‑check and make adjustments based on your project structure.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Your Project

Create a new .NET project in Visual Studio and set up the necessary configurations. Make sure to reference the Aspose.Page library in your project.

## Set Custom Page Size and Add Second PS Page

This section demonstrates exactly how to **set custom page size** for each page and how to **add second ps page** to the same document.

### Step 2: Initialize the Document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Step 3: Add the First Page (default size)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Step 4: Add the Second Page with a Different (Custom) Size

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Step 5: Save the Document

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Follow these steps meticulously, and you'll successfully **set custom page size** and add a **second PS page** to a PostScript document using Aspose.Page for .NET.

## Why This Matters

- **Precision Layout** – Custom page dimensions let you match printer specifications or create unique brochure formats.  
- **Multiple Pages** – Adding a second page (or more) enables multi‑page reports without external merging tools.  
- **Cross‑Platform** – The generated PS file can be rendered on any PostScript‑compatible device or converted to PDF later.

## Common Pitfalls & Troubleshooting

- **Incorrect Path** – Ensure `dataDir` ends with a path separator or use `Path.Combine`.  
- **License Issues** – Without a valid license, the library may add a watermark or limit page count.  
- **Unit Confusion** – Width and height are measured in points (1 point = 1/72 inch). Adjust accordingly.

## Frequently Asked Questions

**Q1: Is Aspose.Page compatible with different document formats?**  
A1: Aspose.Page primarily focuses on PostScript document manipulation. For other formats, you may explore Aspose libraries tailored to specific needs.

**Q2: Can I customize the page size in Aspose.Page?**  
A2: Absolutely! As demonstrated in the tutorial, you can specify different sizes for each page according to your requirements.

**Q3: Where can I find more examples and documentation?**  
A3: Visit the [documentation](https://reference.aspose.com/page/net/) for comprehensive information and a variety of examples.

**Q4: How do I obtain a temporary license for Aspose.Page?**  
A4: Navigate to [this link](https://purchase.aspose.com/temporary-license/) to acquire a temporary license for testing purposes.

**Q5: Where can I seek community support or ask questions?**  
A5: Join the [Aspose.Page community forum](https://forum.aspose.com/c/page/39) to connect with other developers, share experiences, and seek assistance.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}