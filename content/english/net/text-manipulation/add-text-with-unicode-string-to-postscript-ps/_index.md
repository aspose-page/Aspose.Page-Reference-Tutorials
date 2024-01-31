---
title: Add Text with Unicode String to PostScript (PS) with Aspose.Page
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
description: Learn how to add Unicode text to PostScript files using Aspose.Page for .NET. Enhance document manipulation with ease.
type: docs
weight: 11
url: /net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---
## Introduction

In the realm of document manipulation, Aspose.Page for .NET stands out as a robust library that empowers developers to create, edit, and convert various document formats. One of its powerful features is the ability to add text using Unicode strings to PostScript (PS) files. In this tutorial, we'll explore a step-by-step guide on accomplishing this task, providing a seamless experience for developers working with Aspose.Page.

## Prerequisites

Before diving into the tutorial, ensure you have the following prerequisites:

- A working knowledge of C# programming language.
- Aspose.Page for .NET library installed. You can download it from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- A development environment set up with necessary configurations.

## Import Namespaces

In your C# code, import the required namespaces for using Aspose.Page for .NET functionalities:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Document Directory and Fonts Folder

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Step 2: Create Output Stream for PostScript Document

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Step 3: Add Unicode Text with Custom Font

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Step 4: Close the Current Page

```csharp
document.ClosePage();
```

## Step 5: Finalize and Save the Document

```csharp
document.Save();
```

## Conclusion

In this tutorial, we've walked through the process of adding Unicode text to a PostScript document using Aspose.Page for .NET. Leveraging its powerful capabilities, developers can enhance their document manipulation workflows, ensuring flexibility and precision.

## FAQ's

### Q1: Can I use Aspose.Page for .NET with other programming languages?

A1: Aspose.Page is primarily designed for .NET, but there are other versions for Java available.

### Q2: How do I obtain a temporary license for Aspose.Page for .NET?

A2: Visit [Temporary License](https://purchase.aspose.com/temporary-license/) for obtaining a temporary license.

### Q3: Is there a community forum for Aspose.Page discussions?

A3: Yes, visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

### Q4: What formats can Aspose.Page for .NET work with?

A4: Aspose.Page supports various formats, including XPS, PS, EPS, PDF, and more.

### Q5: Can I customize the appearance of the added text?

A5: Yes, you can customize the font, size, color, and other properties of the text in Aspose.Page.
