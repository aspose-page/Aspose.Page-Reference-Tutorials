---
title: แปลง XPS เป็น PDF ด้วย Aspose.Page สำหรับ .NET
linktitle: แปลง XPS เป็น PDF
second_title: Aspose.Page .NET API
description: แปลง XPS เป็น PDF ใน .NET ได้อย่างง่ายดายด้วย Aspose.Page ดาวน์โหลดห้องสมุด สำรวจเอกสาร และทดลองใช้งานฟรี
weight: 11
url: /th/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XPS เป็น PDF ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการแปลงเอกสาร XPS (XML Paper Specification) เป็น PDF (Portable Document Format) โดยใช้ Aspose.Page สำหรับไลบรารี .NET อันทรงพลัง Aspose.Page สำหรับ .NET มอบชุดคุณสมบัติที่มีประสิทธิภาพสำหรับการทำงานกับไฟล์ XPS ช่วยให้นักพัฒนาสามารถแปลงไฟล์เป็นรูปแบบ PDF ได้อย่างราบรื่นด้วยตัวเลือกการปรับแต่งที่หลากหลาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้นการเดินทางของการเปลี่ยนแปลงนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้จาก[เอกสาร Aspose.Page](https://reference.aspose.com/page/net/).

- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ด้วย Visual Studio หรือ IDE อื่น ๆ ที่เข้ากันได้

- เอกสาร XPS: เตรียมเอกสาร XPS ที่คุณต้องการแปลงเป็น PDF นี่อาจเป็นไฟล์ XPS ตัวอย่างของคุณที่จัดเก็บไว้ในไดเร็กทอรีที่กำหนด

## นำเข้าเนมสเปซ

ก่อนที่จะเจาะลึกโค้ด ให้นำเข้าเนมสเปซที่จำเป็นเพื่อให้ฟังก์ชัน Aspose.Page สำหรับ .NET เข้าถึงได้ในโค้ดของเรา:

```csharp
using Aspose.Page.XPS;
```

## ขั้นตอนที่ 1: เริ่มต้นไดเร็กทอรีเอกสาร

```csharp
string dataDir = "Your Document Directory";
```

แทนที่ "Your Document Directory" ด้วยเส้นทางไปยังไดเร็กทอรีที่มีเอกสาร XPS ของคุณ

## ขั้นตอนที่ 2: เริ่มต้นสตรีม PDF และ XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

เปิดสตรีมสำหรับทั้งไฟล์ PDF เอาต์พุตและไฟล์ XPS อินพุต ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าเส้นทางไฟล์ที่เหมาะสม

## ขั้นตอนที่ 3: โหลดเอกสาร XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

โหลดเอกสาร XPS โดยใช้ไลบรารี Aspose.Page สำหรับ .NET

## ขั้นตอนที่ 4: เริ่มต้นตัวเลือกการบันทึก PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

ตั้งค่าตัวเลือกการบันทึก PDF รวมถึงพารามิเตอร์ต่างๆ เช่น ระดับคุณภาพ JPEG การบีบอัดรูปภาพ การบีบอัดข้อความ และหมายเลขหน้าเฉพาะที่จะรวมไว้

## ขั้นตอนที่ 5: สร้างอุปกรณ์แสดงผล PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

สร้างอุปกรณ์เรนเดอร์สำหรับรูปแบบ PDF โดยใช้ไลบรารี Aspose.Page สำหรับ .NET

## ขั้นตอนที่ 6: บันทึกเอกสารเป็น PDF

```csharp
document.Save(device, options);
```

บันทึกเอกสาร XPS เป็น PDF โดยใช้อุปกรณ์เรนเดอร์และตัวเลือกที่ระบุ

## บทสรุป

ยินดีด้วย! คุณได้แปลงเอกสาร XPS เป็น PDF โดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว ไลบรารีอเนกประสงค์นี้มอบชุดเครื่องมืออันทรงพลังแก่นักพัฒนาสำหรับการจัดการรูปแบบเอกสารต่าง ๆ ได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถแปลงไฟล์ XPS หลายไฟล์เป็น PDF เดียวโดยใช้ Aspose.Page สำหรับ .NET ได้หรือไม่

A1: ได้ คุณสามารถวนซ้ำไฟล์ XPS หลายไฟล์และทำตามขั้นตอนเดียวกันเพื่อรวมเป็นไฟล์ PDF เดียว

### คำถามที่ 2: Aspose.Page สำหรับ .NET รองรับรูปแบบเอาต์พุตอื่นๆ หรือไม่

ตอบ 2: ใช่ Aspose.Page สำหรับ .NET รองรับรูปแบบเอาต์พุตที่หลากหลาย รวมถึง TIFF, JPEG, PNG และอื่นๆ

### คำถามที่ 3: ฉันจะปรับแต่งลักษณะที่ปรากฏของเอกสาร PDF ที่แปลงแล้วได้อย่างไร

A3: คุณสามารถปรับแต่งพารามิเตอร์ออบเจ็กต์ตัวเลือกได้ เช่น การบีบอัดรูปภาพและการบีบอัดข้อความ เพื่อให้ได้รูปลักษณ์ที่ต้องการ

### คำถามที่ 4: Aspose.Page สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่

 A4: ได้ คุณสามารถสำรวจความสามารถของ Aspose.Page สำหรับ .NET ได้โดยการทดลองใช้ฟรีจาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะรับการสนับสนุนจากชุมชนสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการอภิปรายและการสนับสนุนของชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
