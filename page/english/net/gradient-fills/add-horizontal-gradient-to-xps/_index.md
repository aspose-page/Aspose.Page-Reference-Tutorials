---
title: "Create XPS Gradient: Horizontal Fill with Aspose.Page for .NET"
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
description: "Learn how to create XPS gradient with a horizontal fill using Aspose.Page for .NET. Elevate visual appeal effortlessly in your documents."
weight: 13
url: /net/gradient-fills/add-horizontal-gradient-to-xps/
date: 2026-02-25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS Gradient – Add Horizontal Gradient to XPS with Aspose.Page for .NET

## Introduction

In this tutorial you’ll **create XPS gradient** fills that run horizontally across your pages. Adding a horizontal gradient can instantly make an XPS document look more polished and engaging, especially for reports, brochures, or any visual‑rich output. We’ll walk through the complete process using Aspose.Page for .NET, from setting up the environment to saving the final XPS file.

## Quick Answers
- **What does this tutorial cover?** Adding a horizontal gradient to an XPS document with Aspose.Page for .NET.  
- **Which library is required?** Aspose.Page for .NET (any recent version).  
- **Do I need a license?** A trial works for development; a commercial license is required for production.  
- **How long does implementation take?** About 5–10 minutes for a basic gradient.  
- **Can I change the gradient direction?** Yes – modify the start/end points of the `LinearGradientBrush`.

## How to create XPS gradient with Aspose.Page for .NET

Below you’ll find a step‑by‑step guide that explains **why** each line of code exists, not just **what** it does. Feel free to follow along in Visual Studio or your preferred .NET editor.

## Prerequisites

Before we begin, make sure you have the following prerequisites in place:

1. Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library installed in your development environment. You can download it from the [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

2. Development Environment: Set up a suitable development environment, including a code editor like Visual Studio.

## Import Namespaces

Start by importing the necessary namespaces into your project. These namespaces are essential for working with Aspose.Page for .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Now, let's break down the provided example into multiple steps.

## Step 1: Set the Document Directory Path

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Initialize Gradient Stops

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Step 4: Create a New Path

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Now, you have successfully added a horizontal gradient to your XPS document using Aspose.Page for .NET.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| Gradient appears solid color | Gradient stops not added correctly | Ensure `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` is executed after setting the brush. |
| Saved file is empty | `dataDir` points to a non‑existent folder | Verify the folder exists or use an absolute path. |
| Compilation error on `PointF` | Missing `System.Drawing` reference | Add a reference to `System.Drawing.Common` (for .NET Core/5+). |

## FAQ's

### Q1: Where can I find the Aspose.Page for .NET documentation?

A1: You can find the documentation [here](https://reference.aspose.com/page/net/).

### Q2: How do I download Aspose.Page for .NET?

A2: You can download the library from the [Aspose.Page for .NET download page](https://releases.aspose.com/page/net/).

### Q3: Where can I purchase Aspose.Page for .NET?

A3: You can purchase Aspose.Page for .NET from the [purchase page](https://purchase.aspose.com/buy).

### Q4: Is there a free trial available?

A4: Yes, you can get a free trial from [here](https://releases.aspose.com/).

### Q5: How do I get a temporary license for Aspose.Page for .NET?

A5: You can obtain a temporary license from [this link](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: Can I use this gradient technique with XPS documents that already contain images?**  
A: Absolutely. The gradient is applied to a path layer, so existing images remain untouched.

**Q: Is it possible to create a vertical gradient instead?**  
A: Yes. Change the `LinearGradientBrush` start and end points to have different Y‑coordinates while keeping X constant.

**Q: Does Aspose.Page support .NET Core?**  
A: The library is fully compatible with .NET Core, .NET 5, and later versions.

**Q: How can I reuse the same gradient across multiple pages?**  
A: Create the `XpsLinearGradientBrush` once, store it in a variable, and assign it to paths on each page.

## Conclusion

Enhancing your XPS documents with gradients not only improves visual appeal but also delivers a more engaging user experience. With Aspose.Page for .NET, you can **create XPS gradient** fills quickly and reliably, giving your reports, brochures, or e‑books a professional polish.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

---