---
title: เพิ่มการไล่ระดับสีแนวตั้งให้กับ XPS ด้วย Aspose.Page สำหรับ .NET
linktitle: เพิ่มการไล่ระดับสีแนวตั้งให้กับ XPS
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีปรับปรุงเอกสาร XPS ด้วยการไล่ระดับสีแนวตั้งโดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 15
url: /th/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มการไล่ระดับสีแนวตั้งให้กับ XPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนทีละขั้นตอนเกี่ยวกับวิธีเพิ่มการไล่ระดับสีแนวตั้งให้กับเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET Aspose.Page เป็น API ที่มีประสิทธิภาพซึ่งช่วยให้คุณสามารถทำงานกับไฟล์ XPS (XML Paper Specification) ในแอปพลิเคชัน .NET ของคุณได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างเอกสาร XPS ใหม่ การเพิ่มการไล่ระดับสีแนวตั้งให้กับเส้นทาง และบันทึกผลลัพธ์

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

-  Aspose.Page สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).

- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ด้วย IDE ที่คุณต้องการ เช่น Visual Studio

ตอนนี้ เรามาเริ่มต้นด้วยการเพิ่มการไล่ระดับสีแนวตั้งให้กับเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET

## นำเข้าเนมสเปซ

ในแอปพลิเคชัน .NET ของคุณ ให้รวมเนมสเปซที่จำเป็นในการเข้าถึงคลาสและวิธีการของ Aspose.Page

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

ก่อนที่คุณจะเริ่มต้น ให้กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณที่คุณต้องการบันทึกเอกสาร XPS ที่เป็นผลลัพธ์

```csharp
// เอ็กซ์สตาร์ท:3
string dataDir = "Your Document Directory";
// สิ้นสุด:3
```

## ขั้นตอนที่ 2: สร้างเอกสาร XPS ใหม่

เตรียมใช้งานเอกสาร XPS ใหม่โดยใช้รหัสต่อไปนี้:

```csharp
// เอ็กซ์สตาร์ท:4
XpsDocument doc = new XpsDocument();
// สิ้นสุด:4
```

## ขั้นตอนที่ 3: กำหนดจุดหยุดการไล่ระดับสี

สร้างรายการจุดหยุดไล่ระดับสี โดยระบุสีและตำแหน่งของจุดหยุดแต่ละจุด ในตัวอย่างนี้ เรากำหนดการไล่ระดับสีแนวตั้งโดยมีจุดหยุด 5 จุด

```csharp
// เอ็กซ์สตาร์ท:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// สิ้นสุด:5
```

## ขั้นตอนที่ 4: สร้างเส้นทางด้วยการไล่ระดับสี

กำหนดเส้นทางโดยการระบุรูปทรงเรขาคณิตและใช้แปรงไล่ระดับสีเชิงเส้น

```csharp
// เอ็กซ์สตาร์ท:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// สิ้นสุด:6
```

## ขั้นตอนที่ 5: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์

บันทึกเอกสาร XPS ที่แก้ไขไปยังไดเร็กทอรีที่ระบุของคุณ

```csharp
// เอ็กซ์สตาร์ท:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// สิ้นสุด:7
```

ยินดีด้วย! คุณได้เพิ่มการไล่ระดับสีแนวตั้งลงในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการใช้ประโยชน์จาก Aspose.Page สำหรับ .NET เพื่อปรับปรุงเอกสาร XPS ด้วยการไล่ระดับสีแนวตั้ง Aspose.Page ทำให้งานที่ซับซ้อนง่ายขึ้น ช่วยให้นักพัฒนาจัดการไฟล์ XPS ในแอปพลิเคชัน .NET ได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page เข้ากันได้กับ Visual Studio 2019 หรือไม่

A1: ใช่ Aspose.Page เข้ากันได้กับ Visual Studio 2019 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีเวอร์ชันที่ถูกต้อง

### คำถามที่ 2: ฉันสามารถใช้ Aspose.Page สำหรับโครงการเชิงพาณิชย์ได้หรือไม่

 A2: ได้ Aspose.Page สามารถใช้สำหรับโครงการเชิงพาณิชย์ได้ เยี่ยม[ที่นี่](https://purchase.aspose.com/buy) เพื่อสำรวจตัวเลือกการออกใบอนุญาต

### คำถามที่ 3: มีการทดลองใช้ฟรีหรือไม่?

 A3: ใช่ คุณสามารถทดลองใช้ Aspose.Page ได้ฟรี[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะหาเอกสารประกอบของ Aspose.Page ได้ที่ไหน

 A4: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/page/net/).

### คำถามที่ 5: ฉันจะรับการสนับสนุนหรือถามคำถามได้อย่างไร

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อสนับสนุนชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
