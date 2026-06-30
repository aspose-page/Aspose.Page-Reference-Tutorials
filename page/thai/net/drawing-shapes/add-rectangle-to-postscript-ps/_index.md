---
date: 2026-06-30
description: เรียนรู้วิธีสร้างเอกสาร postscript .NET และเพิ่มสี่เหลี่ยมโดยใช้ Aspose.Page
  สำหรับ .NET. คู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ด.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: เพิ่มสี่เหลี่ยมใน PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: สร้างเอกสาร PostScript .NET – เพิ่มสี่เหลี่ยม Aspose.Page
url: /th/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มสี่เหลี่ยมผืนผ้าใน PostScript (PS) ด้วย Aspose.Page สำหรับ .NET

## บทนำ

Aspose.Page for .NET เป็นไลบรารีที่ช่วยให้สามารถสร้างและจัดการไฟล์ PostScript, EPS และ XPS ได้โดยโปรแกรม หากคุณกำลังมองหา **create postscript document .net** นี้เป็นบทแนะนำที่สอนวิธีเพิ่มสี่เหลี่ยมผืนผ้าในเอกสาร PostScript ด้วย Aspose.Page เพื่อให้คุณมีพื้นฐานที่มั่นคงสำหรับการสร้างกราฟิกที่ซับซ้อนยิ่งขึ้น

## คำตอบสั้น
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for .NET.  
- **ฉันสามารถสร้างเอกสาร PostScript ตั้งแต่ต้นได้หรือไม่?** ใช่ – API ช่วยให้คุณสร้างไฟล์ PS ได้โดยโปรแกรม  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **ต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีสามารถใช้งานเพื่อทดสอบได้; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับรูปทรงพื้นฐาน.

## การสร้างเอกสาร postscript ด้วย .net คืออะไร?
การสร้างเอกสาร PostScript ใน .NET หมายถึงการสร้างไฟล์ `.ps` อย่างโปรแกรมที่อธิบายเนื้อหาของหน้า—ข้อความ, กราฟิก หรือรูปทรง—โดยใช้ Aspose.Page API วิธีนี้เหมาะสำหรับการสร้างกราฟิกบนเซิร์ฟเวอร์, การสร้างรายงานอัตโนมัติ, หรือสถานการณ์ใด ๆ ที่ต้องการการควบคุมรูปแบบผลลัพธ์อย่างแม่นยำ

## ทำไมต้องใช้ Aspose.Page สำหรับ .NET?
Aspose.Page รองรับ **30+ graphics primitives** และสามารถสร้างไฟล์ได้ถึง **500 MB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ ให้ประสิทธิภาพการเรนเดอร์สูงบน Windows, Linux, และ macOS ให้คุณควบคุมรูปทรง, สี, และเส้นขอบได้เต็มที่โดยไม่ต้องเขียนโค้ด PostScript ระดับต่ำ

- **ควบคุมกราฟิกได้เต็มที่** – วาดรูปทรง, ตั้งค่าสี, และใช้เส้นขอบโดยไม่ต้องจัดการกับไวยากรณ์ PS ระดับต่ำ.  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS runtimes.  
- **ไม่มีการพึ่งพาภายนอก** – ไลบรารีจัดการการสร้าง PS ทั้งหมดภายใน.  
- **เอกสารและตัวอย่างที่ครบถ้วน** – เริ่มใช้งานได้อย่างรวดเร็ว.

## ข้อกำหนดเบื้องต้น

- **Aspose.Page for .NET Library** – ดาวน์โหลดและติดตั้งจาก [here](https://releases.aspose.com/page/net/).  
- **สภาพแวดล้อมการพัฒนา** – Visual Studio, VS Code หรือ IDE ที่รองรับ .NET ใด ๆ

## นำเข้า Namespaces

`Aspose.Page` namespace เปิดเผยคลาสหลักที่คุณต้องใช้ เช่น `Document`, `Page`, `SolidBrush`, และ `Pen` ให้นำเข้า ก่อนเริ่มเขียนโค้ด

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ตอนนี้เราจะแบ่งตัวอย่างออกเป็นขั้นตอนที่ชัดเจนและเป็นลำดับ

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสารของคุณ

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

เปลี่ยน `"Your Document Directory"` เป็นโฟลเดอร์ที่คุณต้องการให้ไฟล์ PS ที่สร้างเสร็จถูกบันทึก

## ขั้นตอนที่ 2: สร้าง Output Stream สำหรับเอกสาร PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

สตรีมนี้ชี้ไปที่ **AddRectangle_outPS.ps** คุณสามารถเปลี่ยนชื่อไฟล์หรือที่ตั้งได้ตามต้องการ

## ขั้นตอนที่ 3: ตั้งค่า Save Options และสร้างเอกสาร PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

ที่นี่เราบอก Aspose.Page ให้ใช้ขนาดหน้า A4 และสร้างเอกสารหน้าเดียว

## ขั้นตอนที่ 4: เพิ่มสี่เหลี่ยมผืนผ้าแบบเติมสี

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

เรากำหนดสี่เหลี่ยมที่ตำแหน่ง (250, 100) ความกว้าง 150 และความสูง 100 ตั้งแปรงสีส้มและเติมรูปทรง

## ขั้นตอนที่ 5: เพิ่มสี่เหลี่ยมผืนผ้าแบบเส้นขอบ

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

สี่เหลี่ยมที่สองถูกสร้างที่ตำแหน่งต่ำกว่าบนหน้า ครั้งนี้ใช้เส้นขอบสีแดงหนา 3 พอยต์

## ขั้นตอนที่ 6: ปิดหน้าและบันทึกเอกสาร

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

การปิดหน้าจะสรุปการวาด, และ `Save()` จะเขียนไฟล์ PS ลงดิสก์

## วิธีสร้างเอกสาร postscript ด้วย .net?
`Document` เป็นคลาสหลักที่แสดงถึงไฟล์ PostScript ใน Aspose.Page `SaveOptions` กำหนดการตั้งค่าเช่นขนาดหน้าและรูปแบบเอาต์พุตสำหรับเอกสาร โหลดอ็อบเจกต์ `Document`, ตั้งค่า `SaveOptions` สำหรับหน้า A4, วาดรูปทรงด้วย `SolidBrush` หรือ `Pen`, แล้วเรียก `document.Save()`—กระบวนการทั้งหมดใช้เพียงไม่กี่บรรทัดโค้ดและทำงานบน .NET runtime ใดก็ได้ที่รองรับ รูปแบบนี้ช่วยให้คุณสร้างไฟล์ PostScript ที่สอดคล้องมาตรฐานโดยไม่ต้องสัมผัสกับไวยากรณ์ PS ดิบ

## วิธีสร้างไฟล์ postscript
ใช้คลาส `SaveOptions` ของ Aspose.Page เพื่อระบุรูปแบบเอาต์พุตเป็น PostScript (`SaveFormat.PS`) ไลบรารีจะสตรีมเนื้อหาโดยตรงไปยังไฟล์หรือเมมโมรีสตรีม ทำให้คุณสามารถสร้างเอกสารขนาดใหญ่ได้อย่างมีประสิทธิภาพโดยไม่ใช้หน่วยความจำมากเกินไป

## ปัญหาที่พบบ่อยและเคล็ดลับ

- **เส้นทางไฟล์ไม่ถูกต้อง** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`\\` หรือ `/`) หรือใช้ `Path.Combine`.  
- **ไม่มีไลเซนส์** – ในสภาพแวดล้อมการผลิต ให้ใช้ไลเซนส์ Aspose ก่อนสร้างเอกสารเพื่อหลีกเลี่ยงลายน้ำการประเมินผล.  
- **สีไม่มองเห็น** – หากสี่เหลี่ยมปรากฏเป็นสีว่างเปล่า ให้ตรวจสอบว่าสีของ brush หรือ pen มีความคอนทราสต์กับพื้นหลังของหน้า.

## คำถามที่พบบ่อย

**Q:** ฉันสามารถปรับสีของสี่เหลี่ยมได้หรือไม่?  
**A:** แน่นอน. เปลี่ยนค่า `Color.Orange` หรือ `Color.Red` ในคอนสตรัคเตอร์ของ `SolidBrush` และ `Pen` เป็น `System.Drawing.Color` ใดก็ได้ที่คุณต้องการ.

**Q:** Aspose.Page รองรับรูปแบบเอกสารอื่นหรือไม่?  
**A:** ใช่. นอกจาก PostScript แล้ว Aspose.Page ยังสนับสนุนการสร้าง XPS และ EPS อีกด้วย.

**Q:** ฉันจะเพิ่มข้อความในเอกสารเดียวกันได้อย่างไร?  
**A:** ใช้คลาส `TextFragment` เพื่อวางข้อความที่พิกัดที่ต้องการ, จากนั้นเรียก `document.Draw(textFragment)`.

**Q:** จะหา ตัวอย่างเพิ่มเติมและเอกสารอ้างอิง API ทั้งหมดได้ที่ไหน?  
**A:** สำรวจเอกสาร [here](https://reference.aspose.com/page/net/) และเข้าร่วมชุมชนที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** สามารถทดลองใช้ Aspose.Page ก่อนซื้อได้หรือไม่?  
**A:** ใช่, ดาวน์โหลดการทดลองใช้ฟรี [here](https://releases.aspose.com/). สำหรับการประเมินผลระยะยาว พิจารณาใช้ [temporary license](https://purchase.aspose.com/temporary-license/).

---

**อัปเดตล่าสุด:** 2026-06-30  
**ทดสอบกับ:** Aspose.Page 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างเอกสาร PostScript ด้วย Aspose.Page สำหรับ .NET](/page/net/document-creation/create-postscript-document/)
- [เพิ่มรูปภาพในเอกสาร PostScript (PS) ด้วย Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [เพิ่มข้อความในเอกสาร PostScript (PS) ด้วย Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}