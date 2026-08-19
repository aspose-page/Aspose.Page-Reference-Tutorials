---
date: 2026-03-03
description: เรียนรู้วิธีใช้ Aspose.Page สำหรับ .NET เพื่อจัดเรียงภาพแบบต่อกันในเอกสาร
  XPS คู่มือขั้นตอนนี้จะแสดงวิธีจัดเรียงภาพอย่างมีประสิทธิภาพและเพิ่มความสวยงามให้กับภาพ
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: วิธีใช้ Aspose.Page เพื่อเพิ่มภาพแบบต่อกระเบื้องในเอกสาร XPS
url: /th/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ Aspose.Page เพื่อเพิ่มภาพแบบต่อกันในเอกสาร XPS

## Introduction

หากคุณกำลังสงสัย **วิธีใช้ Aspose** เพื่อให้ไฟล์ XPS ของคุณมีสไตล์ภาพที่หลากหลายยิ่งขึ้น คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายขั้นตอนที่จำเป็นเพื่อ **ทำภาพเป็นลายต่อกัน** ภายในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET. เมื่อเสร็จคุณจะได้โค้ดสั้นที่สามารถนำไปใช้ในโปรเจกต์ .NET ใดก็ได้เพื่อสร้างกราฟิกภาพต่อกันแบบเรียลไทม์.

## Quick Answers
- **What library is needed?** Aspose.Page for .NET  
- **Which method creates the tiled brush?** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **Can I control opacity?** Yes – set `path.Fill.Opacity` (e.g., 0.5f)  
- **Do I need a license for testing?** A temporary license works for evaluation; a full license is required for production.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## What is Aspose.Page and Why Tile Images?

Aspose.Page เป็น API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสร้าง แก้ไข และเรนเดอร์ XPS, PDF และรูปแบบหน้าอื่น ๆ ได้โดยไม่ต้องพึ่งพา Microsoft Office การทำภาพเป็นลายต่อกัน—การทำซ้ำบิตแมพบนรูปทรง—ช่วยให้คุณเติมพื้นที่ขนาดใหญ่ด้วยลวดลาย, ลายน้ำ, หรือพื้นหลังโดยคงขนาดไฟล์ให้เล็กลง.

## How to Use Aspose.Page to Tile Images in XPS Documents

Below you’ll find a complete, ready‑to‑run example. Each step is explained in plain language before the corresponding code block, so you can see **why** each line matters.

### Prerequisites

- **Aspose.Page for .NET** – download and reference the library from the official site [ที่นี่](https://reference.aspose.com/page/net/).  
- **Development environment** – Visual Studio (any edition) or another .NET IDE you prefer.

### Import Namespaces

First, bring the required namespaces into scope so the compiler knows where to find the XPS classes.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Step 1: Define the Document Directory

Specify where the generated XPS file and source image will live. Replace the placeholder with an actual folder on your machine.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Step 2: Create a New XPS Document

Instantiate an empty XPS document that will hold the tiled graphic.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Step 3: Add a Tiled Image

Here we create a rectangular path, fill it with an `ImageBrush`, and set the brush to tile mode. The `TileMode` property tells the engine to repeat the image both horizontally and vertically. Adjust the rectangle coordinates or the source image as needed for your scenario.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Step 4: Save the Resultant XPS Document

Finally, write the document to disk. The output file can be opened with any XPS viewer or further processed with Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Common Issues & Tips

- **Path errors** – Ensure `dataDir` ends with a trailing slash or use `Path.Combine` to avoid missing‑separator problems.  
- **Image size mismatches** – The source image should be large enough for the tiling area; otherwise the pattern may appear stretched.  
- **Opacity not visible** – Some viewers ignore opacity on XPS; test with a viewer that fully supports XPS rendering (e.g., XPS Viewer on Windows).

## Frequently Asked Questions

### Q1: Is Aspose.Page compatible with all .NET development environments?
A: Yes, Aspose.Page works with Visual Studio, Rider, VS Code, and any IDE that supports .NET.

### Q2: Can I adjust the opacity of the tiled image?
A: Absolutely. The example sets `path.Fill.Opacity = 0.5f;`—you can change the float value between 0 (transparent) and 1 (opaque).

### Q3: Are there other tile modes available in Aspose.Page for .NET?
A: Yes. Besides `XpsTileMode.Tile`, you can use `FlipX`, `FlipY`, and `FlipXY` to create mirrored patterns.

### Q4: How do I handle temporary licenses for Aspose.Page?
A: Refer to the [temporary license](https://purchase.aspose.com/temporary-license/) page on the Aspose website for details on obtaining and applying a trial license.

### Q5: Where can I seek help or connect with the Aspose.Page community?
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to ask questions, share snippets, and learn from other developers.

### Q6: Can I use this approach to create a watermark effect?
A: Yes. By lowering the opacity and choosing a semi‑transparent image, the tiled brush works perfectly as a repeating watermark.

## Conclusion

You now know **how to use Aspose** to add a tiled image to an XPS document, control its opacity, and save the result for further use. This technique is ideal for background patterns, watermarks, or any situation where a repeating graphic adds visual interest without inflating file size. Feel free to experiment with different shapes, images, and tile modes to suit your project’s needs.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}