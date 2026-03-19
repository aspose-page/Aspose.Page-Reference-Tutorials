---
date: 2026-03-19
description: เรียนรู้วิธีเพิ่มตั๋วโดยการสร้างตั๋วพิมพ์แบบกำหนดเองด้วย Aspose.Page
  สำหรับ .NET ปรับประสบการณ์การพิมพ์ของคุณด้วยการควบคุมที่ละเอียดอ่อน
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 'วิธีเพิ่มตั๋ว: สร้างตั๋วการพิมพ์แบบกำหนดเองด้วย Aspose.Page สำหรับ .NET'
url: /th/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม Ticket: สร้าง Custom Print Ticket ด้วย Aspose.Page สำหรับ .NET

## คำนำ

หากคุณต้องการ **วิธีเพิ่ม ticket** ในแอปพลิเคชัน .NET, Aspose.Page จะมอบพลังให้คุณสร้าง custom print ticket โดยตรงจากโค้ด ในบทเรียนนี้เราจะเดินผ่านกระบวนการทั้งหมด—ตั้งค่าสภาพแวดล้อม, สร้างเอกสาร XPS, แนบ custom job print ticket, และบันทึกผลลัพธ์ เมื่อเสร็จคุณจะสามารถเพิ่มการสนับสนุน ticket ให้กับ workflow การพิมพ์ใด ๆ ได้อย่างมั่นใจ

## คำตอบสั้น
- **“add ticket” หมายถึงอะไร?** หมายถึงการฝัง custom print ticket (metadata ของ XPS) ที่ควบคุมการตั้งค่าของเครื่องพิมพ์  
- **ต้องใช้ไลบรารีใด?** Aspose.Page for .NET  
- **ต้องมีลิขสิทธิ์หรือไม่?** ลิขสิทธิ์ชั่วคราวใช้สำหรับการประเมิน; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง  
- **ใช้กับ .NET Core ได้หรือไม่?** ใช่, Aspose.Page รองรับ .NET Framework และ .NET Core  
- **ใช้เวลาติดตั้งเท่าไหร่?** ปกติไม่เกิน 15 นาทีสำหรับ ticket พื้นฐาน

## Custom Print Ticket คืออะไร?
Custom print ticket คือคำอธิบายแบบ XML ของการตั้งค่าการพิมพ์ (เช่น การจัดเรียง, จำนวนสำเนา, การจัดการสี ฯลฯ) ที่เดินทางพร้อมกับเอกสาร XPS มันทำให้ผู้พัฒนาสามารถกำหนดวิธีการพิมพ์เอกสารได้โดยอัตโนมัติ ลดการตั้งค่าด้วยมือบนเครื่องลูกข่าย

## ทำไมต้องเพิ่มการสนับสนุน ticket ด้วย Aspose.Page?
- **การควบคุมละเอียด:** ตั้งค่า collate, จำนวนสำเนา, ประเภทสื่อ, และอื่น ๆ จากโค้ด  
- **ความสอดคล้องข้ามแพลตฟอร์ม:** ticket เดียวกันทำงานบนเครื่องพิมพ์ใดก็ได้ที่เข้าใจ metadata ของ XPS  
- **การบูรณาการที่ราบรื่น:** ทำงานโดยตรงกับโปรเจกต์ .NET ของคุณโดยไม่ต้องใช้บริการเสริม

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความชำนาญพื้นฐานใน C# และการพัฒนา .NET  
- Visual Studio (รุ่นล่าสุดใดก็ได้) ติดตั้งอยู่  
- ไลบรารี Aspose.Page for .NET เพิ่มในโปรเจกต์ของคุณ  

หากคุณยังไม่ได้เพิ่มไลบรารี, สามารถดาวน์โหลดได้จาก [เอกสาร Aspose.Page for .NET](https://reference.aspose.com/page/net/). สำหรับการช่วยเหลือจากชุมชน, เยี่ยมชม [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39).

## นำเข้า Namespaces

เริ่มต้นด้วยการเรียกใช้ namespaces ที่เปิดเผยคลาส XPS และ metadata

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

ตอนนี้เราจะอธิบายการทำงานทีละขั้นตอน

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสาร

กำหนดตำแหน่งที่ไฟล์ XPS ที่สร้างจะถูกบันทึก

```csharp
string dir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง XPS Document ใหม่

สร้างอ็อบเจ็กต์ XPS ใหม่ที่จะเก็บหน้าและ ticket

```csharp
XpsDocument xDocs = new XpsDocument();
```

## ขั้นตอนที่ 3: เพิ่ม Custom Job Print Ticket

แนบ custom job print ticket ไปยังเอกสาร นี่คือหัวใจของ **วิธีเพิ่ม ticket** — ที่นี่คุณจะระบุ collate, copies, rendering intent, การจัดการสี, และการตั้งค่าอื่น ๆ ที่ต้องการ

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **เคล็ดลับ:** แทนที่สตริง snapshot ตัวอย่างด้วยโครงสร้าง DEVMODE ที่เข้ารหัสเป็น Base64 ซึ่งสอดคล้องกับความสามารถของเครื่องพิมพ์ของคุณ

## ขั้นตอนที่ 4: บันทึกเอกสาร

บันทึก XPS document (พร้อม ticket ที่ฝังอยู่) ลงดิสก์

```csharp
xDocs.Save(dir + "output1.xps");
```

เมื่อคุณเปิด *output1.xps* ในตัวดูที่สนับสนุน metadata ของ XPS, เครื่องพิมพ์จะใช้การตั้งค่าที่กำหนดใน ticket โดยอัตโนมัติ

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|----------|
| Ticket ไม่ถูกนำไปใช้ | ตัวดูละเลย metadata ของ XPS | ใช้ไดรเวอร์เครื่องพิมพ์ที่รองรับ XPS print tickets หรือใช้ตัวดูเช่น Microsoft XPS Viewer |
| Base64 snapshot ไม่ถูกต้อง | ข้อมูล DEVMODE เสียหาย | สร้าง snapshot ใหม่จากไดรเวอร์เครื่องพิมพ์โดยใช้ API `GetPrinter` |
| ขาดสิทธิ์ | การเขียนไปยัง `dir` ถูกปฏิเสธ | ตรวจสอบให้แอปพลิเคชันทำงานด้วยสิทธิ์การเข้าถึงไฟล์ระบบที่เพียงพอ |

## คำถามที่พบบ่อย

**ถาม: สามารถใช้ Aspose.Page for .NET กับเฟรมเวิร์ก .NET อื่น ๆ ได้หรือไม่?**  
ตอบ: ใช่, Aspose.Page ทำงานกับ .NET Framework, .NET Core, .NET 5/6 และรุ่นต่อ ๆ ไป

**ถาม: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page ได้อย่างไร?**  
ตอบ: เยี่ยมชม [ลิงก์นี้](https://purchase.aspose.com/temporary-license/) เพื่อรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page

**ถาม: มีฟอรั่มชุมชนสำหรับการสนับสนุน Aspose.Page หรือไม่?**  
ตอบ: แน่นอน, คุณสามารถค้นหาการสนทนาและการสนับสนุนที่เป็นประโยชน์ใน [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39)

**ถาม: ประเภทสื่อใดบ้างที่รองรับใน custom print tickets?**  
ตอบ: Aspose.Page รองรับประเภทสื่อหลากหลาย รวมถึงกระดาษธรรมดา, กระดาษเงา, และการกำหนดสื่อแบบกำหนดเอง

**ถาม: มีตัวอย่างโปรเจกต์สำหรับ Aspose.Page for .NET หรือไม่?**  
ตอบ: สำรวจ [เอกสาร](https://reference.aspose.com/page/net/) เพื่อดูตัวอย่างโปรเจกต์และโค้ดสแนปเพื่อต่อยอดการพัฒนา

## สรุป

เราได้อธิบาย **วิธีเพิ่ม ticket** ให้กับเอกสาร XPS ด้วย Aspose.Page for .NET แล้ว ด้วยขั้นตอนเหล่านี้คุณสามารถฝังคำสั่งการพิมพ์ที่สมบูรณ์ลงในไฟล์ของคุณ ทำให้คุณควบคุม workflow การพิมพ์จากภายในแอปพลิเคชัน .NET ของคุณได้อย่างเต็มที่ อย่าลังเลที่จะทดลองตั้งค่า ticket เพิ่มเติมเพื่อให้ตรงกับสภาพแวดล้อมการพิมพ์ของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-19  
**ทดสอบด้วย:** Aspose.Page for .NET (รุ่นเสถียรล่าสุด)  
**ผู้เขียน:** Aspose  

---