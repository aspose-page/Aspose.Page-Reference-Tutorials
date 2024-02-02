---
title: เพิ่มการไล่ระดับสีแนวนอนให้กับ XPS ด้วย Aspose.Page สำหรับ .NET
linktitle: เพิ่มการไล่ระดับสีแนวนอนให้กับ XPS
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีเพิ่มการไล่ระดับสีแนวนอนที่น่าทึ่งให้กับเอกสาร XPS ของคุณโดยใช้ Aspose.Page สำหรับ .NET ยกระดับความดึงดูดสายตาได้อย่างง่ายดาย
type: docs
weight: 13
url: /th/net/gradient-fills/add-horizontal-gradient-to-xps/
---
## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีปรับปรุงเอกสาร XPS โดยการเพิ่มการไล่ระดับสีแนวนอนโดยใช้ Aspose.Page สำหรับ .NET Aspose.Page สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งให้การจัดการเอกสาร XPS (XML Paper Specification) ในแอปพลิเคชัน .NET ได้อย่างราบรื่น การเพิ่มการไล่ระดับสีสามารถทำให้เอกสารของคุณดูน่าดึงดูด และคู่มือนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Page สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้จาก[Aspose.Page สำหรับเอกสาร .NET](https://reference.aspose.com/page/net/).

2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่เหมาะสม รวมถึงโปรแกรมแก้ไขโค้ด เช่น Visual Studio

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ เนมสเปซเหล่านี้จำเป็นสำหรับการทำงานกับ Aspose.Page สำหรับ .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอน

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร

```csharp
// เอ็กซ์สตาร์ท:3
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// สิ้นสุด:3
```

## ขั้นตอนที่ 2: สร้างเอกสาร XPS ใหม่

```csharp
// เอ็กซ์สตาร์ท:4
// สร้างเอกสาร XPS ใหม่
XpsDocument doc = new XpsDocument();
// สิ้นสุด:4
```

## ขั้นตอนที่ 3: เริ่มต้นการหยุดการไล่ระดับสี

```csharp
// เอ็กซ์สตาร์ท:5
// เริ่มต้นรายการ XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// สิ้นสุด:5
```

## ขั้นตอนที่ 4: สร้างเส้นทางใหม่

```csharp
// เอ็กซ์สตาร์ท:6
//สร้างเส้นทางใหม่โดยกำหนดเรขาคณิตในรูปแบบย่อ
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// สิ้นสุด:6
```

## ขั้นตอนที่ 5: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์

```csharp
// เอ็กซ์สตาร์ท:7
// บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// สิ้นสุด:7
```

ตอนนี้ คุณได้เพิ่มการไล่ระดับสีแนวนอนลงในเอกสาร XPS ของคุณโดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว

## บทสรุป

การปรับปรุงเอกสาร XPS ของคุณด้วยการไล่ระดับสีไม่เพียงแต่ปรับปรุงรูปลักษณ์ที่สวยงาม แต่ยังมอบประสบการณ์ผู้ใช้ที่น่าดึงดูดยิ่งขึ้นอีกด้วย Aspose.Page สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้น ช่วยให้คุณได้รับผลลัพธ์ระดับมืออาชีพได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันจะหาเอกสาร Aspose.Page สำหรับ .NET ได้ที่ไหน

 A1: คุณสามารถค้นหาเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/page/net/).

### คำถามที่ 2: ฉันจะดาวน์โหลด Aspose.Page สำหรับ .NET ได้อย่างไร

 A2: คุณสามารถดาวน์โหลดไลบรารีได้จากไฟล์[Aspose.Page สำหรับหน้าดาวน์โหลด .NET](https://releases.aspose.com/page/net/).

### คำถามที่ 3: ฉันจะซื้อ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A3: คุณสามารถซื้อ Aspose.Page สำหรับ .NET ได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy).

### คำถามที่ 4: มีการทดลองใช้ฟรีหรือไม่?

 A4: ได้ คุณสามารถทดลองใช้งานฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A5: คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).