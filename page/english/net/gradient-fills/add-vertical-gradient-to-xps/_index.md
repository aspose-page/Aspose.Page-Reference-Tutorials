---
title: Create XPS Document with Vertical Gradient using Aspose.Page
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
description: Learn how to create XPS document and apply linear gradient with Aspose.Page for .NET. Follow our step‑by‑step guide to save XPS file.
weight: 15
url: /net/gradient-fills/add-vertical-gradient-to-xps/
date: 2026-02-25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Vertical Gradient to XPS with Aspose.Page for .NET

## Introduction

In this tutorial you’ll **create XPS document** that features a smooth vertical gradient. Adding gradients is a common way to make XPS files look more professional—perfect for reports, brochures, or any printable graphics. We’ll walk through every step, from setting up the project to saving the final XPS file, so you can quickly apply a linear gradient to any path.

## Quick Answers
- **What does this tutorial cover?** Adding a vertical linear gradient to a path in an XPS document.  
- **Which library is required?** Aspose.Page for .NET.  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **How long does implementation take?** About 10‑15 minutes for a basic example.  
- **Can I save the result as an XPS file?** Yes, the `Save` method writes the file to disk.

## What is a vertical gradient in XPS?

A vertical gradient is a color transition that runs from the top of a shape to the bottom. In XPS, this is achieved with a **linear gradient brush** that defines start and end points, plus a collection of gradient stops that control the color at specific positions.

## Why use Aspose.Page to create XPS document with gradients?

- **Full .NET integration** – works with .NET Framework, .NET Core, and .NET 5/6+.  
- **No external dependencies** – all rendering is handled by the library.  
- **High fidelity** – gradients render exactly as defined, matching the XPS specification.  
- **Easy to maintain** – clear object model for paths, brushes, and colors.

## Prerequisites

- Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library installed in your development environment. You can download it [here](https://releases.aspose.com/page/net/).
- Development Environment: Set up a .NET development environment with your preferred IDE, such as Visual Studio.

Now that we have everything ready, let’s dive into the code.

## Import Namespaces

In your .NET application, include the necessary namespaces to access Aspose.Page classes and methods.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set Up Your Document Directory

Define the folder where the generated XPS file will be saved.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

Instantiate a fresh XPS document that we will later populate with a gradient‑filled path.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Define Gradient Stops

Gradient stops determine the colors and their positions along the gradient line. Here we create five stops to produce a smooth vertical transition.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Step 4: Create a Path with Gradient

We draw a rectangle‑shaped path and apply a **linear gradient brush** that runs vertically from point (10, 110) to point (10, 200). The brush receives the gradient stops defined earlier.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

Finally, write the XPS document to disk. This **save XPS file** step produces `AddVerticalGradient_outXPS.xps` in the folder you specified.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Pro tip:** Verify the output by opening the XPS file in Windows XPS Viewer or any third‑party viewer to ensure the gradient appears as expected.

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Gradient appears as solid color | Gradient stops not added to brush | Ensure `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` is executed. |
| File not found on save | `dataDir` points to a non‑existent folder | Create the directory first or use an absolute path. |
| Colors look different | Color values use ARGB order; verify channel order | Use `CreateColor(alpha, red, green, blue)` correctly. |

## Frequently Asked Questions

**Q: Is Aspose.Page compatible with Visual Studio 2019?**  
A: Yes, Aspose.Page is compatible with Visual Studio 2019. Ensure you have the correct version of the library installed.

**Q: Can I use Aspose.Page for commercial projects?**  
A: Yes, Aspose.Page can be used for commercial projects. Visit [here](https://purchase.aspose.com/buy) to explore licensing options.

**Q: Is there a free trial available?**  
A: Yes, you can get a free trial of Aspose.Page [here](https://releases.aspose.com/).

**Q: Where can I find Aspose.Page documentation?**  
A: The documentation is available [here](https://reference.aspose.com/page/net/).

**Q: How can I get support or ask questions?**  
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

## Conclusion

You now know how to **create XPS document**, **apply linear gradient**, and **save XPS file** using Aspose.Page for .NET. This approach gives you full control over visual styling in XPS outputs, making your printable documents stand out.

---  

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}