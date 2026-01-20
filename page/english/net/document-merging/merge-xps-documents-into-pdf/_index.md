---
title: Add Page Numbers PDF – Merge XPS to PDF using Aspose.Page
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
description: Effortlessly add page numbers PDF while merging XPS documents into high‑quality PDFs using Aspose.Page for .NET. Follow our step‑by‑step guide to convert XPS to PDF.
weight: 11
date: 2026-01-20
url: /net/document-merging/merge-xps-documents-into-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Page Numbers PDF – Merge XPS to PDF using Aspose.Page

## Introduction

If you need to **add page numbers PDF** while merging XPS files, Aspose.Page for .NET makes the process painless. In this tutorial we’ll walk through a complete, production‑ready example that converts an XPS document to a high‑quality PDF, lets you control image compression, and automatically inserts page numbers into the final PDF. By the end you’ll have a reusable snippet you can drop into any C# project.

## Quick Answers
- **Can I add page numbers when merging XPS to PDF?** Yes – the `PdfSaveOptions.PageNumbers` property does exactly that.  
- **Which library handles the conversion?** Aspose.Page for .NET.  
- **Do I need a license for production use?** A valid Aspose.Page license is required; a temporary license is available for testing.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **Is high‑quality image output possible?** Absolutely – set `JpegQualityLevel` to 100 and choose `PdfImageCompression.Jpeg`.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for .NET: Ensure you have the Aspose.Page library installed. You can download it from [here](https://releases.aspose.com/page/net/).

- Document Files: Have the XPS document (`input.xps`) ready in your specified directory.

## Import Namespaces

In your .NET project, include the necessary namespaces for working with Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

This step ensures that you have access to the classes and methods required for the document conversion.

## How to add page numbers PDF when merging XPS documents

The `PdfSaveOptions.PageNumbers` collection lets you specify exactly which pages (or page ranges) should appear in the output PDF. By populating it with the page numbers you want, Aspose.Page automatically inserts the correct numbering.

### Step 1: Initialize Streams

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

This step involves setting up the input and output streams for the XPS and PDF files. Ensure the correct paths and file names are used.

### Step 2: Load XPS Document

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Here, we load the XPS document into the `XpsDocument` object, preparing it for further processing.

### Step 3: Initialize Save Options (merge xps to pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Customize the `PdfSaveOptions` object based on your preferences, specifying parameters such as image compression, text compression, and the **page numbers** you want to appear in the final PDF. Setting `JpegQualityLevel` to 100 ensures **high quality PDF images**.

### Step 4: Create Rendering Device

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

The `PdfDevice` is the tool responsible for rendering the XPS document into PDF format.

### Step 5: Save the Document (c# xps to pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Finally, save the document using the rendering device and the specified options. The output PDF will contain the selected pages with automatically added page numbers.

## Why use Aspose.Page for this conversion?

- **Reliability** – Handles complex XPS features without loss of fidelity.  
- **Performance** – Stream‑based processing avoids loading entire files into memory.  
- **Flexibility** – Fine‑grained control over image quality, compression, and page numbering.  
- **Cross‑platform** – Works on Windows, Linux, and macOS with .NET Core.

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **Output PDF is blank** | Verify that the XPS file path is correct and that the file is not corrupted. |
| **Page numbers not appearing** | Ensure `PageNumbers` is set to the correct zero‑based page indices (e.g., `new int[] {1,2,6}`). |
| **Low‑quality images** | Increase `JpegQualityLevel` and choose `PdfImageCompression.Jpeg`. |
| **Large XPS files cause memory pressure** | Process the XPS in smaller chunks or increase the application’s memory limit. |

## Frequently Asked Questions

### Q1: Can I merge multiple XPS files into a single PDF?

A1: Yes, you can. Simply adjust the `PageNumbers` parameter in the `PdfSaveOptions` to include the desired pages from different XPS files, or load each XPS sequentially and call `document.Save` on the same `PdfDevice`.

### Q2: Is a temporary license available for Aspose.Page for .NET?

A2: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing purposes.

### Q3: Are there any limitations on file size when using Aspose.Page for document conversion?

A3: Aspose.Page for .NET does not impose strict limitations on file size, but optimal performance is achieved with reasonably sized files. For very large XPS documents, consider processing them in streams to reduce memory consumption.

### Q4: Can I customize the output PDF further, such as adding watermarks or annotations?

A4: Yes, Aspose.Page for .NET provides extensive features for PDF manipulation. After conversion, you can use the Aspose.PDF library to add watermarks, annotations, or other enhancements.

### Q5: Does Aspose.Page for .NET support cross‑platform development?

A5: Yes, Aspose.Page for .NET is designed to work seamlessly across various platforms, including Windows, Linux, and macOS, when used with .NET Core or .NET 5/6.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}