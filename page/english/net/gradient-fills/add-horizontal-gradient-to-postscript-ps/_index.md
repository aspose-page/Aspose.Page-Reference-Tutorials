---
title: Add a Linear Gradient Rectangle to PostScript (PS) with Aspose.Page
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
description: Enhance PostScript documents with a linear gradient rectangle using Aspose.Page for .NET. Follow our step‑by‑step guide to learn gradient fill text and outline text gradient.
weight: 12
url: /net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
date: 2026-02-25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add a Linear Gradient Rectangle to PostScript (PS) with Aspose.Page

## Introduction

Welcome to this comprehensive tutorial on adding a **linear gradient rectangle** to PostScript (PS) documents using Aspose.Page for .NET. Aspose.Page is a powerful library that lets you create, modify, and render documents in a variety of formats, and today we’ll focus on how to bring eye‑catching gradients into your PS files.

### Quick Answers
- **What does the linear gradient rectangle do?** It fills a rectangular area with a smooth color transition from one side to the other.  
- **Which API handles gradient fill text?** `LinearGradientBrush` combined with `SetPaint` and `FillAndStrokeText`.  
- **Can I outline text with a gradient?** Yes—use `SetStroke` with a gradient brush and call `OutlineText`.  
- **Do I need a license for production?** A commercial Aspose.Page license is required for non‑evaluation use.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Prerequisites

Before we dive in, make sure you have:

- Aspose.Page for .NET Library: Ensure the library is referenced in your project. You can download it from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Document Directory: Create a folder on disk where the generated PS file will be saved and replace **“Your Document Directory”** in the code with that path.

## Import Namespaces

To start, import the namespaces that give you access to the drawing and PS‑specific classes:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## What Is a Linear Gradient Rectangle?

A **linear gradient rectangle** is simply a rectangular shape whose interior is painted with a linear gradient—colors transition smoothly along a straight line, typically from left to right (horizontal) or top to bottom (vertical). In Aspose.Page you achieve this by combining a `GraphicsPath` that defines the rectangle with a `LinearGradientBrush` that describes the color transition.

## Why Use Gradient Fill Text and Outline Text Gradient?

- **Visual Appeal:** Gradient‑filled text adds depth and modern styling to reports, invoices, or promotional materials.  
- **Brand Consistency:** Match corporate colors with precise ARGB values.  
- **Versatility:** The same brush can be reused for shape fills, text fills, and outline gradients, reducing code duplication.

## Step 1: Set Up the Document

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 2: Define Gradient Rectangle and Colors

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Step 3: Set Transform for Brush

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Step 4: Set Paint and Fill the Rectangle

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## How to Apply Gradient Fill Text

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Using Outline Text Gradient

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Step 7: Close the Current Page and Save the Document

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Congratulations! You've successfully added a **linear gradient rectangle** to a PostScript document and used the same brush for **gradient fill text** and an **outline text gradient**.

## Common Use Cases & Tips

- **Report Headers:** Fill large text blocks with gradients to highlight section titles.  
- **Brand Logos:** Recreate logo shapes with gradient fill shapes for consistent branding.  
- **Pro Tip:** Re‑use the same `LinearGradientBrush` instance for multiple drawing calls to keep colors perfectly aligned across shapes and text.

## Frequently Asked Questions

### Q1: Can I apply gradients to other shapes besides rectangles?
**A:** Yes, you can apply gradients to any shape defined by a `GraphicsPath`. Simply add circles, polygons, or custom paths before calling `document.Fill(path)`.

### Q2: How can I change the gradient colors?
**A:** Modify the `Color.FromArgb` values when constructing `LinearGradientBrush`. The first color is the start, the second is the end of the gradient.

### Q3: Is Aspose.Page compatible with different document formats?
**A:** Absolutely. Aspose.Page supports XPS, PS, PDF, and several other vector formats. Check the official docs for the full list.

### Q4: Can I use Aspose.Page for commercial projects?
**A:** Yes, commercial licensing is available. See the purchase page for details: [here](https://purchase.aspose.com/buy).

### Q5: Where can I find community support?
**A:** Join the Aspose.Page community forum: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}