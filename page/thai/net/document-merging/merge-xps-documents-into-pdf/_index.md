---
title: รวมเอกสาร XPS ให้เป็น PDF ด้วย Aspose.Page สำหรับ .NET
linktitle: รวมเอกสาร XPS ให้เป็น PDF
second_title: Aspose.Page .NET API
description: ผสานเอกสาร XPS ให้เป็น PDF คุณภาพสูงได้อย่างง่ายดายโดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อประสบการณ์การแปลงเอกสารที่ราบรื่น
weight: 11
url: /th/net/document-merging/merge-xps-documents-into-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รวมเอกสาร XPS ให้เป็น PDF ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

ในภูมิทัศน์ของการประมวลผลเอกสารที่เปลี่ยนแปลงตลอดเวลา Aspose.Page สำหรับ .NET กลายเป็นเครื่องมืออันทรงพลังสำหรับการรวมเอกสาร XPS เป็นรูปแบบ PDF ได้อย่างราบรื่น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการ โดยแจกแจงแต่ละขั้นตอนเพื่อให้แน่ใจว่าการดำเนินการจะราบรื่นและมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/net/).

- ไฟล์เอกสาร: มีเอกสาร XPS (`input.xps`) พร้อมอยู่ในไดเร็กทอรีที่คุณระบุ

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ให้รวมเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

ขั้นตอนนี้ช่วยให้แน่ใจว่าคุณสามารถเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการแปลงเอกสาร

## ขั้นตอนที่ 1: เริ่มต้นสตรีม

```csharp
// เอ็กซ์สตาร์ท:3
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// เริ่มต้นสตรีมเอาท์พุต PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// เตรียมใช้งานสตรีมอินพุต XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// สิ้นสุด:3
```

ขั้นตอนนี้เกี่ยวข้องกับการตั้งค่าสตรีมอินพุตและเอาต์พุตสำหรับไฟล์ XPS และ PDF ตรวจสอบให้แน่ใจว่ามีการใช้พาธและชื่อไฟล์ที่ถูกต้อง

## ขั้นตอนที่ 2: โหลดเอกสาร XPS

```csharp
// เอ็กซ์สตาร์ท:4
// โหลดเอกสาร XPS จากสตรีม
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// หรือโหลดเอกสาร XPS โดยตรงจากไฟล์ ไม่จำเป็นต้องใช้ xpsStream
//เอกสาร XpsDocument = XpsDocument ใหม่ (inputFileName, XpsLoadOptions ใหม่ ());
// สิ้นสุด:4
```

 ที่นี่ เราโหลดเอกสาร XPS ลงในไฟล์`XpsDocument` วัตถุเพื่อเตรียมการประมวลผลต่อไป

## ขั้นตอนที่ 3: เริ่มต้นตัวเลือกการบันทึก

```csharp
// เอ็กซ์สตาร์ท:5
// เริ่มต้นวัตถุตัวเลือกด้วยพารามิเตอร์ที่จำเป็น
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// สิ้นสุด:5
```

 ปรับแต่ง`PdfSaveOptions` ออบเจ็กต์ตามการตั้งค่าของคุณ โดยระบุพารามิเตอร์ เช่น การบีบอัดรูปภาพ การบีบอัดข้อความ และหมายเลขหน้า

## ขั้นตอนที่ 4: สร้างอุปกรณ์แสดงผล

```csharp
// เอ็กซ์สตาร์ท:6
// สร้างอุปกรณ์เรนเดอร์สำหรับรูปแบบ PDF
PdfDevice device = new PdfDevice(pdfStream);
// สิ้นสุด:6
```

 ที่`PdfDevice` เป็นเครื่องมือที่รับผิดชอบในการแสดงเอกสาร XPS เป็นรูปแบบ PDF

## ขั้นตอนที่ 5: บันทึกเอกสาร

```csharp
// เอ็กซ์สตาร์ท:7
document.Save(device, options);
// สิ้นสุด:7
```

สุดท้าย ให้บันทึกเอกสารโดยใช้อุปกรณ์แสดงผลและตัวเลือกที่ระบุ

## บทสรุป

ยินดีด้วย! คุณได้ผสานเอกสาร XPS ให้เป็น PDF โดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว กระบวนการที่ราบรื่นนี้ช่วยให้มั่นใจได้ถึงการรักษาคุณภาพและการจัดรูปแบบของเอกสาร

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถรวมไฟล์ XPS หลายไฟล์เป็น PDF เดียวได้หรือไม่

 A1: ใช่คุณทำได้ เพียงแค่ปรับ`PageNumbers` พารามิเตอร์ใน`PdfSaveOptions` เพื่อรวมเพจที่ต้องการจากไฟล์ XPS ต่างๆ

### คำถามที่ 2: Aspose.Page สำหรับ .NET มีใบอนุญาตชั่วคราวหรือไม่

 A2: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบ

### คำถามที่ 3: มีข้อจำกัดเกี่ยวกับขนาดไฟล์เมื่อใช้ Aspose.Page สำหรับการแปลงเอกสารหรือไม่

A3: Aspose.Page สำหรับ .NET ไม่ได้กำหนดข้อจำกัดที่เข้มงวดเกี่ยวกับขนาดไฟล์ แต่ได้รับประสิทธิภาพสูงสุดด้วยขนาดไฟล์ที่เหมาะสม

### คำถามที่ 4: ฉันสามารถปรับแต่งเอาต์พุต PDF เพิ่มเติม เช่น เพิ่มลายน้ำหรือคำอธิบายประกอบได้หรือไม่

A4: ใช่ Aspose.Page สำหรับ .NET มีคุณสมบัติมากมายสำหรับการจัดการ PDF ตรวจสอบเอกสารประกอบสำหรับตัวเลือกการปรับแต่งขั้นสูง

### คำถามที่ 5: Aspose.Page สำหรับ .NET รองรับการพัฒนาข้ามแพลตฟอร์มหรือไม่

A5: ใช่ Aspose.Page สำหรับ .NET ได้รับการออกแบบมาให้ทำงานได้อย่างราบรื่นบนแพลตฟอร์มต่างๆ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
