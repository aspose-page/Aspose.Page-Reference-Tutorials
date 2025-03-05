---
title: การตัด PS ด้วย Aspose.Page สำหรับ .NET
linktitle: การตัดป.ล
second_title: Aspose.Page .NET API
description: สำรวจพลังของ Aspose.Page สำหรับ .NET ในบทช่วยสอนทีละขั้นตอนเกี่ยวกับการคลิปเอกสาร PostScript เรียนรู้เพื่อเพิ่มความสามารถในการประมวลผลเอกสารของคุณได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/net/canvas-manipulation/clippingps/
---
## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการใช้ Aspose.Page สำหรับ .NET เพื่อปรับใช้การคลิปในเอกสาร PostScript (PS) บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการตัดเอกสาร PS โดยใช้ Aspose.Page ซึ่งเป็นไลบรารีอันทรงพลังสำหรับการทำงานกับรูปแบบเอกสารที่หลากหลายในแอปพลิเคชัน .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
-  ติดตั้ง Aspose.Page สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript

```csharp
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

## ขั้นตอนที่ 3: สร้างตัวเลือกการบันทึก

```csharp
// สร้างตัวเลือกการบันทึกด้วยค่าเริ่มต้น
PsSaveOptions options = new PsSaveOptions();
```

## ขั้นตอนที่ 4: สร้างเอกสาร PS แบบ 1 หน้าใหม่

```csharp
// สร้างเอกสาร PS 1 หน้าใหม่
PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 5: สร้างเส้นทางกราฟิกจากสี่เหลี่ยมผืนผ้า

```csharp
// สร้างเส้นทางกราฟิกจากสี่เหลี่ยม
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

## ขั้นตอนที่ 6: การตัดตามรูปร่าง

```csharp
// บันทึกสถานะกราฟิกเพื่อกลับสู่สถานะนี้หลังการเปลี่ยนแปลง
document.WriteGraphicsSave();

//แทนที่สถานะกราฟิกปัจจุบันที่ 100 คะแนนทางด้านขวาและ 100 คะแนนที่ด้านล่าง
document.Translate(100, 100);

// สร้างเส้นทางกราฟิกจากวงกลม
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// เพิ่มการคลิปเป็นวงกลมให้กับสถานะกราฟิกปัจจุบัน
document.Clip(circlePath);

// ตั้งค่าสีในสถานะกราฟิกปัจจุบัน
document.SetPaint(new SolidBrush(Color.Blue));

// เติมสี่เหลี่ยมในสถานะกราฟิกปัจจุบัน (พร้อมรูปตัด)
document.Fill(rectanglePath);

// คืนค่าสถานะกราฟิกเป็นระดับก่อนหน้า (บน)
document.WriteGraphicsRestore();
```

## ขั้นตอนที่ 7: แทนที่สถานะกราฟิกระดับบน

```csharp
// แทนที่สถานะกราฟิกระดับบนที่ 100 จุดทางด้านขวาและ 100 จุดไปที่ด้านล่าง
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// วาดรูปสี่เหลี่ยมผืนผ้าในสถานะกราฟิกปัจจุบัน (ไม่มีการคลิป) เหนือสี่เหลี่ยมที่ถูกตัด
document.Draw(rectanglePath);
```

## ขั้นตอนที่ 8: ปิดและบันทึกเอกสาร

```csharp
// ปิดหน้าปัจจุบัน
document.ClosePage();

// บันทึกเอกสาร
document.Save();
```

ตอนนี้ คุณได้ดำเนินการคลิปในเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ Aspose.Page สำหรับ .NET เพื่อปรับใช้การคลิปในเอกสาร PostScript ไลบรารีอันทรงพลังนี้มอบวิธีที่ราบรื่นและมีประสิทธิภาพในการจัดการรูปแบบเอกสารต่าง ๆ ในแอปพลิเคชัน .NET ของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่

A1: Aspose.Page ได้รับการออกแบบมาสำหรับแอปพลิเคชัน .NET เป็นหลัก อย่างไรก็ตาม Aspose มีไลบรารีที่คล้ายกันสำหรับภาษาการเขียนโปรแกรมอื่นๆ

### คำถามที่ 2: ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A2: คุณสามารถสำรวจตัวอย่างเพิ่มเติมและเอกสารประกอบโดยละเอียดเกี่ยวกับ[เอกสาร Aspose.Page](https://reference.aspose.com/page/net/).

### คำถามที่ 3: Aspose.Page สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 A3: ได้ คุณสามารถเข้าถึง Aspose.Page สำหรับ .NET รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A4: คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: ฉันจะรับการสนับสนุนหรือหารือเกี่ยวกับคำถามที่เกี่ยวข้องกับ Aspose.Page ได้ที่ไหน

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปรายของชุมชน