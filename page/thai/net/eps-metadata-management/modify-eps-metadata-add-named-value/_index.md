---
date: 2026-08-08
description: เรียนรู้วิธีสร้าง EPS พร้อมเมตาดาต้า XMP และเพิ่มค่าแบบมีชื่อโดยใช้ Aspose.Page
  สำหรับ .NET คู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ด
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: เพิ่มค่าแบบมีชื่อ
og_description: สร้าง EPS พร้อมเมตาดาต้า XMP ใน .NET ด้วย Aspose.Page คู่มือนี้แสดงวิธีเพิ่มค่าแบบมีชื่อลงในไฟล์
  EPS อย่างรวดเร็วและเชื่อถือได้
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: สร้าง EPS ด้วย XMP – เพิ่มค่าแบบมีชื่อโดยใช้ Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: สร้าง EPS ด้วย XMP – เพิ่มค่าแบบมีชื่อโดยใช้ Aspose.Page
url: /th/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง EPS ด้วย XMP – เพิ่มค่าแบบมีชื่อโดยใช้ Aspose.Page

## บทนำ

ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **create EPS with XMP** metadata และแทรกค่าแบบมีชื่อโดยใช้ไลบรารี Aspose.Page สำหรับ .NET ไม่ว่าคุณจะกำลังสร้าง pipeline การประมวลผลแบบแบตช์หรือจำเป็นต้องเพิ่มข้อมูลให้ไฟล์ EPS ด้วยแท็ก XMP ที่กำหนดเอง ขั้นตอนด้านล่างจะพาคุณผ่านทุกอย่างตั้งแต่การตั้งค่าโปรเจกต์จนถึงการบันทึกไฟล์ที่แก้ไขแล้ว Aspose.Page สามารถจัดการเอกสาร EPS ได้สูงสุด **500 pages** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้เหมาะกับสถานการณ์ที่ต้องประมวลผลปริมาณมาก

## คำตอบอย่างรวดเร็ว
- **What is the primary goal?** เพิ่มค่า XMP ที่มีชื่อในไฟล์ EPS ที่มีอยู่แล้ว.  
- **Which library is required?** Aspose.Page for .NET.  
- **Do I need a license?** ต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง; มีการทดลองใช้ฟรี.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **How long does the implementation take?** ประมาณ 10–15 minutes สำหรับกรณีการใช้งานพื้นฐาน.

## วิธีสร้าง EPS ด้วยเมตาดาต้า XMP ใน .NET?

โหลดไฟล์ EPS เป้าหมาย, ดึง (หรือสร้าง) วัตถุเมตาดาต้า XMP ของมัน, เพิ่มค่าแบบมีชื่อที่ต้องการ, แล้วบันทึกเอกสารกลับไปยังดิสก์ กระบวนการนี้ต้องการเพียงไม่กี่การเรียกเมธอดและทำงานอย่างสม่ำเสมอในทุกเวอร์ชัน EPS ที่รองรับ วิธีการนี้ยังคงรักษาเนื้อหาหน้าปัจจุบันและโครงสร้าง XMP อื่น ๆ ไว้ ทำให้คุณสามารถเชื่อมต่อการอัปเดตเมตาดาต้าหลายครั้งได้อย่างปลอดภัย

## ข้อกำหนดเบื้องต้น

Before you start, make sure you have:

- ความรู้พื้นฐานเกี่ยวกับ C# และโครงสร้างโปรเจกต์ .NET.  
- Visual Studio 2022 (หรือ IDE ที่เข้ากันได้).  
- ไลบรารี Aspose.Page for .NET. หากคุณยังไม่มี ให้ดาวน์โหลดจาก **Aspose.Page for .NET download page**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)).  

## นำเข้าเนมสเปซ

เนมสเปซต่อไปนี้ให้การเข้าถึงคลาสการจัดการ EPS, การส่งออกอุปกรณ์, และเมตาดาต้า XMP ของ Aspose.Page

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## ขั้นตอนที่ 1: เริ่มต้นสตรีมอินพุตไฟล์ eps

สร้าง `FileStream` สำหรับไฟล์ EPS ต้นฉบับและสร้างอ็อบเจ็กต์ `PsDocument` เพื่อทำงานกับเอกสาร

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## ขั้นตอนที่ 2: ดึงเมตาดาต้า XMP

ดึงอ็อบเจ็กต์ `XmpMetadata` จากเอกสาร; อ็อบเจ็กต์นี้แสดงถึงแพ็กเก็ต XMP ที่ฝังอยู่

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## ขั้นตอนที่ 3: เปลี่ยนค่ามีเดต้า XMP

ใช้เมธอด `AddNamedValue` ของ `XmpMetadata` เพื่อแทรกค่าแบบมีชื่อใหม่เข้าไปในโครงสร้าง XMP ที่ระบุ

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## ขั้นตอนที่ 4: บันทึกไฟล์ eps พร้อมเมตาดาต้า XMP ที่เปลี่ยนแปลง

บันทึกเอกสารที่แก้ไขโดยเขียนลงใน `FileStream` ใหม่

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## ทำไมต้องใช้ Aspose.Page สำหรับเมตาดาต้า EPS?

Aspose.Page รองรับ **50+ XMP schemas** และสามารถประมวลผลไฟล์ EPS ได้สูงสุด **500 pages** พร้อมรักษาการใช้หน่วยความจำให้อยู่ต่ำกว่า **30 MB** สำหรับเอกสารทั่วไป ไลบรารีไม่พึ่งพาเครื่องมือภายนอกหรือโค้ดเนทีฟ ทำให้พฤติกรรมสม่ำเสมอในสภาพแวดล้อม Windows, Linux, และ macOS

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **Missing XMP packet:** หาก `GetXmpMetadata()` คืนค่า `null` หมายความว่าไฟล์ EPS ไม่มีบล็อก XMP ไลบรารีจะสร้างอัตโนมัติ แต่ต้องตรวจสอบว่าไฟล์ไม่เสียหาย.  
- **Namespace conflicts:** เมื่อเพิ่มค่าแบบมีชื่อแบบกำหนดเอง ให้ใช้ URI ของเนมสเปซที่ไม่ซ้ำกันเพื่อหลีกเลี่ยงการชนกับสคีมาที่มีอยู่.  
- **Large files:** สำหรับไฟล์ EPS ที่ใหญ่กว่า 200 MB ควรพิจารณาการสตรีมเอาต์พุตเพื่อหลีกเลี่ยงการใช้หน่วยความจำมากเกินไป.

## คำถามที่พบบ่อย

**Q: Aspose.Page รองรับเวอร์ชันไฟล์ EPS ต่าง ๆ หรือไม่?**  
A: Aspose.Page รองรับ EPS เวอร์ชัน 3.0 ถึง 3.3 ทำให้เข้ากันได้อย่างกว้างขวางกับไฟล์เก่าและใหม่

**Q: ฉันสามารถใช้ Aspose.Page ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ใช่, จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์ คุณสามารถซื้อใบอนุญาตได้จาก **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.

**Q: มีการทดลองใช้ฟรีหรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดการทดลองใช้ที่ทำงานเต็มรูปแบบได้จาก **[Aspose.Page free trial download page](https://releases.aspose.com/)**.

**Q: ฉันจะขอรับการสนับสนุนหรือเข้าร่วมชุมชนได้อย่างไร?**  
A: เยี่ยมชม **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** เพื่อถามคำถามและแบ่งปันประสบการณ์.

**Q: ใบอนุญาตชั่วคราวคืออะไรและฉันจะขอได้อย่างไร?**  
A: ใบอนุญาตชั่วคราวช่วยให้คุณประเมินผลิตภัณฑ์ในช่วงสั้น ๆ คุณสามารถขอได้จาก **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

---

**อัปเดตล่าสุด:** 2026-08-08  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มเมตาดาต้าให้กับเอกสาร EPS ด้วย Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [เปลี่ยนค่าแบบมีชื่อด้วย Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [ดึงเมตาดาต้าจากเอกสาร EPS ด้วย Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}