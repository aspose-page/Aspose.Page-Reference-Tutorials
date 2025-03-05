---
title: Add Text with Unicode String to XPS Document with Aspose.Page
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
description: Explore the power of Aspose.Page for .NET with our step-by-step guide on adding Unicode text to XPS documents.
type: docs
weight: 12
url: /net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Introduction

In the ever-evolving landscape of .NET development, Aspose.Page stands out as a powerful tool for handling XPS documents. Among its many features, the ability to add text with Unicode strings to an XPS document is a valuable functionality. This step-by-step guide will walk you through the process, ensuring you harness this capability effectively.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- A basic understanding of .NET development.
- Visual Studio installed on your machine.
- Aspose.Page for .NET library. You can download it from [here](https://releases.aspose.com/page/net/).

## Import Namespaces

To begin, ensure you import the necessary namespaces into your project. This will provide the required classes and functionalities for working with Aspose.Page. Here are the essential namespaces:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set up the Document

Firstly, create a new XPS document where you'll be adding the Unicode text. Follow the code snippet below:

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Step 2: Add Unicode Text

Now, let's add Unicode text to the XPS document. This example uses the Arial font, sets the font size to 20, and positions the text at coordinates (400f, 200f). The Unicode string in this case is "TEN. rof SPX.esopsA". Check out the code snippet below:

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Step 3: Save the Document

Once the Unicode text is added, save the resultant XPS document. Here's the final step:

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Congratulations! You've successfully added Unicode text to an XPS document using Aspose.Page for .NET.

## Conclusion

In this tutorial, we explored the process of adding Unicode text to XPS documents using Aspose.Page for .NET. This functionality opens doors to diverse and dynamic document creation within the .NET environment.

## FAQ's

### Q1: Is Aspose.Page compatible with the latest .NET frameworks?

A1: Yes, Aspose.Page is regularly updated to ensure compatibility with the latest .NET frameworks.

### Q2: Can I customize the font style and size when adding text?

A2: Absolutely! The example code provided allows you to customize font style, size, and other attributes easily.

### Q3: Where can I find additional documentation for Aspose.Page?

A3: You can refer to the documentation [here](https://reference.aspose.com/page/net/) for comprehensive information and examples.

### Q4: Are there any free resources to get started with Aspose.Page?

A4: Yes, you can explore the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support and discussions.

### Q5: Is there a trial version available before making a purchase?

A5: Certainly! You can access the free trial version [here](https://releases.aspose.com/) before making a purchase.
