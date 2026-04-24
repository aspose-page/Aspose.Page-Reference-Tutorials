---
date: 2026-01-05
description: เรียนรู้วิธีเพิ่มคลิปปิ้งพาธใน PostScript ด้วย Aspose.Page สำหรับ .NET
  – คู่มือแบบทีละขั้นตอนพร้อมเทคนิคการตั้งแปรงทาสีและวาดสี่เหลี่ยมจัตุรัสแบบเส้นประ
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: เพิ่มเส้นทางคลิปปิ้งใน PS ด้วย Aspose.Page สำหรับ .NET
url: /th/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่ม Clipping Path ให้กับ PS ด้วย Aspose.Page for .NET

## คำนำ

ในบทแนะนำฉบับเต็มนี้ คุณจะได้เรียนรู้วิธี **เพิ่ม clipping path** ให้กับเอกสาร PostScript (PS) ด้วย Aspose.Page for .NET เราจะเดินผ่านแต่ละขั้นตอน แสดงวิธี **ตั้งค่า paint brush** และสาธิตวิธี **วาดสี่เหลี่ยมจัตุรัสแบบเส้นประ** รอบเนื้อหาที่ถูกคลิป ปิดท้ายด้วยไฟล์ PS ที่ทำงานเต็มรูปแบบซึ่งแสดงการคลิปตามรูปทรง ทำให้กราฟิกของคุณดูไดนามิกและเป็นมืออาชีพมากขึ้น

## คำตอบด่วน
- **“เพิ่ม clipping path” ทำอะไร?** มันจำกัดการวาดให้ทำได้เฉพาะภายในรูปทรงที่กำหนด เท่านั้น ส่วนที่อยู่นอกรูปทรงจะถูกซ่อน  
- **ไลบรารีใดจัดการ clipping ใน .NET?** Aspose.Page for .NET มี API ที่ครบครันสำหรับการจัดการ PS/EPS  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนาได้; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **เปลี่ยนสีของ brush ได้หรือไม่?** ได้, ใช้ `SetPaint` พร้อม `SolidBrush` หรือ gradient ที่ต้องการ  
- **วาดสี่เหลี่ยมจัตุรัสแบบเส้นประเป็นไปได้หรือไม่?** แน่นอน – สร้าง `Pen` ที่มี `DashStyle.Dash` แล้วใช้ `Draw`  

## Clipping path คืออะไรใน PostScript?
Clipping path กำหนดพื้นที่ที่มองเห็นได้ของคำสั่งการวาดต่อไป ทุกอย่างที่วาดอยู่นอกเส้นทางจะถูกละเลย ทำให้คุณสร้างกราฟิกที่มีการมาสก์ซับซ้อนได้โดยไม่ต้องแก้ไขเนื้อหาเดิม

## ทำไมต้องใช้ Aspose.Page สำหรับ clipping?
- **ไม่มีการพึ่งพา external** – ไลบรารี .NET แท้ ๆ  
- **ควบคุมสถานะกราฟิกได้เต็มที่** (save/restore, translate, rotate)  
- ** primitive การวาดที่หลากหลาย** เช่น `SetPaint`, `Clip`, และ `Draw` พร้อม pen และ brush ที่ปรับแต่งได้  

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานด้านการเขียนโปรแกรม C#  
- ติดตั้งไลบรารี Aspose.Page for .NET – สามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/net/)  
- Visual Studio หรือ IDE .NET ที่คุณชื่นชอบ  

## นำเข้า Namespaces

ก่อนอื่นให้นำเข้า namespaces ที่จำเป็นสำหรับการจัดการกราฟิก:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ตอนนี้เราจะอธิบายตัวอย่างเป็นขั้นตอนที่ชัดเจนและเป็นลำดับเลข

### ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสาร

กำหนดโฟลเดอร์ที่ไฟล์ต้นฉบับและไฟล์ผลลัพธ์จะถูกจัดเก็บ

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้าง Output Stream สำหรับเอกสาร PostScript

สร้างสตรีมที่สามารถเขียนได้เพื่อเก็บไฟล์ PS ที่สร้างขึ้น

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### ขั้นตอนที่ 3: สร้าง Save Options

สร้างอินสแตนซ์ `PsSaveOptions` ด้วยการตั้งค่าเริ่มต้น คุณสามารถปรับแต่งต่อได้หากต้องการ

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### ขั้นตอนที่ 4: สร้างเอกสาร PS แบบ 1‑หน้าใหม่

เริ่มต้นอ็อบเจ็กต์ `PsDocument` ที่เป็นตัวแทนไฟล์ PS ของคุณ

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### ขั้นตอนที่ 5: สร้าง Graphics Path จากสี่เหลี่ยม

เราจะใช้สี่เหลี่ยมเป็นรูปทรงพื้นฐานที่จะถูกคลิปต่อไป

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### ขั้นตอนที่ 6: คลิปด้วยรูปทรง

ที่นี่เราจะ **เพิ่ม clipping path** ด้วยวงกลม, **ตั้งค่า paint brush** เป็นสีน้ำเงิน, และเติมสี่เหลี่ยมภายในพื้นที่ที่ถูกคลิป

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### ขั้นตอนที่ 7: ย้าย Graphics State ระดับบนและวาดสี่เหลี่ยมจัตุรัสแบบเส้นประ

หลังจากคืนค่า state ก่อนหน้า เราจะย้ายตำแหน่งกราฟิกอีกครั้ง, **วาดสี่เหลี่ยมจัตุรัสแบบเส้นประ**, และใช้สีสีน้ำเงินเป็นเส้นขอบ

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### ขั้นตอนที่ 8: ปิดและบันทึกเอกสาร

จบหน้ากระดาษและเขียนไฟล์ PS ลงดิสก์

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

คุณได้ **เพิ่ม clipping path** ตั้งค่า paint brush ตามต้องการ และวาดสี่เหลี่ยมจัตุรัสแบบเส้นประรอบกราฟิกของคุณด้วย Aspose.Page for .NET เรียบร้อยแล้ว

## ปัญหาที่พบบ่อยและวิธีแก้

- **คลิปไม่แสดง:** ตรวจสอบว่าคุณเรียก `WriteGraphicsSave()` ก่อนทำการแปลตำแหน่งและ `WriteGraphicsRestore()` หลังการเติมสี  
- **สีไม่ตรง:** ยืนยันว่า `SetPaint` ถูกเรียกหลังจาก `Clip` และก่อน `Fill`  
- **เส้นประแสดงเป็นเส้นทึบ:** ตรวจสอบให้แน่ใจว่า `Pen` มี `DashStyle` ตั้งเป็น `DashStyle.Dash` ก่อน `SetStroke`  

## คำถามที่พบบ่อย

### Q1: สามารถใช้ Aspose.Page for .NET กับภาษาโปรแกรมอื่นได้หรือไม่?
A: Aspose.Page ถูกออกแบบมาสำหรับแอปพลิเคชัน .NET เป็นหลัก อย่างไรก็ตาม Aspose มีไลบรารีที่คล้ายกันสำหรับภาษาอื่น ๆ

### Q2: จะหา ตัวอย่างเพิ่มเติมและเอกสารสำหรับ Aspose.Page for .NET ได้จากที่ไหน?
A: คุณสามารถสำรวจตัวอย่างและเอกสารโดยละเอียดเพิ่มเติมได้ที่ [Aspose.Page documentation](https://reference.aspose.com/page/net/)

### Q3: มีรุ่นทดลองฟรีสำหรับ Aspose.Page for .NET หรือไม่?
A: มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Page for .NET [ที่นี่](https://releases.aspose.com/)

### Q4: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for .NET ได้อย่างไร?
A: คุณสามารถรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

### Q5: จะหาการสนับสนุนหรือพูดคุยเกี่ยวกับ Aspose.Page ได้จากที่ไหน?
A: เยี่ยมชม [Aspose.Page forums](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชนและการสนทนาต่าง ๆ  

---

**อัปเดตล่าสุด:** 2026-01-05  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}