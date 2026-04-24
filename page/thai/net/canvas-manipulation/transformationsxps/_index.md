---
date: 2026-01-05
description: เรียนรู้วิธีแปลงเอกสาร XPS อย่างง่ายดายด้วย Aspose.Page สำหรับ .NET.
  ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการแปลงที่ราบรื่น.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: วิธีแปลง XPS ด้วย Aspose.Page สำหรับ .NET
url: /th/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง XPS ด้วย Aspose.Page สำหรับ .NET

## แนะนำ

ยินดีต้อนรับสู่โลกของ Aspose.Page สำหรับ .NET, ไลบรารีที่ทรงพลังซึ่งช่วยให้คุณทำการแปลงต่าง ๆ บนเอกสาร XPS ได้อย่างง่ายดาย **ในบทเรียนนี้ คุณจะได้ค้นพบวิธีแปลงเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET** ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น เราจะเดินผ่านแต่ละขั้นตอน อธิบายเหตุผลเบื้องหลังการแปลงแต่ละขั้น และให้เคล็ดลับที่คุณสามารถนำไปใช้ในโครงการจริงได้

## คำตอบด่วน
- **คุณสามารถทำอะไรได้บ้าง?** สร้าง, แปล, ปรับขนาด, และหมุนองค์ประกอบของแคนวาส XPS ด้วยโปรแกรม.  
- **ต้องใช้ไลบรารีใด?** Aspose.Page for .NET (เวอร์ชันล่าสุด).  
- **ต้องการใบอนุญาตหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.  
- **แพลตฟอร์มที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ใช้เวลานานเท่าไหร่ในการดำเนินการ?** ประมาณ 10‑15 นาทีสำหรับการแปลงพื้นฐานที่แสดงในที่นี้.

## อะไรคือ “วิธีแปลง xps”?
วลี *how to transform xps* หมายถึงการแก้ไขรูปแบบ, ขนาด, และการวางแนวขององค์ประกอบภายในเอกสาร XPS (XML Paper Specification) ด้วยโปรแกรม โดยใช้ Aspose.Page คุณสามารถใช้การแปลงแบบเมทริกซ์บนแคนวาสได้ ให้การควบคุมตำแหน่ง, การสเกล, และการหมุนอย่างละเอียดโดยไม่ต้องแก้ไข XML ของ XPS ด้วยตนเอง

## ทำไมต้องใช้ Aspose.Page สำหรับการแปลง XPS?
- **การบูรณาการเต็มรูปแบบกับ .NET** – ทำงานอย่างไร้รอยต่อกับ Visual Studio, Rider, และ IDE อื่นๆ.  
- **ไม่มีการพึ่งพาภายนอก** – API จัดการรายละเอียดระดับต่ำของ XPS ให้คุณ.  
- **รองรับการแปลงอย่างหลากหลาย** – แปล, ปรับขนาด, หมุน, และรวมการแปลงหลายอย่างในคำสั่งเดียว.  
- **ปรับประสิทธิภาพการทำงาน** – เหมาะสำหรับการสร้างรายงาน, ใบแจ้งหนี้, หรือกราฟิกที่พิมพ์ได้ทันที.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

- **Aspose.Page for .NET Library** – ดาวน์โหลดและติดตั้งจากเอกสารอย่างเป็นทางการ: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **สภาพแวดล้อมการพัฒนา** – Visual Studio, Visual Studio Code, หรือ IDE ที่รองรับ .NET ใดๆ.  
- **ไดเรกทอรีเอกสาร** – โฟลเดอร์บนเครื่องของคุณที่คุณจะอ่าน/เขียนไฟล์ XPS. แทนที่ตัวแปรในโค้ดด้วยพาธจริง.

ตอนนี้เรามีทุกอย่างพร้อมแล้ว ให้เราดำดิ่งเข้าสู่โค้ดกัน

## นำเข้า Namespaces

ก่อนอื่น ให้นำเข้า namespaces ที่เปิดเผยคลาสของ Aspose.Page ที่คุณต้องใช้:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## วิธีแปลง XPS – คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: สร้างเอกสาร XPS ใหม่

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Explanation*: เราเริ่มโดยกำหนดโฟลเดอร์ที่เก็บไฟล์ต้นฉบับและไฟล์ผลลัพธ์ แล้วสร้างอินสแตนซ์ของ `XpsDocument` ว่างเปล่า วัตถุนี้จะเป็นแคนวาสสำหรับการแปลงทั้งหมดต่อไป

### ขั้นตอนที่ 2: สร้างแคนวาสหลัก

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Why this matters*: แคนวาสหลักทำหน้าที่เป็นคอนเทนเนอร์สำหรับแคนวาสอื่น ๆ ทั้งหมด โดยการเพิ่มออฟเซ็ตเล็กน้อย เราแน่ใจว่าเนื้อหาไม่ถูกตัดที่ขอบหน้า

### ขั้นตอนที่ 3: สร้างรูปทรงเรขาคณิตของเส้นทางสี่เหลี่ยม

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tip*: สตริงของ path ปฏิบัติตามไวยากรณ์มาตรฐานของ XPS (`M` สำหรับย้าย, `L` สำหรับเส้น, `Z` เพื่อปิด). ปรับค่าพิกัดเพื่อเปลี่ยนขนาดของสี่เหลี่ยม

### ขั้นตอนที่ 4: เพิ่มการเติมสีสำหรับสี่เหลี่ยม

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: ใช้ `CreateColor` พร้อมค่าตัวเลข RGB เพื่อให้ตรงกับพาเลตสีของแบรนด์คุณ

### ขั้นตอนที่ 5: เพิ่มแคนวาสใหม่โดยไม่มีการแปลง

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

ที่นี่เราวางสี่เหลี่ยมบนหน้าโดยไม่มีการแปลงเพิ่มเติม—เป็นองค์ประกอบอ้างอิงที่ใช้เปรียบเทียบ

### ขั้นตอนที่ 6: เพิ่มแคนวาสใหม่พร้อมการแปลงการแปล (Translate)

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*What’s happening?* เมทริกซ์แรกย้ายสี่เหลี่ยมลง 200 หน่วย คำสั่ง `Translate` ถัดไปเลื่อนมันไปทางขวา 500 หน่วย แสดงให้เห็นว่าการแปลหลายขั้นตอนสามารถต่อกันได้อย่างไร

### ขั้นตอนที่ 7: เพิ่มแคนวาสใหม่พร้อมการแปลงการสเกลสองเท่า

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Why scale?* การสเกลด้วยค่า 2 ทำให้ความกว้างและความสูงของสี่เหลี่ยมเพิ่มเป็นสองเท่า ช่วยให้คุณสร้างกราฟิกขนาดใหญ่โดยไม่ต้องกำหนดรูปทรงใหม่

### ขั้นตอนที่ 8: เพิ่มแคนวาสใหม่พร้อมการแปลงการหมุนรอบจุด

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Key insight*: `RotateAround` หมุนแคนวาสรอบจุดกำหนดเอง (ที่นี่คือ (100, 50)) ให้คุณควบคุมจุดหมุนได้อย่างละเอียด

### ขั้นตอนที่ 9: บันทึกเอกสาร XPS ที่ได้

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

หลังจากการแปลงทั้งหมดเสร็จสิ้น เอกสารถูกบันทึกลงใน `output1.xps`. เปิดไฟล์ด้วยโปรแกรมดู XPS ใดก็ได้เพื่อดูสี่เหลี่ยมที่ซ้อนกันพร้อมการแปล, การสเกล, และการหมุนตามที่กำหนด

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|-------------------|----------|
| ไฟล์ผลลัพธ์ว่าง | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่ | ตรวจสอบให้แน่ใจว่าโฟลเดอร์มีอยู่หรือใช้พาธแบบเต็ม |
| สี่เหลี่ยมไม่ได้อยู่ตำแหน่งตามที่คาดหวัง | ค่ามาตรฐาน (matrix) ไม่ถูกต้อง | ตรวจสอบลำดับของการเรียก `Translate`, `Scale`, และ `RotateAround` อีกครั้ง |
| สีแสดงผลไม่ถูกต้อง | ค่าระดับสี RGB อยู่เกินช่วง 0‑255 | ใช้ค่าบายต์ที่ถูกต้องสำหรับแต่ละช่อง |

## คำถามที่พบบ่อย

**Q: Aspose.Page for .NET เข้ากันได้กับสภาพแวดล้อมการพัฒนา .NET ทั้งหมดหรือไม่?**  
A: ใช่, ทำงานอย่างไร้รอยต่อกับ Visual Studio, Visual Studio Code, Rider, และ IDE ใด ๆ ที่รองรับ .NET

**Q: จะหา ตัวอย่างเพิ่มเติมและเอกสาร API รายละเอียดได้จากที่ไหน?**  
A: เยี่ยมชมเอกสารอย่างเป็นทางการที่ [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/)

**Q: สามารถทดลองใช้ Aspose.Page ก่อนซื้อใบอนุญาตได้หรือไม่?**  
A: แน่นอน. มีการทดลองใช้ฟรีที่นี่: [Aspose.Page Free Trial](https://releases.aspose.com/)

**Q: จะขอใบอนุญาตชั่วคราวสำหรับการทดสอบได้อย่างไร?**  
A: คุณสามารถขอได้จากหน้าลิขสิทธิ์ชั่วคราว: [Temporary License](https://purchase.aspose.com/temporary-license/)

**Q: จะซื้อใบอนุญาตเต็มได้จากที่ไหน?**  
A: ซื้อโดยตรงจากร้าน Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy)

---

**อัปเดตล่าสุด:** 2026-01-05  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}