---
title: Add Rectangle to XPS Document with Aspose.Page for .NET
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
description: Enhance document creation with Aspose.Page for .NET. Learn how to add rectangles to XPS documents in this step-by-step tutorial.
weight: 13
url: /net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Rectangle to XPS Document with Aspose.Page for .NET

## Introduction

Aspose.Page for .NET is a powerful library that provides a variety of features for working with XPS (XML Paper Specification) documents in .NET applications. In this tutorial, we will focus on adding a rectangle to an XPS document using Aspose.Page for .NET. Follow this step-by-step guide to enhance your document creation process.

## Prerequisites

Before you begin with this tutorial, make sure you have the following prerequisites in place:

1. Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library installed in your development environment. You can download it [here](https://releases.aspose.com/page/net/).

2. Document Directory: Set up a directory where you want to store your XPS documents.

## Import Namespaces

In your .NET application, include the necessary namespaces to use Aspose.Page functionalities.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set the Document Directory

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

## Step 3: Add a Rectangle

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

## Step 4: Save the Document

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Congratulations! You have successfully added a rectangle to an XPS document using Aspose.Page for .NET.

## Conclusion

Aspose.Page for .NET simplifies document manipulation tasks, allowing developers to create and modify XPS documents effortlessly. This step-by-step guide demonstrates how to add a rectangle to your XPS document, providing a solid foundation for further exploration.

## FAQ's

### Q1: Is Aspose.Page compatible with all .NET applications?

A1: Yes, Aspose.Page is designed to work seamlessly with all .NET applications.

### Q2: Where can I find the documentation for Aspose.Page for .NET?

A2: The documentation is available [here](https://reference.aspose.com/page/net/).

### Q3: Can I try Aspose.Page for .NET for free before purchasing?

A3: Yes, you can get a free trial [here](https://releases.aspose.com/).

### Q4: How can I obtain a temporary license for Aspose.Page for .NET?

A4: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain a temporary license.

### Q5: Where can I seek community support or ask questions related to Aspose.Page for .NET?

A5: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
