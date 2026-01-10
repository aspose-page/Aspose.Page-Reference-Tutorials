---
title: Merge XPS Documents with Aspose.Page for .NET
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
description: Learn how to merge XPS documents with Aspose.Page for .NET. This step‑by‑step guide shows page manipulation techniques for efficient results.
weight: 12
url: /net/cross-document-editing/manipulate-pages/
date: 2026-01-10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Merge XPS Documents with Aspose.Page for .NET

## Introduction

In this tutorial you’ll discover how to **merge XPS documents** and manipulate their pages using the Aspose.Page library in a .NET environment. Whether you need to combine multiple reports into a single XPS file or rearrange pages for a polished output, this guide walks you through the process step by step, with clear explanations and ready‑to‑run code.

## Quick Answers
- **What can I do with Aspose.Page?** Merge XPS documents, insert, add, or remove pages, and save the result.  
- **Do I need a license for testing?** A temporary license is available for evaluation.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is Visual Studio required?** No, any IDE that supports C# works, but Visual Studio is recommended.  
- **How long does the merge take?** Typically a few seconds for standard‑size XPS files.

## What is merging XPS documents?
Merging XPS documents means taking pages from two or more existing XPS files and combining them into a single XPS document. This is useful for creating consolidated reports, compiling multipage manuals, or preparing print‑ready packages without converting to another format.

## Why use Aspose.Page for .NET?
Aspose.Page offers a **pure .NET API** that works directly with XPS files—no need for external tools or third‑party components. It gives you fine‑grained control over page order, insertion points, and content preservation, making the merge process reliable and fast.

## Prerequisites

- **Aspose.Page for .NET** – download from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).  
- **Development Environment** – Visual Studio, Rider, or any IDE that supports C#.  
- **Input XPS Files** – three sample files (`input1.xps`, `input2.xps`, `input3.xps`) placed in a known folder.

## Import Namespaces

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

These namespaces give you access to the core XPS document classes, page models, and basic drawing utilities.

## Step 1: Set the Document Directory

```csharp
string dataDir = "Your Document Directory";
```

Replace **Your Document Directory** with the full path where your XPS files are stored, e.g., `C:\\Docs\\XpsFiles\\`.

## Step 2: Create XPS Document Instances

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2`, and `doc3` represent the source documents you want to merge.  
- `doc4` is an empty XPS document that will hold the merged result.

## Step 3: Insert, Add, and Remove Pages

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Here’s what each line does:

1. **InsertPage(1, doc2.Page, false)** – places the first page of `doc2` at position 1 in `doc4`.  
2. **AddPage(doc3.Page, false)** – appends the first page of `doc3` to the end of `doc4`.  
3. **RemovePageAt(2)** – removes the page now at index 2 (useful for eliminating unwanted pages).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – inserts the third page of `doc1` into position 2, completing the merge.

These operations illustrate how you can **merge XPS documents** while reordering or discarding pages as needed.

## Step 4: Save the Merged Document

```csharp
doc4.Save(dataDir + "out.xps");
```

The final merged XPS file (`out.xps`) is written to the same directory. You can now open it in any XPS viewer or further process it with Aspose.Page.

## Common Issues and Solutions
- **File not found** – double‑check the `dataDir` path and ensure the input files exist.  
- **Invalid page index** – page indexes are 1‑based; attempting to insert a non‑existent page throws an exception.  
- **License errors** – use a temporary or full license before deploying to production.

## FAQ's

### Q1: Can I manipulate pages from different XPS documents?

A1: Yes, as demonstrated in the tutorial, you can insert pages from multiple XPS documents into a new document.

### Q2: How can I remove a specific page from a document?

A2: Use the `RemovePageAt` method, specifying the index of the page you want to remove.

### Q3: Is Aspose.Page compatible with Visual Studio?

A3: Yes, Aspose.Page is fully compatible with Visual Studio, making it easy to integrate into your .NET projects.

### Q4: Are there any licensing options available?

A4: Yes, you can explore licensing options and obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q5: Where can I get support or ask questions?

A5: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to get support and engage with the community.

## Frequently Asked Questions

**Q: Can I merge more than three XPS files?**  
A: Absolutely. Create additional `XpsDocument` instances and use `InsertPage` or `AddPage` repeatedly to build a larger merged document.

**Q: Does the merge preserve original formatting and graphics?**  
A: Yes. Aspose.Page copies the page content byte‑for‑byte, so text, images, and vector graphics remain unchanged.

**Q: How do I insert a page at the end without specifying an index?**  
A: Use `AddPage(sourcePage, false)` which appends the page to the document’s end.

**Q: Is it possible to merge XPS documents on a server without a UI?**  
A: The API is fully headless; you can run the same code in ASP.NET, Azure Functions, or any server‑side .NET environment.

**Q: What if my XPS files are password‑protected?**  
A: Aspose.Page currently does not support encrypted XPS files; you must decrypt them before merging.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Page for .NET 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}