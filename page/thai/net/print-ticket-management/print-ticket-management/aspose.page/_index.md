---
title: แก้ไขตั๋วพิมพ์ที่มีอยู่ด้วย Aspose.Page สำหรับ .NET
linktitle: แก้ไขตั๋วพิมพ์ที่มีอยู่
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีแก้ไขตั๋วพิมพ์ในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา ปรับปรุงการควบคุมการพิมพ์เอกสารได้อย่างง่ายดาย
weight: 11
url: /th/net/print-ticket-management/print-ticket-management/aspose.page/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แก้ไขตั๋วพิมพ์ที่มีอยู่ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

ยินดีต้อนรับสู่คู่มือที่ครอบคลุมเกี่ยวกับการแก้ไขตั๋วพิมพ์ที่มีอยู่โดยใช้ Aspose.Page สำหรับ .NET! Aspose.Page เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาทำงานกับเอกสาร XPS ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแก้ไขตั๋วที่พิมพ์ออกมาพร้อมตัวอย่างที่ใช้งานได้จริง โดยแจกแจงรายละเอียดแต่ละขั้นตอนเพื่อประสบการณ์การเรียนรู้ที่ราบรื่น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
- Aspose.Page สำหรับไลบรารี .NET ที่ดาวน์โหลดและอ้างอิงในโครงการของคุณ

 หากคุณยังไม่ได้ติดตั้ง Aspose.Page สำหรับ .NET คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).

## นำเข้าเนมสเปซ

ขั้นแรก ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ สิ่งนี้ทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงฟังก์ชัน Aspose.Page ได้

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

ตอนนี้ เรามาแบ่งโค้ดตัวอย่างที่คุณระบุออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dir = "Your Document Directory";
```

 นี่ครับ แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงที่มีเอกสาร XPS ของคุณอยู่

## ขั้นตอนที่ 2: เปิดเอกสาร XPS พร้อมตั๋วพิมพ์

```csharp
// เอ็กซ์สตาร์ท:3
XpsDocument xDocs = new XpsDocument(dir + "input3.xps");
JobPrintTicket pt = xDocs.JobPrintTicket;
// สิ้นสุด:3
```

ขั้นตอนนี้เกี่ยวข้องกับการเปิดเอกสาร XPS และรับ JobPrintTicket

## ขั้นตอนที่ 3: ลบพารามิเตอร์ออกจาก Job Print Ticket

```csharp
// เอ็กซ์สตาร์ท:4
pt.Remove(
	"ns0000:PageDevmodeSnapshot",
	"ns0000:JobInterleaving",
	"ns0000:JobImageType");
// สิ้นสุด:4
```

 ลบพารามิเตอร์ที่ไม่ต้องการออกจาก JobPrintTicket โดยใช้`Remove`วิธี.

## ขั้นตอนที่ 4: เพิ่มพารามิเตอร์ให้กับตั๋วพิมพ์งาน

```csharp
// เอ็กซ์สตาร์ท:5
pt.Add(
	new JobCopiesAllDocuments(2),
	new PageMediaSize(PageMediaSize.PageMediaSizeOption.ISOA4));
// สิ้นสุด:5
```

 เพิ่มพารามิเตอร์ที่ต้องการให้กับ JobPrintTicket โดยใช้`Add`วิธี.

## ขั้นตอนที่ 5: บันทึกเอกสารด้วยตั๋วพิมพ์งานที่เปลี่ยนแปลง

```csharp
// เอ็กซ์สตาร์ท:6
xDocs.Save(dir + "output3.xps");
// สิ้นสุด:6
```

บันทึกเอกสาร XPS ที่แก้ไขด้วย JobPrintTicket ที่อัปเดต

ทำซ้ำขั้นตอนเหล่านี้เพื่อกระบวนการแก้ไขตั๋วพิมพ์ด้วย Aspose.Page สำหรับ .NET ที่ไม่ยุ่งยาก!

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีแก้ไขตั๋วพิมพ์ที่มีอยู่โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว ไลบรารีอันทรงพลังนี้มอบความยืดหยุ่นและความสะดวกในการจัดการเอกสาร XPS ทำให้เป็นเครื่องมืออันล้ำค่าสำหรับนักพัฒนา

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับรูปแบบเอกสารอื่นๆ ได้หรือไม่

ตอบ 1: ใช่ Aspose.Page สำหรับ .NET เน้นที่เอกสาร XPS เป็นหลัก แต่ Aspose มีไลบรารีที่หลากหลายสำหรับรูปแบบที่แตกต่างกัน ตรวจสอบเอกสารประกอบของพวกเขาสำหรับรายละเอียดเพิ่มเติม

### คำถามที่ 2: Aspose.Page สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่

ตอบ 2: ใช่ Aspose.Page สำหรับ .NET เข้ากันได้กับ .NET Core ซึ่งให้ความยืดหยุ่นในสภาพแวดล้อมการพัฒนาของคุณ

### คำถามที่ 3: ฉันจะรับการสนับสนุนหรือถามคำถามที่เกี่ยวข้องกับ Aspose.Page ได้อย่างไร

 A3: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39)เพื่อรับการสนับสนุนจากชุมชนและเชื่อมต่อกับนักพัฒนารายอื่น

### คำถามที่ 4: Aspose.Page สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 A4: ใช่ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A5: เยี่ยมเลย[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อขอรับใบอนุญาตชั่วคราว
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
