---
date: 2026-01-12
description: เรียนรู้วิธีสร้างเอกสาร PostScript ใน .NET ด้วย Aspose.Page คู่มือขั้นตอนต่อขั้นตอนนี้แสดงวิธีสร้างไฟล์
  PostScript ตั้งค่าขนาดหน้าของ PostScript และปรับแต่งขอบกระดาษเพื่อการผสานรวมที่ราบรื่น
linktitle: Create PostScript Document
second_title: Aspose.Page .NET API
title: วิธีสร้างเอกสาร PostScript ด้วย Aspose.Page สำหรับ .NET
url: /th/net/document-creation/create-postscript-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างเอกสาร PostScript ด้วย Aspose.Page สำหรับ .NET

## Introduction

ยินดีต้อนรับ! ในบทแนะนำที่ครอบคลุมนี้ คุณจะได้ค้นพบ **วิธีสร้าง PostScript** เอกสารโดยใช้โปรแกรมกับ Aspose.Page สำหรับ .NET ไม่ว่าคุณจะสร้างใบแจ้งหนี้, ป้ายจัดส่ง, หรือผลลัพธ์การพิมพ์แบบเวกเตอร์ใด ๆ คู่มือนี้จะพาคุณผ่านทุกขั้นตอน — ตั้งค่าสภาพแวดล้อมจนถึงการบันทึกไฟล์ *.ps* สุดท้าย มาดูกันว่าการผลิตไฟล์ PostScript คุณภาพสูงทำได้ง่ายแค่ไม่กี่บรรทัด C# เพียงเท่าไหร่

## Quick Answers
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for .NET  
- **ฉันสามารถตั้งขนาดหน้าได้หรือไม่?** ใช่ – ใช้ `options.PageSize` (ดู “set PostScript page size”).  
- **ต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์สำหรับการผลิต.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับเอกสารพื้นฐาน.

## What is “how to create PostScript” in .NET?
Aspose.Page มี API ที่ครอบคลุมซึ่งทำให้ซับซ้อนของไวยากรณ์ EPS/PostScript ระดับต่ำหายไป ทำให้คุณมุ่งเน้นที่การจัดหน้า, กราฟิก, และข้อความได้โดยตรง การใช้ไลบรารีนี้ช่วยให้คุณหลีกเลี่ยงการเขียนโค้ด PS ด้วยตนเองและได้รับการสนับสนุนสำหรับฟอนต์, รูปภาพ, และการวัดที่แม่นยำ.

## Why use Aspose.Page for PostScript creation?
- **การควบคุมเต็มรูปแบบ** บนขนาดหน้า, ระยะขอบ, และ primitive การวาด.  
- **ไม่มีการพึ่งพาภายนอก** – ทุกอย่างทำงานภายในกระบวนการ .NET ของคุณ.  
- **รองรับข้ามแพลตฟอร์ม** สำหรับ Windows, Linux, และ macOS.  
- **การจัดการฟอนต์ที่แข็งแรง** รวมถึงโฟลเดอร์ฟอนต์ที่กำหนดเอง.

## Prerequisites

- Aspose.Page for .NET Library: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Page for .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/net/).
- .NET Environment: ตรวจสอบว่าคุณมีสภาพแวดล้อม .NET ที่ทำงานได้บนเครื่องของคุณ.
- Text Editor หรือ IDE: ใช้โปรแกรมแก้ไขข้อความหรือสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณชื่นชอบสำหรับการเขียนโค้ด.

ตอนนี้เรามีทุกอย่างพร้อมแล้ว, มาเริ่มสร้างเอกสารกันเถอะ.

## Import Namespaces

ก่อนอื่นให้ import namespaces ที่ให้คุณเข้าถึงคลาสหลักของ Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.IO;
```

Namespaces เหล่านี้ทำให้คุณเข้าถึง `PsDocument`, `PsSaveOptions`, และคลาสยูทิลิตี้ที่ใช้ตลอดบทแนะนำ.

## Step 1: Set Document Directory

```csharp
string dir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` ด้วยพาธแบบ absolute หรือ relative ที่คุณต้องการให้ไฟล์ **PostScript** สุดท้ายถูกบันทึก.

## Step 2: Create Output Stream

```csharp
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
```

`FileStream` เปิดสตรีมที่เขียนได้ชื่อ **document.ps** คำสั่งวาดทั้งหมดต่อไปจะถูกเขียนลงในสตรีมนี้.

## Step 3: Create Save Options

```csharp
PsSaveOptions options = new PsSaveOptions();
```

`PsSaveOptions` ให้คุณกำหนดวิธีการเรนเดอร์และบันทึกเอกสาร.

## Step 4: Set PostScript Page Size and Margins

```csharp
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT);
options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_ZERO);
```

ที่นี่เรา **ตั้งขนาดหน้า PostScript** เป็น A4 แนวตั้งและลบระยะขอบทั้งหมด คุณสามารถแทนที่ `SIZE_A4` ด้วยค่าคงที่อื่น (เช่น `SIZE_LETTER`) เพื่อให้ตรงกับความต้องการของการจัดหน้า.

## Step 5: Set Additional Fonts Folders

```csharp
options.AdditionalFontsFolders = new string[] { dir };
```

หากเอกสารของคุณใช้ฟอนต์ที่กำหนดเองซึ่งไม่ได้ติดตั้งในระบบ ให้ชี้ Aspose.Page ไปยังโฟลเดอร์ที่มีไฟล์ฟอนต์เหล่านั้น.

## Step 6: Create Multipaged Document

```csharp
bool multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

อินสแตนซ์ `PsDocument` แทนเอกสาร PostScript การตั้งค่า `multiPaged` เป็น `false` จะสร้างเอกสารหน้าเดียว (คุณสามารถเปลี่ยนเป็น `true` เพื่อสร้างหลายหน้า).

## Step 7: Close and Save

```csharp
document.ClosePage();
document.Save();
```

การเรียก `ClosePage()` จะสรุปเนื้อหาหน้า, และ `Save()` จะเขียนสตรีม PostScript ทั้งหมดลงดิสก์.

ขอแสดงความยินดี! คุณเพิ่งเรียนรู้ **วิธีสร้าง PostScript** เอกสารด้วย Aspose.Page สำหรับ .NET.

## Common Issues and Solutions

- **ข้อผิดพลาดของเส้นทางไฟล์** – ตรวจสอบให้แน่ใจว่า ตัวแปร `dir` ลงท้ายด้วยตัวคั่นเส้นทาง (`\` หรือ `/`) หรือใช้ `Path.Combine`.
- **ฟอนต์หาย** – หากข้อความแสดงเป็นฟอนต์เริ่มต้น ตรวจสอบว่า `options.AdditionalFontsFolders` ชี้ไปยังไดเรกทอรีที่ถูกต้อง.
- **ขนาดหน้าผิด** – ตรวจสอบค่าคงที่ที่ส่งให้ `PageConstants.GetSize` อีกครั้ง; คุณยังสามารถกำหนดขนาดที่กำหนดเองผ่าน `new SizeF(width, height)`.

## Frequently Asked Questions

### Q1: ฉันสามารถหาเอกสารสำหรับ Aspose.Page for .NET ได้ที่ไหน?
A1: The documentation is available [here](https://reference.aspose.com/page/net/).

### Q2: ฉันจะดาวน์โหลด Aspose.Page for .NET ได้อย่างไร?
A2: You can download it from [this link](https://releases.aspose.com/page/net/).

### Q3: ฉันสามารถซื้อไลเซนส์สำหรับ Aspose.Page for .NET ได้จากที่ไหน?
A3: You can buy a license [here](https://purchase.aspose.com/buy).

### Q4: มีการทดลองใช้ฟรีสำหรับ Aspose.Page for .NET หรือไม่?
A4: Yes, you can find the free trial [here](https://releases.aspose.com/).

### Q5: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for .NET ได้อย่างไร?
A5: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q6: ฉันสามารถสร้างไฟล์ PostScript หลายหน้าได้หรือไม่?
A6: Absolutely. Set `bool multiPaged = true` when constructing `PsDocument` and call `document.NewPage()` for each additional page.

### Q7: Aspose.Page รองรับการจัดการสีหรือไม่?
A7: Yes, you can embed ICC profiles via `PsSaveOptions.ColorProfile` if needed.

---

**อัปเดตล่าสุด:** 2026-01-12  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}