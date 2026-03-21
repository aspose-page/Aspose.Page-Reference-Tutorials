---
date: 2026-03-21
description: เรียนรู้วิธีสร้างเอกสาร XPS ด้วย .NET และเพิ่มข้อความโดยใช้ Aspose.Page
  สำหรับ .NET คู่มือแบบขั้นตอนสำหรับนักพัฒนา .NET
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: สร้างเอกสาร XPS ด้วย .NET และเพิ่มข้อความด้วย Aspose.Page
url: /th/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร XPS .NET และเพิ่มข้อความด้วย Aspose.Page

ในการพัฒนา .NET สมัยใหม่ ความสามารถในการ **สร้างเอกสาร XPS .NET** อย่างอัตโนมัติเป็นทักษะที่มีคุณค่า โดยเฉพาะเมื่อคุณต้องการสร้างรายงานที่พิมพ์ได้ ใบแจ้งหนี้ หรือกราฟิกแบบกำหนดเอง บทเรียนนี้จะพาคุณผ่านการใช้ Aspose.Page เพื่อ **aspose.page add text** ลงในเอกสาร XPS ให้คุณควบคุมการจัดวางและการสไตล์ได้เต็มที่—ทั้งหมดจากแอปพลิเคชัน .NET ของคุณ

## คำตอบสั้น ๆ
- **บทเรียนนี้ครอบคลุมอะไร?** การเพิ่มข้อความลงในเอกสาร XPS ที่สร้างใหม่โดยใช้ Aspose.Page สำหรับ .NET  
- **ใช้เวลานานเท่าไหร่?** ประมาณ 5‑10 นาทีสำหรับการทำงานพื้นฐาน  
- **ต้องมีสิ่งเตรียมอะไรบ้าง?** สภาพแวดล้อมการพัฒนา .NET และไลบรารี Aspose.Page  
- **ต้องมีลิขสิทธิ์หรือไม่?** ใช่ ต้องมีลิขสิทธิ์ Aspose.Page ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์  
- **สามารถรันบน .NET Core / .NET 6+ ได้หรือไม่?** แน่นอน – Aspose.Page รองรับ .NET เวอร์ชันล่าสุดทั้งหมด

## create xps document .net คืออะไร?

การสร้างเอกสาร XPS ใน .NET หมายถึงการสร้างไฟล์แบบเลย์เอาต์คงที่ที่รักษาลักษณะการแสดงผลของเนื้อหาอย่างแม่นยำบนอุปกรณ์และเครื่องพิมพ์ต่าง ๆ XPS (XML Paper Specification) เป็นมาตรฐานเปิดของ Microsoft สำหรับการอธิบายหน้า คล้ายกับ PDF แต่เป็น XML‑based อย่างเต็มรูปแบบ

## ทำไมต้องใช้ Aspose.Page เพื่อเพิ่มข้อความ?

Aspose.Page มี API ระดับสูงแบบเชิงวัตถุที่ทำให้คุณไม่ต้องจัดการกับ markup ของ XPS ระดับล่าง คุณสามารถเพิ่มข้อความ กราฟิก และรูปร่างได้โดยไม่ต้องเขียน XML ดิบ ทำให้กระบวนการพัฒนารวดเร็วและลดความผิดพลาด

## สิ่งจำเป็นก่อนเริ่ม

- Aspose.Page for .NET: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Page แล้ว คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/)  
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อม .NET ของคุณ หากยังไม่ได้ทำตามขั้นตอนการติดตั้งใน [documentation](https://reference.aspose.com/page/net/)  
- โฟลเดอร์เอกสาร: สร้างโฟลเดอร์สำหรับเก็บเอกสารของคุณ แทนที่ “Your Document Directory” ในโค้ดตัวอย่างด้วยพาธจริง

เมื่อเราเข้าใจพื้นฐานแล้ว ไปที่โค้ดกันเลย

## Import Namespaces

ก่อนอื่นให้นำเข้า namespace ที่จำเป็นเพื่อเริ่มโปรเจกต์:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ขั้นตอนที่ 1: Create XPS document .NET

สร้างเอกสาร XPS ใหม่ที่จะทำหน้าที่เป็นผ้าใบสำหรับข้อความของเรา

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## ขั้นตอนที่ 2: Create a brush for text

กำหนด brush สีทึบที่ใช้กำหนดสีของข้อความ ที่นี่เราใช้สีดำ

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## ขั้นตอนที่ 3: Add glyphs (aspose.page add text)

Glyphs คือการแทนค่าตัวอักษรในระดับต่ำของเอกสาร XPS คำสั่งนี้จะเพิ่มข้อความ “Hello World!” ที่พิกัดที่กำหนด

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## ขั้นตอนที่ 4: Save the resultant XPS document

บันทึกเอกสารลงดิสก์เพื่อให้คุณสามารถดูหรือพิมพ์ได้ในภายหลัง

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

โดยทำตามขั้นตอนเหล่านี้ คุณได้ **create XPS document .NET** และเพิ่มข้อความแบบกำหนดเองด้วย Aspose.Page อย่างสำเร็จ

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **File not found** เมื่อบันทึก | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่ | ตรวจสอบให้แน่ใจว่าโฟลเดอร์มีอยู่หรือใช้ `Directory.CreateDirectory(dataDir)` ก่อนบันทึก |
| **Text not visible** | สีของ brush ตรงกับพื้นหลัง | เปลี่ยน `Color.Black` เป็นสีที่ตัดกันได้ |
| **Unsupported font** | ฟอนต์ไม่ได้ติดตั้งบนเครื่อง | ใช้ฟอนต์ที่มีอยู่บนระบบ หรือฝังฟอนต์ด้วยคุณสมบัติการฝังฟอนต์ของ Aspose.Page |

## คำถามที่พบบ่อย

### Q1: สามารถปรับแต่งฟอนต์และขนาดของข้อความที่เพิ่มได้หรือไม่?

A1: ได้ คุณมีการควบคุมเต็มที่ต่อฟอนต์และขนาด ปรับพารามิเตอร์ในเมธอด `AddGlyphs` ตามต้องการ

### Q2: Aspose.Page รองรับ .NET Core หรือไม่?

A2: แน่นอน! Aspose.Page รองรับ .NET Core ทำให้เข้ากันได้กับเทคโนโลยี .NET ล่าสุด

### Q3: มีข้อกำหนดด้านลิขสิทธิ์สำหรับการใช้ Aspose.Page หรือไม่?

A3: มี คุณต้องมีลิขสิทธิ์ที่ถูกต้อง สำรวจตัวเลือกการซื้อได้ [ที่นี่](https://purchase.aspose.com/buy)

### Q4: จะขอรับการสนับสนุนหรือขอความช่วยเหลือได้อย่างไร?

A4: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและรับความช่วยเหลือ

### Q5: มีรุ่นทดลองใช้งานฟรีหรือไม่?

A5: มีแน่นอน! คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้ [ที่นี่](https://releases.aspose.com/)

**คำถามและคำตอบเพิ่มเติม**

**Q: สามารถเพิ่มบล็อกข้อความหลายบล็อกในหน้าเดียวได้หรือไม่?**  
A: ได้ เพียงเรียก `doc.AddGlyphs` หลายครั้งพร้อมพิกัดที่แตกต่างกัน

**Q: Aspose.Page รองรับการหมุนข้อความหรือไม่?**  
A: คุณสามารถใช้เมทริกซ์การแปลงกับอ็อบเจ็กต์ `XpsGlyphs` เพื่อหมุนหรือบิดเบือนข้อความได้

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**อัปเดตล่าสุด:** 2026-03-21  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

---