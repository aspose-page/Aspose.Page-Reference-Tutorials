---
title: Show Pseudo-Transparency in PostScript (PS) with Aspose.Page
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
description: Explore the power of pseudo-transparency in PostScript with Aspose.Page for .NET. Follow our step-by-step guide for visually stunning documents.
type: docs
weight: 13
url: /net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## Introduction

Are you looking to enhance the visual appeal of your PostScript (PS) documents by incorporating pseudo-transparency? Aspose.Page for .NET provides a powerful solution to achieve this effect effortlessly. In this step-by-step tutorial, we will guide you through the process of showing pseudo-transparency in PostScript using Aspose.Page.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for .NET: Ensure you have the Aspose.Page library for .NET installed. You can download it from the [Aspose.Page documentation](https://reference.aspose.com/page/net/).

- Document Directory: Set up a directory to store your PostScript documents.

Now that you have the necessary tools in your arsenal, let's explore how to showcase pseudo-transparency in PostScript using Aspose.Page.

## Import Namespaces

Before delving into the example, ensure you import the required namespaces:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Create Output Stream for PostScript Document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 2: Create Rectangle with Opaque Gradient Fill

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Step 3: Create Rectangle with Translucent Gradient Fill

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Step 4: Close Current Page and Save the Document

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

By following these steps, you can seamlessly integrate pseudo-transparency into your PostScript documents using Aspose.Page for .NET.

## Conclusion

In conclusion, Aspose.Page for .NET offers a straightforward and efficient way to enhance the visual elements of your PostScript documents. The steps outlined above provide a clear path for incorporating pseudo-transparency, allowing you to create visually stunning outputs.

## FAQ's

### Q1: Is Aspose.Page compatible with all versions of .NET?

A1: Aspose.Page for .NET is compatible with various versions of the .NET framework, ensuring flexibility and ease of integration.

### Q2: Can I apply pseudo-transparency to other shapes besides rectangles?

A2: Yes, the same principles can be applied to other shapes by adjusting the GraphicsPath accordingly.

### Q3: Where can I find additional examples and documentation?

A3: Explore the [Aspose.Page documentation](https://reference.aspose.com/page/net/) for comprehensive examples and detailed documentation.

### Q4: Is there a free trial available for Aspose.Page?

A4: Yes, you can access a free trial of Aspose.Page from [this link](https://releases.aspose.com/).

### Q5: How can I obtain a temporary license for Aspose.Page?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain a temporary license for Aspose.Page.
