---
title: เพิ่มสี่เหลี่ยมผืนผ้าลงใน PostScript (PS) ด้วย Aspose.Page สำหรับ .NET
linktitle: เพิ่มสี่เหลี่ยมผืนผ้าลงใน PostScript (PS)
second_title: Aspose.Page .NET API
description: ปรับปรุงการสร้างเอกสารใน .NET ด้วย Aspose.Page เรียนรู้วิธีการเพิ่มสี่เหลี่ยมลงในไฟล์ PostScript (PS) ทีละขั้นตอน
weight: 12
url: /th/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มสี่เหลี่ยมผืนผ้าลงใน PostScript (PS) ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

หากคุณต้องการปรับปรุงความสามารถในการสร้างเอกสารใน .NET Aspose.Page มอบโซลูชันอันทรงพลังสำหรับการจัดการเอกสาร PostScript ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มสี่เหลี่ยมให้กับเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET Library: ดาวน์โหลดและติดตั้ง Aspose.Page สำหรับ .NET Library จาก[ที่นี่](https://releases.aspose.com/page/net/).

- สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ

## นำเข้าเนมสเปซ

ก่อนที่คุณจะเริ่มเขียนโค้ด ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการที่จำเป็น:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

```csharp
// เอ็กซ์สตาร์ท:1
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
```

ในขั้นตอนนี้ ให้แทนที่ "Your Document Directory" ด้วยเส้นทางที่คุณต้องการบันทึกเอกสาร PostScript

## ขั้นตอนที่ 2: สร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript

```csharp
//สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

ที่นี่ เราสร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript และระบุชื่อไฟล์ ("AddRectangle_outPS.ps") ปรับชื่อไฟล์และตำแหน่งตามความต้องการของคุณ

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการบันทึกและสร้างเอกสาร PS

```csharp
//สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();

// สร้างเอกสาร PS 1 หน้าใหม่
PsDocument document = new PsDocument(outPsStream, options, false);
```

ตั้งค่าตัวเลือกบันทึก โดยระบุขนาดหน้าที่ต้องการ (ในกรณีนี้คือ A4) จากนั้น สร้างเอกสาร PostScript แบบหน้าเดียวใหม่

## ขั้นตอนที่ 4: เพิ่มสี่เหลี่ยมผืนผ้าและเติม

```csharp
//สร้างเส้นทางกราฟิกจากสี่เหลี่ยมแรก
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//เซ็ตสี
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//เติมสี่เหลี่ยม
document.Fill(path);
```

ที่นี่ เราสร้างเส้นทางกราฟิกที่แสดงถึงสี่เหลี่ยมแรก ตั้งค่าสีของสี (ในกรณีนี้คือสีส้ม) และเติมสี่เหลี่ยม

## ขั้นตอนที่ 5: เพิ่มสี่เหลี่ยมผืนผ้าและเส้นขีดอีกอัน

```csharp
//สร้างเส้นทางกราฟิกจากสี่เหลี่ยมที่สอง
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//ตั้งจังหวะ
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//ลากเส้น (ร่าง) สี่เหลี่ยม
document.Draw(path);
```

เช่นเดียวกับขั้นตอนก่อนหน้า เราสร้างเส้นทางกราฟิกสำหรับสี่เหลี่ยมที่สอง ตั้งค่าสีเส้นโครงร่าง (สีแดงที่มีความหนา 3) และร่างกรอบสี่เหลี่ยม

## ขั้นตอนที่ 6: ปิดหน้าและบันทึกเอกสาร

```csharp
//ปิดหน้าปัจจุบัน
document.ClosePage();

//บันทึกเอกสาร
document.Save();
```

สุดท้าย ให้ปิดหน้าปัจจุบันและบันทึกเอกสารทั้งหมด

## บทสรุป

ยินดีด้วย! คุณได้เพิ่มสี่เหลี่ยมลงในเอกสาร PostScript สำเร็จแล้วโดยใช้ Aspose.Page สำหรับ .NET บทช่วยสอนนี้ครอบคลุมขั้นตอนที่จำเป็น ตั้งแต่การตั้งค่าสภาพแวดล้อมการพัฒนาไปจนถึงการบันทึกเอกสารขั้นสุดท้าย

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถปรับแต่งสีของสี่เหลี่ยมได้หรือไม่

A1: ได้ คุณสามารถปรับแต่งสีได้โดยการปรับพารามิเตอร์ใน`SolidBrush` และ`Pen` ชั้นเรียน

### คำถามที่ 2: Aspose.Page เข้ากันได้กับรูปแบบเอกสารอื่นหรือไม่

ตอบ 2: ใช่ Aspose.Page รองรับรูปแบบเอกสารหลากหลาย รวมถึง XPS และ PostScript

### คำถามที่ 3: ฉันจะเพิ่มข้อความลงในเอกสารได้อย่างไร

 A3: คุณสามารถใช้`TextFragment` คลาสใน Aspose.Page เพื่อเพิ่มข้อความลงในเอกสารของคุณ

### คำถามที่ 4: ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน

 A4: สำรวจเอกสารประกอบ[ที่นี่](https://reference.aspose.com/page/net/) และเยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อสนับสนุนชุมชน

### คำถามที่ 5: ฉันสามารถลองใช้ Aspose.Page ก่อนซื้อได้หรือไม่

 A5: ได้ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/) และสำหรับการใช้งานแบบขยาย ให้พิจารณาก[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
