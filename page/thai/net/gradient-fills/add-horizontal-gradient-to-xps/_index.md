---
date: 2026-02-25
description: เรียนรู้วิธีสร้างไล่สี XPS ด้วยการเติมแนวนอนโดยใช้ Aspose.Page สำหรับ
  .NET ยกระดับความสวยงามของเอกสารของคุณได้อย่างง่ายดาย.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'สร้างไล่ระดับสี XPS: เติมแนวนอนด้วย Aspose.Page สำหรับ .NET'
url: /th/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง XPS Gradient – เพิ่ม Gradient แนวนอนให้กับ XPS ด้วย Aspose.Page for .NET

## บทนำ

ในบทเรียนนี้คุณจะ **สร้างการเติมสี Gradient สำหรับ XPS** ที่วิ่งแนวนอนทั่วทั้งหน้า การเพิ่ม Gradient แนวนอนสามารถทำให้เอกสาร XPS ดูเป็นมืออาชีพและน่าสนใจมากขึ้นโดยทันที โดยเฉพาะสำหรับรายงาน โบรชัวร์ หรือผลลัพธ์ที่มีภาพกราฟิกมาก เราจะเดินผ่านกระบวนการทั้งหมดโดยใช้ Aspose.Page for .NET ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการบันทึกไฟล์ XPS สุดท้าย

## คำตอบสั้น
- **บทเรียนนี้ครอบคลุมอะไร?** การเพิ่ม Gradient แนวนอนให้กับเอกสาร XPS ด้วย Aspose.Page for .NET  
- **ต้องใช้ไลบรารีใด?** Aspose.Page for .NET (เวอร์ชันล่าสุดใดก็ได้)  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองสำหรับการพัฒนาได้; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ใช้เวลานานเท่าไหร่ในการทำ?** ประมาณ 5–10 นาทีสำหรับ Gradient พื้นฐาน  
- **สามารถเปลี่ยนทิศทางของ Gradient ได้หรือไม่?** ได้ – ปรับจุดเริ่มต้น/สิ้นสุดของ `LinearGradientBrush`

## วิธีสร้าง XPS Gradient ด้วย Aspose.Page for .NET

ด้านล่างนี้เป็นคู่มือแบบขั้นตอนที่อธิบาย **ทำไม** แต่ละบรรทัดของโค้ดจึงมีอยู่, ไม่ใช่แค่ **ทำอะไร** ทำตามได้ใน Visual Studio หรือเครื่องมือ .NET ที่คุณชื่นชอบ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่ม, ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

1. Aspose.Page for .NET Library: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Page for .NET ในสภาพแวดล้อมการพัฒนาแล้ว สามารถดาวน์โหลดได้จาก [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/)  
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒที่เหมาะสม รวมถึงโปรแกรมแก้ไขโค้ดอย่าง Visual Studio

## นำเข้า Namespaces

เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็นเข้าสู่โปรเจกต์ของคุณ Namespaces เหล่านี้จำเป็นสำหรับการทำงานกับ Aspose.Page for .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

ตอนนี้มาทำความเข้าใจตัวอย่างที่ให้มาเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีของเอกสาร

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## ขั้นตอนที่ 2: สร้าง XPS Document ใหม่

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## ขั้นตอนที่ 3: เริ่มต้น Gradient Stops

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## ขั้นตอนที่ 4: สร้าง Path ใหม่

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## ขั้นตอนที่ 5: บันทึก XPS Document ที่ได้ผลลัพธ์

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

ตอนนี้คุณได้เพิ่ม Gradient แนวนอนให้กับเอกสาร XPS ของคุณเรียบร้อยแล้วโดยใช้ Aspose.Page for .NET

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| Gradient ปรากฏเป็นสีเดียว | Gradient stops ไม่ได้เพิ่มอย่างถูกต้อง | ตรวจสอบให้แน่ใจว่า `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` ถูกเรียกหลังจากตั้งค่า brush |
| ไฟล์ที่บันทึกเป็นไฟล์เปล่า | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่ | ตรวจสอบว่าโฟลเดอร์มีอยู่หรือใช้เส้นทางแบบ absolute |
| เกิดข้อผิดพลาดการคอมไพล์ที่ `PointF` | ขาดการอ้างอิง `System.Drawing` | เพิ่มการอ้างอิง `System.Drawing.Common` (สำหรับ .NET Core/5+) |

## คำถามที่พบบ่อย

### Q1: จะหาเอกสาร Aspose.Page for .NET ได้ที่ไหน?

A1: คุณสามารถดูเอกสารได้ [ที่นี่](https://reference.aspose.com/page/net/)

### Q2: จะดาวน์โหลด Aspose.Page for .NET ได้อย่างไร?

A2: ดาวน์โหลดไลบรารีได้จาก [หน้าดาวน์โหลด Aspose.Page for .NET](https://releases.aspose.com/page/net/)

### Q3: จะซื้อ Aspose.Page for .NET ได้จากที่ไหน?

A3: สามารถซื้อได้จาก [หน้า purchase](https://purchase.aspose.com/buy)

### Q4: มีรุ่นทดลองฟรีหรือไม่?

A4: มี, คุณสามารถรับรุ่นทดลองฟรีได้จาก [ที่นี่](https://releases.aspose.com/)

### Q5: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for .NET ได้อย่างไร?

A5: รับลิขสิทธิ์ชั่วคราวได้จาก [ลิงก์นี้](https://purchase.aspose.com/temporary-license/)

## Frequently Asked Questions

**Q: สามารถใช้เทคนิค Gradient นี้กับเอกสาร XPS ที่มีรูปภาพอยู่แล้วได้หรือไม่?**  
A: แน่นอน Gradient จะถูกนำไปใช้กับเลเยอร์ Path ดังนั้นรูปภาพที่มีอยู่จะไม่ได้รับผลกระทบ

**Q: สามารถสร้าง Gradient แนวตั้งแทนได้หรือไม่?**  
A: ได้ เปลี่ยนจุดเริ่มต้นและสิ้นสุดของ `LinearGradientBrush` ให้มีค่า Y ต่างกันในขณะที่ค่า X คงที่

**Q: Aspose.Page รองรับ .NET Core หรือไม่?**  
A: ไลบรารีนี้รองรับ .NET Core, .NET 5 และเวอร์ชันต่อ ๆ ไปอย่างเต็มที่

**Q: จะใช้ Gradient เดียวกันหลายหน้าอย่างไร?**  
A: สร้าง `XpsLinearGradientBrush` ครั้งเดียว เก็บไว้ในตัวแปร แล้วกำหนดให้กับ Path บนแต่ละหน้า

## สรุป

การเพิ่ม Gradient ให้กับเอกสาร XPS ไม่เพียงทำให้ดูสวยงามขึ้นเท่านั้น แต่ยังมอบประสบการณ์ผู้ใช้ที่ดีกว่า ด้วย Aspose.Page for .NET คุณสามารถ **สร้าง XPS Gradient** ได้อย่างรวดเร็วและเชื่อถือได้ ทำให้รายงาน โบรชัวร์ หรือ e‑book ของคุณดูเป็นมืออาชีพยิ่งขึ้น

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-02-25  
**ทดสอบด้วย:** Aspose.Page for .NET 24.11  
**ผู้เขียน:** Aspose  

---