---
title: Add Diagonal Gradient to PostScript (PS) with Aspose.Page .NET
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
description: Explore the simplicity of adding diagonal gradients to PostScript documents in .NET with Aspose.Page. Elevate your projects with dynamic visual elements.
weight: 10
url: /net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Diagonal Gradient to PostScript (PS) with Aspose.Page .NET

## Introduction

Adding a diagonal gradient to a PostScript (PS) document can bring visual appeal and creativity to your projects. Aspose.Page for .NET provides a seamless solution for integrating this feature into your applications. In this tutorial, we'll guide you through the process of adding a diagonal gradient to a PS document using Aspose.Page, step by step.

## Prerequisites

Before we dive into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for .NET Library: Ensure that you have the Aspose.Page for .NET library installed. You can download it [here](https://releases.aspose.com/page/net/).

- Document Directory: Set up a directory for your documents where the output PS file will be saved.

Now, let's move on to the step-by-step guide.

## Import Namespaces

Firstly, make sure to import the necessary namespaces into your project. These namespaces are crucial for working with Aspose.Page functionalities.

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
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Step 2: Create Save Options with A4 Size

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Step 3: Create a New 1-Paged PS Document

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Define Rectangle Parameters

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Step 5: Create Graphics Path

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Step 6: Create Linear Gradient Brush

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Step 7: Create Transform for Brush

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Step 8: Apply Transformations to Brush

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Step 9: Set Transform to Brush

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Step 10: Set Paint and Fill the Rectangle

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Step 11: Close the Current Page

```csharp
	//Close current page
	document.ClosePage();
```

## Step 12: Save the Document

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

By following these steps, you'll successfully add a diagonal gradient to a PostScript document using Aspose.Page for .NET.

## Conclusion

Enhancing your PS documents with diagonal gradients can make your projects visually appealing and dynamic. Aspose.Page for .NET simplifies this process, allowing developers to effortlessly integrate this feature into their applications.

## FAQ's

### Q1: Is Aspose.Page compatible with all .NET frameworks?

A1: Aspose.Page supports various .NET frameworks, ensuring compatibility with a wide range of development environments.

### Q2: Can I customize the gradient colors in Aspose.Page?

A2: Yes, Aspose.Page provides flexibility in choosing and customizing gradient colors according to your project requirements.

### Q3: Is there a trial version available for Aspose.Page?

A3: Yes, you can explore Aspose.Page's features by downloading the trial version [here](https://releases.aspose.com/).

### Q4: How can I get a temporary license for Aspose.Page?

A4: Obtain a temporary license for Aspose.Page [here](https://purchase.aspose.com/temporary-license/) to unlock additional features.

### Q5: Where can I find community support for Aspose.Page?

A5: Engage with the Aspose.Page community on the [forum](https://forum.aspose.com/c/page/39) for assistance and discussions.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
