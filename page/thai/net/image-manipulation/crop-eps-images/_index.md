---
date: 2026-03-16
description: เรียนรู้วิธีตัดภาพ EPS และปรับขนาดไฟล์ภาพ EPS ใน .NET ด้วย Aspose.Page
  ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อการตัดและปรับขนาดภาพ EPS อย่างง่ายดาย.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: วิธีตัดภาพ EPS ด้วย Aspose.Page สำหรับ .NET
url: /th/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตัดภาพ EPS ด้วย Aspose.Page for .NET

## บทนำ

หากคุณต้องการทราบ **วิธีตัดภาพ EPS** ในแอปพลิเคชัน .NET คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนการตัดและปรับขนาดไฟล์ EPS ด้วยไลบรารี Aspose.Page for .NET ที่ทรงพลัง ไม่ว่าคุณจะกำลังปรับปรุงเครื่องมือรายงานหรือเตรียมกราฟิกสำหรับเว็บเซอร์วิส การเชี่ยวชาญเทคนิคนี้จะช่วยคุณประหยัดเวลาและได้ผลลัพธ์ที่พิกเซล‑เพอร์เฟ็กต์

## คำตอบสั้น
- **ไลบรารีที่จัดการการตัด EPS คืออะไร?** Aspose.Page for .NET  
- **เมธอดหลักคืออะไร?** `doc.CropEps(outputStream, newBoundingBox)`  
- **ฉันสามารถปรับขนาด EPS ได้ด้วยหรือไม่?** ได้ – ใช้ `ResizeEps` พร้อมหน่วยเป็นนิ้ว, มิลลิเมตร หรือเปอร์เซ็นต์  
- **ข้อกำหนดเบื้องต้น?** .NET (Framework 4.5+ / .NET Core 3.1+), ติดตั้ง Aspose.Page, มีไฟล์ EPS  
- **เวลาในการทำงานโดยประมาณ?** ประมาณ 10 นาทีสำหรับเวิร์กโฟลว์การตัด‑และ‑ปรับขนาดพื้นฐาน

## ข้อกำหนดเบื้องต้น

ก่อนจะลงมือเขียนโค้ด โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานการพัฒนา .NET  
- ไลบรารี Aspose.Page for .NET ติดตั้งแล้ว หากยังไม่มีสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/net/)  
- ตัวอย่างไฟล์ EPS (เปลี่ยน `"input.eps"` ในโค้ดเป็นไฟล์ของคุณจริง)

## นำเข้า Namespaces

เริ่มต้นด้วยการนำเข้า namespaces ที่ให้เราเข้าถึงคลาสการจัดการ EPS

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## วิธีตัดภาพ EPS – คู่มือขั้นตอน‑โดย‑ขั้นตอน

### ขั้นตอนที่ 1: เริ่มต้น `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

เราจะสร้างอินสแตนซ์ `PsDocument` จากสตรีม EPS เข้าด้านเข้า อินสแตนซ์นี้เป็นตัวแทนของไฟล์ EPS ในหน่วยความจำและให้เราเข้าถึงเมธอดการตัดและปรับขนาดได้

### ขั้นตอนที่ 2: ดึง Bounding Box ดั้งเดิม

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Bounding box บอกขนาดปัจจุบันของแคนวาส EPS การรู้ค่าต่าง ๆ นี้ช่วยให้คุณกำหนดสี่เหลี่ยมตัดที่ปลอดภัยได้

### ขั้นตอนที่ 3: สร้าง Output Stream

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

เราจะเปิดสตรีมที่สามารถเขียนได้เพื่อบันทึก EPS ที่ถูกตัด การใช้บล็อก `using` จะทำให้สตรีมปิดอย่างถูกต้อง

### ขั้นตอนที่ 4: กำหนด Bounding Box ใหม่

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

แทนที่ตัวเลขด้วยพิกัดที่คุณต้องการเก็บไว้ ตรวจสอบให้ค่าที่ใหม่อยู่ภายใน Bounding Box ดั้งเดิม มิฉะนั้นการดำเนินการจะล้มเหลว

### ขั้นตอนที่ 5: ตัดและบันทึก EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

บรรทัดเดียวนี้ทำการตัดและเขียนผลลัพธ์ไปยัง `output_crop.eps` เมธอดนี้แก้ไขเอกสารในหน่วยความจำ ดังนั้นคุณสามารถต่อเนื่องกับการดำเนินการอื่น ๆ ได้หากต้องการ

## ปรับขนาดภาพ EPS

หลังจากตัดแล้ว คุณอาจต้องการเปลี่ยนขนาดของ EPS เพื่อการแสดงผลหรือการพิมพ์ Aspose.Page รองรับหน่วยวัดสามประเภท

### ปรับขนาดเป็นนิ้ว

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### ปรับขนาดเป็นมิลลิเมตร

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### ปรับขนาดเป็นเปอร์เซ็นต์

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

แต่ละการเรียกจะเขียนทับไฟล์ผลลัพธ์ก่อนหน้า ดังนั้นหากต้องการไฟล์แยกตามขนาดแต่ละแบบ ให้สร้างสตรีมใหม่สำหรับแต่ละครั้ง

## ปัญหาที่พบบ่อย & การแก้ไข

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| **ค่าของ Bounding box อยู่นอกช่วง** | กล่องใหม่เกินขนาดเดิม | ตรวจสอบค่า `initialBoundingBox` และเลือกพิกัดที่อยู่ภายในช่วงนั้น |
| **ไฟล์ผลลัพธ์ว่างเปล่า** | สตรีมผลลัพธ์ไม่ได้ flush หรือปิด | ให้แน่ใจว่าบล็อก `using` ทำงานจนเสร็จก่อนเข้าถึงไฟล์ หรือเรียก `outputEpsStream.Flush()` |
| **การสเกลที่ไม่คาดคิด** | ผสมหน่วย (เช่น นิ้วกับมิลลิเมตร) | ระบุ enum `Units` ที่ตรงกับค่าขนาดของคุณเสมอ |

## คำถามที่พบบ่อย

### Q1: ฉันสามารถใช้ Aspose.Page for .NET กับรูปแบบภาพอื่นได้หรือไม่?

A1: Aspose.Page มุ่งเน้นที่ภาพ EPS เป็นหลัก แต่ Aspose มีไลบรารีหลายตัวสำหรับรูปแบบต่าง ๆ ตรวจสอบเอกสารของพวกเขาสำหรับรูปแบบเฉพาะ

### Q2: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page for .NET ได้อย่างไร?

A2: เยี่ยมชม [ลิงก์นี้](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวสำหรับการทดสอบ

### Q3: มีข้อจำกัดใดเกี่ยวกับขนาดภาพที่ฉันสามารถประมวลผลด้วย Aspose.Page for .NET หรือไม่?

A3: Aspose.Page ถูกออกแบบให้รองรับภาพหลายขนาด อย่างไรก็ตามประสิทธิภาพอาจแตกต่างกันตามความซับซ้อนของภาพ

### Q4: มีฟอรั่มชุมชนสำหรับการสนทนาเกี่ยวกับ Aspose.Page หรือไม่?

A5: มีครับ คุณสามารถเข้าร่วมชุมชน Aspose.Page ได้ [ที่นี่](https://forum.aspose.com/c/page/39)

### Q5: ฉันจะหาเอกสารรายละเอียดของ Aspose.Page for .NET ได้จากที่ไหน?

A5: ดูเอกสารได้ [ที่นี่](https://reference.aspose.com/page/net/)

---

**อัปเดตล่าสุด:** 2026-03-16  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}