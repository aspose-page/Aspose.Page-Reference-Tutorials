---
title: เปลี่ยนค่าด้วย Aspose.Page สำหรับ .NET
linktitle: การเปลี่ยนแปลงค่า
second_title: Aspose.Page .NET API
description: การจัดการไฟล์ EPS ต้นแบบด้วย Aspose.Page สำหรับ .NET เปลี่ยนค่าข้อมูลเมตา XMP ได้อย่างง่ายดาย
type: docs
weight: 17
url: /th/net/eps-metadata-management/modify-eps-metadata-change-values/
---
## การแนะนำ

ในโลกแบบไดนามิกของการประมวลผลเอกสาร Aspose.Page สำหรับ .NET มีความโดดเด่นในฐานะเครื่องมืออันทรงพลัง ช่วยให้นักพัฒนาสามารถจัดการไฟล์ EPS ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการเปลี่ยนแปลงค่าภายในไฟล์ EPS โดยใช้ Aspose.Page สำหรับ .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ที่อยากรู้อยากเห็น คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณมีทักษะที่จำเป็นในการแก้ไขข้อมูลเมตา XMP ในไฟล์ EPS ของคุณได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

### 1. Aspose.Page สำหรับ .NET Library

ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ ถ้าไม่คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).

### 2. ไดเร็กทอรีเอกสาร

ตั้งค่าไดเร็กทอรีสำหรับเอกสารของคุณ นี่จะเป็นตำแหน่งที่เก็บไฟล์ EPS ของคุณ

ตอนนี้เราได้จัดเรียงข้อกำหนดเบื้องต้นแล้ว มาดูขั้นตอนสำคัญถัดไปกันดีกว่า

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ใดๆ จำเป็นต้องนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชันการทำงานของ Aspose.Page ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## ขั้นตอนที่ 1: เริ่มต้นสตรีมอินพุตไฟล์ EPS

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// เริ่มต้นสตรีมอินพุตไฟล์ EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## ขั้นตอนที่ 2: สร้างอินสแตนซ์ PsDocument จากสตรีม

```csharp
//สร้างอินสแตนซ์ PsDocument จากสตรีม
PsDocument document = new PsDocument(psStream);
```

ตอนนี้เราได้กำหนดขั้นตอนแล้ว มาดูเนื้อหาหลักของบทช่วยสอนของเรากันดีกว่า - การเปลี่ยนค่าข้อมูลเมตา XMP ภายในไฟล์ EPS

## ขั้นตอนที่ 3: รับข้อมูลเมตา XMP

```csharp
// รับข้อมูลเมตา XMP หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP เราจะได้ไฟล์ใหม่ที่เต็มไปด้วยค่าจากความคิดเห็นข้อมูลเมตา PS (%%Creator, %%CreateDate, %%Title ฯลฯ)
XmpMetadata xmp = document.GetXmpMetadata();
```

## ขั้นตอนที่ 4: แก้ไขค่าข้อมูลเมตา XMP

ตอนนี้ เรามาเปลี่ยนค่าคีย์บางค่าในข้อมูลเมตา XMP กัน:

### ขั้นตอนที่ 4.1: เปลี่ยนค่า ModifyDate

```csharp
// เปลี่ยนค่า ModifyDate
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### ขั้นตอนที่ 4.2: เปลี่ยนค่าผู้สร้าง

```csharp
// เปลี่ยนค่าผู้สร้าง
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### ขั้นตอนที่ 4.3: เปลี่ยนค่าชื่อเรื่อง

```csharp
// เปลี่ยนค่าชื่อเรื่อง
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

เมื่อทำการเปลี่ยนแปลงเหล่านี้แล้ว เรามาต่อกันที่ขั้นตอนสุดท้าย - บันทึกไฟล์ EPS ที่แก้ไข

## ขั้นตอนที่ 5: บันทึกไฟล์ EPS พร้อมข้อมูลเมตา XMP ที่เปลี่ยนแปลง

### ขั้นตอนที่ 5.1: สร้างสตรีมเอาท์พุต

```csharp
// สร้างกระแสเอาต์พุต
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### ขั้นตอนที่ 5.2: บันทึกไฟล์ EPS

```csharp
// บันทึกไฟล์ EPS
document.Save(outPsStream);
```

สุดท้าย ปิดสตรีมอินพุต:

```csharp
finally
{
    psStream.Close();
}
```

ยินดีด้วย! คุณได้แก้ไขค่าข้อมูลเมตา XMP ในไฟล์ EPS โดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการที่ราบรื่นของการเปลี่ยนแปลงค่าภายในไฟล์ EPS โดยใช้ Aspose.Page สำหรับ .NET ในฐานะนักพัฒนา ขณะนี้คุณมีเครื่องมืออันทรงพลังสำหรับการจัดการเอกสารอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับไฟล์รูปแบบอื่นได้หรือไม่

A1: Aspose.Page เน้นไปที่การจัดการไฟล์ EPS เป็นหลัก สำหรับรูปแบบอื่นๆ โปรดดูผลิตภัณฑ์ที่หลากหลายของ Aspose

### คำถามที่ 2: มีเวอร์ชันทดลองใช้งานหรือไม่

 ตอบ 2: ได้ คุณสามารถลองใช้ Aspose.Page สำหรับ .NET โดยมีรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### Q3: ฉันจะหาเอกสารโดยละเอียดได้จากที่ไหน?

 A3: สามารถดูเอกสารประกอบที่ครอบคลุมได้[ที่นี่](https://reference.aspose.com/page/net/).

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร

 A4: คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: ฉันสามารถซื้อ Aspose.Page สำหรับ .NET ได้หรือไม่

 A5: แน่นอน! เยี่ยมชมหน้าการซื้อ[ที่นี่](https://purchase.aspose.com/buy) สำหรับตัวเลือกการออกใบอนุญาต