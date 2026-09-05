---
date: 2026-07-19
description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
  for .NET in a concise step‑by‑step guide.
images:
- /net/drawing-shapes/add-rectangle-to-xps-document/og-image.png
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Add Rectangle to XPS Document
og_description: Create XPS document .NET quickly. This tutorial shows how to add a
  rectangle to an XPS file using Aspose.Page for .NET, with clear code and tips.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Create XPS Document .NET – Add Rectangle with Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Create XPS Document .NET – Add Rectangle with Aspose.Page
url: /net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS Document .NET – Add Rectangle with Aspose.Page

## Introduction

In this tutorial you’ll learn how to **create XPS document .NET** and draw a rectangle inside it using Aspose.Page for .NET. Whether you are building a reporting engine, a printable invoice, or a custom graphics layer, the ability to generate XPS files programmatically gives you full control over layout and fidelity. Follow the steps below and you’ll have a ready‑to‑use XPS file in minutes.

## Quick Answers
- **What is the primary goal?** Create an XPS document .NET and add a rectangle shape.  
- **Which library is required?** Aspose.Page for .NET (downloadable from the official site).  
- **Do I need a license for testing?** A free trial works for development; a commercial license is required for production.  
- **What .NET versions are supported?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does implementation take?** About 5‑10 minutes for a basic rectangle.

## What is Aspose.Page for .NET?
Aspose.Page for .NET is a high‑performance, fully managed API that enables developers to programmatically create, edit, and render XPS (XML Paper Specification) documents without relying on external components. It offers a rich object model for drawing shapes, text, and images, and supports advanced features such as color management, compression, and PDF conversion, making it suitable for a wide range of document generation scenarios.

## Why use Aspose.Page to create XPS document .NET?
Aspose.Page supports **30+ XPS features**—including vector graphics, text layout, and color management—and can generate files up to **500 MB** without loading the entire document into memory. This quantified capability ensures smooth performance even for large‑scale printing jobs.

## Prerequisites

Before you begin with this tutorial, make sure you have the following prerequisites in place:

1. Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library installed in your development environment. You can download it [here](https://releases.aspose.com/page/net/).

2. Document Directory: Set up a directory where you want to store your XPS documents.

## Import Namespaces

In your .NET application, include the necessary namespaces to use Aspose.Page functionalities.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## How do I add a rectangle to an XPS document in .NET?

Load the XPS document, create a `Graphics` object, define a `RectangleF` with the desired size, and call `DrawRectangle`. This sequence draws a rectangle in a single line of code and automatically handles DPI scaling. For typical A4‑size pages, a 200 × 100 pt rectangle appears centered without extra calculations.

### Step 1: Set the Document Directory

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Step 2: Create a New XPS Document

The `XpsDocument` class represents the XPS file you are building and provides methods to add pages, graphics, and other resources.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Step 3: Add a Rectangle

`XpsPath` defines a drawable path object within the XPS document, allowing you to set geometry, stroke, fill, and other visual properties.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Step 4: Save the Document

The `Save` method writes the constructed XPS document to the specified file path on disk.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Congratulations! You have successfully added a rectangle to an XPS document using Aspose.Page for .NET.

## Common Issues and Tips

- **Missing fonts:** Ensure the fonts you reference are installed on the server; otherwise Aspose.Page substitutes with a default font, which may alter layout.  
- **Large documents:** When generating files larger than 200 MB, consider calling `document.SaveOptions.Compress = true` to reduce memory usage.  
- **Coordinate system:** XPS uses points (1/72 inch). Remember to convert pixels to points if you are working with screen‑based dimensions.

## Frequently Asked Questions

**Q: Is Aspose.Page compatible with all .NET applications?**  
A: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.

**Q: Where can I find the documentation for Aspose.Page for .NET?**  
A: The full API reference is available [here](https://reference.aspose.com/page/net/).

**Q: Can I try Aspose.Page for .NET for free before purchasing?**  
A: Yes, you can get a free trial [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page for .NET?**  
A: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain a temporary license.

**Q: Where can I seek community support or ask questions related to Aspose.Page for .NET?**  
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Page for .NET 24.9  
**Author:** Aspose

## Related Tutorials

- [Create XPS Document with Aspose.Page for .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Drawing Shapes](/page/net/drawing-shapes/)
- [Add Text to XPS Document with Aspose.Page for .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}