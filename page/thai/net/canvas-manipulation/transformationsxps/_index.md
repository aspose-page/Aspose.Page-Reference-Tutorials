---
title: การแปลง XPS ด้วย Aspose.Page สำหรับ .NET
linktitle: การเปลี่ยนแปลง XPS
second_title: Aspose.Page .NET API
description: แปลงเอกสาร XPS ได้อย่างง่ายดายด้วย Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการเปลี่ยนแปลงที่ราบรื่น
weight: 13
url: /th/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การแปลง XPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

ยินดีต้อนรับสู่โลกของ Aspose.Page สำหรับ .NET ซึ่งเป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสามารถดำเนินการแปลงเอกสาร XPS ต่างๆ ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการแปลงเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คู่มือนี้จะแนะนำคุณในแต่ละขั้นตอน เพื่อให้มั่นใจว่าคุณจะเข้าใจแนวคิดได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

-  Aspose.Page สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Page สำหรับเอกสาร .NET](https://reference.aspose.com/page/net/).

- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่เข้ากันได้ เช่น Visual Studio หรือเครื่องมือการพัฒนา .NET อื่นๆ

- ไดเร็กทอรีเอกสารของคุณ: แทนที่ตัวยึดตำแหน่งในโค้ดด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

ตอนนี้ เรามาเข้าสู่บทช่วยสอนกันดีกว่า!

## นำเข้าเนมสเปซ

ประการแรก ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นเพื่อให้ฟังก์ชัน Aspose.Page สำหรับ .NET พร้อมใช้งานในโค้ดของคุณ เพิ่มเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของสคริปต์ของคุณ:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ขั้นตอนที่ 1: สร้างเอกสาร XPS ใหม่

```csharp
// เอ็กซ์สตาร์ท:1
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างเอกสาร XPS ใหม่
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 2: สร้างผืนผ้าใบหลัก

```csharp
// สร้างผืนผ้าใบหลักซึ่งใช้ร่วมกันในทุกองค์ประกอบของหน้า
XpsCanvas canvas1 = doc.AddCanvas();

// สร้างออฟเซ็ตด้านซ้ายและด้านบนในพื้นที่ทำงานหลัก
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## ขั้นตอนที่ 3: สร้างเรขาคณิตเส้นทางสี่เหลี่ยมผืนผ้า

```csharp
// สร้างเรขาคณิตเส้นทางรูปสี่เหลี่ยมผืนผ้า
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## ขั้นตอนที่ 4: เพิ่มการเติมสำหรับสี่เหลี่ยม

```csharp
// สร้างการเติมสำหรับสี่เหลี่ยม
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## ขั้นตอนที่ 5: เพิ่ม Canvas ใหม่โดยไม่มีการเปลี่ยนแปลง

```csharp
// เพิ่มผืนผ้าใบใหม่โดยไม่มีการเปลี่ยนแปลงใดๆ ให้กับผืนผ้าใบหลัก
XpsCanvas canvas2 = canvas1.AddCanvas();

// สร้างสี่เหลี่ยมผืนผ้าบนผืนผ้าใบนี้แล้วเติมให้เต็ม
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## ขั้นตอนที่ 6: เพิ่ม Canvas ใหม่พร้อมการแปลงการแปล

```csharp
// เพิ่มผืนผ้าใบใหม่พร้อมการแปลการเปลี่ยนแปลงไปยังผืนผ้าใบหลัก
XpsCanvas canvas3 = canvas1.AddCanvas();

// แปลผืนผ้าใบนี้เพื่อวางตำแหน่งสี่เหลี่ยมผืนผ้าใหม่ใต้สี่เหลี่ยมผืนผ้าก่อนหน้า
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// แปลผืนผ้าใบนี้ไปทางด้านขวาของหน้า
canvas3.RenderTransform.Translate(500, 0);

// สร้างสี่เหลี่ยมผืนผ้าบนผืนผ้าใบนี้แล้วเติมให้เต็ม
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## ขั้นตอนที่ 7: เพิ่มผืนผ้าใบใหม่พร้อมการแปลงสเกลสองเท่า

```csharp
//เพิ่มผืนผ้าใบใหม่พร้อมการเปลี่ยนแปลงขนาดสองเท่าให้กับผืนผ้าใบหลัก
XpsCanvas canvas4 = canvas1.AddCanvas();

// แปลผืนผ้าใบนี้เพื่อวางตำแหน่งสี่เหลี่ยมผืนผ้าใหม่ใต้สี่เหลี่ยมผืนผ้าก่อนหน้า
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// ปรับขนาดผืนผ้าใบนี้
canvas4.RenderTransform.Scale(2, 2);

// สร้างสี่เหลี่ยมผืนผ้าบนผืนผ้าใบนี้แล้วเติมให้เต็ม
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## ขั้นตอนที่ 8: เพิ่มผืนผ้าใบใหม่พร้อมการหมุนรอบการเปลี่ยนแปลงจุด

```csharp
// เพิ่มผืนผ้าใบใหม่โดยหมุนรอบการเปลี่ยนจุดไปยังผืนผ้าใบหลัก
XpsCanvas canvas5 = canvas1.AddCanvas();

// แปลผืนผ้าใบนี้เพื่อวางตำแหน่งสี่เหลี่ยมผืนผ้าใหม่ใต้สี่เหลี่ยมผืนผ้าก่อนหน้า
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// หมุนผืนผ้าใบนี้ไปรอบ ๆ จุดที่ 45 องศา
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// สร้างสี่เหลี่ยมผืนผ้าบนผืนผ้าใบนี้แล้วเติมให้เต็ม
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## ขั้นตอนที่ 9: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์

```csharp
// บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
doc.Save(dataDir + "output1.xps");
// สิ้นสุด:1
```

## บทสรุป

ยินดีด้วย! คุณได้แปลงเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว คู่มือนี้ครอบคลุมขั้นตอนสำคัญ ตั้งแต่การตั้งค่าข้อกำหนดเบื้องต้นไปจนถึงการดำเนินการแปลงต่างๆ ทดลองใช้เทคนิคเหล่านี้และปลดล็อกศักยภาพสูงสุดของ Aspose.Page สำหรับ .NET ในโปรเจ็กต์ของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page สำหรับ .NET เข้ากันได้กับสภาพแวดล้อมการพัฒนา .NET ทั้งหมดหรือไม่

ตอบ 1: ใช่ Aspose.Page สำหรับ .NET ได้รับการออกแบบมาให้ทำงานได้อย่างราบรื่นกับสภาพแวดล้อมการพัฒนา .NET ต่างๆ รวมถึง Visual Studio

### คำถามที่ 2: ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A2: เยี่ยมชม[Aspose.Page สำหรับเอกสาร .NET](https://reference.aspose.com/page/net/) สำหรับเอกสารและตัวอย่างที่ครอบคลุม

### คำถามที่ 3: ฉันสามารถลองใช้ Aspose.Page สำหรับ .NET ก่อนซื้อได้หรือไม่

 A3: ได้ คุณสามารถสำรวจเวอร์ชันทดลองใช้ฟรีได้โดยไปที่[Aspose.Page ทดลองใช้ฟรี](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A4: รับใบอนุญาตชั่วคราวโดยไปที่[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: ฉันจะซื้อ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A5: ซื้อ Aspose.Page สำหรับ .NET ที่[Aspose.เพจซื้อ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
