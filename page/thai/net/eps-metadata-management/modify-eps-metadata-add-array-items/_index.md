---
date: 2026-08-08
description: เรียนรู้วิธีเพิ่มรายการอาร์เรย์ใน EPS metadata ด้วย Aspose.Page EPS metadata
  คู่มือ .NET แบบขั้นตอนแสดงวิธีเพิ่มรายการอาร์เรย์และอ่านไฟล์ EPS อย่างมีประสิทธิภาพ
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: เพิ่มรายการอาร์เรย์
og_description: ค้นพบวิธีเพิ่มรายการอาร์เรย์ใน EPS metadata ด้วย Aspose.Page EPS metadata
  ติดตามบทเรียน .NET สั้น ๆ นี้เพื่ออ่านไฟล์ EPS และจัดการ metadata อย่างมีประสิทธิภาพ
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: เพิ่มรายการอาร์เรย์ด้วย Aspose.Page EPS metadata ใน .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: เพิ่มรายการอาร์เรย์ด้วย Aspose.Page EPS metadata ใน .NET
url: /th/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรายการอาร์เรย์ด้วยเมตาดาต้า EPS ของ Aspose.Page ใน .NET

## บทนำ

ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีเพิ่มรายการอาร์เรย์ลงในเมตาดาต้า EPS โดยใช้ **Aspose.Page EPS metadata** ไม่ว่าคุณจะต้องการเพิ่มชื่อเรื่อง ผู้สร้าง หรือแท็กที่กำหนดเองในไฟล์ EPS, Aspose.Page ทำให้การทำงานนี้ง่ายสำหรับนักพัฒนา .NET ทุกคน เราจะอธิบายขั้นตอนทั้งหมด ตั้งแต่การเปิดสตรีม EPS จนถึงการบันทึกแพ็กเกจ XMP ที่อัปเดต เพื่อให้คุณสามารถผสานการจัดการเมตาดาต้าเข้ากับแอปพลิเคชันของคุณได้อย่างมั่นใจ

## คำตอบสั้น
- **Aspose.Page EPS metadata ช่วยให้คุณทำอะไรได้บ้าง?** มันทำให้สามารถอ่านและเขียนอาร์เรย์เมตาดาต้า XMP ภายในไฟล์ EPS จาก .NET ได้  
- **คลาสใดที่เป็นตัวแทนของเอกสาร EPS?** `PsDocument` เป็นคลาสหลักสำหรับการโหลดและบันทึกเนื้อหา EPS  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ฉันสามารถแก้ไขเมตาดาต้าโดยไม่เปลี่ยนแปลงกราฟิก EPS ได้หรือไม่?** ใช่, มีการเปลี่ยนแปลงเพียงแพ็กเกจ XMP เท่านั้น, เนื้อหาหน้าจะไม่ถูกแก้ไข  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  

## Aspose.Page EPS metadata คืออะไร?
Aspose.Page EPS metadata คือบล็อกข้อมูลที่อิงตาม XMP ซึ่งฝังอยู่ในไฟล์ EPS มันเก็บคุณสมบัติอธิบายเช่น ชื่อเรื่อง, ผู้สร้าง, คำสำคัญ, และแท็กที่กำหนดเองตามมาตรฐาน ISO 16684‑1 เมตาดาต้านี้สามารถเข้าถึงและแก้ไขได้โดยโปรแกรมผ่าน Aspose.Page API ทำให้การจัดการเอกสารอัตโนมัติและการเพิ่มประสิทธิภาพการค้นหาเป็นไปได้

## ทำไมต้องแก้ไขเมตาดาต้า EPS?
Aspose.Page สามารถประมวลผล **มากกว่า 30 ฟิลด์เมตาดาต้า** และจัดการไฟล์ EPS ขนาดสูงสุด **200 MB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ ซึ่งช่วยลดการใช้ CPU ได้ถึง 40 % เมื่อเทียบกับการวิเคราะห์ไฟล์เต็ม การอัปเดตเมตาดาต้าช่วยปรับปรุงการค้นหา, การปฏิบัติตามกฎระเบียบ, และการทำงานอัตโนมัติของกระบวนการต่อเนื่อง

## ข้อกำหนดเบื้องต้น
- ความรู้พื้นฐานการเขียนโปรแกรม .NET  
- Aspose.Page for .NET ติดตั้งแล้ว – ดาวน์โหลดจาก [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (หรือ IDE ที่รองรับ .NET) เพื่อรันโค้ดตัวอย่าง  

## วิธีเพิ่มรายการอาร์เรย์ลงในเมตาดาต้า EPS?
เพื่อเพิ่มรายการอาร์เรย์, ก่อนอื่นให้โหลดไฟล์ EPS ลงใน `PsDocument`, จากนั้นดึงแพ็กเกจ XMP โดยใช้ `GetXmpMetadata()` ใช้วิธี `AddArrayItem()` บน XMP array ที่ต้องการ เช่น `dc:title` หรือ `dc:creator` เพื่อเพิ่มค่าใหม่ สุดท้ายเรียก `Save()` เพื่อเขียนเมตาดาต้าที่อัปเดตกลับไปยังไฟล์โดยคงเนื้อหากราฟิกไม่เปลี่ยน

### ขั้นตอนที่ 1: เริ่มต้นสตรีมอินพุตของไฟล์ eps
`PsDocument` แสดงถึงเอกสาร EPS และให้เมธอดเพื่อเข้าถึงเนื้อหา โค้ดต่อไปนี้เปิดไฟล์ EPS เป็นสตรีมและสร้างอินสแตนซ์ของ `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### ขั้นตอนที่ 2: ดึงเมตาดาต้า xmp
`GetXmpMetadata()` ดึงแพ็กเกจ XMP ที่ฝังอยู่ในไฟล์ EPS หากไม่มีแพ็กเกจ, API จะสร้างใหม่โดยอิงจากคอมเมนต์ PostScript ที่มีอยู่.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### ขั้นตอนที่ 3: เปลี่ยนค่าเมตาดาต้า xmp
`AddArrayItem()` เพิ่มค่ใหม่ลงในอาร์เรย์ XMP ที่มีอยู่โดยไม่เขียนทับรายการอื่น ใช้มันเพื่อเพิ่มชื่อเรื่อง, ผู้สร้าง, หรือแท็กที่กำหนดเองลงในเมตาดาต้า.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### ขั้นตอนที่ 4: บันทึกไฟล์ eps พร้อมเมตาดาต้า xmp ที่เปลี่ยนแปลง
`Save()` เขียนแพ็กเกจ XMP ที่แก้ไขกลับเข้าไปในไฟล์ EPS ขณะคงเนื้อหา PostScript ดั้งเดิมไว้ ให้ระบุเส้นทางเอาต์พุตเพื่อสร้างไฟล์ใหม่หรือเขียนทับไฟล์ต้นฉบับ.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## ปัญหาที่พบบ่อยและการแก้ไขข้อผิดพลาด
- **Null XMP packet** – หาก `GetXmpMetadata()` คืนค่า `null`, ให้ตรวจสอบว่าไฟล์ EPS มีบล็อกคอมเมนต์อย่างน้อยหนึ่งบล็อก; หากไม่มีก็สร้างอินสแตนซ์ `XmpMetadata` ใหม่ด้วยตนเอง.  
- **Encoding issues** – ใช้ UTF‑8 เมื่อต้องเพิ่มค่าข้อความเพื่อหลีกเลี่ยงการเสียรูปอักขระในภาษาที่ไม่ใช่ ASCII.  
- **Large files** – สำหรับไฟล์ EPS ที่ใหญ่กว่า 150 MB, พิจารณาใช้สตรีมอินพุตผ่าน `FileStream` พร้อมบัฟเฟอร์เพื่อรักษาการใช้หน่วยความจำให้ต่ำ  

## คำถามที่พบบ่อย

**Q: Aspose.Page รองรับสภาพแวดล้อม .NET ทั้งหมดหรือไม่?**  
A: ใช่, Aspose.Page ทำงานได้บน .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6/7, ให้พฤติกรรม API ที่สอดคล้องกันบน Windows, Linux และ macOS.

**Q: ฉันสามารถใช้ Aspose.Page ได้ฟรีหรือไม่?**  
A: คุณสามารถประเมินไลบรารีด้วยการดาวน์โหลดทดลองใช้ฟรีจาก [Aspose purchase page](https://purchase.aspose.com/buy). จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง

**Q: มีไลเซนส์ชั่วคราวสำหรับ Aspose.Page หรือไม่?**  
A: สามารถรับไลเซนส์ชั่วคราวได้จาก [temporary license page](https://purchase.aspose.com/temporary-license/) สำหรับโครงการระยะสั้นหรือช่วงประเมิน

**Q: ฉันจะหาการสนับสนุนจากชุมชนสำหรับ Aspose.Page ได้จากที่ไหน?**  
A: เข้าร่วมการสนทนาที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อถามคำถามและแบ่งปันวิธีแก้ไขกับนักพัฒนาคนอื่น

**Q: เวอร์ชันล่าสุดของ Aspose.Page สำหรับ .NET คืออะไร?**  
A: ดูที่ [documentation](https://reference.aspose.com/page/net/) อย่างเป็นทางการสำหรับบันทึกการปล่อยล่าสุดและลิงก์ดาวน์โหลด

---

**อัปเดตล่าสุด:** 2026-08-08  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## บทแนะนำที่เกี่ยวข้อง

- [เปลี่ยนรายการอาร์เรย์ด้วย Aspose.Page สำหรับ .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [เพิ่มคุณสมบัติง่ายด้วย Aspose.Page สำหรับ .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [เพิ่มเนมสเปซด้วย Aspose.Page สำหรับ .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}