---
title: Create XPS Document – Add Glyph Clone & Change Color with Aspose.Page for .NET
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
description: Learn how to create XPS document, add glyph clones, use a solid color brush, and save XPS file with Aspose.Page for .NET.
weight: 10
url: /net/cross-document-editing/add-glyph-clone-and-change-color/
date: 2026-01-07
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS Document – Add Glyph Clone & Change Color with Aspose.Page for .NET

## Introduction

Welcome to this step‑by‑step guide that shows you **how to create XPS document** files, clone glyphs, and change their colors using Aspose.Page for .NET. Whether you’re building dynamic reports, invoices, or custom graphics, mastering these techniques lets you produce visually rich XPS output without leaving the .NET ecosystem.

## Quick Answers
- **What is the primary goal?** Create an XPS document, add glyph clones, and change their colors.  
- **Which library is used?** Aspose.Page for .NET.  
- **Do I need a license?** A temporary license is available for evaluation; a full license is required for production.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **How do I save the result?** Use the `Save` method to write the XPS file to disk.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites:

- A basic understanding of C# programming language.  
- Visual Studio or any other preferred C# development environment installed.  
- Aspose.Page for .NET library. You can download it [here](https://releases.aspose.com/page/net/).  
- Familiarity with the XPS document format.

## Import Namespaces

To get started, include the necessary namespaces in your C# project:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## How to Create XPS Document and Add Glyph Clones

### Step 1: Set up Your Document Directory

Begin by setting up the directory where your documents will be stored:

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create the First XPS Document

Now, let's create the first XPS document:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Step 3: Add Glyphs to the First Document

Add glyphs to the first document using the specified parameters:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 4: Fill Glyphs with a Solid Color Brush

Fill the glyphs in the first document with a **solid color brush**, for example, green:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Step 5: Create the Second XPS Document

Now, create the second XPS document:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Step 6: How to Add Glyph Clone to Another Document

Clone glyphs from the first document and add them to the second document:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Step 7: How to Change Color of the Cloned Glyph

Change the color of the cloned glyphs in the second document, for example, to red. This demonstrates **how to change color** of a glyph after cloning:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Step 8: Save XPS File – First Document

Save the first XPS document to the folder you defined earlier:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Step 9: Save XPS File – Second Document

Save the second XPS document:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Congratulations! You have successfully **created XPS document** files, added glyph clones, and changed their colors using Aspose.Page for .NET.

## Why Use Glyph Cloning and Color Changes?

- **Reusability:** Clone existing glyphs to reuse complex vector shapes without redefining them.  
- **Performance:** Reduces processing time compared to recreating glyphs from scratch.  
- **Design Flexibility:** Apply different `SolidColorBrush` instances to the same glyph to achieve varied visual themes.  
- **Cross‑Document Editing:** Clone glyphs across multiple XPS files, enabling consistent branding across reports.

## Common Issues & Troubleshooting

| Issue | Solution |
|-------|----------|
| **Clone returns null** | Ensure the source glyph (`glyphs`) is added to the first document before cloning. |
| **Color does not change** | Cast `glyphs.Fill` to `XpsSolidColorBrush` before setting the `Color` property (as shown in Step 7). |
| **File not saved** | Verify that `dataDir` points to a valid, writable folder and that you have appropriate file‑system permissions. |
| **Unexpected glyph size** | Adjust the font size parameter (second argument in `AddGlyphs`) to scale the glyph appropriately. |

## Frequently Asked Questions

**Q1: Can I use Aspose.Page for .NET with other document formats?**  
A1: Aspose.Page for .NET is specifically designed for working with XPS documents. If you need to manipulate other formats, you may explore other Aspose libraries tailored for those formats.

**Q2: Is a temporary license available for Aspose.Page for .NET?**  
A2: Yes, you can obtain a temporary license for testing purposes. Visit [here](https://purchase.aspose.com/temporary-license/) for more information.

**Q3: How can I get support or seek assistance for any issues?**  
A3: Feel free to visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with the community and seek assistance.

**Q4: Are there any limitations to the free trial version?**  
A4: The free trial version has some limitations, and it is recommended to review the documentation for details before use.

**Q5: Where can I find comprehensive documentation for Aspose.Page for .NET?**  
A5: You can refer to the documentation [here](https://reference.aspose.com/page/net/) for detailed information and examples.

**Q6: How do I change the stroke color of a glyph instead of the fill?**  
A6: Use `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` to set a stroke brush.

**Q7: Can I add multiple glyph clones to the same document?**  
A7: Yes, call `doc2.Add(glyphs.Clone());` repeatedly, adjusting positions as needed.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}