---
title: เพิ่ม Circle Ellipse ใน PostScript (PS) ด้วย Aspose.Page
linktitle: เพิ่ม Circle Ellipse ใน PostScript (PS)
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีเพิ่มวงรีวงกลมลงในเอกสาร PostScript (PS) ได้อย่างง่ายดายโดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 10
url: /th/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่ม Circle Ellipse ใน PostScript (PS) ด้วย Aspose.Page

## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการเพิ่มวงรีวงกลมลงในเอกสาร PostScript (PS) โดยใช้ Aspose.Page สำหรับ .NET Aspose.Page เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาทำงานกับ PostScript และรูปแบบเอกสารอื่นๆ ได้อย่างราบรื่น ในคู่มือนี้ เราจะแนะนำคุณตลอดขั้นตอนการรวมวงรีวงกลมเข้ากับเอกสาร PS ของคุณอย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Page สำหรับ .NET Library: ดาวน์โหลดและติดตั้ง Aspose.Page สำหรับ .NET Library จาก[ที่นี่](https://releases.aspose.com/page/net/).

2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้บนเครื่องของคุณ

ตอนนี้ เรามาเริ่มด้วยคำแนะนำทีละขั้นตอนกันดีกว่า

## นำเข้าเนมสเปซ

ในขั้นตอนแรก คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำให้ฟังก์ชัน Aspose.Page พร้อมใช้งานในโค้ดของคุณ

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ตอนนี้ เราจะแจกแจงตัวอย่างที่ให้ไว้เป็นหลายขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการเพิ่มวงรีวงกลมให้กับเอกสาร PostScript

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

```csharp
// เอ็กซ์สตาร์ท:1
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
```

ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: สร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript

```csharp
//สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

ที่นี่ FileStream ถูกสร้างขึ้นเพื่อเขียนเอกสาร PostScript และโหมดไฟล์ถูกตั้งค่าให้สร้างไฟล์ใหม่

## ขั้นตอนที่ 3: สร้างตัวเลือกการบันทึกและเอกสาร PS

```csharp
//สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();

// สร้างเอกสาร PS 1 หน้าใหม่
PsDocument document = new PsDocument(outPsStream, options, false);
```

ขั้นตอนนี้เกี่ยวข้องกับการสร้างตัวเลือกการบันทึกในขนาด A4 และการเริ่มต้นเอกสาร PS 1 หน้าใหม่

## ขั้นตอนที่ 4: สร้างเส้นทางกราฟิกสำหรับวงรีแรก

```csharp
//สร้างเส้นทางกราฟิกจากวงรีแรก
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

เส้นทางกราฟิกจะถูกสร้างขึ้นสำหรับวงรีวงแรก โดยระบุตำแหน่งและขนาดของวงรี

## ขั้นตอนที่ 5: ตั้งค่าสีและเติมวงรี

```csharp
//เซ็ตสี
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//เติมวงรี
document.Fill(path);
```

ที่นี่สีจะถูกตั้งค่าและวงรีแรกจะถูกเติมด้วยสีที่ระบุ

## ขั้นตอนที่ 6: สร้างเส้นทางกราฟิกสำหรับวงรีที่สอง

```csharp
//สร้างเส้นทางกราฟิกจากวงรีที่สอง
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

ในทำนองเดียวกัน เส้นทางกราฟิกจะถูกสร้างขึ้นสำหรับวงรีที่สอง เพื่อกำหนดตำแหน่งและขนาดของวงรีนั้น

## ขั้นตอนที่ 7: ตั้งค่า Stroke และวาดวงรี

```csharp
//ตั้งจังหวะ
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//ลากเส้น (โครงร่าง) วงรี
document.Draw(path);
```

ในขั้นตอนนี้ กำหนดเส้นโครงร่าง และวงรีที่สองจะถูกร่างด้วยสีและความหนาของเส้นที่ระบุ

## ขั้นตอนที่ 8: ปิดหน้าปัจจุบันและบันทึกเอกสาร

```csharp
//ปิดหน้าปัจจุบัน
document.ClosePage();

//บันทึกเอกสาร
document.Save();
```

สุดท้าย หน้าปัจจุบันจะถูกปิด และเอกสารทั้งหมดจะถูกบันทึก ทำให้กระบวนการเสร็จสมบูรณ์

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มวงรีวงกลมให้กับเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำโดยละเอียดทีละขั้นตอนเพื่อช่วยให้คุณรวมฟังก์ชันนี้เข้ากับโปรเจ็กต์ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับรูปแบบเอกสารอื่นๆ ได้หรือไม่

 A1: Aspose.Page เน้นที่ PostScript เป็นหลัก แต่ Aspose มีไลบรารีอื่นๆ สำหรับรูปแบบเอกสารต่างๆ ตรวจสอบ[จัดทำเอกสาร](https://reference.aspose.com/page/net/) สำหรับรายละเอียดเพิ่มเติม

### คำถามที่ 2: ฉันจะรับการสนับสนุนเพิ่มเติมและการสนทนาในชุมชนได้จากที่ไหน

 A2: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการอภิปรายและการสนับสนุนของชุมชน

### คำถามที่ 3: Aspose.Page สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 A3: ใช่ คุณสามารถเข้าถึง[ทดลองฟรี](https://releases.aspose.com/)เพื่อสำรวจคุณสมบัติของ Aspose.Page สำหรับ .NET

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร

 A4: รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบและประเมินผล

### คำถามที่ 5: ฉันจะซื้อ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A5: ซื้อ Aspose.Page สำหรับ .NET จาก[ซื้อหน้า](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
