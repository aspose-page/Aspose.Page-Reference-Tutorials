---
title: เปลี่ยนรายการอาร์เรย์ด้วย Aspose.Page สำหรับ .NET
linktitle: เปลี่ยนรายการอาร์เรย์
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีเปลี่ยนรายการอาร์เรย์ในไฟล์ EPS โดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการข้อมูลเมตาที่มีประสิทธิภาพ
type: docs
weight: 15
url: /th/net/eps-metadata-management/modify-eps-metadata-change-array-items/
---
## การแนะนำ

ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมเกี่ยวกับการเปลี่ยนรายการอาร์เรย์โดยใช้ Aspose.Page สำหรับ .NET! Aspose.Page เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับรูปแบบเอกสารที่หลากหลาย รวมถึงไฟล์ EPS ในบทช่วยสอนนี้ เราจะเน้นไปที่การจัดการข้อมูลเมตา XMP ภายในไฟล์ EPS โดยเฉพาะการเปลี่ยนรายการอาร์เรย์

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Aspose.Page สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Page สำหรับ .NET Library แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/net/).

2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่คุณต้องการ ไม่ว่าจะเป็น Visual Studio หรือ IDE อื่นๆ ที่รองรับการพัฒนา .NET

## นำเข้าเนมสเปซ

ในแอปพลิเคชัน .NET ของคุณ คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Page เพิ่มเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของโค้ดของคุณ:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

เรามาแยกย่อยตัวอย่างที่ให้ไว้เป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: เริ่มต้นสตรีมอินพุตไฟล์ EPS

```csharp
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

 ในขั้นตอนนี้ เราจะเริ่มต้นสตรีมอินพุตไฟล์ EPS และสร้างไฟล์`PsDocument` ตัวอย่างจากมัน

## ขั้นตอนที่ 2: รับข้อมูลเมตา XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

ดึงข้อมูลเมตา XMP จากไฟล์ EPS หากไฟล์ไม่มีข้อมูลเมตา XMP ไฟล์ใหม่จะถูกสร้างขึ้นโดยมีค่าจากความคิดเห็นข้อมูลเมตา PS

## ขั้นตอนที่ 3: เปลี่ยนค่าข้อมูลเมตา XMP

```csharp
xmp.SetArrayItem("dc:title", 0, new XmpValue("NewTitle"));
xmp.SetArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

ที่นี่ เราเปลี่ยนชื่อและรายการผู้สร้างที่ดัชนี 0 ภายในข้อมูลเมตา XMP

## ขั้นตอนที่ 4: บันทึกไฟล์ EPS พร้อมข้อมูลเมตา XMP ที่เปลี่ยนแปลง

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

สร้างสตรีมเอาต์พุตและบันทึกไฟล์ EPS ด้วยข้อมูลเมตา XMP ที่แก้ไข

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีเปลี่ยนรายการอาร์เรย์ในไฟล์ EPS โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว นี่อาจเป็นขั้นตอนสำคัญในการปรับแต่งและจัดการข้อมูลเมตาภายในเอกสารของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับรูปแบบเอกสารอื่นๆ ได้หรือไม่

A1: Aspose.Page เกี่ยวข้องกับไฟล์ EPS เป็นหลัก แต่ Aspose มีไลบรารีที่แตกต่างกันสำหรับการทำงานกับรูปแบบเอกสารที่หลากหลาย

### คำถามที่ 2: ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?

 A2: โปรดดูเอกสารประกอบที่[Aspose.Page สำหรับเอกสาร .NET](https://reference.aspose.com/page/net/).

### คำถามที่ 3: มีการทดลองใช้ฟรีหรือไม่?

 A3: ได้ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะรับใบอนุญาตชั่วคราวได้อย่างไร

 A4: รับใบอนุญาตชั่วคราวจาก[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: ฉันจะรับการสนับสนุนหรือเชื่อมต่อกับชุมชนได้ที่ไหน

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปรายของชุมชน