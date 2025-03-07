---
title: เพิ่มค่าชื่อด้วย Aspose.Page
linktitle: เพิ่มค่าชื่อ
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีเพิ่มค่าที่มีชื่อให้กับไฟล์ EPS ใน .NET โดยใช้ Aspose.Page บทช่วยสอนที่ครอบคลุมนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน
weight: 12
url: /th/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มค่าชื่อด้วย Aspose.Page

## การแนะนำ

ในขอบเขตของการประมวลผลเอกสารด้วย .NET นั้น Aspose.Page มีความโดดเด่นในฐานะเครื่องมืออันทรงพลังสำหรับการจัดการไฟล์ EPS Aspose.Page ช่วยให้นักพัฒนาจัดการข้อมูลเมตา XMP ได้ อำนวยความสะดวกให้กับงานต่างๆ เช่น การเพิ่มค่าที่กำหนดชื่อ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มค่าที่มีชื่อให้กับไฟล์ EPS โดยใช้ Aspose.Page ในลักษณะทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Visual Studio ที่ติดตั้ง
-  Aspose.Page สำหรับไลบรารี .NET หากไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/net/).

## นำเข้าเนมสเปซ

ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณกันก่อน เนมสเปซเหล่านี้มีความสำคัญต่อการเข้าถึงฟังก์ชันการทำงานที่ Aspose.Page มอบให้:

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

 ขั้นตอนเริ่มต้นเกี่ยวข้องกับการเริ่มต้นสตรีมอินพุตสำหรับไฟล์ EPS แทนที่`"Your Document Directory"` ด้วยเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:

```csharp
// เอ็กซ์สตาร์ท:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## ขั้นตอนที่ 2: รับข้อมูลเมตา XMP

ดึงข้อมูลเมตา XMP จากไฟล์ EPS หากไฟล์ EPS ขาดข้อมูลเมตา XMP ไฟล์ใหม่จะถูกสร้างขึ้นโดยเติมค่าจากความคิดเห็นข้อมูลเมตา PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## ขั้นตอนที่ 3: เปลี่ยนค่าข้อมูลเมตา XMP

ตอนนี้ เรามาทำการเปลี่ยนแปลงข้อมูลเมตา XMP กันดีกว่า ในตัวอย่างนี้ เราจะเพิ่มค่าที่มีชื่อให้กับโครงสร้าง "xmpTPg:MaxPageSize":

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## ขั้นตอนที่ 4: บันทึกไฟล์ EPS ด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง

บันทึกไฟล์ EPS ด้วยข้อมูลเมตา XMP ที่อัปเดต สร้างเอาต์พุตสตรีมและบันทึกไฟล์ EPS ที่แก้ไข:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## บทสรุป

ยินดีด้วย! คุณได้เพิ่มค่าที่มีชื่อลงในไฟล์ EPS โดยใช้ Aspose.Page ใน .NET สำเร็จแล้ว บทช่วยสอนนี้ได้อธิบายขั้นตอนสำคัญต่างๆ ให้คุณทราบ โดยจัดแสดงความเรียบง่ายและประสิทธิผลของ Aspose.Page ในการจัดการเอกสาร

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page เข้ากันได้กับไฟล์ EPS เวอร์ชันต่างๆ หรือไม่

คำตอบ 1: Aspose.Page รองรับไฟล์ EPS เวอร์ชันต่างๆ เพื่อให้มั่นใจว่าสามารถใช้งานร่วมกับเอกสารได้หลากหลาย

### คำถามที่ 2: ฉันสามารถใช้ Aspose.Page สำหรับโครงการเชิงพาณิชย์ได้หรือไม่

 A2: ใช่ Aspose.Page มาพร้อมกับใบอนุญาตเชิงพาณิชย์ และคุณสามารถซื้อได้[ที่นี่](https://purchase.aspose.com/buy).

### คำถามที่ 3: Aspose.Page มีรุ่นทดลองใช้ฟรีหรือไม่

 A3: ได้ คุณสามารถสำรวจ Aspose.Page พร้อมให้ทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะรับการสนับสนุนหรือเชื่อมต่อกับชุมชน Aspose ได้อย่างไร

 A4: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนและเชื่อมต่อกับชุมชน

### คำถามที่ 5: ใบอนุญาตชั่วคราวคืออะไร และฉันจะขอรับใบอนุญาตได้อย่างไร

 A5: หากคุณต้องการใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการทดสอบหรือประเมินผล คุณสามารถขอรับได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
