---
title: ครอบตัดรูปภาพ EPS ด้วย Aspose.Page สำหรับ .NET
linktitle: ครอบตัดรูปภาพ EPS
second_title: Aspose.Page .NET API
description: สำรวจโลกที่ไร้รอยต่อของการจัดการภาพ EPS ใน .NET ด้วย Aspose.Page ครอบตัดและปรับขนาดรูปภาพได้อย่างง่ายดายเพื่อผลลัพธ์ที่น่าทึ่ง
weight: 10
url: /th/net/image-manipulation/crop-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ครอบตัดรูปภาพ EPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

คุณกำลังดิ้นรนกับการจัดการอิมเมจ EPS ในแอปพลิเคชัน .NET ของคุณหรือไม่? ไม่ต้องมองอีกต่อไป! ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการครอบตัดรูปภาพ EPS โดยใช้ Aspose.Page สำหรับไลบรารี .NET อันทรงพลัง ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณครอบตัดรูปภาพได้อย่างแม่นยำและง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้ด้านการทำงานของการพัฒนา .NET
-  ติดตั้ง Aspose.Page สำหรับไลบรารี .NET แล้ว ถ้าไม่คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).
- รูปภาพ EPS ตัวอย่าง (แทนที่ "input.eps" ในโค้ดด้วยไฟล์จริงของคุณ)

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อให้โค้ดของเราทำงานได้อย่างราบรื่น 

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

ตอนนี้ เรามาแบ่งบทช่วยสอนออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: เริ่มต้น PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 เริ่มต้นก`PsDocument` วัตถุที่มีสตรีม EPS อินพุต

## ขั้นตอนที่ 2: แยก Bounding Box

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

ดึงกล่องขอบเขตเริ่มต้นของอิมเมจ EPS

## ขั้นตอนที่ 3: สร้างกระแสเอาต์พุต

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

สร้างสตรีมเอาต์พุตสำหรับอิมเมจ EPS ที่ครอบตัด

## ขั้นตอนที่ 4: กำหนด Bounding Box ใหม่

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

กำหนดกรอบขอบเขตใหม่สำหรับการครอบตัด ตรวจสอบให้แน่ใจว่าค่าใหม่อยู่ภายในกล่องขอบเขตเริ่มต้น

## ขั้นตอนที่ 5: ครอบตัดและบันทึก

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

ครอบตัดรูปภาพ EPS โดยใช้กล่องขอบใหม่และบันทึกลงในเอาต์พุตสตรีม

ทำซ้ำขั้นตอนเหล่านี้สำหรับสถานการณ์การปรับขนาดที่แตกต่างกัน

## การปรับขนาดภาพ EPS

### ปรับขนาดเป็นนิ้ว

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

ปรับขนาดภาพ EPS และบันทึกตามขนาดที่ระบุเป็นนิ้ว

### ปรับขนาดเป็นมิลลิเมตร

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

ปรับขนาดภาพ EPS และบันทึกตามขนาดที่ระบุในหน่วยมิลลิเมตร

### ปรับขนาดเป็นเปอร์เซ็นต์

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

ปรับขนาดภาพ EPS และบันทึกตามขนาดที่ระบุเป็นเปอร์เซ็นต์

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีครอบตัดและปรับขนาดอิมเมจ EPS โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว ตอนนี้เพิ่มความสามารถในการจัดการภาพของคุณและนำแอปพลิเคชัน .NET ของคุณไปสู่อีกระดับ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับรูปแบบรูปภาพอื่นได้หรือไม่

A1: Aspose.Page เน้นที่ภาพ EPS เป็นหลัก แต่ Aspose มีไลบรารีที่หลากหลายสำหรับรูปแบบที่แตกต่างกัน ตรวจสอบเอกสารประกอบสำหรับรูปแบบเฉพาะ

### คำถามที่ 2: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A2: เยี่ยมเลย[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวสำหรับการทดสอบ

### คำถามที่ 3: มีข้อจำกัดเกี่ยวกับขนาดภาพที่ฉันสามารถประมวลผลด้วย Aspose.Page สำหรับ .NET หรือไม่

A3: Aspose.Page ได้รับการออกแบบมาเพื่อจัดการรูปภาพขนาดต่างๆ อย่างไรก็ตาม ประสิทธิภาพอาจแตกต่างกันไปขึ้นอยู่กับความซับซ้อนของภาพ

### คำถามที่ 4: มีฟอรัมชุมชนสำหรับการสนทนา Aspose.Page หรือไม่

 A4: ได้ คุณสามารถมีส่วนร่วมกับชุมชน Aspose.Page ได้[ที่นี่](https://forum.aspose.com/c/page/39).

### คำถามที่ 5: ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A5: โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
