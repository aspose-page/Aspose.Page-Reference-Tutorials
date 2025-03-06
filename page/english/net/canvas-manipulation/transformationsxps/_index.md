---
title: Transformations XPS with Aspose.Page for .NET
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
description: Transform XPS documents effortlessly with Aspose.Page for .NET. Follow our step-by-step guide for seamless transformations.
weight: 13
url: /net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Transformations XPS with Aspose.Page for .NET

## Introduction

Welcome to the world of Aspose.Page for .NET, a powerful library that enables you to perform various transformations on XPS documents effortlessly. In this tutorial, we'll dive into the process of transforming XPS documents using Aspose.Page for .NET. Whether you're a seasoned developer or just starting, this guide will walk you through each step, ensuring you grasp the concepts easily.

## Prerequisites

Before we begin, make sure you have the following in place:

- Aspose.Page for .NET Library: Download and install the library from [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

- Development Environment: Set up a compatible development environment, such as Visual Studio or any other .NET development tool.

- Your Document Directory: Replace the placeholder in the code with the actual path to your document directory.

Now, let's jump into the tutorial!

## Import Namespaces

Firstly, ensure you import the necessary namespaces to make the Aspose.Page for .NET functionalities available in your code. Add the following namespaces at the beginning of your script:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Create a New XPS Document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Step 2: Create a Main Canvas

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Step 3: Create a Rectangle Path Geometry

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Step 4: Add a Fill for Rectangles

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Step 5: Add a New Canvas Without Transformations

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Step 6: Add a New Canvas with Translate Transformation

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Step 7: Add a New Canvas with Double Scale Transformation

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Step 8: Add a New Canvas with Rotation Around a Point Transformation

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Step 9: Save Resultant XPS Document

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

## Conclusion

Congratulations! You've successfully transformed an XPS document using Aspose.Page for .NET. This guide covered essential steps, from setting up prerequisites to performing various transformations. Experiment with these techniques and unlock the full potential of Aspose.Page for .NET in your projects.

## FAQ's

### Q1: Is Aspose.Page for .NET compatible with all .NET development environments?

A1: Yes, Aspose.Page for .NET is designed to work seamlessly with various .NET development environments, including Visual Studio.

### Q2: Where can I find additional examples and documentation for Aspose.Page for .NET?

A2: Visit the [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) for comprehensive documentation and examples.

### Q3: Can I try Aspose.Page for .NET before purchasing?

A3: Yes, you can explore a free trial version by visiting [Aspose.Page Free Trial](https://releases.aspose.com/).

### Q4: How can I obtain a temporary license for Aspose.Page for .NET?

A4: Get a temporary license by visiting [Temporary License](https://purchase.aspose.com/temporary-license/).

### Q5: Where can I purchase Aspose.Page for .NET?

A5: Purchase Aspose.Page for .NET at [Aspose.Page Buy](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
