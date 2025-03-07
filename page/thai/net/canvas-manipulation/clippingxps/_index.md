---
title: การตัด XPS ด้วย Aspose.Page สำหรับ .NET
linktitle: การตัด XPS
second_title: Aspose.Page .NET API
description: สำรวจพลังของ Aspose.Page สำหรับ .NET ในคำแนะนำทีละขั้นตอนเกี่ยวกับการคลิปเอกสาร XPS สร้าง จัดการ และบันทึกไฟล์ XPS ได้อย่างง่ายดาย
weight: 11
url: /th/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การตัด XPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับ Clipping XPS โดยใช้ Aspose.Page สำหรับ .NET! ในคู่มือนี้ เราจะแนะนำคุณตลอดกระบวนการสร้าง จัดการ และบันทึกเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET XPS หรือ XML Paper Specification เป็นรูปแบบเอกสารมาตรฐานและเปิดกว้าง และ Aspose.Page สำหรับ .NET ก็มีเครื่องมือที่มีประสิทธิภาพในการทำงานกับเอกสาร XPS ในแอปพลิเคชัน .NET ของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  เพิ่ม Aspose.Page สำหรับไลบรารี .NET ในโครงการของคุณ คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ

หากต้องการใช้ฟังก์ชัน Aspose.Page สำหรับ .NET คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ ทำตามขั้นตอนเหล่านี้:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

ตอนนี้ เรามาแบ่งโค้ดตัวอย่างที่คุณระบุออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร

```csharp
string dataDir = "Your Document Directory";
```

ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: สร้างเอกสาร XPS ใหม่

```csharp
XpsDocument doc = new XpsDocument();
```

สิ่งนี้จะสร้างเอกสาร XPS ใหม่ที่คุณจะใช้งาน

## ขั้นตอนที่ 3: สร้างผืนผ้าใบหลัก

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

ขั้นตอนนี้จะสร้างพื้นที่หลักซึ่งเป็นเรื่องปกติสำหรับองค์ประกอบของหน้าทั้งหมด

## ขั้นตอนที่ 4: ตั้งค่าออฟเซ็ตด้านซ้ายและด้านบนในพื้นที่ทำงานหลัก

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

ปรับออฟเซ็ตด้านซ้ายและด้านบนตามความต้องการของคุณ

## ขั้นตอนที่ 5: สร้างเรขาคณิตเส้นทางรูปสี่เหลี่ยมผืนผ้า

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

สิ่งนี้จะสร้างเส้นทางเรขาคณิตสำหรับสี่เหลี่ยมผืนผ้า

## ขั้นตอนที่ 6: สร้างการเติมสำหรับสี่เหลี่ยม

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

กำหนดสีเติมสำหรับสี่เหลี่ยม

## ขั้นตอนที่ 7: เพิ่มผืนผ้าใบอื่นพร้อมคลิปลงบนผืนผ้าใบหลัก

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

ขั้นตอนนี้จะเพิ่มผืนผ้าใบอื่นให้กับผืนผ้าใบหลัก

## ขั้นตอนที่ 8: สร้างเรขาคณิตวงกลมสำหรับคลิป

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

ซึ่งจะสร้างเรขาคณิตของคลิปวงกลมและนำไปใช้กับผืนผ้าใบที่สอง

## ขั้นตอนที่ 9: สร้างสี่เหลี่ยมผืนผ้าบนผืนผ้าใบที่สองแล้วเติมให้เต็ม

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

ขั้นตอนนี้จะสร้างสี่เหลี่ยมผืนผ้าใบที่สองและเติมให้เต็ม

## ขั้นตอนที่ 10: เพิ่มผืนผ้าใบที่สองด้วยสี่เหลี่ยมลายเส้นบนผืนผ้าใบหลัก

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

นี่เป็นการเพิ่มผืนผ้าใบอื่นให้กับผืนผ้าใบหลัก

## ขั้นตอนที่ 11: สร้างสี่เหลี่ยมผืนผ้าใบที่สามแล้วลากเส้น

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

สิ่งนี้จะสร้างสี่เหลี่ยมผืนผ้าใบผืนที่สามและใช้เส้นขีดกับผืนผ้าใบนั้น

## ขั้นตอนที่ 12: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์

```csharp
doc.Save(dataDir + "output2.xps");
```

ซึ่งจะบันทึกเอกสาร XPS ลงในไดเร็กทอรีที่ระบุ

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีคลิป XPS โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว คู่มือนี้ให้คำแนะนำโดยละเอียดเกี่ยวกับขั้นตอนที่เกี่ยวข้องในกระบวนการนี้

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับรูปแบบเอกสารอื่นๆ ได้หรือไม่

A1: Aspose.Page สำหรับ .NET เน้นที่เอกสาร XPS เป็นหลัก แต่ Aspose มีไลบรารีอื่นๆ สำหรับรูปแบบเอกสารที่หลากหลาย

### คำถามที่ 2: Aspose.Page สำหรับ .NET เหมาะสำหรับผู้เริ่มต้นหรือไม่

ตอบ 2: ใช่ Aspose.Page สำหรับ .NET ได้รับการออกแบบมาให้ใช้งานง่าย และผู้เริ่มต้นสามารถเข้าใจฟังก์ชันการทำงานได้อย่างรวดเร็วด้วยเอกสารประกอบที่เหมาะสม

### คำถามที่ 3: ฉันจะหาตัวอย่างและแหล่งข้อมูลเพิ่มเติมได้จากที่ไหน

 A3: เยี่ยมชม[เอกสารประกอบ](https://reference.aspose.com/page/net/) และ[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับแหล่งข้อมูลและตัวอย่างมากมาย

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A4: คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: Aspose.Page สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 A5: ได้ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
