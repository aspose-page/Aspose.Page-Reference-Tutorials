---
title: Add Tiled Image to XPS Document with Aspose.Page for .NET
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
description: Explore adding tiled images to XPS documents effortlessly with Aspose.Page for .NET. Enhance visual appeal and create stunning documents.
type: docs
weight: 12
url: /net/image-management/add-tiled-image-to-xps-document/
---
## Introduction

Are you looking to enhance your XPS documents by adding visually appealing tiled images? Aspose.Page for .NET empowers developers to achieve this seamlessly. In this step-by-step guide, we'll walk you through the process of adding a tiled image to an XPS document using Aspose.Page for .NET.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for .NET: Ensure that you have the Aspose.Page library installed. You can find detailed documentation and download the library [here](https://reference.aspose.com/page/net/).
- Development Environment: Set up your preferred .NET development environment, such as Visual Studio.

## Import Namespaces

To begin, import the necessary namespaces into your project. This ensures that you have access to the classes and methods required for working with Aspose.Page. Add the following namespaces at the beginning of your code:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Now, let's break down the example into multiple steps.

## Step 1: Define the Document Directory

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Ensure to replace "Your Document Directory" with the actual path where you want to save your XPS document.

## Step 2: Create a New XPS Document

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Instantiate a new XPS document using the `XpsDocument` class.

## Step 3: Add a Tiled Image

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

This step adds a tiled image to the XPS document. Adjust the coordinates and image file path as per your requirements.

## Step 4: Save the Resultant XPS Document

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Save the modified XPS document to the specified directory.

## Conclusion

Congratulations! You've successfully learned how to add a tiled image to an XPS document using Aspose.Page for .NET. This simple yet powerful feature allows you to enhance the visual appeal of your documents effortlessly.

## FAQ's

### Q1: Is Aspose.Page compatible with all .NET development environments?

A1: Yes, Aspose.Page is designed to work seamlessly with various .NET development environments, including Visual Studio.

### Q2: Can I adjust the opacity of the tiled image?

A2: Certainly, as demonstrated in the example, you can set the opacity of the filled rectangle using the `Opacity` property.

### Q3: Are there other tile modes available in Aspose.Page for .NET?

A3: Yes, Aspose.Page provides different tile modes. In this tutorial, we used `XpsTileMode.Tile`, but you can explore other options in the documentation.

### Q4: How do I handle temporary licenses for Aspose.Page?

A4: Refer to the [temporary license](https://purchase.aspose.com/temporary-license/) page on the Aspose website for guidance on obtaining and implementing temporary licenses.

### Q5: Where can I seek help or connect with the Aspose.Page community?

A5: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to engage with the community, ask questions, and find solutions.
