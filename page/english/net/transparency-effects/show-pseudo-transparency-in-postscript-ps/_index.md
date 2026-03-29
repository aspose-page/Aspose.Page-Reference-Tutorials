---
title: Linear Gradient Brush C# for Pseudo-Transparency in PS
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
description: Learn how to use a linear gradient brush C# to create pseudo‑transparency in PostScript with Aspose.Page for .NET.
weight: 13
url: /net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
date: 2026-03-29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linear Gradient Brush C# for Pseudo-Transparency in PostScript (PS)

## Introduction

If you need to add a subtle see‑through effect to your PostScript (PS) files, the **linear gradient brush C#** is the perfect tool. Aspose.Page for .NET makes it easy to paint rectangles with both opaque and translucent gradient fills, giving your documents a modern, layered look. In this tutorial we’ll walk through the exact steps required to create pseudo‑transparency using a linear gradient brush in C#.

## Quick Answers
- **What library provides the linear gradient brush?** Aspose.Page for .NET
- **Which graphics class creates the gradient?** `LinearGradientBrush`
- **Can I control opacity per color?** Yes, using `Color.FromArgb(alpha, …)`
- **Do I need a license for production?** A valid Aspose.Page license is required
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## What is a linear gradient brush C#?

A `LinearGradientBrush` is a GDI+ object that paints a smooth transition between two colors along a straight line. When you specify the alpha channel (0‑255) for each color, you can create translucent gradients—exactly what we need for pseudo‑transparency in PostScript.

## Why use a linear gradient brush C# for pseudo‑transparency?

- **Fine‑grained opacity control:** Adjust each color’s alpha to achieve the desired see‑through level.  
- **Device‑independent rendering:** The brush works the same on screen, PDF, EPS, and PS outputs.  
- **Simple API:** A few lines of C# code produce professional‑grade visual effects.

## Prerequisites

Before diving into the code, make sure you have:

- Aspose.Page for .NET installed. You can download it from the [Aspose.Page documentation](https://reference.aspose.com/page/net/).
- A writable folder where the generated PostScript document will be saved.

Now that you have the necessary tools, let’s start building the pseudo‑transparent rectangles.

## Import Namespaces

Before we begin, import the namespaces that contain the classes we’ll use:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Create the output stream for the PostScript document

We start by creating a file stream that will hold the resulting PS file, then initialise the `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 2: Create a rectangle with an **opaque** gradient fill

Here we build a `LinearGradientBrush` whose colors are fully opaque (alpha = 255). This rectangle will serve as the background layer.

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Step 3: Create a rectangle with a **translucent** gradient fill

Now we use a **linear gradient brush C#** where the alpha values are less than 255 (e.g., 150 and 50). This makes the rectangle partially see‑through, achieving the pseudo‑transparency effect.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Step 4: Close the page and save the document

Finally we finish the page and write the PS file to disk.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

By following these four steps you can seamlessly blend opaque and translucent rectangles, creating a convincing pseudo‑transparent effect in any PostScript output.

## Common Issues and Solutions

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| Colors appear fully opaque | Alpha value set to 255 by mistake | Use `Color.FromArgb(alpha, …)` with `alpha` < 255 |
| Gradient is stretched incorrectly | Incorrect transformation matrix | Verify the matrix parameters match the rectangle dimensions |
| Output file is empty | Stream not closed or `Save()` not called | Ensure `document.ClosePage()` and `document.Save()` are executed inside the `using` block |

## Frequently Asked Questions

**Q: Is Aspose.Page compatible with all versions of .NET?**  
A: Aspose.Page for .NET is compatible with various versions of the .NET framework, ensuring flexibility and ease of integration.

**Q: Can I apply pseudo‑transparency to other shapes besides rectangles?**  
A: Yes, the same principles can be applied to any shape by adjusting the `GraphicsPath` accordingly.

**Q: Where can I find additional examples and documentation?**  
A: Explore the [Aspose.Page documentation](https://reference.aspose.com/page/net/) for comprehensive examples and detailed API references.

**Q: Is there a free trial available for Aspose.Page?**  
A: Yes, you can access a free trial of Aspose.Page from [this link](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page?**  
A: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain a temporary license for Aspose.Page.

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}