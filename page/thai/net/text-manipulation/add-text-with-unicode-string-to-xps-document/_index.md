---
title: เพิ่มข้อความด้วยสตริง Unicode ลงในเอกสาร XPS ด้วย Aspose.Page
linktitle: เพิ่มข้อความด้วยสตริง Unicode ลงในเอกสาร XPS
second_title: Aspose.Page .NET API
description: สำรวจพลังของ Aspose.Page สำหรับ .NET ด้วยคำแนะนำทีละขั้นตอนในการเพิ่มข้อความ Unicode ลงในเอกสาร XPS
weight: 12
url: /th/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มข้อความด้วยสตริง Unicode ลงในเอกสาร XPS ด้วย Aspose.Page

## การแนะนำ

ในสภาพแวดล้อมการพัฒนา .NET ที่เปลี่ยนแปลงตลอดเวลา Aspose.Page มีความโดดเด่นในฐานะเครื่องมืออันทรงพลังสำหรับการจัดการเอกสาร XPS ในบรรดาคุณสมบัติต่างๆ มากมาย ความสามารถในการเพิ่มข้อความด้วยสตริง Unicode ลงในเอกสาร XPS ถือเป็นฟังก์ชันการทำงานที่มีคุณค่า คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ เพื่อให้มั่นใจว่าคุณจะควบคุมความสามารถนี้ได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความเข้าใจพื้นฐานเกี่ยวกับการพัฒนา .NET
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  Aspose.Page สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/net/).

## นำเข้าเนมสเปซ

ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ ซึ่งจะจัดเตรียมคลาสและฟังก์ชันที่จำเป็นสำหรับการทำงานกับ Aspose.Page เนมสเปซที่จำเป็นมีดังนี้:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ขั้นตอนที่ 1: ตั้งค่าเอกสาร

ขั้นแรก สร้างเอกสาร XPS ใหม่ที่คุณจะเพิ่มข้อความ Unicode ทำตามข้อมูลโค้ดด้านล่าง:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// สร้างเอกสาร XPS ใหม่
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 2: เพิ่มข้อความ Unicode

ตอนนี้ มาเพิ่มข้อความ Unicode ลงในเอกสาร XPS กันดีกว่า ตัวอย่างนี้ใช้ฟอนต์ Arial ตั้งค่าขนาดฟอนต์เป็น 20 และวางตำแหน่งข้อความที่พิกัด (400f, 200f) สตริง Unicode ในกรณีนี้คือ "TEN. rof SPX.esopsA" ตรวจสอบข้อมูลโค้ดด้านล่าง:

```csharp
// เพิ่มข้อความ
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## ขั้นตอนที่ 3: บันทึกเอกสาร

เมื่อเพิ่มข้อความ Unicode แล้ว ให้บันทึกเอกสาร XPS ที่เป็นผลลัพธ์ ขั้นตอนสุดท้ายมีดังนี้:

```csharp
// บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
doc.Save(dataDir + "AddTextRTL_out.xps");
```

ยินดีด้วย! คุณได้เพิ่มข้อความ Unicode ลงในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการเพิ่มข้อความ Unicode ลงในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET ฟังก์ชันการทำงานนี้เปิดประตูสู่การสร้างเอกสารที่หลากหลายและไดนามิกภายในสภาพแวดล้อม .NET

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page เข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุดหรือไม่

ตอบ 1: ใช่ Aspose.Page ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าเข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุด

### คำถามที่ 2: ฉันสามารถปรับแต่งรูปแบบและขนาดแบบอักษรเมื่อเพิ่มข้อความได้หรือไม่

A2: แน่นอน! โค้ดตัวอย่างที่ให้ไว้ช่วยให้คุณสามารถปรับแต่งรูปแบบตัวอักษร ขนาด และคุณลักษณะอื่นๆ ได้อย่างง่ายดาย

### คำถามที่ 3: ฉันจะหาเอกสารเพิ่มเติมสำหรับ Aspose.Page ได้ที่ไหน

 A3: คุณสามารถดูเอกสารประกอบได้[ที่นี่](https://reference.aspose.com/page/net/) สำหรับข้อมูลและตัวอย่างที่ครอบคลุม

### คำถามที่ 4: มีแหล่งข้อมูลฟรีสำหรับการเริ่มต้นใช้งาน Aspose.Page หรือไม่

 A4: ใช่ คุณสามารถสำรวจได้[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปรายของชุมชน

### คำถามที่ 5: มีเวอร์ชันทดลองใช้ก่อนตัดสินใจซื้อหรือไม่

 A5: แน่นอน! คุณสามารถเข้าถึงเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/) ก่อนตัดสินใจซื้อ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
