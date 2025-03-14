---
title: เพิ่มรายการอาร์เรย์ด้วย Aspose.Page
linktitle: เพิ่มรายการอาร์เรย์
second_title: Aspose.Page .NET API
description: สำรวจวิธีเพิ่มรายการอาร์เรย์ในไฟล์ EPS โดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการเอกสารที่ราบรื่น
weight: 11
url: /th/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรายการอาร์เรย์ด้วย Aspose.Page

## การแนะนำ

ในขอบเขตของการจัดการและประมวลผลเอกสารใน .NET Aspose.Page มีความโดดเด่นในฐานะเครื่องมืออันทรงพลัง ท่ามกลางความสามารถมากมาย การจัดการรายการอาร์เรย์ภายในไฟล์ EPS ถือเป็นข้อกำหนดทั่วไป ในบทช่วยสอนนี้ เราจะสำรวจกระบวนการทีละขั้นตอนในการเพิ่มรายการอาร์เรย์โดยใช้ Aspose.Page ในสภาพแวดล้อม .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ คู่มือนี้จะแนะนำคุณตลอดกระบวนการด้วยความชัดเจนและแม่นยำ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม .NET
-  ติดตั้ง Aspose.Page สำหรับ .NET แล้ว หากไม่ใช่คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/net/).
- โปรแกรมแก้ไขโค้ด เช่น Visual Studio เพื่อทำตามตัวอย่าง

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Page เพิ่มบรรทัดต่อไปนี้ที่จุดเริ่มต้นของโค้ดของคุณ:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

เนมสเปซเหล่านี้ให้การเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการจัดการไฟล์ EPS

## ขั้นตอนที่ 1: เริ่มต้นสตรีมอินพุตไฟล์ EPS

```csharp
// เอ็กซ์สตาร์ท:3
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// เริ่มต้นสตรีมอินพุตไฟล์ EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//สร้างอินสแตนซ์ PsDocument จากสตรีม
PsDocument document = new PsDocument(psStream);            
// สิ้นสุด:3
```

 ที่นี่ เรากำลังตั้งค่าสตรีมอินพุตเริ่มต้นสำหรับไฟล์ EPS และสร้างไฟล์`PsDocument` ตัวอย่าง.

## ขั้นตอนที่ 2: รับข้อมูลเมตา XMP

```csharp
// เอ็กซ์สตาร์ท:4
// รับข้อมูลเมตา XMP หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP เราจะได้ไฟล์ใหม่ที่เต็มไปด้วยค่าจากความคิดเห็นข้อมูลเมตา PS (%%Creator, %%CreateDate, %%Title ฯลฯ)
XmpMetadata xmp = document.GetXmpMetadata();
// สิ้นสุด:4
```

ดึงข้อมูลเมตา XMP จากไฟล์ EPS หากไฟล์ EPS ขาดข้อมูลเมตา XMP ไฟล์ใหม่จะถูกสร้างขึ้นโดยมีค่าจากความคิดเห็นข้อมูลเมตา PS

## ขั้นตอนที่ 3: เปลี่ยนค่าข้อมูลเมตา XMP

```csharp
// เอ็กซ์สตาร์ท:5
// เปลี่ยนค่าข้อมูลเมตา XMP

// เพิ่มอีกหนึ่งชื่อ มันจะถูกเพิ่มที่ส่วนท้ายของอาร์เรย์ตามค่าเริ่มต้น
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// เพิ่มผู้สร้างอีกหนึ่งคน มันจะถูกเพิ่มในอาร์เรย์ด้วยดัชนี (0)
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// สิ้นสุด:5
```

แก้ไขข้อมูลเมตา XMP โดยเพิ่มชื่อและผู้สร้างใหม่ลงในอาร์เรย์

## ขั้นตอนที่ 4: บันทึกไฟล์ EPS พร้อมข้อมูลเมตา XMP ที่เปลี่ยนแปลง

```csharp
// เอ็กซ์สตาร์ท:6
// บันทึกไฟล์ EPS พร้อมข้อมูลเมตา XMP ที่เปลี่ยนแปลง

// สร้างกระแสเอาต์พุต
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // บันทึกไฟล์ EPS
    document.Save(outPsStream);
}
// สิ้นสุด:6
```

สุดท้าย ให้บันทึกไฟล์ EPS ด้วยข้อมูลเมตา XMP ที่อัปเดต การเปลี่ยนแปลงที่เกิดขึ้นกับรายการอาร์เรย์จะสะท้อนให้เห็นในไฟล์เอาต์พุต

## บทสรุป

การเพิ่มรายการอาร์เรย์ด้วย Aspose.Page ใน .NET เป็นกระบวนการที่ไม่ซับซ้อน ดังที่แสดงในบทช่วยสอนนี้ ด้วยข้อกำหนดเบื้องต้นที่เหมาะสมและคำแนะนำทีละขั้นตอน นักพัฒนาสามารถจัดการไฟล์ EPS ได้อย่างราบรื่น เพื่อให้มั่นใจว่าเอกสารของพวกเขาตรงตามข้อกำหนดเมตาดาต้าเฉพาะ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page เข้ากันได้กับสภาพแวดล้อม .NET ทั้งหมดหรือไม่

ตอบ 1: ใช่ Aspose.Page ได้รับการออกแบบมาให้ทำงานได้อย่างราบรื่นกับสภาพแวดล้อม .NET ทั้งหมด โดยมีฟังก์ชันการทำงานที่สอดคล้องกันในทุกแพลตฟอร์ม

### คำถามที่ 2: ฉันสามารถใช้ Aspose.Page ได้ฟรีหรือไม่

 คำตอบ 2: Aspose.Page มีเวอร์ชันทดลองใช้ฟรี ให้ผู้ใช้สามารถสำรวจฟีเจอร์ต่างๆ ของมันได้ สำหรับการใช้งานต่อเนื่อง จะต้องซื้อใบอนุญาตจาก[ที่นี่](https://purchase.aspose.com/buy).

### คำถามที่ 3: Aspose.Page มีใบอนุญาตชั่วคราวหรือไม่

 A3: ได้ สามารถรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/) สำหรับความต้องการของโครงการระยะสั้น

### คำถามที่ 4: ฉันจะหาการสนับสนุนชุมชนสำหรับ Aspose.Page ได้ที่ไหน

A4: สำหรับการสนทนาและการสนับสนุนของชุมชน โปรดไปที่[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39).

### คำถามที่ 5: Aspose.Page สำหรับ .NET เวอร์ชันล่าสุดคืออะไร

 A5: หากต้องการเข้าถึงเวอร์ชันล่าสุดของ Aspose.Page สำหรับ .NET โปรดดูที่[เอกสารประกอบ](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
