---
title: Add Vertical Gradient to PostScript (PS) with Aspose.Page
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
description: Learn how to add visually appealing vertical gradients to PostScript (PS) documents in .NET using Aspose.Page. Elevate your document creation with this step-by-step guide.
weight: 14
url: /net/gradient-fills/add-vertical-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Vertical Gradient to PostScript (PS) with Aspose.Page

## Introduction

In the realm of document manipulation and creation, Aspose.Page for .NET stands out as a powerful tool for developers. This tutorial will guide you through the process of adding a vertical gradient to a PostScript (PS) document using Aspose.Page for .NET. By the end of this guide, you'll have a clear understanding of the necessary steps to achieve this visually appealing effect.

## Prerequisites

Before diving into the tutorial, make sure you have the following in place:

- Aspose.Page for .NET: Ensure that you have the Aspose.Page library installed. You can find the necessary resources and documentation [here](https://reference.aspose.com/page/net/).

- Development Environment: Set up a suitable development environment, including an Integrated Development Environment (IDE) for .NET development.

- Basic Understanding: Familiarize yourself with the basics of .NET development, including working with streams, graphics paths, and color manipulation.

## Import Namespaces

In your C# project, include the required namespaces at the beginning of your code file:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up the Document Directory

Begin by specifying the path to your document directory. This is the location where your PS document will be saved.

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream for PostScript Document

Generate an output stream for the PostScript document using the FileStream class.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Step 3: Create Save Options and PS Document

Create save options with A4 size and initialize a new 1-paged PS document.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Define Rectangle Dimensions

Specify the dimensions and position of the rectangle where the vertical gradient will be applied.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Step 5: Create Graphics Path

Build a graphics path from the defined rectangle.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Step 6: Define Interpolation Colors

Establish an array of interpolation colors and positions for the gradient.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Step 7: Create Linear Gradient Brush

Form a linear gradient brush with the rectangle as bounds, start and end colors.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Step 8: Set Brush Transform

Establish a transform for the brush, ensuring that the X and Y scale components match the width and height of the rectangle.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Step 9: Set Paint and Fill the Rectangle

Set the paint for the document, and fill the previously defined rectangle.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Step 10: Close the Current Page and Save the Document

Close the current page and save the PostScript document.

```csharp
document.ClosePage();
document.Save();
```

Congratulations! You have successfully added a vertical gradient to a PostScript document using Aspose.Page for .NET. Experiment with different parameters and colors to achieve various visual effects in your documents.

## Conclusion

In this tutorial, we explored the process of enhancing your PostScript documents by incorporating vertical gradients. Aspose.Page for .NET provides a seamless environment for such manipulations, empowering developers to create visually stunning documents effortlessly.

## FAQ's

### Q1: Can I apply multiple gradients to different regions of the same document?

A1: Yes, you can. Simply repeat the steps for each region with its specific dimensions and color scheme.

### Q2: How can I integrate this code into my existing .NET project?

A2: Copy and paste the code into your project file and ensure that you have the Aspose.Page library referenced.

### Q3: Are there other gradient types available in Aspose.Page for .NET?

A3: Aspose.Page supports various gradient types, including radial and path gradients. Refer to the documentation for more details.

### Q4: Can I use Aspose.Page for commercial projects?

A4: Yes, you can. Visit [here](https://purchase.aspose.com/buy) to explore licensing options.

### Q5: Is there a community forum for Aspose.Page where I can seek help?

A5: Certainly! Head to the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with other developers and get assistance.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
