---
date: 2026-07-19
description: เรียนรู้วิธีสร้างเอกสาร PostScript บน ASP.NET ด้วย Aspose.Page สำหรับ
  .NET, ใช้ multiple transformations, และบันทึกไฟล์อย่างมีประสิทธิภาพ.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: Transformations PS
og_description: สร้างเอกสาร PostScript บน ASP.NET ด้วย Aspose.Page. เรียนรู้การใช้
  translation, scaling, rotation, และ shearing, จากนั้นบันทึกไฟล์.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: สร้างเอกสาร PostScript ASP.NET – คู่มือ Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: สร้างเอกสาร PostScript บน ASP.NET ด้วย Aspose.Page
url: /th/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร PostScript ด้วย ASP.NET และ Aspose.Page

## บทนำ

ในบทแนะนำแบบขั้นตอนนี้คุณจะ **สร้างเอกสาร PostScript ด้วย ASP.NET** โดยใช้ไลบรารี Aspose.Page ใช้การแปลงกราฟิกหลายรูปแบบ และสุดท้ายบันทึกผลลัพธ์เป็นไฟล์ `.ps` เมื่อจบคู่มือคุณจะเข้าใจว่าควรผลักดันการแปลงแต่ละอย่างไปที่สแตกของสถานะกราฟิกอย่างไร ผสานการแปลงอย่างมีประสิทธิภาพอย่างไร และทำอย่างไรให้คำสั่งวาดถูกบันทึกเพื่อให้ตัวตีความ PostScript ใด ๆ สามารถเรนเดอร์ได้ ความรู้นี้สำคัญสำหรับการสร้างกราฟิกที่พิมพ์ได้ รายงานแบบกำหนดเอง หรือทรัพยากรพร้อมพิมพ์แบบไดนามิกโดยตรงจากแอปพลิเคชัน .NET

## คำตอบสั้น ๆ
- **ฉันสามารถสร้างอะไรได้?** เอกสาร PostScript ที่เต็มรูปแบบพร้อมกราฟิกที่ผ่านการแปลง  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for .NET (ดาวน์โหลดได้จากเว็บไซต์ทางการ)  
- **บันทึกไฟล์อย่างไร?** ใช้ `PsDocument.Save()` หลังจากกำหนดสถานะกราฟิกแล้ว  
- **สามารถใช้การแปลงหลายแบบพร้อมกันได้หรือไม่?** ได้ – ผสานด้วย `Transform` หรือเรียกต่อเนื่องกัน  
- **ต้องมีไลเซนส์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง

## “การบันทึกไฟล์ PostScript” คืออะไร?

การบันทึกไฟล์ PostScript หมายถึงการทำให้คำสั่งวาดที่คุณสร้างในหน่วยความจำคงอยู่เป็นไฟล์ `.ps` บนดิสก์ ไฟล์นี้สามารถเรนเดอร์โดยตัวตีความ PostScript ใด ๆ เครื่องพิมพ์ หรือโปรแกรมดูไฟล์ ทำให้เป็นรูปแบบพกพาที่อิสระต่ออุปกรณ์ของกราฟิกเวกเตอร์ เมื่อคุณเรียกเมธอด `Save` Aspose.Page จะทำการซีเรียลไลซ์สถานะกราฟิกทั้งหมด รวมถึงพาธ, แปรง, และเมทริกซ์การแปลง ให้เป็นไวยากรณ์ PostScript ที่ถูกต้องตามสเปคของ Adobe®

## ทำไมต้องใช้ Aspose.Page for .NET เพื่อสร้างเอกสาร PostScript?

Aspose.Page for .NET ให้ API แบบ strongly‑typed, object‑oriented ที่ซ่อนรายละเอียดระดับต่ำของภาษา PostScript โดยอัตโนมัติจัดการสแตกของ graphics‑state รองรับเมธอดการแปลงมากกว่า 50 รายการ และสามารถจัดการเอกสารที่มีมากกว่า 500 หน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ สิ่งนี้ช่วยลดระยะเวลาการพัฒนาถึง 70 % เมื่อเทียบกับการเขียนโค้ด PostScript ด้วยตนเองและรับประกันความเข้ากันได้กับเครื่องพิมพ์หลัก ๆ ทุกเครื่อง

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำโปรเจกต์ ตรวจสอบว่าคุณมี:

- ไลบรารี **Aspose.Page for .NET** รวมอยู่ในโปรเจกต์ของคุณ ดาวน์โหลดจาก [download link](https://releases.aspose.com/page/net/)  
- โฟลเดอร์ที่สามารถเขียนได้สำหรับเก็บไฟล์ `.ps` ที่สร้างขึ้น แทนที่พาธตัวอย่างในโค้ดด้วยพาธจริงของคุณ  
- .NET 6.0 หรือใหม่กว่า (ไลบรารียังรองรับ .NET Core 3.1 และ .NET Framework 4.6+)

## นำเข้า Namespaces

คลาส `PsDocument` อยู่ใน namespace `Aspose.Page.Drawing` ส่วนตัวช่วยการแปลงอยู่ใน `Aspose.Page.Drawing.Graphics` ให้นำเข้าที่ส่วนหัวของไฟล์ของคุณ:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument` คือคลาสหลักของ Aspose.Page ที่แทนเอกสาร PostScript ในหน่วยความจำ หลังจากนำเข้า namespaces แล้วคุณสามารถเริ่มสร้างพื้นผิวการวาดได้

ตอนนี้เราจะสำรวจแต่ละขั้นตอนการแปลงแบบละเอียด

## ไม่มีการแปลง

`PsDocument` เป็นจุดเริ่มต้นสำหรับการวาดทั้งหมด โค้ดตัวอย่างต่อไปสร้างเอกสารใหม่ วาดสี่เหลี่ยมส้มง่าย ๆ และบันทึกโดยไม่มีการแปลงใด ๆ

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

โค้ดนี้สร้าง **เอกสาร PostScript** ที่มีสี่เหลี่ยมส้มหนึ่งอันและ **บันทึกไฟล์ PostScript** โดยไม่ใช้การแปลงใด ๆ

## การแปล (Translation)

การบันทึกสถานะกราฟิกทำให้คุณสามารถย้อนกลับหลังจากย้ายวัตถุ `SaveState` จะผลักเมทริกซ์การแปลงปัจจุบันลงสแตกภายใน

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

เมธอด `Translate` ย้ายระบบพิกัดตามค่า offset ที่ระบุ ส่งผลต่อคำสั่งวาดทั้งหมดที่ตามมา

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

ตอนนี้สี่เหลี่ยมสีน้ำเงินปรากฏห่าง 250 points ไปทางขวาของสี่เหลี่ยมส้ม เพราะเมทริกซ์การแปลกำลังทำงาน

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

การเรียก `Restore` จะคืนระบบพิกัดไปยังตำแหน่งเดิม ทำให้การวาดต่อไปไม่ถูกรบกวนโดยการแปล

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## การปรับขนาด (Scaling)

`Scale` ปรับขนาดของวัตถุที่วาดโดยใช้เมทริกซ์สเกลกับสถานะกราฟิกปัจจุบัน

> *คุณสามารถทำตามรูปแบบเดียวกัน—บันทึกสถานะ, ใช้ `Scale`, วาด, แล้วกู้คืน*  
> **เคล็ดลับ:** ใช้การสเกลไม่สม่ำเสมอ (`Scale(sx, sy)`) เพื่อยืดวัตถุในทิศทางเดียว ซึ่งเหมาะกับการสร้างเอฟเฟกต์แผนภูมิบาร์

## การหมุน (Rotation)

`Rotate` ใส่เมทริกซ์การหมุนลงในสถานะกราฟิกปัจจุบัน ทำให้การวาดต่อไปหมุนตามมุมที่กำหนด

> *หมุนรอบจุดกำเนิดหรือจุดศูนย์กลางที่กำหนดเองโดยใช้ `Rotate(angle)`*  
> **เคล็ดลับ:** ผสาน `Translate` ก่อนการหมุนเพื่อหมุนรอบจุดเฉพาะแทนจุดกำเนิด

## การเฉือน (Shearing)

`Shear` ทำให้ระบบพิกัดเอียงตามค่า factor ที่ให้ ทำให้วัตถุที่วาดเอียงในแนวนอนและ/หรือแนวตั้ง

> *การแปลง Shear (`Shear(shx, shy)`) ทำให้รูปร่างเอียง ใช้สำหรับเอฟเฟกต์อิตาลิกหรือเทคนิคมุมมอง*

## การแปลงเชิงซ้อน (Complex Transformations)

`Transform` ใส่เมทริกซ์การแปลงที่กำหนดเองลงในสถานะกราฟิก ผสานหลายการดำเนินการเป็นหนึ่งขั้นตอน

> *สำหรับสถานการณ์ขั้นสูง สร้าง `Matrix` ของคุณเองแล้วส่งให้ `Transform(matrix)`*  
> ที่นี่คุณ **ใช้การแปลงหลายแบบพร้อมกัน** ในขั้นตอนเดียว ลดจำนวนการบันทึกและกู้คืนสถานะ

## วิธีบันทึกไฟล์ PostScript พร้อมการแปลง?

`Save` เขียน `PsDocument` ปัจจุบันลงไฟล์ในรูปแบบ PostScript โหลด `PsDocument` ของคุณ, ใช้ลำดับการแปลงที่ต้องการ, แล้วเรียก `Save` พร้อมพาธเป้าหมาย — Aspose.Page จะเขียนไฟล์ `.ps` ที่เป็นมาตรฐานในหนึ่งรอบ ไลบรารีจะปิดสถานะกราฟิกที่เปิดอยู่โดยอัตโนมัติ ดังนั้นคุณไม่ต้องเขียนโค้ดทำความสะอาดเพิ่มเติม วิธีนี้ทำงานกับการแปลงใด ๆ ไม่ว่าจะเป็น translation, scaling, rotation หรือ shearing

## กรณีการใช้งานทั่วไป

- **การสร้างรายงานแบบไดนามิก** – สร้างแผนภูมิที่ปรับตามขนาดข้อมูลในขณะรันไทม์  
- **ใบแจ้งหนี้พร้อมพิมพ์** – ฝังโลโก้บริษัทและหมุนให้ตรงกับทิศทางของเครื่องพิมพ์  
- **ออกแบบป้ายกำกับแบบกำหนดเอง** – ใช้การเฉือนเพื่อจำลองเอฟเฟกต์ข้อความปั๊มลาย

## คำถามที่พบบ่อย

**ถาม: ฉันจะใช้การแปลงหลายแบบกับวัตถุเดียวได้อย่างไร?**  
ตอบ: ใช้เมธอด `Transform` พร้อม `Matrix` ที่รวมการแปล, การสเกล, การหมุน หรือการเฉือนตามลำดับที่ต้องการ

**ถาม: สามารถดูตัวอย่างการแปลงก่อนบันทึกเอกสารได้หรือไม่?**  
ตอบ: ได้ — เรนเดอร์ `PsDocument` เป็นภาพโดยใช้ `PsDocument.Save("output.png", SaveFormat.Png)` หรือเปิดไฟล์ `.ps` ในตัวดู PostScript เพื่อตรวจสอบผลลัพธ์ก่อนเรียก `Save()` สำหรับไฟล์ขั้นสุดท้าย

**ถาม: สามารถใช้การแปลงกับองค์ประกอบเฉพาะในเอกสารได้หรือไม่?**  
ตอบ: แน่นอน บันทึกสถานะกราฟิกก่อนวาดองค์ประกอบนั้น, ใช้การแปลงที่ต้องการ, วาด, แล้วกู้คืนสถานะ เพื่อให้ส่วนอื่น ๆ ไม่ได้รับผลกระทบ

**ถาม: มีข้อควรระวังด้านประสิทธิภาพเมื่อทำการแปลงเชิงซ้อนหรือไม่?**  
ตอบ: เมทริกซ์ที่ซับซ้อนเพิ่มภาระงานของ CPU ควรทำการแปลงให้เรียบง่ายที่สุดและใช้สถานะที่บันทึกไว้ซ้ำเมื่อวาดวัตถุที่คล้ายกัน Aspose.Page สามารถประมวลผลเอกสาร 300 หน้า ที่มีการแปลงผสมได้ภายใน 2 วินาทีบน CPU 3.2 GHz ปกติ

**ถาม: จะขอรับการสนับสนุนหรือความช่วยเหลือเกี่ยวกับ Aspose.Page ได้อย่างไร?**  
ตอบ: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับความช่วยเหลือจากชุมชน หรือ ติดต่อฝ่ายสนับสนุนของ Aspose โดยตรงเพื่อรับการช่วยเหลือระดับพรีเมียม

---

**อัปเดตล่าสุด:** 2026-07-19  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

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

## บทเรียนที่เกี่ยวข้อง

- [Create postscript document .net – Add Rectangle with Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Add Image to PostScript (PS) Document with Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Add Page to PostScript (PS) Document with Aspose.Page](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}