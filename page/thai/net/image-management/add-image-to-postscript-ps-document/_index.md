---
title: เพิ่มรูปภาพลงในเอกสาร PostScript (PS) ด้วย Aspose.Page
linktitle: เพิ่มรูปภาพลงในเอกสาร PostScript (PS)
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีการปรับปรุงเอกสาร PostScript ของคุณโดยการเพิ่มรูปภาพโดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อประสบการณ์ที่ราบรื่น
weight: 10
url: /th/net/image-management/add-image-to-postscript-ps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรูปภาพลงในเอกสาร PostScript (PS) ด้วย Aspose.Page

## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจกระบวนการเพิ่มรูปภาพลงในเอกสาร PostScript (PS) โดยใช้ไลบรารี Aspose.Page สำหรับ .NET อันทรงพลัง Aspose.Page ทำให้การจัดการเอกสาร PS ง่ายขึ้น โดยนำเสนอวิธีที่มีประสิทธิภาพและตรงไปตรงมาในการปรับปรุงเอกสารของคุณด้วยรูปภาพ คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ เพื่อให้มั่นใจว่าคุณจะเข้าใจแต่ละแนวคิดได้อย่างถี่ถ้วน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET Library: ดาวน์โหลดและติดตั้ง Aspose.Page สำหรับ .NET Library จาก[ที่นี่](https://releases.aspose.com/page/net/).
- ไดเร็กทอรีเอกสาร: สร้างไดเร็กทอรีบนระบบของคุณเพื่อจัดเก็บเอกสารและไฟล์รูปภาพ

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ของคุณ เนมสเปซเหล่านี้ช่วยให้คุณใช้ฟังก์ชัน Aspose.Page ในแอปพลิเคชัน .NET ของคุณได้:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

 ตรวจสอบให้แน่ใจว่าคุณมีไดเร็กทอรีเฉพาะสำหรับเอกสารของคุณ แทนที่`"Your Document Directory"` ในข้อมูลโค้ดด้านล่างพร้อมเส้นทางไปยังไดเรกทอรีเอกสารของคุณ

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างสตรีมเอาท์พุตสำหรับเอกสาร PS

ตั้งค่าสตรีมเอาต์พุตสำหรับเอกสาร PostScript สตรีมนี้จะใช้เพื่อบันทึกเอกสารที่แก้ไข

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## ขั้นตอนที่ 3: สร้างตัวเลือกการบันทึก

สร้างตัวเลือกการบันทึกสำหรับเอกสาร PS โดยระบุการตั้งค่าที่ต้องการ เช่น ขนาดหน้า

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## ขั้นตอนที่ 4: สร้างเอกสาร PS

เริ่มต้นเอกสาร PS 1 หน้าใหม่และเตรียมพร้อมสำหรับการทำงานด้านกราฟิก

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## ขั้นตอนที่ 5: เพิ่มรูปภาพลงในเอกสาร

โหลดวัตถุบิตแมปจากไฟล์รูปภาพและใช้การแปลง เพิ่มรูปภาพลงในเอกสาร PS

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

## ขั้นตอนที่ 6: เสร็จสิ้นการทำงานของกราฟิก

สรุปการดำเนินการด้านกราฟิกและปิดหน้าปัจจุบัน

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## ขั้นตอนที่ 7: บันทึกเอกสาร

บันทึกเอกสาร PS ที่แก้ไข

```csharp
document.Save();
```

## บทสรุป

ยินดีด้วย! คุณได้เพิ่มรูปภาพลงในเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำที่ชัดเจนและกระชับสำหรับการรวมรูปภาพลงในเอกสาร PS ของคุณ ทำให้เอกสารของคุณดูน่าดึงดูดและมีส่วนร่วม

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถเพิ่มรูปภาพหลายรูปลงในเอกสาร PS เดียวโดยใช้ Aspose.Page ได้หรือไม่

A1: ใช่คุณทำได้ เพียงทำซ้ำขั้นตอนการเพิ่มรูปภาพภายในเอกสาร

### คำถามที่ 2: Aspose.Page สำหรับ .NET รองรับรูปแบบรูปภาพใดบ้าง

A2: Aspose.Page สำหรับ .NET รองรับรูปแบบรูปภาพที่หลากหลาย รวมถึง JPEG, PNG, BMP และ GIF

### คำถามที่ 3: สามารถเพิ่มขนาดรูปภาพได้หรือไม่

A3: ขีดจำกัดขนาดขึ้นอยู่กับข้อกำหนดของเอกสาร PS และทรัพยากรระบบ Aspose.Page รองรับขนาดรูปภาพที่หลากหลาย

### คำถามที่ 4: ฉันสามารถใช้เอฟเฟ็กต์เพิ่มเติมกับรูปภาพ เช่น ฟิลเตอร์หรือโอเวอร์เลย์ได้หรือไม่

A4: ใช่ Aspose.Page อนุญาตให้คุณใช้การแปลงและเอฟเฟกต์ต่างๆ กับรูปภาพก่อนที่จะเพิ่มลงในเอกสาร

### คำถามที่ 5: ฉันจะแยกรูปภาพจากเอกสาร PS ได้อย่างไร

A5: Aspose.Page สำหรับ .NET จัดเตรียมวิธีการแยกรูปภาพจากเอกสาร PS โปรดดูเอกสารประกอบสำหรับข้อมูลโดยละเอียด
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
