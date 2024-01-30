---
title: Add Horizontal Gradient to XPS with Aspose.Page for .NET
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
description: Learn how to add stunning horizontal gradients to your XPS documents using Aspose.Page for .NET. Elevate visual appeal effortlessly.
type: docs
weight: 13
url: /net/gradient-fills/add-horizontal-gradient-to-xps/
---
## Introduction

In this tutorial, we will explore how to enhance XPS documents by adding a horizontal gradient using Aspose.Page for .NET. Aspose.Page for .NET is a powerful library that provides seamless handling of XPS (XML Paper Specification) documents in .NET applications. Adding gradients can bring visual appeal to your documents, and this guide will walk you through the process step by step.

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

## Conclusion

Enhancing your XPS documents with gradients not only improves their visual appeal but also provides a more engaging user experience. Aspose.Page for .NET simplifies this process, allowing you to achieve professional results effortlessly.

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
