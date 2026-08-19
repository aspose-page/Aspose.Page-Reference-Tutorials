---
date: 2026-02-28
description: เรียนรู้วิธีเพิ่มรูปภาพลงในเอกสาร PostScript ด้วย Aspose.Page สำหรับ
  .NET คู่มือนี้ยังครอบคลุมวิธีแทรกบิตแมปลงใน PS และการสกัดรูปภาพจาก PS เมื่อจำเป็น
linktitle: Add Image to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: วิธีเพิ่มรูปภาพในเอกสาร PostScript (PS) ด้วย Aspose.Page
url: /th/net/image-management/add-image-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มรูปภาพลงในเอกสาร PostScript (PS) ด้วย Aspose.Page

## วิธีเพิ่มรูปภาพลงในเอกสาร PostScript (PS)

ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีเพิ่มรูปภาพ** ลงในเอกสาร PostScript (PS) ด้วยไลบรารี Aspose.Page for .NET ที่ทรงพลัง ไม่ว่าคุณจะกำลังเตรียมโบรชัวร์ที่พิมพ์ได้, แผนภาพเทคนิค, หรือรายงานแบบกำหนดเอง การฝังกราฟิกโดยตรงลงในไฟล์ PS สามารถปรับปรุงคุณภาพภาพได้อย่างมาก เราจะเดินผ่านแต่ละขั้นตอน, อธิบายเหตุผลของแต่ละบรรทัด, และให้เคล็ดลับที่คุณสามารถนำไปใช้ในโครงการต่อไป

## คำตอบสั้น
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for .NET (เวอร์ชันล่าสุด)
- **สามารถแทรก bitmap ลงใน ps ได้หรือไม่?** ได้ – ใช้ `DrawImage` กับอ็อบเจ็กต์ `Bitmap`
- **ใช้เวลานานแค่ไหนในการทำงาน?** ปกติไม่เกิน 10 นาทีสำหรับการเพิ่มรูปภาพพื้นฐาน
- **ต้องมีลิขสิทธิ์หรือไม่?** รุ่นทดลองใช้ได้สำหรับการประเมิน; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง
- **สามารถดึงรูปภาพออกจาก ps ได้ภายหลังหรือไม่?** แน่นอน – Aspose.Page ยังมี API สำหรับการสกัดภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

- ไลบรารี Aspose.Page for .NET: ดาวน์โหลดและติดตั้ง Aspose.Page for .NET จาก [ที่นี่](https://releases.aspose.com/page/net/).
- โฟลเดอร์เอกสาร: สร้างโฟลเดอร์บนระบบของคุณเพื่อเก็บไฟล์เอกสารและรูปภาพ

## นำเข้า Namespaces

เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็นในโปรเจกต์ของคุณ เพื่อให้สามารถใช้ฟังก์ชันของ Aspose.Page ในแอปพลิเคชัน .NET ได้:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสาร

ตรวจสอบว่าคุณมีโฟลเดอร์เฉพาะสำหรับเอกสารของคุณ แทนที่ `"Your Document Directory"` ในโค้ดด้านล่างด้วยพาธของโฟลเดอร์เอกสารของคุณ

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง Output Stream สำหรับเอกสาร PS

ตั้งค่า output stream สำหรับเอกสาร PostScript ซึ่ง stream นี้จะใช้ในการบันทึกเอกสารที่แก้ไขแล้ว

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## ขั้นตอนที่ 3: สร้าง Save Options

สร้างตัวเลือกการบันทึกสำหรับเอกสาร PS โดยระบุการตั้งค่าที่ต้องการ เช่น ขนาดหน้า

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## ขั้นตอนที่ 4: สร้างเอกสาร PS

เริ่มต้นเอกสาร PS แบบ 1‑หน้าใหม่ และเตรียมพร้อมสำหรับการทำงานกราฟิก

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## ขั้นตอนที่ 5: แทรก Bitmap ลงในเอกสาร PS

โหลดอ็อบเจ็กต์ `Bitmap` จากไฟล์รูปภาพและทำการแปลงค่า นี่คือหัวใจของ **วิธีเพิ่มรูปภาพ** – เราจะวาด bitmap ลงบนแคนวาสของ PS

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

> **เคล็ดลับ:** ปรับค่า `Translate`, `Scale`, และ `Rotate` เพื่อกำหนดตำแหน่งและขนาดของรูปภาพให้ตรงตามที่ต้องการ

## ขั้นตอนที่ 6: สรุปการทำงานกราฟิก

สรุปการทำงานกราฟิกและปิดหน้าเอกสารปัจจุบัน

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## ขั้นตอนที่ 7: บันทึกเอกสาร

บันทึกเอกสาร PS ที่แก้ไขแล้ว

```csharp
document.Save();
```

## วิธีสกัดภาพจากเอกสาร PS

หากคุณต้องการดึงกราฟิกในภายหลัง Aspose.Page มีเมธอดสกัดภาพเช่น `PsDocument.ExtractImages` แม้ว่าบทแนะนำนี้จะเน้นที่การแทรก แต่ไลบรารีเดียวกันก็สามารถ **สกัดภาพจาก ps** เพื่อการนำกลับมาใช้ใหม่หรือวิเคราะห์ได้

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| รูปภาพแสดงบิดเบี้ยว | เมทริกซ์สเกลไม่ถูกต้อง | ตรวจสอบค่าของ `Scale` อีกครั้ง; ใช้สเกลแบบสม่ำเสมอ (เช่น `Scale(1,1)`) เพื่อขนาดดั้งเดิม |
| ไฟล์ผลลัพธ์ว่างเปล่า | Stream ไม่ได้ flush | ตรวจสอบให้แน่ใจว่าเรียก `document.Save()` ภายในบล็อก `using` |
| รูปแบบภาพไม่รองรับ | Bitmap ไม่สามารถโหลดไฟล์ | แปลงภาพเป็นรูปแบบที่รองรับ เช่น JPEG, PNG, BMP หรือ GIF |

## สรุป

ขอแสดงความยินดี! คุณได้เรียนรู้ **วิธีเพิ่มรูปภาพ** ลงในเอกสาร PostScript ด้วย Aspose.Page for .NET อย่างสำเร็จแล้ว ตอนนี้คุณมีพื้นฐานที่มั่นคงสำหรับการแทรกกราฟิก และยังรู้วิธี **สกัดภาพจาก ps** และ **แทรก bitmap ลงใน ps** เมื่อจำเป็น อย่าลังเลที่จะทดลองกับหลายรูปภาพ, การแปลงค่าแบบต่าง ๆ, หรือแม้กระทั่งคำสั่งวาดแบบกำหนดเองเพื่อสร้างเนื้อหาที่พิมพ์ได้อย่างสวยงาม

## คำถามที่พบบ่อย

### Q1: สามารถเพิ่มหลายรูปภาพในเอกสาร PS เดียวโดยใช้ Aspose.Page ได้หรือไม่?

A1: ได้ คุณเพียงแค่ทำซ้ำขั้นตอนการเพิ่มรูปภาพภายในเอกสาร

### Q2: รองรับรูปแบบภาพใดบ้างใน Aspose.Page for .NET?

A2: Aspose.Page for .NET รองรับรูปแบบภาพหลายประเภท รวมถึง JPEG, PNG, BMP, และ GIF

### Q3: มีขีดจำกัดขนาดของภาพที่สามารถเพิ่มได้หรือไม่?

A3: ขีดจำกัดขนาดขึ้นอยู่กับสเปคของเอกสาร PS และทรัพยากรของระบบ Aspose.Page สามารถจัดการกับขนาดภาพที่หลากหลายได้

### Q4: สามารถใช้เอฟเฟกต์เพิ่มเติมกับภาพได้หรือไม่ เช่น ฟิลเตอร์หรือโอเวอร์เลย์?

A4: ได้ Aspose.Page อนุญาตให้คุณใช้การแปลงและเอฟเฟกต์ต่าง ๆ กับภาพก่อนนำไปใส่ในเอกสาร

### Q5: วิธีสกัดภาพจากเอกสาร PS คืออะไร?

A5: Aspose.Page for .NET มีเมธอดสำหรับสกัดภาพจากเอกสาร PS โปรดดูเอกสารสำหรับข้อมูลรายละเอียด

---

**อัปเดตล่าสุด:** 2026-02-28  
**ทดสอบด้วย:** Aspose.Page for .NET (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}