---
title: "Create a Vertical Gradient Fill – Gradient Fills with Aspose.Page .NET"
linktitle: Gradient Fills
second_title: Aspose.Page .NET API
description: "Learn how to add vertical gradient fills in .NET using Aspose.Page. Elevate your PS and XPS documents with dynamic diagonal, horizontal, and vertical gradients."
weight: 27
url: /net/gradient-fills/
date: 2026-02-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gradient Fills

## Introduction

Are you ready to take your document creations to the next level? **Aspose.Page for .NET** brings you a series of tutorials on gradient fills, allowing you to infuse dynamic visual elements into your PostScript (PS) and XPS documents. In this guide, we'll walk you through the seamless process of **adding vertical gradient** fills, as well as diagonal and horizontal gradients, enhancing the overall appeal of your projects.

## Sample Code

Below is a minimal C# example that demonstrates how to create a vertical gradient fill using Aspose.Page for .NET:

```csharp
// C# example to create a vertical gradient fill
using Aspose.Page;
using Aspose.Page.Drawing;
using Aspose.Page.XPS;
using Aspose.Page.PS;

var document = new XpsDocument(); // or new PsDocument()
var page = document.Pages.Add();
var brush = new LinearGradientBrush(
    new PointF(0, 0), new PointF(0, page.Height),
    new GradientStop[] {
        new GradientStop(Color.Red, 0f),
        new GradientStop(Color.Blue, 1f)
    });
page.Graphics.FillRectangle(brush, new RectangleF(0, 0, page.Width, page.Height));
document.Save("VerticalGradient.xps");
```

## Quick Answers
- **What can I create with Aspose.Page?** PS and XPS documents with advanced graphic effects.  
- **Which gradient types are covered?** Diagonal, horizontal, and **vertical gradient** fills.  
- **Do I need a license?** A free trial is available; a commercial license is required for production.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does implementation take?** Typically under 10 minutes for a basic gradient.

## What is a vertical gradient?

A **vertical gradient** blends two or more colors from the top edge of a shape to its bottom edge, creating a smooth transition that adds depth and visual interest to your document elements.

## Why use gradient fills with Aspose.Page?

- **Professional look:** Gradients make static documents feel more modern.  
- **Cross‑format support:** The same code works for both PostScript and XPS outputs.  
- **Fine‑grained control:** Choose colors, positions, and gradient types programmatically.  
- **Performance‑optimized:** Aspose.Page renders gradients efficiently, even for large documents.

## Add Diagonal Gradient to PostScript (PS) with Aspose.Page .NET

Unlock the simplicity of incorporating diagonal gradients into your PostScript documents using Aspose.Page. Follow our step‑by‑step tutorial to effortlessly elevate your visual elements, bringing a fresh perspective to your projects. [Read the diagonal gradient tutorial for PostScript]({{< relref "add-diagonal-gradient-to-postscript-ps/_index.md" >}})

## Add Diagonal Gradient to XPS with Aspose.Page for .NET

Curious about making your XPS documents more visually appealing? Dive into this tutorial to learn how Aspose.Page for .NET enables you to add captivating diagonal gradients, enhancing the aesthetic appeal of your presentations. [Read the diagonal gradient tutorial for XPS]({{< relref "add-diagonal-gradient-to-xps/_index.md" >}})

## Add Horizontal Gradient to PostScript (PS) with Aspose.Page

Elevate your PostScript documents with stunning horizontal gradients. Our tutorial guides you through the process, ensuring a seamless implementation with Aspose.Page for .NET. Transform your projects effortlessly. [Read the horizontal gradient tutorial for PostScript]({{< relref "add-horizontal-gradient-to-postscript-ps/_index.md" >}})

## Add Horizontal Gradient to XPS with Aspose.Page for .NET

Unleash the visual power of horizontal gradients in your XPS documents. Aspose.Page for .NET makes it easy with our step‑by‑step guide. Enhance the appeal of your visual presentations effortlessly. [Read the horizontal gradient tutorial for XPS]({{< relref "add-horizontal-gradient-to-xps/_index.md" >}})

## Add Vertical Gradient to PostScript (PS) with Aspose.Page

Learn the art of incorporating visually appealing **vertical gradient** fills into your PostScript documents. Aspose.Page for .NET provides a comprehensive guide, ensuring you elevate your document creation effortlessly. [Read the vertical gradient tutorial for PostScript]({{< relref "add-vertical-gradient-to-postscript-ps/_index.md" >}})

## Add Vertical Gradient to XPS with Aspose.Page for .NET

Enhance your XPS documents with **vertical gradient** fills using Aspose.Page for .NET. Our step‑by‑step guide makes integration seamless, allowing you to bring a touch of sophistication to your projects. [Read the vertical gradient tutorial for XPS]({{< relref "add-vertical-gradient-to-xps/_index.md" >}})

Dive into these tutorials and discover the creative possibilities that Aspose.Page for .NET unlocks for your document creations. Elevate your projects with dynamic and visually stunning gradient fills.

## Gradient fills tutorials
### [Add Diagonal Gradient to PostScript (PS) with Aspose.Page .NET]({{< relref "add-diagonal-gradient-to-postscript-ps/_index.md" >}})
Explore the simplicity of adding diagonal gradients to PostScript documents in .NET with Aspose.Page. Elevate your projects with dynamic visual elements.
### [Add Diagonal Gradient to XPS with Aspose.Page for .NET]({{< relref "add-diagonal-gradient-to-xps/_index.md" >}})
Learn how to add captivating diagonal gradients to XPS documents using Aspose.Page for .NET. Elevate your visual presentations effortlessly.
### [Add Horizontal Gradient to PostScript (PS) with Aspose.Page]({{< relref "add-horizontal-gradient-to-postscript-ps/_index.md" >}})
Enhance PostScript documents with stunning horizontal gradients using Aspose.Page for .NET. Follow our step‑by‑step tutorial for seamless implementation.
### [Add Horizontal Gradient to XPS with Aspose.Page for .NET]({{< relref "add-horizontal-gradient-to-xps/_index.md" >}})
Learn how to add stunning horizontal gradients to your XPS documents using Aspose.Page for .NET. Elevate visual appeal effortlessly.
### [Add Vertical Gradient to PostScript (PS) with Aspose.Page]({{< relref "add-vertical-gradient-to-postscript-ps/_index.md" >}})
Learn how to add visually appealing vertical gradients to PostScript (PS) documents in .NET using Aspose.Page. Elevate your document creation with this step‑by‑step guide.
### [Add Vertical Gradient to XPS with Aspose.Page for .NET]({{< relref "add-vertical-gradient-to-xps/_index.md" >}})
Learn how to enhance XPS documents with vertical gradients using Aspose.Page for .NET. Follow our step‑by‑step guide for seamless integration.

## Frequently asked questions

**Q: Can I use these gradient techniques in a commercial application?**  
A: Yes. Simply apply a valid Aspose.Page license for production use.

**Q: Are the gradient APIs the same for PS and XPS?**  
A: The API calls are identical; Aspose.Page abstracts the underlying format, letting you reuse the same code.

**Q: What if I need more than two colors in a gradient?**  
A: Aspose.Page supports multi‑stop gradients; you can define additional color stops programmatically.

**Q: Is there a performance impact when adding many gradients?**  
A: Gradients are rendered efficiently, but for very large documents consider batching drawing operations.

**Q: Where can I find the full API reference?**  
A: The official Aspose.Page for .NET API docs are available on the Aspose website.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Page for .NET latest release  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}