---
date: 2026-02-28
description: เรียนรู้วิธีสร้างเอกสาร XPS ด้วย .NET และเพิ่มรูปภาพโดยใช้ Aspose.Page
  สำหรับ .NET ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อประสบการณ์การพัฒนาที่ราบรื่น.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: สร้างเอกสาร XPS ด้วย .NET – เพิ่มรูปภาพด้วย Aspose.Page
url: /th/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรูปภาพลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **create XPS document .NET** และฝังรูปภาพโดยใช้ไลบรารี Aspose.Page ที่ทรงพลัง ไม่ว่าคุณจะสร้างรายงาน ใบแจ้งหนี้ หรือกราฟิกแบบกำหนดเอง การเพิ่มองค์ประกอบภาพลงในไฟล์ XPS เป็นความต้องการที่พบบ่อยสำหรับนักพัฒนา .NET

## บทนำ

ในโลกของการพัฒนา .NET การใส่รูปภาพลงในเอกสาร XPS เป็นความต้องการที่ทั่วไป Aspose.Page สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้น โดยนำเสนอชุดเครื่องมือที่ทรงพลังสำหรับจัดการและปรับปรุงเอกสาร XPS อย่างไม่มีความยุ่งยาก บทเรียนนี้จะนำคุณผ่านขั้นตอนการเพิ่มรูปภาพลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

## คำตอบอย่างรวดเร็ว
- **บทเรียนนี้ครอบคลุมอะไร?** Adding an image to an XPS document with Aspose.Page for .NET.  
- **คีย์เวิร์ดหลักที่มุ่งหมายคืออะไร?** *create xps document .net*  
- **ต้องใช้ลิขสิทธิ์หรือไม่?** มีการทดลองใช้ฟรี; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์จริง.  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** ทำงานกับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 5‑10 นาทีสำหรับการแทรกรูปภาพพื้นฐาน.

## “create XPS document .NET” คืออะไร?
การสร้างเอกสาร XPS ใน .NET หมายถึงการสร้างไฟล์ XML Paper Specification (XPS) — รูปแบบเอกสารแบบเลย์เอาต์คงที่ — อย่างโปรแกรมโดยใช้ C# หรือ VB.NET Aspose.Page ให้ API ที่เป็น fluent ซึ่งซ่อนรายละเอียดระดับต่ำ ทำให้คุณสามารถมุ่งเน้นที่เนื้อหาเช่นข้อความ รูปร่าง และรูปภาพได้

## ทำไมต้องใช้ Aspose.Page เพื่อเพิ่มรูปภาพ?
- **Full control** บนการกำหนดตำแหน่ง การปรับขนาด และการตัดภาพ.  
- **No external dependencies** – ไลบรารีจัดการการถอดรหัสรูปภาพภายใน.  
- **Cross‑platform** support for Windows and Linux environments. – รองรับการทำงานบน Windows และ Linux.  
- **High fidelity** rendering that preserves image quality in the final XPS file. – การเรนเดอร์คุณภาพสูงที่รักษาคุณภาพของรูปภาพในไฟล์ XPS สุดท้าย.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มบทเรียน โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

1. Aspose.Page for .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/).

2. Development Environment: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio.

3. Sample Image: มีไฟล์รูปตัวอย่าง (เช่น "QL_logo_color.tif") ที่คุณต้องการเพิ่มลงในเอกสาร XPS.

## นำเข้า Namespaces

เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็นเข้าสู่โครงการ .NET ของคุณ Namespaces เหล่านี้สำคัญสำหรับการใช้คุณลักษณะที่ Aspose.Page for .NET มีให้

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Aspose.Page เพิ่มรูปภาพลงในเอกสาร XPS

ด้านล่างเราจะอธิบายขั้นตอนแต่ละขั้นตอนที่จำเป็นเพื่อ **create XPS document .NET** และฝังรูปภาพ

### ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสาร

เริ่มต้นโดยระบุเส้นทางไปยังโฟลเดอร์เอกสารของคุณ ขั้นตอนนี้ทำให้โครงการของคุณรู้ว่าจะค้นหาและบันทึกไฟล์ที่ไหน

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### ขั้นตอนที่ 2: สร้างเอกสาร XPS

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### ขั้นตอนที่ 3: เพิ่มรูปภาพลงในเอกสาร XPS

ตอนนี้เราจะเพิ่มรูปภาพลงในเอกสาร XPS ในตัวอย่างนี้เราจะใช้รูปภาพตัวอย่างชื่อ "QL_logo_color.tif"

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### ขั้นตอนที่ 4: บันทึกเอกสาร XPS ที่ได้

บันทึกเอกสาร XPS พร้อมรูปภาพที่เพิ่มเข้าไป

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

ตอนนี้คุณได้เพิ่มรูปภาพลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET อย่างสำเร็จแล้ว!

## ปัญหาทั่วไปและวิธีแก้

- **File not found error** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและชื่อไฟล์รูปภาพตรงกันอย่างสมบูรณ์ รวมถึงความแตกต่างของตัวอักษรใหญ่‑เล็กบน Linux.  
- **Image appears distorted** – ปรับค่า scaling ของ `CreateMatrix` หรือพารามิเตอร์ของ `RectangleF` เพื่อควบคุมขนาดและอัตราส่วน.  
- **Unsupported image format** – Aspose.Page รองรับรูปแบบเรสเตอร์ทั่วไป (PNG, JPEG, TIFF) แปลงรูปแบบที่ไม่รองรับก่อนใช้ `CreateImageBrush`.

## คำถามที่พบบ่อย

### Q1: Aspose.Page สำหรับ .NET เข้ากันได้กับเวอร์ชัน .NET framework ล่าสุดหรือไม่?

A1: Aspose.Page สำหรับ .NET ถูกออกแบบให้เข้ากันได้กับหลายเวอร์ชันของ .NET framework รวมถึงเวอร์ชันล่าสุดด้วย ดูรายละเอียดเพิ่มเติมใน [documentation](https://reference.aspose.com/page/net/).

### Q2: สามารถใช้ Aspose.Page สำหรับ .NET ได้ทั้งบน Windows และ Linux หรือไม่?

A2: ใช่, Aspose.Page สำหรับ .NET เป็นแพลตฟอร์มอิสระ จึงเหมาะสำหรับการใช้งานทั้งบน Windows และ Linux.

### Q3: มีตัวเลือกการให้ลิขสิทธิ์สำหรับ Aspose.Page สำหรับ .NET หรือไม่?

A3: มี, คุณสามารถสำรวจตัวเลือกการให้ลิขสิทธิ์และทำการซื้อได้ [ที่นี่](https://purchase.aspose.com/buy).

### Q4: มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ .NET หรือไม่?

A4: มี, คุณสามารถทดลองใช้ Aspose.Page สำหรับ .NET ได้ฟรีโดยเข้าถึง [free trial](https://releases.aspose.com/).

### Q5: จะหาความช่วยเหลือหรือเข้าร่วมชุมชนของ Aspose.Page สำหรับ .NET ได้จากที่ไหน?

A5: เยี่ยมชม [Aspose.Page for .NET forum](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและรับการสนับสนุน.

## สรุป

ในบทเรียนนี้ เราได้สำรวจวิธีใช้ Aspose.Page สำหรับ .NET เพื่อผสานรูปภาพลงในเอกสาร XPS อย่างราบรื่น คู่มือขั้นตอนนี้ช่วยให้การรวมรูปภาพเป็นไปอย่างง่ายดาย เพิ่มศักยภาพการพัฒนา .NET ของคุณและช่วยให้คุณ **create XPS document .NET** ด้วยความสมบูรณ์ของภาพ

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Page for .NET 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}