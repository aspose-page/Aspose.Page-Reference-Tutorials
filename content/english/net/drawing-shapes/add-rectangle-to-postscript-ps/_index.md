---
title: Add Rectangle to PostScript (PS) with Aspose.Page for .NET
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
description: Enhance document creation in .NET with Aspose.Page. Learn to add rectangles to PostScript (PS) files step-by-step.
type: docs
weight: 12
url: /net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## Introduction

If you're looking to enhance your document creation capabilities in .NET, Aspose.Page provides a powerful solution for handling PostScript documents. In this tutorial, we will guide you through the process of adding rectangles to a PostScript document using Aspose.Page for .NET.

## Prerequisites

Before diving into the tutorial, ensure that you have the following prerequisites in place:

- Aspose.Page for .NET Library: Download and install the Aspose.Page for .NET library from [here](https://releases.aspose.com/page/net/).

- Development Environment: Make sure you have a .NET development environment set up on your machine.

## Import Namespaces

Before you start coding, make sure to import the necessary namespaces to access the required classes and methods:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Now, let's break down the example into multiple steps:

## Step 1: Set up Your Document Directory

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

In this step, replace "Your Document Directory" with the path where you want to save your PostScript document.

## Step 2: Create Output Stream for PostScript Document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Here, we create an output stream for the PostScript document and specify the file name ("AddRectangle_outPS.ps"). Adjust the file name and location according to your preferences.

## Step 3: Set Save Options and Create PS Document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Set the save options, specifying the desired page size (A4 in this case). Then, create a new single-paged PostScript document.

## Step 4: Add Rectangle and Fill

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Here, we create a graphics path representing the first rectangle, set the paint color (in this case, orange), and fill the rectangle.

## Step 5: Add Another Rectangle and Stroke

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Similar to the previous step, we create a graphics path for the second rectangle, set the stroke color (red with a thickness of 3), and outline the rectangle.

## Step 6: Close the Page and Save the Document

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Finally, close the current page and save the entire document.

## Conclusion

Congratulations! You've successfully added rectangles to a PostScript document using Aspose.Page for .NET. This tutorial covered the essential steps, from setting up your development environment to saving the final document.

## FAQ's

### Q1: Can I customize the colors of the rectangles?

A1: Yes, you can customize the colors by adjusting the parameters in the `SolidBrush` and `Pen` classes.

### Q2: Is Aspose.Page compatible with other document formats?

A2: Yes, Aspose.Page supports various document formats, including XPS and PostScript.

### Q3: How can I add text to the document?

A3: You can use the `TextFragment` class in Aspose.Page to add text to your document.

### Q4: Where can I find additional examples and documentation?

A4: Explore the documentation [here](https://reference.aspose.com/page/net/) and visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

### Q5: Can I try Aspose.Page before purchasing?

A5: Yes, you can get a free trial version [here](https://releases.aspose.com/), and for extended use, consider a [temporary license](https://purchase.aspose.com/temporary-license/).

