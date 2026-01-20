---
date: 2026-01-20
description: เพิ่มเลขหน้า PDF อย่างง่ายดายขณะรวมเอกสาร XPS เป็น PDF คุณภาพสูงด้วย
  Aspose.Page สำหรับ .NET ทำตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อแปลง XPS เป็น PDF
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: เพิ่มหมายเลขหน้า PDF – รวม XPS เป็น PDF ด้วย Aspose.Page
url: /th/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มหมายเลขหน้า PDF – รวม XPS เป็น PDF ด้วย Aspose.Page

## บทนำ

หากคุณต้องการ **add page numbers PDF** ขณะรวมไฟล์ XPS, Aspose.Page for .NET ทำให้กระบวนการเป็นเรื่องง่าย ในบทเรียนนี้เราจะอธิบายตัวอย่างที่สมบูรณ์พร้อมใช้งานในระดับการผลิต ซึ่งแปลงเอกสาร XPS เป็น PDF คุณภาพสูง ให้คุณควบคุมการบีบอัดภาพ และแทรกหมายเลขหน้าโดยอัตโนมัติลงใน PDF สุดท้าย เมื่อเสร็จคุณจะได้โค้ดสั้นที่สามารถนำไปใช้ในโปรเจกต์ C# ใดก็ได้

## คำตอบเร็ว
- **Can I add page numbers when merging XPS to PDF?** ใช่ – property `PdfSaveOptions.PageNumbers` ทำเช่นนั้นโดยตรง.  
- **Which library handles the conversion?** Aspose.Page for .NET.  
- **Do I need a license for production use?** จำเป็นต้องมีใบอนุญาต Aspose.Page ที่ถูกต้อง; มีใบอนุญาตชั่วคราวสำหรับการทดสอบ.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+.  
- **Is high‑quality image output possible?** แน่นอน – ตั้งค่า `JpegQualityLevel` เป็น 100 และเลือก `PdfImageCompression.Jpeg`.

## ข้อกำหนดเบื้องต้น

ก่อนจะลงลึกในบทเรียน โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

- Aspose.Page for .NET: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Page แล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/net/).

- Document Files: เตรียมไฟล์เอกสาร XPS (`input.xps`) ไว้ในไดเรกทอรีที่กำหนดไว้.

## นำเข้า Namespaces

ในโปรเจกต์ .NET ของคุณ ให้รวม Namespaces ที่จำเป็นสำหรับการทำงานกับ Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

ขั้นตอนนี้ทำให้คุณเข้าถึงคลาสและเมธอดที่จำเป็นสำหรับการแปลงเอกสารได้.

## วิธีเพิ่มหมายเลขหน้า PDF เมื่อรวมเอกสาร XPS

คอลเลกชัน `PdfSaveOptions.PageNumbers` ให้คุณระบุหน้าที่ต้องการ (หรือช่วงหน้า) ให้ปรากฏใน PDF ผลลัพธ์โดยตรง เมื่อใส่หมายเลขหน้าที่ต้องการ Aspose.Page จะทำการแทรกลำดับเลขอัตโนมัติ.

### ขั้นตอนที่ 1: เริ่มต้น Streams

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

ขั้นตอนนี้เกี่ยวข้องกับการตั้งค่า stream สำหรับไฟล์อินพุตและเอาต์พุตของ XPS และ PDF ตรวจสอบให้แน่ใจว่าใช้เส้นทางและชื่อไฟล์ที่ถูกต้อง.

### ขั้นตอนที่ 2: โหลดเอกสาร XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

ที่นี่ เราโหลดเอกสาร XPS เข้าไปในอ็อบเจกต์ `XpsDocument` เพื่อเตรียมการประมวลผลต่อไป.

### ขั้นตอนที่ 3: เริ่มต้น Save Options (รวม XPS เป็น PDF)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

ปรับแต่งอ็อบเจกต์ `PdfSaveOptions` ตามความต้องการของคุณ โดยระบุพารามิเตอร์เช่นการบีบอัดภาพ, การบีบอัดข้อความ, และ **page numbers** ที่ต้องการให้ปรากฏใน PDF สุดท้าย การตั้งค่า `JpegQualityLevel` เป็น 100 จะทำให้ **high quality PDF images**.

### ขั้นตอนที่ 4: สร้าง Rendering Device

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` เป็นเครื่องมือที่รับผิดชอบการเรนเดอร์เอกสาร XPS ไปเป็นรูปแบบ PDF.

### ขั้นตอนที่ 5: บันทึกเอกสาร (c# XPS เป็น PDF)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

สุดท้าย บันทึกเอกสารโดยใช้ rendering device และตัวเลือกที่กำหนดไว้ PDF ที่ได้จะมีหน้าที่เลือกพร้อมหมายเลขหน้าที่เพิ่มโดยอัตโนมัติ.

## ทำไมต้องใช้ Aspose.Page สำหรับการแปลงนี้?

- **Reliability** – จัดการคุณลักษณะซับซ้อนของ XPS โดยไม่สูญเสียความแม่นยำ.  
- **Performance** – การประมวลผลแบบสตรีมช่วยหลีกเลี่ยงการโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.  
- **Flexibility** – ควบคุมคุณภาพภาพ การบีบอัด และการจัดหมายเลขหน้าอย่างละเอียด.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS ด้วย .NET Core.

## ปัญหาที่พบบ่อยและวิธีแก้

| Issue | Solution |
|-------|----------|
| **Output PDF is blank** | ตรวจสอบว่าเส้นทางไฟล์ XPS ถูกต้องและไฟล์ไม่เสียหาย. |
| **Page numbers not appearing** | ตรวจสอบว่า `PageNumbers` ถูกตั้งค่าเป็นดัชนีหน้าแบบ zero‑based ที่ถูกต้อง (เช่น `new int[] {1,2,6}`). |
| **Low‑quality images** | เพิ่มค่า `JpegQualityLevel` และเลือก `PdfImageCompression.Jpeg`. |
| **Large XPS files cause memory pressure** | ประมวลผล XPS เป็นส่วนย่อย ๆ หรือเพิ่มขีดจำกัดหน่วยความจำของแอปพลิเคชัน. |

## คำถามที่พบบ่อย

### Q1: ฉันสามารถรวมไฟล์ XPS หลายไฟล์เป็น PDF ไฟล์เดียวได้หรือไม่?

A1: ได้ คุณเพียงปรับพารามิเตอร์ `PageNumbers` ใน `PdfSaveOptions` ให้รวมหน้าที่ต้องการจากไฟล์ XPS ต่าง ๆ หรือโหลดแต่ละ XPS อย่างต่อเนื่องแล้วเรียก `document.Save` บน `PdfDevice` เดียวกัน.

### Q2: มีใบอนุญาตชั่วคราวสำหรับ Aspose.Page for .NET หรือไม่?

A2: มี คุณสามารถรับใบอนุญาตชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/) สำหรับการทดสอบ.

### Q3: มีข้อจำกัดใด ๆ เกี่ยวกับขนาดไฟล์เมื่อใช้ Aspose.Page สำหรับการแปลงเอกสารหรือไม่?

A3: Aspose.Page for .NET ไม่กำหนดข้อจำกัดที่เข้มงวดเกี่ยวกับขนาดไฟล์ แต่ประสิทธิภาพที่ดีที่สุดจะได้จากไฟล์ที่มีขนาดสมเหตุสมผล สำหรับเอกสาร XPS ขนาดใหญ่มาก ควรประมวลผลเป็นสตรีมเพื่อลดการใช้หน่วยความจำ.

### Q4: ฉันสามารถปรับแต่ง PDF ผลลัพธ์เพิ่มเติม เช่น การเพิ่มลายน้ำหรือคำอธิบายประกอบได้หรือไม่?

A4: ได้ Aspose.Page for .NET มีฟีเจอร์การจัดการ PDF อย่างกว้างขวาง หลังจากแปลงแล้ว คุณสามารถใช้ไลบรารี Aspose.PDF เพื่อเพิ่มลายน้ำ, คำอธิบายประกอบ หรือการปรับปรุงอื่น ๆ.

### Q5: Aspose.Page for .NET รองรับการพัฒนาแบบข้ามแพลตฟอร์มหรือไม่?

A5: รองรับ Aspose.Page for .NET ถูกออกแบบให้ทำงานได้อย่างราบรื่นบนหลายแพลตฟอร์ม รวมถึง Windows, Linux, และ macOS เมื่อใช้ร่วมกับ .NET Core หรือ .NET 5/6.

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}