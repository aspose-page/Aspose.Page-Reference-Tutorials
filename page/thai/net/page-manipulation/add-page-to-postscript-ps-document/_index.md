---
date: 2026-03-03
description: เรียนรู้วิธีตั้งค่าขนาดหน้ากำหนดเองและเพิ่มหน้าที่สองในเอกสาร PostScript
  โดยใช้ Aspose.Page สำหรับ .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: ตั้งค่าขนาดหน้าที่กำหนดเองในเอกสาร PS ด้วย Aspose.Page
url: /th/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มหน้าในเอกสาร PostScript (PS) ด้วย Aspose.Page

## Introduction

ในการพัฒนา .NET การสามารถ **ตั้งค่าขนาดหน้าที่กำหนดเอง** และ **เพิ่มหน้า PS ที่สอง** ในเอกสาร PostScript (PS) ให้คุณควบคุมการจัดวางของการพิมพ์ รายงาน หรือกราฟิกที่สร้างขึ้นได้อย่างละเอียด Aspose.Page สำหรับ .NET ทำให้ภารกิจนี้ง่ายดายด้วย API ที่เป็นวัตถุ‑เชิงวัตถุ ในบทเรียนนี้คุณจะได้เรียนรู้วิธีสร้างไฟล์ PS แบบหลายหน้า กำหนดขนาดที่กำหนดเองสำหรับแต่ละหน้า และบันทึกผลลัพธ์—ทั้งหมดด้วยเพียงไม่กี่บรรทัดของโค้ด C#.

## Quick Answers
- **ฉันสามารถตั้งค่าขนาดหน้าที่กำหนดเองได้หรือไม่?** ใช่ – เพียงส่งค่าความกว้างและความสูงเมื่อเปิดหน้า.  
- **ฉันจะเพิ่มหน้า PS ที่สองได้อย่างไร?** เรียก `document.OpenPage(width, height)` อีกครั้ง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ฉันต้องการใบอนุญาตหรือไม่?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการทดสอบ; ใบอนุญาตเต็มจำเป็นสำหรับการใช้งานจริง.  
- **ฉันสามารถดาวน์โหลด Aspose.Page ได้จากที่ไหน?** จากหน้าดาวน์โหลดอย่างเป็นทางการที่ลิงก์ด้านล่าง.

## Prerequisites

ก่อนจะเริ่มบทเรียน โปรดตรวจสอบว่าคุณมีเงื่อนไขต่อไปนี้พร้อมอยู่แล้ว:

- ความรู้พื้นฐานในการพัฒนา .NET  
- ติดตั้ง Visual Studio บนเครื่องของคุณ  
- ไลบรารี Aspose.Page สำหรับ .NET ซึ่งคุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/page/net/).  
- ไดเรกทอรีเอกสารที่คุณต้องการใช้สำหรับการทดสอบ

## Import Namespaces

ตรวจสอบให้แน่ใจว่าคุณได้รวมเนมสเปซที่จำเป็นในโปรเจกต์ของคุณเพื่อเข้าถึงฟังก์ชันที่ Aspose.Page ให้มา ในตัวอย่างที่ให้มา เนมสเปซถูกนำเข้าโดยอัตโนมัติ แต่ควรตรวจสอบและปรับให้เหมาะกับโครงสร้างโปรเจกต์ของคุณ

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Your Project

สร้างโปรเจกต์ .NET ใหม่ใน Visual Studio และตั้งค่าการกำหนดค่าที่จำเป็น ตรวจสอบให้แน่ใจว่าได้อ้างอิงไลบรารี Aspose.Page ในโปรเจกต์ของคุณ.

## Set Custom Page Size and Add Second PS Page

ส่วนนี้จะแสดงวิธี **ตั้งค่าขนาดหน้าที่กำหนดเอง** สำหรับแต่ละหน้าและวิธี **เพิ่มหน้า ps ที่สอง** ไปยังเอกสารเดียวกันอย่างชัดเจน.

### Step 2: Initialize the Document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Step 3: Add the First Page (default size)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Step 4: Add the Second Page with a Different (Custom) Size

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Step 5: Save the Document

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

ทำตามขั้นตอนเหล่านี้อย่างละเอียด คุณจะสามารถ **ตั้งค่าขนาดหน้าที่กำหนดเอง** และเพิ่ม **หน้า PS ที่สอง** ในเอกสาร PostScript ด้วย Aspose.Page สำหรับ .NET ได้สำเร็จ.

## Why This Matters

- **การจัดวางที่แม่นยำ** – ขนาดหน้าที่กำหนดเองช่วยให้คุณตรงกับสเปคของเครื่องพิมพ์หรือสร้างรูปแบบโบรชัวร์ที่เป็นเอกลักษณ์.  
- **หลายหน้า** – การเพิ่มหน้า (หรือหลายหน้า) ทำให้สามารถสร้างรายงานหลายหน้าได้โดยไม่ต้องใช้เครื่องมือรวมภายนอก.  
- **ข้ามแพลตฟอร์ม** – ไฟล์ PS ที่สร้างขึ้นสามารถแสดงผลบนอุปกรณ์ที่รองรับ PostScript ใด ๆ หรือแปลงเป็น PDF ในภายหลัง.

## Common Pitfalls & Troubleshooting

- **เส้นทางไม่ถูกต้อง** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทางหรือใช้ `Path.Combine`.  
- **ปัญหาใบอนุญาต** – หากไม่มีใบอนุญาตที่ถูกต้อง ไลบรารีอาจใส่ลายน้ำหรือจำกัดจำนวนหน้า.  
- **ความสับสนของหน่วย** – ความกว้างและความสูงวัดเป็นจุด (1 point = 1/72 นิ้ว) ปรับให้เหมาะสม.

## Frequently Asked Questions

**Q1: Aspose.Page รองรับรูปแบบเอกสารต่าง ๆ หรือไม่?**  
A1: Aspose.Page มุ่งเน้นการจัดการเอกสาร PostScript เป็นหลัก สำหรับรูปแบบอื่น ๆ คุณสามารถสำรวจไลบรารี Aspose ที่ออกแบบมาเฉพาะตามความต้องการได้.

**Q2: ฉันสามารถปรับขนาดหน้าใน Aspose.Page ได้หรือไม่?**  
A2: แน่นอน! ตามที่แสดงในบทเรียน คุณสามารถระบุขนาดที่แตกต่างกันสำหรับแต่ละหน้าได้ตามความต้องการของคุณ.

**Q3: ฉันจะหา ตัวอย่างและเอกสารเพิ่มเติมได้จากที่ไหน?**  
A3: เยี่ยมชม [documentation](https://reference.aspose.com/page/net/) เพื่อรับข้อมูลที่ครบถ้วนและตัวอย่างหลากหลาย.

**Q4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร?**  
A4: ไปที่ [this link](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวสำหรับการทดสอบ.

**Q5: ฉันจะหาการสนับสนุนจากชุมชนหรือถามคำถามได้จากที่ไหน?**  
A5: เข้าร่วม [Aspose.Page community forum](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับนักพัฒนาคนอื่น ๆ แบ่งปันประสบการณ์ และขอความช่วยเหลือ.

---

**อัปเดตล่าสุด:** 2026-03-03  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}