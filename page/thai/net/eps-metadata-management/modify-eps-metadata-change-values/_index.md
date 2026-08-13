---
date: 2026-08-13
description: เรียนรู้วิธีใช้ Aspose.Page เพื่อเปลี่ยนค่า EPS ในแอปพลิเคชัน .NET รวมถึงการอัปเดต
  XMP metadata อย่างเป็นขั้นตอน
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: เปลี่ยนค่า
og_description: บทเรียน Aspose.Page change EPS values แสดงวิธีแก้ไข XMP metadata ภายในไฟล์
  EPS ด้วย .NET ทำตามคู่มือแบบ step‑by‑step เพื่ออัปเดต creator, title และ modify
  date อย่างทันที
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page เปลี่ยนค่า EPS ด้วย .NET บทเรียน
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page เปลี่ยนค่า EPS ด้วย .NET – บทเรียน
url: /th/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page เปลี่ยนค่า eps ด้วย .NET – บทแนะนำ

## บทนำ

ในบทแนะนำนี้คุณจะได้ค้นพบวิธี **aspose.page change eps values** โดยการแก้ไขเมตาดาต้า XMP ที่ฝังอยู่ในไฟล์ EPS ไม่ว่าคุณจะต้องการอัปเดตชื่อผู้สร้าง ปรับชื่อเรื่อง หรือแก้ไขวันที่แก้ไข Aspose.Page สำหรับ .NET จะมอบ API แบบ code‑first ที่สะอาดและทำงานได้บน Windows, Linux, และ macOS เมื่อจบคู่มือคุณจะมีโค้ดส่วนนำกลับมาใช้ใหม่ที่สามารถนำไปใส่ในบริการหรือแอปคอนโซล .NET ใดก็ได้

## คำตอบอย่างรวดเร็ว
- **บทแนะนำครอบคลุมอะไร?** การเปลี่ยนเมตาดาต้า XMP (creator, title, modify date) ภายในไฟล์ EPS โดยใช้ Aspose.Page สำหรับ .NET.  
- **ต้องการเวอร์ชันของไลบรารีใด?** ปล่อย Aspose.Page สำหรับ .NET ใดก็ได้ที่รองรับ XMP (v24.10+).  
- **ฉันต้องการไลเซนส์หรือไม่?** จำเป็นต้องมีไลเซนส์ชั่วคราวสำหรับการใช้งานจริง; การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา.  
- **ฉันสามารถรันบน .NET Core ได้หรือไม่?** ใช่ – API รองรับ .NET 5, .NET 6, และ .NET Core 3.1+.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 5‑10 นาทีสำหรับการอัปเดตเมตาดาต้าพื้นฐาน.

## XMP metadata คืออะไร?

XMP metadata คือบล็อก XML มาตรฐานที่เก็บข้อมูลอธิบาย (author, title, dates) ภายในไฟล์ EPS และรูปแบบกราฟิกอื่น ๆ มันฝังอยู่โดยตรงในส่วนหัวของไฟล์และสามารถอ่านได้โดยเครื่องมือออกแบบและการเผยแพร่หลาย ๆ ตัว ทำให้การจัดการเมตาดาต้าสอดคล้องกันข้ามแพลตฟอร์ม การอัปเดต XMP ทำให้แอปพลิเคชันต่อไปแสดงคุณสมบัติของเอกสารที่ถูกต้องโดยไม่ต้องเปลี่ยนแปลงเนื้อหาภาพ

## ทำไมต้องใช้ Aspose.Page สำหรับเมตาดาต้า EPS?

Aspose.Page สามารถประมวลผลรูปแบบกราฟิก **30+** และจัดการไฟล์ EPS ขนาดถึง **1 GB** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้ลดการใช้ RAM ลง **70 %** เมื่อเทียบกับการแยกสตรีมแบบธรรมดา ไลบรารียังรับประกันว่าการเรนเดอร์ภาพของ EPS จะไม่เปลี่ยนแปลงหลังจากแก้ไขเมตาดาต้า

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน ให้ตรวจสอบว่ามีสิ่งต่อไปนี้พร้อมใช้งาน:

1. **Aspose.Page for .NET library** – ดาวน์โหลดจากหน้า releases อย่างเป็นทางการของ Aspose.Page for .NET [ที่นี่](https://releases.aspose.com/page/net/). คุณยังสามารถสำรวจ releases ของผลิตภัณฑ์ Aspose อื่น ๆ [ที่นี่](https://releases.aspose.com/).  
2. **Document directory** – สร้างโฟลเดอร์บนเครื่องของคุณเพื่อเก็บไฟล์ EPS ต้นฉบับและไฟล์ผลลัพธ์

เมื่อสภาพแวดล้อมพร้อมแล้ว เรามา import namespaces ที่คุณต้องการใช้กัน

## นำเข้า namespaces

`Aspose.Page` namespace ให้คลาสหลัก ส่วน `System.IO` ให้ความสามารถในการจัดการสตรีม

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## วิธีการเปลี่ยนค่าเมตาดาต้า EPS?

โหลดไฟล์ EPS, ดึง XMP packet, แก้ไขฟิลด์ที่ต้องการ, และเขียน EPS ที่อัปเดตกลับไปยังดิสก์ กระบวนการไม่ต้องเรนเดอร์เนื้อหาหน้า ทำให้เร็วและประหยัดหน่วยความจำ ทำตามขั้นตอนละเอียดเพื่อดูตัวอย่างโค้ดสำหรับแต่ละการดำเนินการ กระบวนการแบบ end‑to‑end นี้อธิบายไว้ในขั้นตอนต่อไป

### ขั้นตอนที่ 1: เริ่มต้นสตรีมอินพุตของไฟล์ EPS

สร้าง `FileStream` แบบอ่าน‑อย่างเดียวที่ชี้ไปยังไฟล์ EPS ต้นฉบับ

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### ขั้นตอนที่ 2: สร้างอินสแตนซ์ PsDocument จากสตรีม

`PsDocument` คืออ็อบเจ็กต์ระดับบนสุดที่แทนเอกสาร EPS ในหน่วยความจำ ให้คุณเข้าถึงเนื้อหาหน้าและเมตาดาต้า XMP ที่ฝังอยู่

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### ขั้นตอนที่ 3: ดึงเมตาดาต้า XMP

พร็อพเพอร์ตี้ `XmpMetadata` จะคืนค่าอ็อบเจ็กต์ `XmpPacket` ที่คุณสามารถสอบถามและแก้ไขได้

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### ขั้นตอนที่ 4: แก้ไขค่าเมตาดาต้า XMP

ตอนนี้คุณจะเปลี่ยนสามฟิลด์ทั่วไป: **ModifyDate**, **Creator**, และ **Title**.

#### ขั้นตอนที่ 4.1: เปลี่ยนค่า ModifyDate

ตั้งค่า `ModifyDate` ให้เป็นเวลาตร.UTC ปัจจุบัน

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### ขั้นตอนที่ 4.2: เปลี่ยนค่า Creator

แทนที่ผู้สร้างเดิมด้วยชื่อแอปพลิเคชันของคุณ

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### ขั้นตอนที่ 4.3: เปลี่ยนค่า Title

อัปเดตชื่อเรื่องเพื่อสะท้อนวัตถุประสงค์ของเนื้อหาใหม่

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### ขั้นตอนที่ 5: บันทึกไฟล์ EPS พร้อมเมตาดาต้า XMP ที่เปลี่ยนแปลง

หลังจากแก้ไขแล้ว ให้เขียนเอกสารออกไปใหม่

#### ขั้นตอนที่ 5.1: สร้างสตรีมเอาต์พุต

เปิด `FileStream` สำหรับไฟล์ EPS ปลายทาง

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### ขั้นตอนที่ 5.2: บันทึกไฟล์ EPS

เรียก `Save` บนอินสแตนซ์ `PsDocument` โดยส่งสตรีมเอาต์พุตเป็นพารามิเตอร์

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

สุดท้าย ปิดสตรีมอินพุตเพื่อปล่อยแฮนด์เดิลของไฟล์

```csharp
// Save EPS file
document.Save(outPsStream);
```

ยินดีด้วย! คุณได้ทำการ **aspose.page change eps values** สำเร็จโดยการอัปเดตเมตาดาต้า XMP ภายในไฟล์ EPS

## ปัญหาที่พบบ่อยและการแก้ไขปัญหา

- **Empty XMP packet** – บางไฟล์ EPS ถูกสร้างโดยไม่มี XMP ในกรณีนั้นให้สร้าง `XmpPacket` ใหม่โดยใช้ `new XmpPacket()` ก่อนกำหนดค่า  
- **Large files** – สำหรับ EPS ที่ใหญ่กว่า 500 MB ให้เปิดใช้งานการบัฟเฟอร์สตรีมโดยตั้งค่า `PsDocumentOptions.UseMemoryMappedFiles = true` เพื่อหลีกเลี่ยง `OutOfMemoryException`  
- **Incorrect date format** – XMP ต้องการรูปแบบ ISO 8601 ใช้ `DateTime.UtcNow.ToString("o")` เพื่อสร้างสตริงที่สอดคล้อง

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับรูปแบบกราฟิกอื่นได้หรือไม่?**  
A: ใช่, ไลบรารีรองรับมากกว่า 30 รูปแบบรวมถึง PDF, SVG, และ AI แต่ API การแก้ไข XMP จะเฉพาะกับ EPS และ PDF  

**Q: มีเวอร์ชันทดลองหรือไม่?**  
A: ใช่, คุณสามารถทดลองใช้ Aspose.Page สำหรับ .NET ด้วยการทดลองฟรีที่หน้า releases ของ Aspose [ที่นี่](https://releases.aspose.com/).  

**Q: ฉันสามารถหาเอกสารรายละเอียดได้ที่ไหน?**  
A: อ้างอิง API Aspose.Page .NET อย่างครบถ้วนสามารถพบได้ [ที่นี่](https://reference.aspose.com/page/net/).  

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวได้อย่างไร?**  
A: คุณสามารถรับไลเซนส์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).  

**Q: ฉันสามารถซื้อ Aspose.Page สำหรับ .NET ได้หรือไม่?**  
A: ได้เลย! เยี่ยมชมหน้าการซื้อ Aspose.Page [ที่นี่](https://purchase.aspose.com/buy) สำหรับตัวเลือกการให้สิทธิ์

---

**อัปเดตล่าสุด:** 2026-08-13  
**ทดสอบด้วย:** Aspose.Page 24.10 for .NET  
**ผู้เขียน:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มเมตาดาต้าให้กับเอกสาร EPS ด้วย Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [ดึงเมตาดาต้าจากเอกสาร EPS ด้วย Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [เปลี่ยนค่า Named Value ด้วย Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}