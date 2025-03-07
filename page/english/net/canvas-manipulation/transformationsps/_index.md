---
title: Transformations PS with Aspose.Page for .NET
linktitle: Transformations PS
second_title: Aspose.Page .NET API
description: Unlock the potential of Aspose.Page for .NET with this comprehensive guide on PostScript transformations. Create dynamic graphics effortlessly.
weight: 12
url: /net/canvas-manipulation/transformationsps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Transformations PS with Aspose.Page for .NET

## Introduction

Welcome to the world of Aspose.Page for .NET, where you can unleash the power of transformations in PostScript documents. This tutorial will guide you through various transformations such as translation, scaling, rotation, shearing, and complex transformations, allowing you to create visually stunning and dynamic graphics.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library integrated into your project. You can download it from the [download link](https://releases.aspose.com/page/net/).

- Document Directory: Set up a directory for your documents and replace the placeholder in the code with the actual path.

## Import Namespaces

In your .NET project, import the necessary namespaces for working with Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Now, let's break down each example into multiple steps in a step-by-step guide format.


## No Transformations

### Step 1: Create Output Stream

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

This code creates a PostScript document with no transformations, filling a rectangle with an orange color.

## Translation

### Step 1: Save Graphics State

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

This step saves the current graphics state, allowing us to return to it after the transformation.

### Step 2: Translate Graphics State

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Translate the current graphics state by adding a translation component, then set the paint in the current graphics state to a blue color.

### Step 3: Fill Rectangle with Translation Transformation

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

This step fills the second rectangle in the current graphics state, which now includes the translation transformation.

### Step 4: Restore Graphics State

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

After filling the rectangle, restore the graphics state to the previous level.

Continue this step-by-step guide for each transformation type, including Scaling, Rotation, Shearing, and Complex Transformations.

## Conclusion

Congratulations! You've successfully navigated through the transformative capabilities of Aspose.Page for .NET. Now, experiment with different combinations and unleash your creativity in PostScript document transformations.

## FAQ's

### Q1: How can I apply multiple transformations to a single object?

A1: To apply multiple transformations, use the `Transform` method with a custom transformation matrix.

### Q2: Can I preview the transformations before saving the document?

A2: Yes, you can visualize transformations by rendering the document and previewing it in a suitable viewer.

### Q3: Is it possible to apply transformations to specific elements in a document?

A3: Yes, you can isolate transformations to specific graphics elements within a document.

### Q4: Are there any performance considerations when dealing with complex transformations?

A4: Complex transformations may impact performance, so optimize your code for efficiency.

### Q5: How can I get support or seek assistance for Aspose.Page-related queries?

A5: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support and discussions.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
