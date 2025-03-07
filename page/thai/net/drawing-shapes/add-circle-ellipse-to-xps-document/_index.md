---
title: เพิ่ม Circle Ellipse ลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET
linktitle: เพิ่ม Circle Ellipse ลงในเอกสาร XPS
second_title: Aspose.Page .NET API
description: ปรับปรุงเอกสาร XPS ด้วยการไล่ระดับสีแบบรัศมีที่มีชีวิตชีวาโดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อรับเอฟเฟ็กต์ภาพที่น่าทึ่ง
weight: 11
url: /th/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่ม Circle Ellipse ลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

การสร้างเอกสาร XPS ที่ดึงดูดสายตาถือเป็นข้อกำหนดทั่วไปในแอปพลิเคชันต่างๆ Aspose.Page สำหรับ .NET มีชุดคุณลักษณะอันทรงพลังเพื่อจัดการเอกสาร XPS ได้อย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะเน้นไปที่การเพิ่มวงรีวงกลมให้กับเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อปรับปรุงเอกสาร XPS ของคุณด้วยการไล่ระดับสีแบบรัศมีที่สดใส

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  ติดตั้ง Aspose.Page สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/net/).
- สภาพแวดล้อมการพัฒนา โดยเฉพาะ Visual Studio หรือเครื่องมือพัฒนา .NET อื่นๆ
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ

ในการเริ่มต้น ให้รวมเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: ตั้งค่าเอกสาร

```csharp
// เอ็กซ์สตาร์ท:1
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// สร้างเอกสาร XPS ใหม่
XpsDocument doc = new XpsDocument();
```

ที่นี่ เราเริ่มต้นเอกสาร XPS ใหม่โดยใช้ Aspose.Page สำหรับ .NET

## ขั้นตอนที่ 2: กำหนดวงรีไล่ระดับสีแบบเรเดียล

```csharp
// วงรีลากเส้นแบบรัศมีที่ด้านซ้ายล่าง
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

ขั้นตอนนี้เกี่ยวข้องกับการกำหนดวงรีไล่ระดับแนวรัศมีด้วยการหยุดสีต่างๆ

## ขั้นตอนที่ 3: ตั้งค่า Radial Gradient Brush

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

ที่นี่ เราตั้งค่าจังหวะของวงรีเป็นแปรงไล่ระดับสีแบบรัศมี โดยให้พารามิเตอร์ที่จำเป็นแก่มัน

## ขั้นตอนที่ 4: ปรับความหนาของเส้นขีด

```csharp
path.StrokeThickness = 12f;
```

ขั้นตอนนี้เกี่ยวข้องกับการปรับความหนาของเส้นขีดเพื่อให้เห็นภาพได้ดีขึ้น

## ขั้นตอนที่ 5: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์

```csharp
// บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// สิ้นสุด:1
```

สุดท้าย ให้บันทึกเอกสาร XPS ที่แก้ไขแล้วไปยังตำแหน่งที่ต้องการ

## บทสรุป

ยินดีด้วย! คุณได้เพิ่มวงรีวงกลมที่มีการไล่ระดับสีแบบรัศมีลงในเอกสาร XPS ของคุณโดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว ทดลองใช้พารามิเตอร์และสีต่างๆ เพื่อให้ได้เอฟเฟ็กต์ภาพที่ต้องการในเอกสารของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับรูปแบบเอกสารอื่นๆ ได้หรือไม่

A1: Aspose.Page สำหรับ .NET เกี่ยวข้องกับการจัดการเอกสาร XPS โดยเฉพาะ สำหรับรูปแบบอื่นๆ ให้ลองใช้ไลบรารี Aspose ที่เกี่ยวข้อง

### คำถามที่ 2: มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่

 A2: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับการทดสอบได้โดยไปที่[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 3: ฉันจะรับความช่วยเหลือและการสนทนาเพิ่มเติมได้ที่ไหน

 A3: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปรายของชุมชน

### คำถามที่ 4: มีเอกสารตัวอย่างสำหรับการอ้างอิงหรือไม่

 A4: สำรวจ[เอกสารประกอบ](https://reference.aspose.com/page/net/) สำหรับตัวอย่างและแนวทางที่ครอบคลุม

### คำถามที่ 5: ฉันสามารถซื้อ Aspose.Page สำหรับ .NET ได้หรือไม่

 A5: ได้ คุณสามารถซื้อห้องสมุดได้[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
