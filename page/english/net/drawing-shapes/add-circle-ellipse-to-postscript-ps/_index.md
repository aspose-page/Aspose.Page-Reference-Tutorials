---
title: Add Circle Ellipse to PostScript (PS) with Aspose.Page
linktitle: Add Circle Ellipse to PostScript (PS)
second_title: Aspose.Page .NET API
description: Learn how to effortlessly add circle ellipses to PostScript (PS) documents using Aspose.Page for .NET. Follow our step-by-step guide for seamless integration.
type: docs
weight: 10
url: /net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## Introduction

Welcome to this comprehensive tutorial on adding circle ellipses to PostScript (PS) documents using Aspose.Page for .NET. Aspose.Page is a powerful library that allows developers to work with PostScript and other document formats seamlessly. In this guide, we will walk you through the process of incorporating circle ellipses into your PS documents with ease.

## Prerequisites

Before we dive into the tutorial, make sure you have the following prerequisites in place:

1. Aspose.Page for .NET Library: Download and install the Aspose.Page for .NET library from [here](https://releases.aspose.com/page/net/).

2. Development Environment: Ensure you have a working .NET development environment set up on your machine.

Now, let's get started with the step-by-step guide.

## Import Namespaces

In the first step, you need to import the necessary namespaces to make the Aspose.Page functionality available in your code.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Now, let's break down the example provided into multiple steps to guide you through the process of adding circle ellipses to a PostScript document.

## Step 1: Set the Document Directory

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Ensure to replace "Your Document Directory" with the actual path to your documents directory.

## Step 2: Create Output Stream for PostScript Document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Here, a FileStream is created to write the PostScript document, and the file mode is set to create a new file.

## Step 3: Create Save Options and PS Document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

This step involves creating save options with A4 size and initializing a new 1-paged PS Document.

## Step 4: Create Graphics Path for the First Ellipse

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

A graphics path is created for the first ellipse, specifying its position and dimensions.

## Step 5: Set Paint and Fill the Ellipse

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

Here, the paint is set, and the first ellipse is filled with the specified color.

## Step 6: Create Graphics Path for the Second Ellipse

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Similarly, a graphics path is created for the second ellipse, defining its position and dimensions.

## Step 7: Set Stroke and Draw the Ellipse

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

In this step, the stroke is set, and the second ellipse is outlined with the specified color and line thickness.

## Step 8: Close the Current Page and Save the Document

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Finally, the current page is closed, and the entire document is saved, completing the process.

## Conclusion

Congratulations! You have successfully learned how to add circle ellipses to PostScript documents using Aspose.Page for .NET. This tutorial provided a detailed, step-by-step guide to help you integrate this functionality into your projects seamlessly.

## FAQ's

### Q1: Can I use Aspose.Page for .NET with other document formats?

A1: Aspose.Page primarily focuses on PostScript, but Aspose provides other libraries for various document formats. Check the [Aspose documentation](https://reference.aspose.com/page/net/) for more details.

### Q2: Where can I find additional support and community discussions?

A2: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community discussions and support.

### Q3: Is there a free trial available for Aspose.Page for .NET?

A3: Yes, you can access the [free trial](https://releases.aspose.com/) to explore the features of Aspose.Page for .NET.

### Q4: How can I obtain a temporary license for Aspose.Page?

A4: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing and evaluation purposes.

### Q5: Where can I purchase Aspose.Page for .NET?

A5: Purchase Aspose.Page for .NET from the [buy page](https://purchase.aspose.com/buy).
