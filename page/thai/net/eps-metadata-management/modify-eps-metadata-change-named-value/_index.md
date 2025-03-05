---
title: เปลี่ยนค่าชื่อด้วย Aspose.Page สำหรับ .NET
linktitle: เปลี่ยนค่าชื่อ
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีเปลี่ยนชื่อในไฟล์ EPS โดยใช้ Aspose.Page สำหรับ .NET ปรับแต่งข้อมูลเมตา XMP ได้อย่างง่ายดายเพื่อการประมวลผลเอกสารที่ปรับแต่งโดยเฉพาะ
type: docs
weight: 16
url: /th/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## การแนะนำ

ในโลกของการประมวลผลเอกสาร Aspose.Page สำหรับ .NET มีความโดดเด่นในฐานะเครื่องมืออันทรงพลังสำหรับจัดการไฟล์ EPS ฟังก์ชันหลักประการหนึ่งที่มีให้คือความสามารถในการเปลี่ยนค่าที่มีชื่อภายในเมตาดาต้า XMP บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเปลี่ยนชื่อโดยใช้ Aspose.Page สำหรับ .NET ซึ่งช่วยให้คุณปรับแต่งไฟล์ EPS ตามความต้องการเฉพาะของคุณได้

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page สำหรับ .NET แล้ว ถ้าไม่คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).

- ไดเร็กทอรีเอกสาร: มีไดเร็กทอรีที่กำหนดสำหรับไฟล์ EPS ของคุณ ซึ่งคุณสามารถดำเนินการเปลี่ยนแปลงค่าที่ตั้งชื่อได้

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันที่ Aspose.Page มอบให้ เพิ่มเนมสเปซต่อไปนี้ลงในโค้ดของคุณ:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ตอนนี้ เรามาแบ่งโค้ดออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ครอบคลุม:

## ขั้นตอนที่ 1: เริ่มต้นสตรีมอินพุตไฟล์ EPS

```csharp
// เอ็กซ์สตาร์ท:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// สิ้นสุด:1
```

ในขั้นตอนนี้ เราได้ตั้งค่าอินพุตสตรีมสำหรับไฟล์ EPS ที่คุณต้องการแก้ไข ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: รับข้อมูลเมตา XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

ดึงข้อมูลเมตา XMP ที่มีอยู่จากไฟล์ EPS หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP ไฟล์ใหม่จะถูกสร้างขึ้นโดยมีค่าจากความคิดเห็นข้อมูลเมตา PS

## ขั้นตอนที่ 3: เปลี่ยนค่าข้อมูลเมตา XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

ที่นี่ เราสาธิตการเปลี่ยนแปลงค่าที่มีชื่อสองค่าภายในโครงสร้าง "xmpTPg:MaxPageSize" คุณสามารถปรับแต่งสิ่งนี้ได้ตามความต้องการเฉพาะของคุณ

## ขั้นตอนที่ 4: บันทึกไฟล์ EPS ด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

บันทึกไฟล์ EPS ที่แก้ไขไปยังเอาต์พุตสตรีม ตอนนี้ไฟล์จะแสดงการเปลี่ยนแปลงที่ทำกับข้อมูลเมตา XMP

## บทสรุป

ด้วยบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ประโยชน์จาก Aspose.Page สำหรับ .NET เพื่อเปลี่ยนชื่อค่าภายในเมตาดาต้า XMP ในไฟล์ EPS ฟังก์ชันการทำงานนี้เปิดโลกแห่งความเป็นไปได้ในการปรับแต่งและปรับแต่งเอกสารของคุณให้ตรงตามความต้องการเฉพาะ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับรูปแบบเอกสารอื่นๆ ได้หรือไม่

A1: ใช่ Aspose.Page รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง EPS, XPS และ PDF

### คำถามที่ 2: Aspose.Page สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่

 A2: ได้ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A3: โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/page/net/).

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A4: คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: Aspose.Page สำหรับผู้ใช้ .NET มีตัวเลือกการสนับสนุนใดบ้าง

 A5: เยี่ยมชมฟอรั่มชุมชน[ที่นี่](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปราย