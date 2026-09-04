---
title: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with Aspose.Page
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
description: Learn how to create XPS document .NET and add image‑filled glyphs or foreign images using Aspose.Page for .NET in a few easy steps.
date: 2026-06-30
weight: 11
url: /net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
keywords:
  - create xps document .net
  - image filled glyph
  - foreign image
schemas:
- type: TechArticle
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  dateModified: '2026-06-30'
  author: Aspose
- type: FAQPage
  questions:
  - question: What does Aspose.Page support?
    answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
  - question: How many lines of code to add an image‑filled glyph?
    answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
  - question: Do I need a license for production?
    answer: Yes, a commercial license removes evaluation watermarks.
  - question: Which .NET versions are compatible?
    answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
  - question: Can I reuse fonts from another XPS?
    answer: Absolutely – you can import the font collection from the first document
      into the second.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with Aspose.Page

## Introduction

In .NET development, **create XPS document .NET** tasks are common when you need high‑quality, resolution‑independent graphics. Aspose.Page for .NET makes this straightforward and lets you enrich XPS files with image‑filled glyphs or pull in images from another XPS document. By the end of this tutorial you’ll know how to create two XPS documents, fill glyphs with images, and reuse those images across documents—perfect for generating invoices, certificates, or any visual‑rich output.

## Quick Answers
- **What does Aspose.Page support?** Over 25 image formats and the ability to process XPS files up to 500 MB without full memory loading.  
- **How many lines of code to add an image‑filled glyph?** Just two lines: create an `ImageBrush` and assign it to a `Glyph`.  
- **Do I need a license for production?** Yes, a commercial license removes evaluation watermarks.  
- **Which .NET versions are compatible?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I reuse fonts from another XPS?** Absolutely – you can import the font collection from the first document into the second.

## How do you create an XPS document using Aspose.Page .NET?

Load the Aspose.Page library, instantiate an `XpsDocument`, add a page, and call `Save` – that’s the complete workflow in three concise statements. The API automatically handles page size, DPI, and resource management, so you don’t need to manage low‑level XPS structures yourself. This approach scales from a single‑page flyer to multi‑hundred‑page catalogs.

## Prerequisites

Before you start, ensure you have:

- **Aspose.Page for .NET** – download it from [here](https://releases.aspose.com/page/net/).  
- **A .NET IDE** – Visual Studio, Rider, or VS Code with the C# extension.  
- **A folder for your documents** – we’ll refer to it as **Your Document Directory** in the code snippets.

## Import Namespaces

The `Aspose.Page.XPS` namespace provides core XPS document classes, while `Aspose.Page.XPS.XpsModel` contains model elements such as glyphs and brushes. Import them at the top of your file:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## What is an Image‑Filled Glyph?

A glyph is a vector shape that can be rendered with a solid color, gradient, or an image brush. When you apply an `ImageBrush`, the glyph’s interior is painted with the supplied image, enabling complex visual effects without rasterizing the whole page.

## Step 1: Create the First XPS Document

`XpsDocument` represents an XPS package and is the entry point for creating and saving XPS files. Begin by creating the first XPS document that will host the image‑filled glyphs.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Step 2: Add Glyphs to the First Document

`XpsGlyphs` defines a collection of glyphs (text characters) that can be placed on a page. Add glyphs to the first document, specifying the font, size, style, and position.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Step 3: Fill Glyphs with an Image Brush

`ImageBrush` paints an area with an image, allowing patterns or pictures to fill shapes. Fill the glyphs with an image brush, utilizing an image from your data directory.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Step 4: Create the Second XPS Document

`XpsDocument` is used to create a new XPS file that can contain pages, resources, and content. Now, create the second XPS document that will incorporate glyphs from the first document.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Step 5: Add Glyphs with the Font from the First Document

`Font` represents a typeface used to render text in an XPS document. Add glyphs to the second document, using the font extracted from the first document. By sharing the font collection, you keep the file size low and ensure visual consistency.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Step 6: Create an Image Brush from the Fill of the First Document

`ImageBrush` can be created from an existing fill to reuse the same image across documents. Create an image brush from the fill of the first document and use it to fill the glyphs in the second document. This “foreign image” technique lets you reuse artwork without duplicating the source file.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Step 7: Save the Documents

`Save` writes the XPS package to a file, embedding all resources. Save both the first and second XPS documents to the output folder. The `Save` method writes the XPS package, embedding all resources and preserving the image‑filled glyphs.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Common Issues and Solutions

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Image not appearing inside glyph** | The `ImageBrush` was created with an incorrect URI or the image size exceeds the glyph bounds. | Verify the image path, and optionally set `ImageBrush.Stretch = Stretch.Uniform`. |
| **Fonts missing in the second document** | Font resources were not exported from the first XPS. | Use `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` before adding glyphs. |
| **Performance slowdown on large files** | Loading large images into memory for each glyph. | Reuse a single `ImageBrush` instance for all glyphs, or down‑sample the image before use. |

## Frequently Asked Questions

### Q1: Can I use different image formats for filling glyphs?

A1: Yes, Aspose.Page supports PNG, JPEG, BMP, GIF, TIFF, and more—over 25 formats in total.

### Q2: How can I customize the appearance of glyphs further?

A2: Explore properties like `Glyph.Stroke`, `Glyph.FillOpacity`, and `Glyph.Transform` to adjust outlines, transparency, and rotation.

### Q3: Is Aspose.Page suitable for handling large document sets?

A3: Absolutely. The library processes multi‑hundred‑page XPS files using streaming, keeping memory usage under 100 MB even for 500‑page documents.

### Q4: Can I apply different styles to individual glyphs?

A4: Yes, each `Glyph` instance has its own `Fill`, `Stroke`, and `Transform` properties, allowing per‑glyph styling.

### Q5: What are the benefits of using Aspose.Page over other XPS tools?

A5: Aspose.Page supports 25+ image formats, processes files up to 500 MB without full memory load, and provides a 100 % .NET‑native API—eliminating the need for COM interop or external tools.

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Create XPS Document – Aspose.Page for .NET](/page/net/document-creation/)
- [Add Image to XPS Document with Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [Add Glyph Clone and Change Color with Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}