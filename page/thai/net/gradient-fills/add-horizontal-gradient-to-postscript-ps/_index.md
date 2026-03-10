---
date: 2026-02-25
description: เสริมเอกสาร PostScript ด้วยสี่เหลี่ยมไล่สีเชิงเส้นโดยใช้ Aspose.Page
  สำหรับ .NET. ตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อเรียนรู้การเติมสีไล่สีในข้อความและการไล่สีเส้นขอบข้อความ.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: เพิ่มสี่เหลี่ยมผืนผ้ากราดิเอนท์เชิงเส้นใน PostScript (PS) ด้วย Aspose.Page
url: /th/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

.

Let's produce final translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มสี่เหลี่ยมกราดเชิงเส้นใน PostScript (PS) ด้วย Aspose.Page

## Introduction

ยินดีต้อนรับสู่บทแนะนำแบบครบถ้วนนี้เกี่ยวกับการเพิ่ม **สี่เหลี่ยมกราดเชิงเส้น** ลงในเอกสาร PostScript (PS) ด้วย Aspose.Page สำหรับ .NET Aspose.Page เป็นไลบรารีที่ทรงพลังซึ่งช่วยให้คุณสร้าง, แก้ไข, และเรนเดอร์เอกสารในรูปแบบต่าง ๆ ได้หลายรูปแบบ และในวันนี้เราจะมุ่งเน้นไปที่การนำกราดสีที่ดึงดูดสายตาเข้าสู่ไฟล์ PS ของคุณ

### Quick Answers
- **สี่เหลี่ยมกราดเชิงเส้นทำหน้าที่อะไร?** มันเติมพื้นที่สี่เหลี่ยมด้วยการเปลี่ยนสีอย่างราบรื่นจากด้านหนึ่งไปยังอีกด้านหนึ่ง  
- **API ใดจัดการการเติมข้อความด้วยกราด?** `LinearGradientBrush` ร่วมกับ `SetPaint` และ `FillAndStrokeText`  
- **ฉันสามารถทำขอบข้อความด้วยกราดได้หรือไม่?** ได้ — ใช้ `SetStroke` กับแปรงกราดและเรียก `OutlineText`  
- **ต้องใช้ไลเซนส์สำหรับการผลิตหรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์ของ Aspose.Page สำหรับการใช้งานที่ไม่ใช่การประเมินผล  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7

## Prerequisites

ก่อนที่เราจะเริ่มต้น โปรดตรวจสอบว่าคุณมี:

- Aspose.Page for .NET Library: ตรวจสอบให้แน่ใจว่าไลบรารีถูกอ้างอิงในโปรเจกต์ของคุณ คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/)  
- Document Directory: สร้างโฟลเดอร์บนดิสก์ที่ไฟล์ PS ที่สร้างขึ้นจะถูกบันทึกและแทนที่ **“Your Document Directory”** ในโค้ดด้วยเส้นทางนั้น

## Import Namespaces

เพื่อเริ่มต้น ให้นำเข้า namespace ที่ให้คุณเข้าถึงคลาสการวาดและคลาสเฉพาะของ PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## What Is a Linear Gradient Rectangle?

**สี่เหลี่ยมกราดเชิงเส้น** คือรูปสี่เหลี่ยมที่ภายในถูกทาด้วยกราดเชิงเส้น — สีจะเปลี่ยนอย่างราบรื่นตามเส้นตรงหนึ่งเส้น โดยทั่วไปจากซ้ายไปขวา (แนวนอน) หรือจากบนลงล่าง (แนวตั้ง) ใน Aspose.Page คุณทำได้โดยการผสาน `GraphicsPath` ที่กำหนดสี่เหลี่ยมกับ `LinearGradientBrush` ที่อธิบายการเปลี่ยนสี

## Why Use Gradient Fill Text and Outline Text Gradient?

- **ความสวยงาม:** ข้อความที่เติมด้วยกราดเพิ่มความลึกและสไตล์สมัยใหม่ให้กับรายงาน, ใบแจ้งหนี้, หรือสื่อส่งเสริมการขาย  
- **ความสอดคล้องของแบรนด์:** สามารถจับคู่สีขององค์กรด้วยค่า ARGB ที่แม่นยำ  
- **ความหลากหลาย:** แปรงเดียวสามารถนำไปใช้ซ้ำได้สำหรับการเติมรูปทรง, การเติมข้อความ, และกราดขอบข้อความ ลดการทำซ้ำโค้ด

## Step 1: Set Up the Document

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 2: Define Gradient Rectangle and Colors

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Step 3: Set Transform for Brush

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Step 4: Set Paint and Fill the Rectangle

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## How to Apply Gradient Fill Text

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Using Outline Text Gradient

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Step 7: Close the Current Page and Save the Document

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Congratulations! You've successfully added a **linear gradient rectangle** to a PostScript document and used the same brush for **gradient fill text** and an **outline text gradient**.

ขอแสดงความยินดี! คุณได้เพิ่ม **สี่เหลี่ยมกราดเชิงเส้น** ลงในเอกสาร PostScript อย่างสำเร็จและใช้แปรงเดียวกันสำหรับ **การเติมข้อความด้วยกราด** และ **กราดขอบข้อความ** แล้ว

## Common Use Cases & Tips

- **หัวข้อรายงาน:** เติมข้อความบล็อกขนาดใหญ่ด้วยกราดเพื่อเน้นหัวข้อส่วน  
- **โลโก้แบรนด์:** สร้างรูปโลโก้ด้วยรูปทรงที่เติมกราดเพื่อความสอดคล้องของแบรนด์  
- **Pro Tip:** ใช้ `LinearGradientBrush` ตัวเดียวกันซ้ำหลายครั้งสำหรับการวาดเพื่อให้สีสอดคล้องกันอย่างสมบูรณ์ระหว่างรูปทรงและข้อความ

## Frequently Asked Questions

### Q1: Can I apply gradients to other shapes besides rectangles?
**A:** Yes, you can apply gradients to any shape defined by a `GraphicsPath`. Simply add circles, polygons, or custom paths before calling `document.Fill(path)`.

### Q2: How can I change the gradient colors?
**A:** Modify the `Color.FromArgb` values when constructing `LinearGradientBrush`. The first color is the start, the second is the end of the gradient.

### Q3: Is Aspose.Page compatible with different document formats?
**A:** Absolutely. Aspose.Page supports XPS, PS, PDF, and several other vector formats. Check the official docs for the full list.

### Q4: Can I use Aspose.Page for commercial projects?
**A:** Yes, commercial licensing is available. See the purchase page for details: [here](https://purchase.aspose.com/buy).

### Q5: Where can I find community support?
**A:** Join the Aspose.Page community forum: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}