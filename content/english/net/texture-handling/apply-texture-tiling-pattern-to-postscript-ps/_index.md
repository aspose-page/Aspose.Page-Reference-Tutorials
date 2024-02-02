---
title: Apply Texture Tiling Pattern to PostScript (PS) with Aspose.Page
linktitle: Apply Texture Tiling Pattern to PostScript (PS)
second_title: Aspose.Page .NET API
description: Enhance your PostScript (PS) documents with texture tiling patterns using Aspose.Page for .NET. Follow our step-by-step guide for a creative touch.
type: docs
weight: 10
url: /net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## Introduction

Welcome to this step-by-step tutorial on how to apply a texture tiling pattern to a PostScript (PS) document using Aspose.Page for .NET. Aspose.Page is a powerful library that allows you to work with various document formats, and in this tutorial, we'll explore how to enhance your PS documents by adding texture tiling patterns.

## Prerequisites

Before we dive into the tutorial, make sure you have the following:

- [Visual Studio](https://visualstudio.microsoft.com/) installed on your machine.
- Basic knowledge of C# programming.
- Download and install the [Aspose.Page for .NET library](https://releases.aspose.com/page/net/).
- An image file for the texture pattern (e.g., "TestTexture.bmp").

## Import Namespaces

In your C# code, ensure you import the necessary namespaces:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Let's break down the provided example into multiple steps to guide you through the process.

## Step 1: Set Up Document Directory

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Make sure to replace "Your Document Directory" with the path where you want to save your PS document.

## Step 2: Create Output Stream for PS Document

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

This step sets up the output stream for the PS document, including defining the document size.

## Step 3: Apply Texture Tiling Pattern

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

This step involves creating a texture brush from an image and setting it as the current paint for the document.

## Step 4: Create Rectangle Path and Fill

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Here, we define a rectangle path and fill it with the previously set texture brush.

## Step 5: Set Stroke and Draw

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

This step involves setting stroke properties and drawing the outlined rectangle.

## Step 6: Fill and Outline Text with Texture Pattern

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Finally, we fill and outline text with the texture pattern, enhancing the visual appeal of your document.

## Step 7: Save and Close Document

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Make sure to close the current page and save the document to apply the changes.

## Conclusion

Congratulations! You've successfully learned how to apply a texture tiling pattern to a PostScript document using Aspose.Page for .NET. Experiment with different images and patterns to customize your PS documents further.

## FAQ's

### Q1: Can I use other image formats for the texture pattern?

A1: Yes, Aspose.Page supports various image formats. Ensure compatibility with the library documentation.

### Q2: Is Aspose.Page compatible with .NET Core?

A2: Yes, Aspose.Page is compatible with both .NET Framework and .NET Core.

### Q3: How can I adjust the size of the textured rectangle?

A3: Modify the dimensions in the `RectangleF` parameters during the path creation.

### Q4: Can I add multiple texture patterns to a single document?

A4: Yes, you can repeat the process with different images and paths.

### Q5: Where can I find additional resources and support?

A5: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) for community support and explore the [documentation](https://reference.aspose.com/page/net/).

