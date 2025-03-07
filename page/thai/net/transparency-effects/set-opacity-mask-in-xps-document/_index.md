---
title: ตั้งค่า Opacity Mask ในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET
linktitle: ตั้งค่า Opacity Mask ในเอกสาร XPS
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีตั้งค่ามาสก์ความทึบในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET ปรับปรุงความสวยงามของเอกสารได้อย่างง่ายดาย
weight: 12
url: /th/net/transparency-effects/set-opacity-mask-in-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่า Opacity Mask ในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

มาสก์ทึบแสงถือเป็นสิ่งสำคัญเมื่อคุณต้องการสร้างเอกสารที่ดึงดูดสายตาด้วยระดับความโปร่งใสที่แตกต่างกัน Aspose.Page สำหรับ .NET ช่วยให้กระบวนการนี้ง่ายขึ้น โดยนำเสนอชุดเครื่องมือที่ครอบคลุมสำหรับนักพัฒนาเพื่อปรับปรุงเอกสาร XPS ในบทช่วยสอนนี้ เราจะสำรวจวิธีตั้งค่ามาสก์ความทึบในคำแนะนำทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/page/net/).

- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีเพื่อจัดเก็บเอกสาร XPS ของคุณ

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## ขั้นตอนที่ 1: สร้างเอกสาร XPS ใหม่

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// สร้างเอกสาร XPS ใหม่
XpsDocument doc = new XpsDocument();
```

เริ่มต้นด้วยการสร้างเอกสาร XPS ใหม่โดยใช้ Aspose.Page สำหรับ .NET

## ขั้นตอนที่ 2: เพิ่ม Canvas ไปยังอินสแตนซ์ XpsDocument

```csharp
// เพิ่ม Canvas ไปยังอินสแตนซ์ XpsDocument
XpsCanvas canvas = doc.AddCanvas();
```

ตอนนี้ เพิ่มแคนวาสลงในเอกสาร XPS ผืนผ้าใบจะทำหน้าที่เป็นที่เก็บสำหรับองค์ประกอบกราฟิกต่างๆ

## ขั้นตอนที่ 3: เพิ่มสี่เหลี่ยมผืนผ้าด้วย Opacity Mask

```csharp
// สี่เหลี่ยมผืนผ้าที่มีความทึบซึ่งปกปิดโดย ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

 เพิ่มสี่เหลี่ยมผืนผ้าใบและตั้งค่าความทึบโดยใช้`OpacityMask`คุณสมบัติ. ในตัวอย่างนี้ เราใช้รูปภาพเป็นมาสก์ความทึบ

## ขั้นตอนที่ 4: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์

```csharp
// บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
doc.Save(dataDir + "OpacityMask_out.xps");
```

สุดท้าย ให้บันทึกเอกสาร XPS ที่แก้ไขแล้วโดยใช้มาสก์ความทึบ

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีตั้งค่ามาสก์ความทึบในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว ฟีเจอร์นี้เปิดขอบเขตความเป็นไปได้ที่สร้างสรรค์สำหรับการออกแบบเอกสารที่ซับซ้อนและดึงดูดสายตา

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้มาสก์ทึบกับรูปร่างอื่นนอกเหนือจากสี่เหลี่ยมได้หรือไม่

ตอบ 1: ใช่ Aspose.Page สำหรับ .NET อนุญาตให้คุณใช้มาสก์ทึบกับรูปร่างต่างๆ รวมถึงวงกลม รูปหลายเหลี่ยม และเส้นทางแบบกำหนดเอง

### คำถามที่ 2: หน้ากากทึบแสงจำกัดอยู่ที่รูปภาพหรือไม่

A2: ไม่ แม้ว่าบทช่วยสอนนี้ใช้รูปภาพเป็นมาสก์ความทึบ แต่คุณสามารถใช้สีทึบ การไล่ระดับสี หรือแม้แต่ลวดลายได้

### คำถามที่ 3: มีตัวเลือกขั้นสูงสำหรับปรับระดับความทึบแบบละเอียดหรือไม่

A3: แน่นอนว่า Aspose.Page สำหรับ .NET ให้การควบคุมการตั้งค่าความทึบโดยละเอียด ช่วยให้คุณได้รับเอฟเฟกต์ความโปร่งใสที่แม่นยำ

### คำถามที่ 4: ฉันสามารถใช้มาสก์ทึบหลายอันกับองค์ประกอบเดียวได้หรือไม่

A4: ได้ คุณสามารถเลเยอร์มาสก์ทึบหลายชั้นเพื่อสร้างเอฟเฟกต์โปร่งใสที่ซับซ้อนได้

### คำถามที่ 5: Aspose.Page เข้ากันได้กับรูปแบบเอกสารอื่นหรือไม่

A5: Aspose.Page มุ่งเน้นไปที่เอกสาร XPS เป็นหลัก แต่ Aspose มีผลิตภัณฑ์มากมายสำหรับการจัดการรูปแบบที่แตกต่างกัน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
