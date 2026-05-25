---
title: "Create XPS Document: Add Rectangle with Aspose.Page for .NET"
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
description: "Learn how to create XPS document, add a rectangle and save XPS file using Aspose.Page for .NET in this step‑by‑step guide."
weight: 13
url: /net/drawing-shapes/add-rectangle-to-xps-document/
date: 2026-01-20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS Document: Add Rectangle with Aspose.Page for .NET

## Introduction

In this tutorial you'll **create XPS document** files and draw a rectangle inside them using the Aspose.Page for .NET library. Adding shapes like rectangles is a common requirement when you need to generate invoices, reports, or custom graphics programmatically. Follow the steps below and you'll have a ready‑to‑use XPS file in minutes.

## Quick Answers
- **What can I generate?** XPS documents with vector graphics and text.  
- **Which library?** Aspose.Page for .NET (free trial available).  
- **How long does it take?** About 5‑10 minutes to implement and run.  
- **Do I need a license?** A temporary license is required for production use.  
- **Can I save the result as an XPS file?** Yes – the `Save` method writes a **save XPS file** to disk.

## What is “create XPS document”?

Creating an XPS document means programmatically building a page description in the XML Paper Specification format. The resulting file is resolution‑independent, ideal for printing and high‑quality display across platforms.

## Why use Aspose.Page to create XPS document?

- **Full .NET support** – works with .NET Framework, .NET Core, and .NET 5/6+.  
- **Rich drawing API** – includes path geometry, brushes, pens, and text handling.  
- **No external dependencies** – everything runs in‑process without needing Office or Acrobat.  

## Prerequisites

Before you begin, make sure you have the following:

1. **Aspose.Page for .NET** – download it [here](https://releases.aspose.com/page/net/).  
2. **A writable folder** where the generated XPS files will be stored.

## Import Namespaces

In your .NET project, import the required namespaces:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set the Document Directory

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Pro tip:** Use an absolute path or `Path.Combine` to avoid path‑separator issues on different OSes.

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

At this point you have **created an XPS document** object that will hold all drawing elements.

## Step 3: Add a Rectangle (using create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

The `CreatePathGeometry` call **creates path geometry** that defines the rectangle’s outline. You can modify the SVG‑like command string to draw other shapes.

## Step 4: Save the Document (save XPS file)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Calling `Save` writes the **save XPS file** to the location you specified.

Congratulations! You have successfully **created an XPS document**, added a rectangle, and saved the file.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| `FileNotFoundException` on `doc.Save` | `dataDir` points to a non‑existent folder | Ensure the directory exists or create it with `Directory.CreateDirectory(dataDir)`. |
| Rectangle not visible | Stroke color profile missing or path geometry malformed | Verify the ICC file path and the geometry string (`M … Z`). |
| Performance slowdown on large documents | Too many individual `AddPath` calls | Batch drawing operations or reuse brushes/pen objects. |

## Frequently Asked Questions

**Q: Is Aspose.Page compatible with all .NET applications?**  
A: Yes, Aspose.Page is designed to work seamlessly with all .NET applications.

**Q: Where can I find the documentation for Aspose.Page for .NET?**  
A: The documentation is available [here](https://reference.aspose.com/page/net/).

**Q: Can I try Aspose.Page for .NET for free before purchasing?**  
A: Yes, you can get a free trial [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page for .NET?**  
A: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain a temporary license.

**Q: Where can I seek community support or ask questions related to Aspose.Page for .NET?**  
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}