---
date: 2026-01-18
description: เรียนรู้วิธีสร้างเอกสาร PostScript ด้วย .NET และเพิ่มสี่เหลี่ยมโดยใช้
  Aspose.Page for .NET คู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ด
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: สร้างเอกสาร PostScript .NET – เพิ่มสี่เหลี่ยมด้วย Aspose.Page
url: /th/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มสี่เหลี่ยมผืนผ้าใน PostScript (PS) ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

เอกสาร ** สร้างเอกสาร postscript ด้วย .NET** Aspose.Page จะช่วยให้สามารถจัดการไฟล์ PostScript ในบทแนะนำนี้เพื่อให้คุณสามารถผ่านขั้นตอนการปกครองในเอกสาร PostScript ด้วย Aspose.Page สำหรับ .NET เพื่อให้คุณมีพื้นฐานที่มั่นคงสำหรับประสิทธิภาพกราฟิกที่มากขึ้น

## คำตอบด่วน
- **ต้องการไลบรารีอะไร?** Aspose.Page for .NET.
- **ฉันทำเอกสาร PostScript ได้ในเริ่มต้นได้อย่างไร** มีปัญหา – API ช่วยให้คุณสร้างไฟล์ PS โดยทางโปรแกรม
- ** รองรับ .NET รองรับอะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7
- ** ต้องการลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีสำหรับการทดสอบ; ต้องมีใบอนุญาตสำหรับการผลิต
- **การดำเนินการทำได้เท่าไหร่?** โดยทั่วไปจะใช้เวลาไม่เกิน 10 นาทีสำหรับรูปร่างพื้นฐาน

## การสร้างเอกสาร postscript .net คืออะไร
ที่สำคัญเอกสาร PostScript ใน .NET การสร้างไฟล์ .ps ด้วยโปรแกรมอธิบายส่วนที่หน้า—ข้อความ, กราฟิกหรือรูปทรง— Aspose.Page API วิธีการสร้างกราฟิกบนเซิร์ฟเวอร์, รายงานอัตโนมัติ, หรือสถานการณ์ใด ๆ ที่ต้องการควบคุมรูปแบบผลลัพธ์อย่างมีประสิทธิภาพ

## เหตุใดจึงต้องใช้ Aspose.Page สำหรับ .NET
- **ควบคุมกราฟิกได้เต็มที่** – วาดรูปร่าง กำหนดสี และใช้สโตรกโดยไม่ต้องจัดการกับไวยากรณ์ PS ระดับต่ำ
- **ข้ามแพลตฟอร์ม** – ใช้งานได้บนรันไทม์ Windows, Linux และ macOS
- **ไม่มีการรองรับภายนอก** – ไลบรารีจะจัดการการสร้าง PS ทั้งหมดเป็นการภายใน
- ** เอกสารและตัวอย่างที่สมบูรณ์** – พร้อมใช้งานอย่างรวดเร็ว

## ข้อกำหนดเบื้องต้น

- **Aspose.Page สำหรับ .NET Library** – ดาวน์โหลดและติดตั้งได้จาก [ที่นี่](https://releases.aspose.com/page/net/)
- **สภาพแวดล้อมการพัฒนา** – Visual Studio, VS Code หรือ IDE ที่ใช้งานร่วมกับ .NET ได้

## นำเข้าเนมสเปซ

ก่อนเริ่มเขียนโค้ด โปรดนำเข้าเนมสเปซที่เปิดเผยคลาสที่จำเป็น:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ต่อไปนี้เราจะแยกตัวอย่างออกเป็นขั้นตอนที่ชัดเจนและมีหมายเลขกำกับ

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` ด้วยโฟลเดอร์ที่คุณต้องการบันทึกไฟล์ PS ที่ได้

## ขั้นตอนที่ 2: สร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

สตรีมนี้ชี้ไปยัง **AddRectangle_outPS.ps** คุณสามารถเปลี่ยนชื่อไฟล์หรือเปลี่ยนตำแหน่งได้ตามต้องการ

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการบันทึกและสร้างเอกสาร PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

ในขั้นตอนนี้ เราบอก Aspose.Page ให้ใช้ขนาดหน้ากระดาษ A4 และสร้างเอกสารหน้าเดียว

## ขั้นตอนที่ 4: เพิ่มสี่เหลี่ยมผืนผ้าที่เติมสี

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

เรากำหนดสี่เหลี่ยมผืนผ้าที่ (250,100) ด้วยความกว้าง 150 และความสูง 100 ตั้งค่าแปรงสีส้ม และเติมสีลงในรูปทรง

## ขั้นตอนที่ 5: เพิ่มสี่เหลี่ยมผืนผ้าที่มีเส้นขอบ

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

สี่เหลี่ยมผืนผ้าที่สองถูกสร้างขึ้นด้านล่างของหน้ากระดาษ คราวนี้มีเส้นขอบสีแดง 3 จุด

## ขั้นตอนที่ 6: ปิดหน้าเว็บและบันทึกเอกสาร

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

การปิดหน้าเป็นการสรุปการวาดภาพ และ `Save()` จะเขียนไฟล์ PS ลงดิสก์

## ปัญหาและเคล็ดลับทั่วไป

- **เส้นทางไฟล์สำหรับ** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`\\` หรือ `/`) หรือใช้ `Path.Combine`
- **ไม่มีลิขสิทธิ์** – ในสภาพแวดล้อมการใช้งานจริง ให้ใช้สิทธิ์การใช้งาน Aspose ของคุณก่อนที่จะสร้างเอกสารเพื่อหลีกเลี่ยงลายน้ำในการประเมิน
- **ในส่วนสี** – หากสี่เหลี่ยมว่างเปล่า ให้ตรวจสอบว่าสีแปรงหรือปากกาตัดกับพื้นหลังของหน้า

## คำถามที่พบบ่อย

**Q:** ฉันจะติดตามเรื่องราวต่างๆ ได้อย่างไร?
**ก:** อย่างแน่นอน เปลี่ยนค่า 'Color.Orange' หรือ 'Color.Red' ในคอนสตรัคเตอร์ 'SolidBrush' และ 'Pen' เป็น 'System. Drawing.Color' ใดๆ ที่คุณต้องการ

**ถาม:** Aspose.Page รองรับรูปแบบเอกสารอื่นหรือไม่?
**ก. ใช่. นอกจาก PostScript แล้ว Aspose.Page ยังรองรับการสร้าง XPS และ EPS อีกด้วย

**ถาม:** ฉันจะเพิ่มข้อความในเอกสารเดียวกันได้อย่างไร?
**ตอบ:** ใช้คลาส `TextFragment` เพื่อวางข้อความในพิกัดที่ต้องการ จากนั้นเรียก `document.Draw(textFragment)`

**ถาม:** ฉันหาความหมายเพิ่มเติมและอ้างอิง API จากที่ไหน?
**ตอบ:** สำรวจเอกสารประกอบ[ที่นี่](https://reference.aspose.com/page/net/) และเข้าร่วมชุมชนที่ [ฟอรัม Aspose.Page](https://forum.aspose.com/c/page/39)

**Q:** เอกสารประกอบ Aspose.Page และซื้ออะไรบ้าง?
**ตอบ:** ใช่ ดาวน์โหลดรุ่นทดลองใช้ฟรี [ที่นี่](https://releases.aspose.com/) หากต้องการการประเมินเพิ่มเติม โปรดพิจารณา [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/)

---

**อัปเดตล่าสุด:** 2026-01-18  
**ทดสอบด้วย:** Aspose.Page 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}