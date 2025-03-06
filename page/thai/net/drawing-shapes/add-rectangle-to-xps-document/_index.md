---
title: เพิ่มสี่เหลี่ยมผืนผ้าลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET
linktitle: เพิ่มสี่เหลี่ยมผืนผ้าลงในเอกสาร XPS
second_title: Aspose.Page .NET API
description: ปรับปรุงการสร้างเอกสารด้วย Aspose.Page สำหรับ .NET เรียนรู้วิธีเพิ่มสี่เหลี่ยมลงในเอกสาร XPS ในบทช่วยสอนทีละขั้นตอนนี้
weight: 13
url: /th/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มสี่เหลี่ยมผืนผ้าลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

Aspose.Page สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีคุณสมบัติที่หลากหลายสำหรับการทำงานกับเอกสาร XPS (XML Paper Specification) ในแอปพลิเคชัน .NET ในบทช่วยสอนนี้ เราจะเน้นที่การเพิ่มสี่เหลี่ยมให้กับเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อปรับปรุงกระบวนการสร้างเอกสารของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มด้วยบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Page สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).

2. ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีที่คุณต้องการจัดเก็บเอกสาร XPS ของคุณ

## นำเข้าเนมสเปซ

ในแอปพลิเคชัน .NET ของคุณ ให้รวมเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Page

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

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

## ขั้นตอนที่ 3: เพิ่มสี่เหลี่ยมผืนผ้า

```csharp
// เอ็กซ์สตาร์ท:5
// สี่เหลี่ยมผืนผ้าขีดสีทึบ CMYK (สีน้ำเงิน) ที่ด้านซ้ายล่าง
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// สิ้นสุด:5
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

```csharp
// เอ็กซ์สตาร์ท:6
// บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// สิ้นสุด:6
```

ยินดีด้วย! คุณได้เพิ่มสี่เหลี่ยมลงในเอกสาร XPS เรียบร้อยแล้วโดยใช้ Aspose.Page สำหรับ .NET

## บทสรุป

Aspose.Page สำหรับ .NET ช่วยให้งานการจัดการเอกสารง่ายขึ้น ช่วยให้นักพัฒนาสามารถสร้างและแก้ไขเอกสาร XPS ได้อย่างง่ายดาย คำแนะนำทีละขั้นตอนนี้สาธิตวิธีเพิ่มสี่เหลี่ยมผืนผ้าลงในเอกสาร XPS ของคุณ ซึ่งเป็นรากฐานที่มั่นคงสำหรับการสำรวจเพิ่มเติม

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page เข้ากันได้กับแอปพลิเคชัน .NET ทั้งหมดหรือไม่

ตอบ 1: ใช่ Aspose.Page ได้รับการออกแบบมาให้ทำงานได้อย่างราบรื่นกับแอปพลิเคชัน .NET ทั้งหมด

### คำถามที่ 2: ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A2: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/page/net/).

### คำถามที่ 3: ฉันสามารถลองใช้ Aspose.Page สำหรับ .NET ฟรีก่อนซื้อได้หรือไม่

 A3: ใช่ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A4: เยี่ยมเลย[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อขอรับใบอนุญาตชั่วคราว

### คำถามที่ 5: ฉันจะขอการสนับสนุนจากชุมชนหรือถามคำถามที่เกี่ยวข้องกับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อสนับสนุนชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
