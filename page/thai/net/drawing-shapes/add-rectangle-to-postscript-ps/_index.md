---
date: 2026-01-18
description: เรียนรู้วิธีสร้างเอกสาร PostScript ด้วย .NET และเพิ่มสี่เหลี่ยมโดยใช้
  Aspose.Page for .NET คู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ด
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: สร้างเอกสาร PostScript .NET – เพิ่มสี่เหลี่ยมด้วย Aspose.Page
url: /th/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มสี่เหลี่ยมผืนผ้าใน PostScript (PS) ด้วย Aspose.Page สำหรับ .NET

## Introduction

หากคุณกำลังมองหา **สร้างเอกสาร postscript ด้วย .NET** Aspose.Page ให้โซลูชันที่ทรงพลังสำหรับการจัดการไฟล์ PostScript ในบทแนะนำนี้ เราจะพาคุณผ่านขั้นตอนการเพิ่มสี่เหลี่ยมผืนผ้าในเอกสาร PostScript ด้วย Aspose.Page สำหรับ .NET เพื่อให้คุณมีพื้นฐานที่มั่นคงสำหรับการสร้างกราฟิกที่ซับซ้อนยิ่งขึ้น.

## Quick Answers
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for .NET.
- **ฉันสามารถสร้างเอกสาร PostScript ตั้งแต่เริ่มต้นได้หรือไม่?** ใช่ – the API lets you build PS files programmatically.
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **ฉันต้องการลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** A free trial works for testing; a license is required for production.
- **การดำเนินการใช้เวลานานเท่าไหร่?** Typically under 10 minutes for basic shapes.

## What is creating a postscript document .net?
การสร้างเอกสาร PostScript ใน .NET หมายถึงการสร้างไฟล์ .ps ด้วยโปรแกรมที่อธิบายเนื้อหาของหน้า—ข้อความ, กราฟิก หรือรูปทรง—โดยใช้ Aspose.Page API วิธีนี้เหมาะสำหรับการสร้างกราฟิกบนเซิร์ฟเวอร์, การสร้างรายงานอัตโนมัติ, หรือสถานการณ์ใด ๆ ที่คุณต้องการควบคุมรูปแบบผลลัพธ์อย่างแม่นยำ.

## Why use Aspose.Page for .NET?
- **ควบคุมกราฟิกได้เต็มที่** – draw shapes, set colors, and apply strokes without dealing with low‑level PS syntax.
- **ข้ามแพลตฟอร์ม** – works on Windows, Linux, and macOS runtimes.
- **ไม่มีการพึ่งพาภายนอก** – the library handles all PS generation internally.
- **เอกสารและตัวอย่างที่ครบถ้วน** – get up‑and‑running quickly.

## Prerequisites

- **Aspose.Page for .NET Library** – download and install from [here](https://releases.aspose.com/page/net/).
- **Development Environment** – Visual Studio, VS Code, or any .NET‑compatible IDE.

## Import Namespaces

Before you start coding, import the namespaces that expose the required classes:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Now let’s break the example into clear, numbered steps.

## Step 1: Set up Your Document Directory

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` with the folder where you want the resulting PS file saved.

## Step 2: Create Output Stream for the PostScript Document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

This stream points to **AddRectangle_outPS.ps**. Feel free to rename the file or change the location as needed.

## Step 3: Set Save Options and Create the PS Document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Here we tell Aspose.Page to use an A4 page size and create a single‑page document.

## Step 4: Add a Filled Rectangle

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

We define a rectangle at (250, 100) with width 150 and height 100, set an orange brush, and fill the shape.

## Step 5: Add an Outlined Rectangle

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

A second rectangle is created lower on the page, this time with a red 3‑point stroke.

## Step 6: Close the Page and Save the Document

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Closing the page finalizes the drawing, and `Save()` writes the PS file to disk.

## Common Issues & Tips

- **เส้นทางไฟล์ไม่ถูกต้อง** – Ensure `dataDir` ends with a path separator (`\\` or `/`) or use `Path.Combine`.
- **ไม่มีลิขสิทธิ์** – In a production environment, apply your Aspose license before creating the document to avoid evaluation watermarks.
- **การมองเห็นสี** – If the rectangle appears blank, verify that the brush or pen colors contrast with the page background.

## Frequently Asked Questions

**Q:** ฉันสามารถปรับแต่งสีของสี่เหลี่ยมได้หรือไม่?  
**A:** Absolutely. Change the `Color.Orange` or `Color.Red` values in the `SolidBrush` and `Pen` constructors to any `System.Drawing.Color` you prefer.

**Q:** Aspose.Page รองรับรูปแบบเอกสารอื่นหรือไม่?  
**A:** Yes. Besides PostScript, Aspose.Page also supports XPS and EPS generation.

**Q:** ฉันจะเพิ่มข้อความในเอกสารเดียวกันได้อย่างไร?  
**A:** Use the `TextFragment` class to place text at desired coordinates, then call `document.Draw(textFragment)`.

**Q:** ฉันจะหา ตัวอย่างเพิ่มเติมและอ้างอิง API เต็มรูปแบบได้จากที่ไหน?  
**A:** Explore the documentation [here](https://reference.aspose.com/page/net/) and join the community at the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** ฉันสามารถทดลองใช้ Aspose.Page ก่อนซื้อได้หรือไม่?  
**A:** Yes, download a free trial [here](https://releases.aspose.com/). For extended evaluation, consider a [temporary license](https://purchase.aspose.com/temporary-license/).

---

**อัปเดตล่าสุด:** 2026-01-18  
**ทดสอบด้วย:** Aspose.Page 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}