---
title: How to Add Unicode Text to XPS Document with Aspose.Page
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
description: Learn how to add Unicode text to an XPS document using Aspose.Page for .NET. This guide shows you how to create XPS document C# and aspose page add text with Unicode strings.
weight: 12
url: /net/text-manipulation/add-text-with-unicode-string-to-xps-document/
date: 2026-03-21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Add Unicode Text to XPS Document with Aspose.Page

## Introduction

If you need to **how to add unicode** characters to an XPS file, you’ve come to the right place. In this tutorial we’ll walk through the exact steps required to **create XPS document C#**‑style using Aspose.Page for .NET and demonstrate the **aspose page add text** capability with a Unicode string. By the end you’ll have a fully functional XPS document that displays right‑to‑left (RTL) Unicode text correctly.

## Quick Answers
- **What does the tutorial cover?** Adding Unicode text to an XPS document with Aspose.Page for .NET.  
- **Which language is used?** C# (compatible with .NET Framework and .NET Core).  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Can I change the font or size?** Yes – the example uses Arial 20 pt, but any installed font works.  
- **Is RTL support included?** Setting `BidiLevel = 1` enables right‑to‑left rendering for Unicode strings.

## What is “how to add unicode” in XPS?

Adding Unicode text means inserting characters from any language—Arabic, Hebrew, Chinese, etc.—into an XPS document. Aspose.Page’s `XpsGlyphs` class handles the low‑level glyph placement, while the `BidiLevel` property controls text direction for RTL scripts.

## Why use Aspose.Page to add text?

- **Full .NET integration** – works with .NET Framework, .NET Core, .NET 5/6+.  
- **No external dependencies** – pure managed code, no COM interop.  
- **Rich typography support** – fonts, styles, colors, and bidirectional text.  
- **High performance** – creates and saves XPS files quickly, ideal for server‑side generation.

## Prerequisites

- Basic knowledge of C# and .NET development.  
- Visual Studio (any recent version).  
- Aspose.Page for .NET library – download it from [here](https://releases.aspose.com/page/net/).

## Import Namespaces

First, import the namespaces that give you access to the XPS model and drawing utilities.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set up the Document – create XPS document C#

Create a fresh XPS document that will host the Unicode text.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Step 2: Add Unicode Text – aspose page add text

Now we add the actual Unicode string. In this example we use the Arial font, size 20, and position the text at (400 f, 200 f). The `BidiLevel` of 1 tells the renderer to treat the string as right‑to‑left.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Step 3: Save the Document

Finally, persist the XPS file to disk.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Congratulations! You have successfully **how to add unicode** text to an XPS document using Aspose.Page for .NET.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| Text appears garbled | Font does not support the Unicode range | Use a font that contains the required glyphs (e.g., Arial Unicode MS). |
| RTL text still left‑to‑right | `BidiLevel` not set or set to 0 | Ensure `glyphs.BidiLevel = 1;` for RTL scripts. |
| File not saved | Invalid `dataDir` path | Verify that the directory exists and the app has write permissions. |

## Frequently Asked Questions

**Q: Is Aspose.Page compatible with the latest .NET frameworks?**  
A: Yes, Aspose.Page is regularly updated to support .NET Framework, .NET Core, and .NET 5/6+.

**Q: Can I customize the font style and size when adding text?**  
A: Absolutely! The `AddGlyphs` method lets you specify any font family, size, and `FontStyle` you need.

**Q: Where can I find additional documentation for Aspose.Page?**  
A: You can refer to the documentation [here](https://reference.aspose.com/page/net/) for comprehensive API details.

**Q: Are there any free resources to get started with Aspose.Page?**  
A: Yes, explore the community forum at [Aspose.Page forum](https://forum.aspose.com/c/page/39) for tips, examples, and peer support.

**Q: Is there a trial version available before making a purchase?**  
A: Certainly! Download the free trial from [here](https://releases.aspose.com/) to evaluate the library.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}