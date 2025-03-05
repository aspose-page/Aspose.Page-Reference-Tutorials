---
title: Add Horizontal Gradient to PostScript (PS) with Aspose.Page
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
description: Enhance PostScript documents with stunning horizontal gradients using Aspose.Page for .NET. Follow our step-by-step tutorial for seamless implementation.
type: docs
weight: 12
url: /net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
---
## Introduction

Welcome to this comprehensive tutorial on adding horizontal gradients to PostScript (PS) documents using Aspose.Page for .NET. Aspose.Page is a powerful library that facilitates document manipulation in various formats, providing developers with the tools they need to create, modify, and render documents seamlessly.

In this tutorial, we'll focus on enhancing your PostScript documents by incorporating eye-catching horizontal gradients. We'll walk you through each step of the process, ensuring that you gain a solid understanding of the implementation.

## Prerequisites

Before we dive into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library integrated into your development environment. You can download it from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).

- Document Directory: Set up a directory to store your documents, and replace "Your Document Directory" in the provided code with the actual path.

Now, let's explore how to add a horizontal gradient to a PostScript document step by step.

## Import Namespaces

Before you begin, it's essential to import the necessary namespaces to access the functionalities provided by Aspose.Page. Add the following namespaces at the beginning of your code:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

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

## Step 5: Fill Text with Gradient

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Step 6: Set Stroke and Outline Text

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

Congratulations! You've successfully added a horizontal gradient to a PostScript document using Aspose.Page for .NET.

## Conclusion

In this tutorial, we covered the process of enhancing your PostScript documents with horizontal gradients using the Aspose.Page for .NET library. By following the step-by-step guide, you've gained valuable insights into leveraging this powerful tool for document manipulation.

## FAQ's

### Q1: Can I apply gradients to other shapes besides rectangles?

A1: Yes, you can apply gradients to various shapes using Aspose.Page. Modify the `GraphicsPath` creation to suit your specific shape.

### Q2: How can I change the gradient colors?

A2: Adjust the `Color.FromArgb` values in the `LinearGradientBrush` instantiation to achieve the desired gradient colors.

### Q3: Is Aspose.Page compatible with different document formats?

A3: Aspose.Page supports various document formats, including XPS, PS, PDF, and more. Refer to the documentation for a comprehensive list.

### Q4: Can I use Aspose.Page for commercial projects?

A4: Yes, Aspose.Page comes with commercial licensing options. Visit [here](https://purchase.aspose.com/buy) for details.

### Q5: Is there a community forum for Aspose.Page users?

A5: Yes, join the Aspose.Page community at [Aspose.Page Forum](https://forum.aspose.com/c/page/39) to connect with other users and seek assistance.
