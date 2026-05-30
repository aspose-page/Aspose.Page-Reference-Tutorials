---
title: How to Use Aspose: Add Circle Ellipse to XPS Document
linktitle: Add Circle Ellipse to XPS Document
second_title: Aspose.Page .NET API
description: Learn how to use Aspose to add a circle ellipse with radial gradients, adjust stroke thickness, and save XPS document using Aspose.Page for .NET.
weight: 11
url: /net/drawing-shapes/add-circle-ellipse-to-xps-document/
date: 2026-01-18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Circle Ellipse to XPS Document with Aspose.Page for .NET

## Introduction

Creating visually appealing XPS documents is a common requirement in many business applications. In this guide you’ll discover **how to use Aspose** to add a circle ellipse with a vibrant radial gradient, adjust stroke thickness, and save XPS document efficiently. Follow the step‑by‑step instructions below to give your XPS files a professional look.

## Quick Answers
- **What library is required?** Aspose.Page for .NET  
- **Which primary task does this tutorial cover?** Adding a circle ellipse with a radial gradient  
- **Can I change the line width?** Yes – you can adjust stroke thickness in the code  
- **How do I persist the changes?** Use `doc.Save(...)` to save the XPS document  
- **What development environment works best?** Visual Studio or any .NET‑compatible IDE  

## How to Use Aspose to Add a Circle Ellipse

Below you’ll find everything you need to get started, from prerequisites to the final save operation.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Installed Aspose.Page for .NET library. You can download it from [here](https://releases.aspose.com/page/net/).
- A development environment, preferably Visual Studio or any other .NET development tool.
- Basic knowledge of C# programming.

## Import Namespaces

To start, include the necessary namespaces in your C# code:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Now, let's break down the example into multiple steps:

## Step 1: Set up the Document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Here, we initialize a new XPS document using Aspose.Page for .NET.

## Step 2: Define Radial Gradient Ellipse

```csharp
// Radial gradient stroked ellipse in the lower left
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

This step involves defining a radial gradient ellipse with various color stops.

## Step 3: Set Radial Gradient Brush

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Here, we set the stroke of the ellipse to a radial gradient brush, providing it with the necessary parameters.

## Step 4: Adjust Stroke Thickness

```csharp
path.StrokeThickness = 12f;
```

You can **adjust stroke thickness** by changing the numeric value. A thicker stroke makes the ellipse stand out more in the final output.

## Step 5: Save the Resultant XPS Document

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExEnd:1
```

The `doc.Save(...)` call **save XPS document** to the location you specify, completing the modification process.

## Conclusion

Congratulations! You've successfully learned **how to use Aspose** to add a circle ellipse with radial gradients, adjust stroke thickness, and **save XPS document** using Aspose.Page for .NET. Feel free to experiment with different colors, gradient stops, and geometry strings to create custom shapes that match your branding.

## Frequently Asked Questions

### Q1: Can I use Aspose.Page for .NET with other document formats?
A1: Aspose.Page for .NET specifically deals with XPS document manipulation. For other formats, consider using related Aspose libraries.

### Q2: Is a temporary license available for testing purposes?
A2: Yes, you can obtain a temporary license for testing by visiting [this link](https://purchase.aspose.com/temporary-license/).

### Q3: Where can I find additional help and discussions?
A3: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support and discussions.

### Q4: Are there any sample documents available for reference?
A4: Explore the [documentation](https://reference.aspose.com/page/net/) for comprehensive examples and guidelines.

### Q5: Can I purchase Aspose.Page for .NET?
A5: Yes, you can purchase the library [here](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}