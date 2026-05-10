---
title: "How to Add Gradient – Diagonal Gradient in PostScript (PS) with Aspose.Page .NET"
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
description: "Learn how to add gradient to PostScript files, save PostScript file with A4 page size, and fill rectangle gradient using Aspose.Page for .NET."
weight: 10
url: /net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
date: 2026-02-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Add Gradient: Diagonal Gradient to PostScript (PS) with Aspose.Page .NET

## Introduction

Adding a diagonal gradient to a PostScript (PS) document can dramatically improve visual appeal, especially when you need to **how to add gradient** effects in technical reports, brochures, or graphics‑intensive applications. In this tutorial you’ll see exactly how to add gradient to a PostScript file, set an A4 page size, and fill a rectangle with a smooth color transition using Aspose.Page for .NET.

## Quick Answers
- **What library is required?** Aspose.Page for .NET  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Can I change the gradient direction?** Yes – rotate the brush transform as shown in the code  
- **How do I save the result?** Use `PsDocument.Save()` which writes a PostScript file to disk  
- **Is a license needed for production?** Yes, a commercial license unlocks full functionality  

## What is a diagonal gradient in PostScript?

A diagonal gradient is a linear color transition that runs at an angle (typically 45°) across a shape. In PostScript, this is achieved by applying a `LinearGradientBrush` with a custom transformation matrix that rotates, scales, and translates the gradient to match the desired rectangle.

## Why use Aspose.Page for gradient fills?

Aspose.Page abstracts the low‑level PostScript commands, letting you work with familiar .NET graphics objects. You can create complex fills, set page dimensions, and export directly to a **save PostScript file** without dealing with raw PS syntax.

## Prerequisites

- **Aspose.Page for .NET Library** – download it [here](https://releases.aspose.com/page/net/).  
- **Document Directory** – a folder where the generated `*.ps` file will be written.

Now that we have the basics covered, let’s walk through the implementation step by step.

## Import Namespaces

First, import the namespaces that give you access to the EPS device, drawing utilities, and I/O classes.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Create Output Stream for PostScript Document (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Step 2: Set A4 Page Size (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Step 3: Create a New 1‑Paged PS Document

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Define Rectangle Parameters

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Step 5: Create Graphics Path

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Step 6: Create Linear Gradient Brush (Fill Rectangle Gradient)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Step 7: Create Transform for Brush

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Step 8: Apply Transformations to Brush (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Step 9: Set Transform to Brush

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Step 10: Set Paint and Fill the Rectangle

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Step 11: Close the Current Page

```csharp
	//Close current page
	document.ClosePage();
```

## Step 12: Save the Document (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## How to Save PostScript File

The `PsDocument.Save()` call writes the fully‑formed PostScript content to the stream you opened in **Step 1**. After the `using` block completes, the file `DiagonaGradient_outPS.ps` will be available in the directory you specified.

## Common Use Cases

- **Technical documentation** that needs a subtle background shading.  
- **Marketing brochures** where a diagonal gradient adds a modern look.  
- **Automated report generators** that produce printable PS files on the fly.

## Troubleshooting & Tips

- **Incorrect colors** – double‑check the ARGB values passed to `LinearGradientBrush`.  
- **Gradient not visible** – ensure the transform matrix correctly rotates and scales; the `Rotate(-45)` call sets the diagonal angle.  
- **File not created** – verify that `dataDir` points to an existing folder and that the application has write permissions.

## Frequently Asked Questions

**Q: Is Aspose.Page compatible with all .NET frameworks?**  
A: Aspose.Page supports a wide range of .NET versions, from .NET Framework 4.5+ to .NET 6+, ensuring broad compatibility.

**Q: Can I customize the gradient colors in Aspose.Page?**  
A: Yes, you can specify any ARGB colors when constructing `LinearGradientBrush`, giving you full control over start and end hues.

**Q: Is there a trial version available for Aspose.Page?**  
A: Yes, you can explore Aspose.Page's features by downloading the trial version [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page?**  
A: Obtain a temporary license for Aspose.Page [here](https://purchase.aspose.com/temporary-license/) to unlock additional capabilities during evaluation.

**Q: Where can I find community support for Aspose.Page?**  
A: Engage with the Aspose.Page community on the [forum](https://forum.aspose.com/c/page/39) for assistance and discussions.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Page for .NET (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}