---
title: Add Transparent Rectangle using Grid Visual Brush (.NET)
linktitle: Apply Grid Visual Brush
second_title: Aspose.Page .NET API
description: Learn how to add a transparent rectangle and apply a Grid Visual Brush in .NET using Aspose.Page for stunning XPS documents.
weight: 10
url: /net/visual-brushes/apply-grid-visual-brush/
date: 2026-04-03
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Transparent Rectangle using Grid Visual Brush (.NET)

## Introduction

If you’re looking to **add a transparent rectangle** to an XPS document while also applying a stylish Grid Visual Brush, you’ve come to the right place. In this tutorial we’ll walk through the exact steps needed with Aspose.Page for .NET, so you can create visually rich documents that stand out. By the end you’ll have a complete, runnable example that demonstrates both techniques in a single, easy‑to‑follow workflow.

## Quick Answers
- **What does a transparent rectangle do?** It adds a semi‑opaque overlay that lets background content show through.  
- **Which API creates the brush?** `XpsDocument.CreateVisualBrush` builds the Grid Visual Brush.  
- **Do I need a license?** A free trial works for testing; a commercial license is required for production.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **How long does the implementation take?** About 10‑15 minutes for a basic example.

## What is a Transparent Rectangle in XPS?
A transparent rectangle is simply a shape whose fill color includes an alpha component less than 1.0, allowing the underlying graphics to be partially visible. This is perfect for highlighting sections without completely obscuring the background.

## Why use a Grid Visual Brush?
A Grid Visual Brush lets you tile a small vector graphic across a larger area, creating patterns such as grids, hatches, or custom textures. Combining it with a transparent rectangle gives you layered visual effects that are both lightweight and resolution‑independent.

## Prerequisites

Before diving into the code, make sure you have:

- **Aspose.Page for .NET** – you can download it [here](https://releases.aspose.com/page/net/).
- A .NET development environment (Visual Studio, VS Code, or any IDE you prefer).
- A folder where the generated XPS files will be saved.

## Import Namespaces

In your C# file, import the required namespaces:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Now let’s break the solution into clear, numbered steps.

## Step 1: Initialize XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

We start by creating an `XpsDocument` instance, which will hold all subsequent drawing operations.

## Step 2: Create Magenta Grid Geometry

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

This geometry defines the outline of the grid that the visual brush will fill.

## Step 3: Design Magenta Grid VisualBrush

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Here we draw a small magenta tile that will be repeated across the grid.

## Step 4: Apply VisualBrush to Grid

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

The `CreateVisualBrush` call ties the magenta tile to the grid geometry and enables tiling.

## Step 5: Add Grid to Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

We place the tiled grid onto a canvas and apply a translation transform so it appears at the desired location.

## Step 6: Add Transparent Rectangle

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

In this step we **add a transparent rectangle** (the red shape with `Opacity = 0.7f`). Adjust the opacity value to control how see‑through the rectangle is.

## Step 7: Save the Document

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

The XPS file is written to the folder you specified earlier.

## Common Use Cases

- **Report Highlighting:** Overlay a semi‑transparent rectangle to emphasize a chart or table.  
- **Watermark Effects:** Combine a tiled grid with a transparent overlay for subtle branding.  
- **Interactive PDFs/XPS:** Use the pattern as a background for form fields while keeping the UI readable.

## Troubleshooting Tips

- **Opacity Not Visible?** Ensure your viewer supports XPS transparency; some older viewers may ignore the `Opacity` property.  
- **Incorrect Tile Size?** Verify the source rectangle (`new RectangleF(0f, 0f, 10f, 10f)`) matches the dimensions of the vector tile.  
- **File Not Saved?** Double‑check that `dataDir` points to an existing, writable directory.

## Frequently Asked Questions

**Q: Can I use Aspose.Page for .NET in both web and desktop applications?**  
A: Yes, the library works across all .NET application types.

**Q: Is there a trial version available before purchasing?**  
A: Absolutely, you can access the free trial [here](https://releases.aspose.com/).

**Q: Where can I find additional support or community discussions?**  
A: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) for help from the community and Aspose engineers.

**Q: How can I obtain a temporary license for evaluation?**  
A: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: What other documentation is available for Aspose.Page for .NET?**  
A: Explore the comprehensive documentation [here](https://reference.aspose.com/page/net/).

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}