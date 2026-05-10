---
date: 2026-01-12
description: เรียนรู้วิธีบันทึกไฟล์ PostScript และสร้างเอกสาร PostScript ด้วย Aspose.Page
  สำหรับ .NET พร้อมประยุกต์ใช้การแปลงหลายแบบสำหรับกราฟิกแบบไดนามิก
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: บันทึกไฟล์ PostScript ด้วยการแปลงของ Aspose.Page (.NET)
url: /th/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกไฟล์ PostScript ด้วย Aspose.Page Transformations (.NET)

## บทนำ

ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **บันทึกไฟล์ PostScript** ขณะทำงานกับ Aspose.Page for .NET เราจะเดินผ่านการสร้างเอกสาร PostScript การใช้การแปลงหลายแบบเช่น การย้ายตำแหน่ง (translation), การปรับขนาด (scaling), การหมุน (rotation) และการบิด (shearing) และสุดท้ายบันทึกผลลัพธ์ เมื่อเสร็จแล้วคุณจะสามารถสร้างกราฟิกแบบไดนามิกโดยโปรแกรมได้อย่างมั่นใจและรู้ว่าต้องวางการแปลงแต่ละขั้นตอนไว้ที่ไหนใน graphics state

## คำตอบอย่างรวดเร็ว
- **ฉันสามารถสร้างอะไรได้?** เอกสาร PostScript ที่เต็มรูปแบบพร้อมกราฟิกที่แปลงแล้ว  
- **ต้องใช้ไลบรารีใด?** Aspose.Page for .NET (ดาวน์โหลดได้จากเว็บไซต์ทางการ)  
- **ฉันบันทึกไฟล์อย่างไร?** ใช้ `PsDocument.Save()` หลังจากกำหนด graphics state แล้ว  
- **สามารถใช้การแปลงหลายแบบได้หรือไม่?** ได้ – รวมกันด้วย `Transform` หรือเรียกต่อเนื่องกัน  
- **ต้องมีลิขสิทธิ์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการผลิต

## “การบันทึกไฟล์ postscript” คืออะไร?

การบันทึกไฟล์ PostScript หมายถึงการบันทึกคำสั่งวาดที่คุณสร้างไว้ในหน่วยความจำลงเป็นไฟล์ `.ps` บนดิสก์ ไฟล์นี้สามารถถูกเรนเดอร์โดยตัวแปล PostScript, เครื่องพิมพ์ หรือโปรแกรมดูไฟล์ใดก็ได้

## ทำไมต้องใช้ Aspose.Page for .NET เพื่อสร้างเอกสาร postscript?

Aspose.Page ให้ API ระดับสูงที่อิสระต่ออุปกรณ์และแยกความซับซ้อนของไวยากรณ์ PostScript คุณจะได้:

- วัตถุ C# ที่มีชนิดชัดเจนสำหรับ paths, brushes, และ transformations  
- การจัดการ graphics state stack (save/restore) อัตโนมัติ  
- การสนับสนุนเต็มรูปแบบสำหรับเมทริกซ์การแปลงที่ซับซ้อนโดยไม่ต้องคำนวณด้วยตนเอง  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ตรวจสอบว่าคุณมี:

- ไลบรารี **Aspose.Page for .NET** รวมอยู่ในโปรเจกต์ของคุณ ดาวน์โหลดจาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/page/net/)  
- โฟลเดอร์ที่สามารถเขียนไฟล์ได้สำหรับเก็บไฟล์ `.ps` ที่สร้างขึ้น แทนที่เส้นทางตัวอย่างในโค้ดด้วยไดเรกทอรีของคุณเอง

## นำเข้า Namespaces

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ตอนนี้มาดูแต่ละขั้นตอนของการแปลงกันทีละขั้นตอน

## ไม่มีการแปลง

### ขั้นตอนที่ 1: สร้าง Output Stream

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

โค้ดส่วนนี้สร้าง **เอกสาร PostScript** ที่มีสี่เหลี่ยมส้มสีเดียวและ **บันทึกไฟล์ PostScript** โดยไม่ใช้การแปลงใด ๆ

## การแปลตำแหน่ง (Translation)

### ขั้นตอนที่ 1: บันทึก Graphics State

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

การบันทึก graphics state ช่วยให้คุณสามารถย้อนกลับได้หลังจากย้ายวัตถุต่าง ๆ

### ขั้นตอนที่ 2: แปลตำแหน่ง Graphics State

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

การแปลตำแหน่งจะย้ายทุกอย่างที่วาดหลังจากคำสั่งนี้ไปทางขวา 250 หน่วย

### ขั้นตอนที่ 3: เติมสี่เหลี่ยมด้วยการแปลตำแหน่ง

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

ตอนนี้สี่เหลี่ยมสีน้ำเงินจะปรากฏห่างจากสี่เหลี่ยมส้ม 250 จุดทางขวา

### ขั้นตอนที่ 4: คืนค่า Graphics State

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

การคืนค่าสถานะจะทำให้ระบบพิกัดกลับไปยังตำแหน่งเดิม ดังนั้นการวาดต่อไปจะไม่ถูกกระทบจากการแปลตำแหน่ง

## การปรับขนาด (Scaling)

> *คุณสามารถทำตามรูปแบบเดียวกัน – บันทึกสถานะ, ใช้ `Scale`, วาด, แล้วคืนค่า*  
> **เคล็ดลับ:** ใช้การปรับขนาดไม่สม่ำเสมอ (`Scale(sx, sy)`) เพื่อยืดหรือหดวัตถุในทิศทางเดียว

## การหมุน (Rotation)

> *หมุนรอบจุดกำเนิดหรือจุดศูนย์กลางที่กำหนดเองโดยใช้ `Rotate(angle)`*  
> **เคล็ดลับ:** ผสาน `Translate` ก่อนการหมุนเพื่อหมุนรอบจุดที่ต้องการ

## การบิด (Shearing)

> *การบิด (`Shear(shx, shy)`) ทำให้รูปทรงเอียง เหมาะสำหรับเอฟเฟกต์อิตาลิก*  

## การแปลงเชิงซับซ้อน (Complex Transformations)

> *สำหรับสถานการณ์ขั้นสูง สร้าง `Matrix` ที่กำหนดเองและส่งให้ `Transform(matrix)`*  
> ที่นี่คุณ **ใช้การแปลงหลายแบบ** ในขั้นตอนเดียว

## สรุป

คุณได้เรียนรู้วิธี **บันทึกไฟล์ PostScript**, **สร้างเอกสาร PostScript**, และ **ใช้การแปลงหลายแบบ** ด้วย Aspose.Page for .NET ทดลองเปลี่ยนลำดับการแปลงต่าง ๆ ผสานเข้าด้วยกัน แล้วดูว่ากราฟิกของคุณเปลี่ยนแปลงอย่างไร

## คำถามที่พบบ่อย

**ถาม: ฉันจะใช้การแปลงหลายแบบกับวัตถุเดียวได้อย่างไร?**  
ตอบ: ใช้เมธอด `Transform` พร้อม `Matrix` ที่กำหนดเองซึ่งรวมการแปลตำแหน่ง, การปรับขนาด, การหมุน หรือการบิดตามลำดับที่ต้องการ

**ถาม: ฉันสามารถดูตัวอย่างการแปลงก่อนบันทึกเอกสารได้หรือไม่?**  
ตอบ: ได้ – เรนเดอร์ `PsDocument` เป็นภาพหรือใช้โปรแกรมดู PostScript เพื่อตรวจสอบผลลัพธ์ก่อนเรียก `Save()`

**ถาม: สามารถใช้การแปลงกับองค์ประกอบเฉพาะในเอกสารได้หรือไม่?**  
ตอบ: แน่นอน บันทึก graphics state ก่อนวาดองค์ประกอบนั้น, ใช้การแปลงที่ต้องการ, วาด, แล้วคืนค่า state

**ถาม: มีข้อพิจารณาด้านประสิทธิภาพเมื่อทำงานกับการแปลงเชิงซับซ้อนหรือไม่?**  
ตอบ: เมทริกซ์ที่ซับซ้อนจะเพิ่มภาระงานของ CPU ควรทำให้การแปลงง่ายที่สุดเท่าที่จะทำได้และใช้ state ที่บันทึกไว้ซ้ำเมื่อวาดวัตถุที่คล้ายกันหลายครั้ง

**ถาม: ฉันจะขอรับการสนับสนุนหรือความช่วยเหลือเกี่ยวกับ Aspose.Page ได้อย่างไร?**  
ตอบ: เยี่ยมชม [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อขอความช่วยเหลือจากชุมชน หรือ ติดต่อฝ่ายสนับสนุนของ Aspose โดยตรง

---

**อัปเดตล่าสุด:** 2026-01-12  
**ทดสอบกับ:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}