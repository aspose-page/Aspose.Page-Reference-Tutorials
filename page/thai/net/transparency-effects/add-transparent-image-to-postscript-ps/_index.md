---
date: 2026-03-26
description: เรียนรู้วิธีสร้างเอกสาร PostScript ด้วย .NET และเพิ่มภาพที่โปร่งใสโดยใช้
  Aspose.Page คู่มือขั้นตอนต่อขั้นตอนนี้ครอบคลุมข้อกำหนดเบื้องต้น โค้ด และเคล็ดลับ
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: สร้างเอกสาร PostScript ด้วย .NET พร้อมภาพโปร่งใส (Aspose.Page)
url: /th/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร PostScript .NET พร้อมภาพโปร่งแสง (Aspose.Page)

## Introduction

ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีสร้างเอกสาร PostScript .NET** และฝังไฟล์ PNG โปร่งแสงโดยใช้ Aspose.Page for .NET การเพิ่มภาพโปร่งแสงช่วยให้คุณสร้างกราฟิกหลายชั้นที่สมบูรณ์แบบสำหรับลายน้ำ, การซ้อนทับ, หรือการจำลอง UI ภายในไฟล์ PS เราจะอธิบายทุกขั้นตอน ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการเรนเดอร์ภาพที่ทึบและโปร่งแสง

## Quick Answers
- **Aspose.Page ทำอะไร?** มันให้ API ที่ครบถ้วนสำหรับการสร้าง, แก้ไข, และเรนเดอร์เอกสาร PostScript (PS) และ XPS ใน .NET.  
- **ฉันสามารถเพิ่ม PNG โปร่งแสงได้หรือไม่?** ได้ — ใช้ `DrawTransparentImage` เพื่อควบคุมความทึบแสง.  
- **เวอร์ชัน .NET ใดที่รองรับ?** ทั้งหมดของ .NET Framework, .NET Core, และ .NET 5/6 ล่าสุด.  
- **ฉันต้องการไลเซนส์หรือไม่?** รุ่นทดลองใช้งานฟรีสำหรับการประเมิน; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน.

## Prerequisites

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- **Aspose.Page for .NET** – ดาวน์โหลดได้จาก [download link](https://releases.aspose.com/page/net/).  
- โฟลเดอร์ที่คุณจะเก็บเอกสาร PS และภาพที่ต้องการฝัง.  
- ไฟล์ PNG โปร่งแสง (เช่น `mask1.png`) ที่จะใช้เป็นชั้นโปร่งแสง.

## Import Namespaces

ก่อนอื่นให้ทำการนำเข้า namespace ที่มีคลาสที่เราต้องการใช้ ซึ่งจะทำให้เราสามารถเข้าถึงโมเดลเอกสาร PS, ยูทิลิตี้กราฟิก, และประเภทการวาดพื้นฐานของ .NET.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Your Document Directory

กำหนดเส้นทางที่ไฟล์ภาพต้นฉบับและไฟล์ PS ผลลัพธ์จะอยู่ แทนที่ placeholder ด้วยเส้นทางจริงบนเครื่องของคุณ.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream for PostScript Document

เราจะเขียนเนื้อหา PS ที่สร้างขึ้นลงในไฟล์สตรีม สตรีมนี้จะถูกส่งต่อไปยังคอนสตรัคเตอร์ของ `PsDocument` ในขั้นตอนต่อไป.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## Step 3: Set Save Options and Background Color

กำหนดค่า `PsSaveOptions` เพื่อระบุวิธีการบันทึกไฟล์ การตั้งค่าสีพื้นหลังเป็นประโยชน์เมื่อคุณต้องการแคนวาสสีทึบอยู่ด้านหลังองค์ประกอบโปร่งแสง.

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## Step 4: Create a New 1‑Paged PS Document

สร้างเอกสารโดยใช้สตรีมและตัวเลือกที่กำหนดไว้ข้างต้น ธง `false` บอก Aspose.Page ไม่ให้ปิดสตรีมโดยอัตโนมัติ.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Write Graphics Save and Translate

ก่อนการวาด เราจะบันทึกสถานะกราฟิกปัจจุบันและแปลตำแหน่งต้นกำเนิดเพื่อให้ภาพของเราปรากฏที่ตำแหน่งที่ต้องการบนหน้า.

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## How to add transparent image to a PostScript document

### Step 6: Add Opaque RGB Image

แรกเราจะเพิ่ม PNG เดียวกันเป็นภาพทึบปกติ ซึ่งจะแสดงความแตกต่างของภาพเมื่อเรานำความโปร่งแสงมาใช้ในขั้นตอนต่อไป.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### Step 7: Add Transparent Image

ต่อมาเราจะใช้ `DrawTransparentImage` เพื่อเรนเดอร์ PNG ด้วยค่าความทึบแสง พารามิเตอร์ที่สาม (`255`) แทนความทึบเต็ม; ค่าที่ต่ำกว่าจะทำให้ภาพโปร่งแสงมากขึ้น นี่คือจุดที่เราจะ **ตั้งค่าความโปร่งแสงของภาพใน .NET**.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **Pro tip:** เพื่อทำให้ภาพโปร่งแสง 50 % ให้ส่งค่า `128` แทน `255`.

## Step 8: Write Graphics Restore and Close Page

หลังการวาด เราจะคืนสถานะกราฟิกก่อนหน้าและปิดหน้าเพื่อสรุปเนื้อหา.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Step 9: Save the Document

สุดท้ายบันทึกไฟล์ PS ลงดิสก์.

```csharp
document.Save();
```

โดยทำตามขั้นตอนเหล่านี้คุณได้ **สร้างเอกสาร PostScript .NET** ที่มีทั้งภาพทึบและภาพโปร่งแสง แสดงวิธี **วาดภาพโปร่งแสงด้วย C#** ด้วย Aspose.Page.

## Why use Aspose.Page for transparency effects?

- **Full control** over graphics state, matrices, and opacity levels.  
- **No external dependencies**—everything runs inside pure .NET code.  
- **Cross‑platform** support lets you generate PS files on Windows, Linux, or macOS.

## Common Pitfalls & Troubleshooting

| ปัญหา | วิธีแก้ |
|-------|----------|
| Image appears fully opaque even after `DrawTransparentImage` | Ensure the alpha value (third argument) is less than `255`. |
| PS file shows a blank page | Verify that the background color is set and that the stream path is correct. |
| Exception “File not found” | Double‑check `dataDir` and that `mask1.png` exists in that folder. |

## Frequently Asked Questions

**Q: ฉันสามารถใช้รูปแบบภาพอื่นนอกจาก PNG สำหรับความโปร่งแสงได้หรือไม่?**  
A: ใช่ — Aspose.Page รองรับ PNG, GIF, และ TIFF สำหรับการเรนเดอร์โปร่งแสง.

**Q: Aspose.Page รองรับ .NET framework เวอร์ชันล่าสุดหรือไม่?**  
A: แน่นอน. ไลบรารีนี้อัปเดตเป็นประจำสำหรับ .NET 6, .NET 7 และรุ่นใหม่กว่า.

**Q: ฉันสามารถนำความโปร่งแสงไปใช้กับเอกสาร PS ที่มีอยู่แล้วได้หรือไม่?**  
A: ได้. เปิดเอกสารด้วย `PsDocument`, เพิ่มหน้าใหม่หรือแก้ไขหน้าที่มีอยู่, แล้วใช้วิธี `DrawTransparentImage` เดิม.

**Q: ข้อได้เปรียบของ Aspose.Page เมื่อเทียบกับไลบรารีกราฟิกทั่วไปคืออะไร?**  
A: มันถูกออกแบบมาเฉพาะสำหรับ PS/XPS, ให้การควบคุมที่แม่นยำต่อกราฟิกเวกเตอร์, ฟอนต์, และการจัดการภาพโดยไม่ต้องใช้เอนจินเรนเดอร์เต็มรูปแบบ.

**Q: มีขีดจำกัดของระดับความโปร่งแสงที่ฉันสามารถตั้งค่าได้หรือไม่?**  
A: ไม่มี. คุณสามารถระบุค่าอัลฟาใดก็ได้ตั้งแต่ `0` (โปร่งแสงเต็ม) ถึง `255` (ทึบเต็ม).

## Conclusion

เราได้สาธิตวิธี **สร้างเอกสาร PostScript .NET** และฝังภาพทั้งแบบทึบและโปร่งแสงโดยใช้ Aspose.Page เทคนิคนี้เปิดประตูสู่การออกแบบเอกสารที่ซับซ้อน, การใส่ลายน้ำ, และกราฟิกหลายชั้น—ทั้งหมดสร้างขึ้นโดยโปรแกรมจาก C#.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}