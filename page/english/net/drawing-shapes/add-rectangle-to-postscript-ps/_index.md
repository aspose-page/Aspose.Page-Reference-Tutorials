---
title: Create postscript document .net – Add Rectangle with Aspose.Page
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
description: Learn how to create postscript document .net and add rectangles using Aspose.Page for .NET. Step‑by‑step guide with code samples.
weight: 12
url: /net/drawing-shapes/add-rectangle-to-postscript-ps/
date: 2026-01-18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Rectangle to PostScript (PS) with Aspose.Page for .NET

## Introduction

If you're looking to **create postscript document .net**, Aspose.Page provides a powerful solution for handling PostScript files. In this tutorial, we’ll walk you through adding rectangles to a PostScript document using Aspose.Page for .NET, giving you a solid foundation for richer graphics generation.

## Quick Answers
- **What library do I need?** Aspose.Page for .NET.
- **Can I create a PostScript document from scratch?** Yes – the API lets you build PS files programmatically.
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Do I need a license for development?** A free trial works for testing; a license is required for production.
- **How long does the implementation take?** Typically under 10 minutes for basic shapes.

## What is creating a postscript document .net?
Creating a PostScript document in .NET means programmatically generating a .ps file that describes page content—text, graphics, or shapes—using the Aspose.Page API. This approach is ideal for server‑side graphics generation, automated report creation, or any scenario where you need precise control over the output format.

## Why use Aspose.Page for .NET?
- **Full control over graphics** – draw shapes, set colors, and apply strokes without dealing with low‑level PS syntax.
- **Cross‑platform** – works on Windows, Linux, and macOS runtimes.
- **No external dependencies** – the library handles all PS generation internally.
- **Rich documentation & examples** – get up‑and‑running quickly.

## Prerequisites

- **Aspose.Page for .NET Library** – download and install from [here](https://releases.aspose.com/page/net/).
- **Development Environment** – Visual Studio, VS Code, or any .NET‑compatible IDE.

## Import Namespaces

Before you start coding, import the namespaces that expose the required classes:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Now let’s break the example into clear, numbered steps.

## Step 1: Set up Your Document Directory

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` with the folder where you want the resulting PS file saved.

## Step 2: Create Output Stream for the PostScript Document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

This stream points to **AddRectangle_outPS.ps**. Feel free to rename the file or change the location as needed.

## Step 3: Set Save Options and Create the PS Document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Here we tell Aspose.Page to use an A4 page size and create a single‑page document.

## Step 4: Add a Filled Rectangle

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

We define a rectangle at (250, 100) with width 150 and height 100, set an orange brush, and fill the shape.

## Step 5: Add an Outlined Rectangle

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

A second rectangle is created lower on the page, this time with a red 3‑point stroke.

## Step 6: Close the Page and Save the Document

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Closing the page finalizes the drawing, and `Save()` writes the PS file to disk.

## Common Issues & Tips

- **Incorrect file path** – Ensure `dataDir` ends with a path separator (`\\` or `/`) or use `Path.Combine`.
- **Missing license** – In a production environment, apply your Aspose license before creating the document to avoid evaluation watermarks.
- **Color visibility** – If the rectangle appears blank, verify that the brush or pen colors contrast with the page background.

## Frequently Asked Questions

**Q:** Can I customize the colors of the rectangles?  
**A:** Absolutely. Change the `Color.Orange` or `Color.Red` values in the `SolidBrush` and `Pen` constructors to any `System.Drawing.Color` you prefer.

**Q:** Is Aspose.Page compatible with other document formats?  
**A:** Yes. Besides PostScript, Aspose.Page also supports XPS and EPS generation.

**Q:** How can I add text to the same document?  
**A:** Use the `TextFragment` class to place text at desired coordinates, then call `document.Draw(textFragment)`.

**Q:** Where can I find additional examples and full API reference?  
**A:** Explore the documentation [here](https://reference.aspose.com/page/net/) and join the community at the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Can I try Aspose.Page before buying?  
**A:** Yes, download a free trial [here](https://releases.aspose.com/). For extended evaluation, consider a [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}