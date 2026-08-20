---
date: 2026-03-19
description: Lär dig hur du **tar bort sida i XPS‑dokument** och **raderar sida på
  ett index** med Aspose.Page för .NET – en komplett steg‑för‑steg‑guide med förutsättningar,
  kodexempel och vanliga frågor.
linktitle: Remove Page from XPS Document
second_title: Aspose.Page .NET API
title: Ta bort sida från XPS-dokument med Aspose.Page för .NET
url: /sv/net/page-manipulation/remove-page-from-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Remove Page from XPS Document with Aspose.Page for .NET

## Introduction

If you need to **remove page xps** files programmatically, Aspose.Page for .NET gives you a clean, reliable way to do it. In this tutorial we’ll walk through the exact steps required to delete a specific page from an XPS document, explain why this operation matters, and show you how to save the updated file back to disk.

## Quick Answers
- **What does “remove page xps” mean?** It refers to deleting a single page from an XPS (XML Paper Specification) document.  
- **Which method deletes a page?** Use `RemovePageAt(index)` where the index is zero‑based.  
- **Can I delete a page at any position?** Yes – you can **delete page at index** 0, 1, 2, etc., as needed.  
- **Do I need a license for Aspose.Page?** A temporary license is required for testing; a full license is needed for production.  
- **Is the code compatible with .NET 6?** Absolutely – Aspose.Page supports .NET Framework, .NET Core, and .NET 5/6.

## What is “remove page xps”?
Removing a page from an XPS document means taking out one of the document’s pages while preserving the rest of the content, layout, and metadata. This operation is useful when you need to trim PDFs, generate custom reports, or comply with document size limits.

## Why use Aspose.Page for .NET?
- **No external dependencies** – pure .NET library.  
- **High fidelity** – retains vector graphics and layout precision.  
- **Cross‑platform** – works on Windows, Linux, and macOS.  
- **Simple API** – a single method call (`RemovePageAt`) handles the heavy lifting.

## Prerequisites

Before diving into the code, make sure you have:

- **Aspose.Page for .NET** – download it from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).  
- A **.NET development environment** (Visual Studio, VS Code, or any IDE you prefer).  
- A **sample XPS document** (e.g., `Sample.xps`) placed in a folder you can reference from your project.

## Import Namespaces

Add the required namespaces at the top of your C# file so the compiler knows where to find the XPS classes.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set the Document Directory

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Pro tip:** Use `Path.Combine` for cross‑platform path building.

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// ExEnd:4
```

This line loads the existing XPS file (`Sample.xps`) into an `XpsDocument` object, ready for manipulation.

## Step 3: Delete Page at Index

```csharp
// ExStart:5
// Remove the first page (at index 1).
doc.RemovePageAt(1);
// ExEnd:5
```

The `RemovePageAt` method **deletes the page at the specified index**. Remember that indexing starts at 0, so `1` removes the second page. Adjust the index to target the page you need to delete.

## Step 4: Save the Resultant XPS Document

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "Sample_out.xps");
// ExEnd:6
```

After removal, the document is saved as `Sample_out.xps`. You can now open this file to verify that the unwanted page is gone.

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **Index out of range** | Trying to delete a page that doesn’t exist. | Verify the page count with `doc.Pages.Count` before calling `RemovePageAt`. |
| **File locked** | The XPS file is open in another program. | Close any viewers or ensure the file is not in use before running the code. |
| **License not applied** | Using the library without a valid license in production. | Apply a temporary or permanent license using `License license = new License(); license.SetLicense("Aspose.Page.lic");` |

## Frequently Asked Questions

**Q1: Can I remove multiple pages at once using Aspose.Page for .NET?**  
A1: Yes, simply call `RemovePageAt` repeatedly or loop through a list of indexes (remember to remove from highest to lowest index to keep the remaining indexes valid).

**Q2: Is Aspose.Page compatible with the latest .NET framework?**  
A2: Aspose.Page is regularly updated to support the newest .NET releases, including .NET 6 and .NET 7.

**Q3: Can I use Aspose.Page for commercial applications?**  
A3: Absolutely. For licensing details, visit the [Aspose.Purchase](https://purchase.aspose.com/buy) page.

**Q4: Where can I find additional support and discussions on Aspose.Page?**  
A4: Join the community at the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for tips, examples, and troubleshooting help.

**Q5: Do I need a temporary license for testing Aspose.Page?**  
A5: Yes, you can obtain a [temporary license](https://purchase.aspose.com/temporary-license/) to evaluate the library before purchasing.

**Q6: How do I preserve document metadata after removing a page?**  
A6: The `RemovePageAt` method retains the original metadata automatically. If you need to modify it, use the `doc.DocumentProperties` collection.

## Conclusion

You’ve now learned how to **remove page xps** documents and **delete page at index** using Aspose.Page for .NET. This concise approach lets you integrate page‑removal logic directly into your .NET applications, giving you full control over XPS document content.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}