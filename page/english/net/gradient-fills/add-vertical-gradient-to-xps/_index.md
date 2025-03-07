---
title: Add Vertical Gradient to XPS with Aspose.Page for .NET
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
description: Learn how to enhance XPS documents with vertical gradients using Aspose.Page for .NET. Follow our step-by-step guide for seamless integration.
weight: 15
url: /net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Vertical Gradient to XPS with Aspose.Page for .NET

## Introduction

Welcome to this step-by-step tutorial on how to add a vertical gradient to an XPS document using Aspose.Page for .NET. Aspose.Page is a powerful API that allows you to work with XPS (XML Paper Specification) files in your .NET applications. In this tutorial, we'll guide you through the process of creating a new XPS document, adding a vertical gradient to a path, and saving the result.

## Prerequisites

Before we dive into the tutorial, make sure you have the following prerequisites:

- Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library installed in your development environment. You can download it [here](https://releases.aspose.com/page/net/).

- Development Environment: Set up a .NET development environment with your preferred IDE, such as Visual Studio.

Now, let's get started with adding a vertical gradient to an XPS document using Aspose.Page for .NET.

## Import Namespaces

In your .NET application, include the necessary namespaces to access Aspose.Page classes and methods.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set Up Your Document Directory

Before you begin, set the path to your document directory where you want to save the resulting XPS document.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

Initialize a new XPS document using the following code:

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Define Gradient Stops

Create a list of gradient stops, specifying the color and position for each stop. In this example, we define a vertical gradient with five stops.

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

Define a path by specifying its geometry and apply a linear gradient brush to it.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

Save the modified XPS document to your specified directory.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

Congratulations! You've successfully added a vertical gradient to an XPS document using Aspose.Page for .NET.

## Conclusion

In this tutorial, we explored how to leverage Aspose.Page for .NET to enhance XPS documents with vertical gradients. Aspose.Page simplifies complex tasks, providing developers with a seamless way to manipulate XPS files in their .NET applications.

## FAQ's

### Q1: Is Aspose.Page compatible with Visual Studio 2019?

A1: Yes, Aspose.Page is compatible with Visual Studio 2019. Ensure you have the correct version of the library installed.

### Q2: Can I use Aspose.Page for commercial projects?

A2: Yes, Aspose.Page can be used for commercial projects. Visit [here](https://purchase.aspose.com/buy) to explore licensing options.

### Q3: Is there a free trial available?

A3: Yes, you can get a free trial of Aspose.Page [here](https://releases.aspose.com/).

### Q4: Where can I find Aspose.Page documentation?

A4: The documentation is available [here](https://reference.aspose.com/page/net/).

### Q5: How can I get support or ask questions?

A5: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
