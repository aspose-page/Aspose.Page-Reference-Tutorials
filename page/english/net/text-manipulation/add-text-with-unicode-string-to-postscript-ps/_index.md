---
title: Create PostScript document C# with Unicode text – Aspose.Page
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
description: Learn how to create PostScript document C# with Unicode text using Aspose.Page for .NET – a fast way to enhance document manipulation.
weight: 11
url: /net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
date: 2026-03-21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Text with Unicode String to PostScript (PS) with Aspose.Page

## Introduction

If you need to **create a PostScript document C#** and embed Unicode characters, Aspose.Page for .NET makes the process straightforward. In this tutorial we’ll walk through a complete, hands‑on example that shows you how to add Japanese text (or any Unicode string) to a PS file, choose a custom font, and save the result. By the end, you’ll have a reusable snippet you can drop into any C# project.

## Quick Answers
- **What does this tutorial cover?** Adding Unicode text to a PostScript file using Aspose.Page in C#.
- **Which library is required?** Aspose.Page for .NET (latest version).
- **Do I need a special font?** Any TrueType/OpenType font that supports the desired Unicode range, e.g., *Arial Unicode MS*.
- **How many lines of code?** About 30 lines, split into clear steps.
- **Is a license needed?** A temporary license works for evaluation; a full license is required for production.

## What is “create postscript document c#”?
Creating a PostScript document in C# means programmatically generating a .ps file that follows the PostScript language specifications. Aspose.Page abstracts the low‑level details, letting you focus on content such as text, graphics, and fonts.

## Why use Aspose.Page for Unicode text?
- **Full Unicode support** – render characters from any language without manual encoding.
- **Device‑independent** – the same code works for PS, EPS, and PDF outputs.
- **No external dependencies** – the library handles font loading and glyph mapping internally.

## Prerequisites

- Basic familiarity with C# and .NET development.
- Aspose.Page for .NET library installed. You can download it from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- A folder containing the fonts you plan to use (e.g., *Arial Unicode MS*).

## Import Namespaces

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

## Common Issues and Solutions

- **Font not found** – Ensure the `AdditionalFontsFolders` path points to the folder containing the .ttf/.otf files and that the font name matches exactly.
- **Garbage characters** – Verify that the source string is encoded as UTF‑8 in your C# source file (use `#pragma warning disable 1591` if needed).
- **File not created** – Check write permissions on `dataDir` and that the stream is properly disposed (the `using` block handles this).

## Frequently Asked Questions

**Q: Can I use Aspose.Page for .NET with other programming languages?**  
A: Aspose.Page is primarily designed for .NET, but there are Java equivalents available.

**Q: How do I obtain a temporary license for Aspose.Page for .NET?**  
A: Visit [Temporary License](https://purchase.aspose.com/temporary-license/) for obtaining a temporary license.

**Q: Is there a community forum for Aspose.Page discussions?**  
A: Yes, visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

**Q: What formats can Aspose.Page for .NET work with?**  
A: Aspose.Page supports various formats, including XPS, PS, EPS, PDF, and more.

**Q: Can I customize the appearance of the added text?**  
A: Yes, you can customize the font, size, color, and other properties of the text in Aspose.Page.

## Conclusion

In this tutorial we demonstrated how to **create a PostScript document C#** and embed Unicode text using Aspose.Page. By following the steps above you can quickly integrate multilingual text rendering into any .NET application, giving you full control over document generation and layout.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}