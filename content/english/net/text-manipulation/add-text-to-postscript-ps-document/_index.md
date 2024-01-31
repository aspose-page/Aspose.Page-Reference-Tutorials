---
title: Add Text to PostScript (PS) Document with Aspose.Page
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
description: Enhance your .NET development skills by learning to add text to PostScript (PS) documents using Aspose.Page. Explore step-by-step examples and unleash the power of document manipulation.
type: docs
weight: 10
url: /net/text-manipulation/add-text-to-postscript-ps-document/
---
## Introduction

In the dynamic world of .NET development, manipulating and enhancing PostScript (PS) documents is a common requirement. Aspose.Page for .NET provides a powerful set of tools to effortlessly add text to your PS documents. This tutorial will guide you through the process, ensuring you can seamlessly integrate this functionality into your projects.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Aspose.Page for .NET: Ensure that you have the Aspose.Page library integrated into your .NET project. You can download it from the [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/).

- Document Directory: Set up a directory where your documents will be stored. This will be referred to as "Your Document Directory" in the examples.

- Fonts Folder: Create a folder to store custom fonts, referred to as "Your Document Directory" in the examples.

## Import Namespaces

Before getting started, make sure to include the necessary namespaces in your project:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Now, let's break down the example into multiple steps.

## Step 1: Create Output Stream for PS Document

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 2: Fill Text with System Font

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## Step 3: Fill Text with Custom Font

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Step 4: Outline Text with System Font

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## Step 5: Outline Text with Custom Font

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## Step 6: Close and Save

```csharp
document.ClosePage();
document.Save();
}
```

## Conclusion

Congratulations! You have successfully learned how to add text to a PostScript (PS) document using Aspose.Page for .NET. Feel free to explore more features and enhance your document manipulation capabilities.

## FAQ's

### Q1: Can I use Aspose.Page with other .NET libraries?

A1: Yes, Aspose.Page seamlessly integrates with other .NET libraries, providing a versatile environment for document manipulation.

### Q2: Are custom fonts essential for this process?

A2: While you can use system fonts, incorporating custom fonts allows for greater flexibility and design choices.

### Q3: Is Aspose.Page suitable for large-scale document processing?

A3: Absolutely! Aspose.Page is designed to handle large-scale document processing with efficiency and reliability.

### Q4: Can I modify the position of the text in the PS document?

A4: Certainly! Adjust the coordinates in the provided examples to change the position of the added text.

### Q5: Where can I seek assistance for Aspose.Page-related queries?

A5: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) to connect with the community and seek expert advice.
