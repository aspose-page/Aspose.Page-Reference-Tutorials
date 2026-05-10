---
date: 2026-03-26
description: เรียนรู้วิธีสร้างเอกสาร PostScript ด้วย .NET พร้อมลายเทกซ์เจอร์แบบต่อกันโดยใช้
  Aspose.Page. ทำตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อเพิ่มเทกซ์เจอร์ที่หลากหลายให้กับไฟล์
  PS ของคุณ.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: สร้างเอกสาร PostScript .NET พร้อมการทำเทกเจอร์ต่อ
url: /th/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร PostScript .NET ด้วยการทำลายพื้นผิวแบบต่อกัน

## วิธีสร้างเอกสาร PostScript .NET ด้วยการทำลายพื้นผิวแบบต่อกัน

ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **สร้างเอกสาร PostScript .NET** และเพิ่มลวดลายการทำลายพื้นผิวแบบต่อกันโดยใช้ไลบรารี Aspose.Page เราจะเดินผ่านแต่ละขั้นตอน ตั้งแต่การตั้งค่าโครงการของคุณจนถึงการเติมและวาดขอบข้อความด้วยแปรงพื้นผิว เพื่อให้คุณสามารถสร้างไฟล์ PS ที่ดูสวยงามได้ในไม่กี่นาที

## คำตอบสั้น
- **ไลบรารีที่ใช้คืออะไร?** Aspose.Page for .NET  
- **ฉันสามารถใช้ .NET Core ได้หรือไม่?** ใช่ ไลบรารีรองรับ .NET Core และ .NET 5/6  
- **รูปแบบภาพใดทำงานกับพื้นผิวได้?** รูปแบบใดก็ได้ที่ System.Drawing รองรับ (BMP, PNG, JPEG, ฯลฯ)  
- **การทำงานนี้ใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง  

## ข้อกำหนดเบื้องต้น

- [Visual Studio](https://visualstudio.microsoft.com/) ติดตั้งบนเครื่องของคุณ.  
- ความรู้พื้นฐานของการเขียนโปรแกรม C#.  
- ดาวน์โหลดและติดตั้ง [Aspose.Page for .NET library](https://releases.aspose.com/page/net/).  
- ไฟล์ภาพสำหรับลวดลายพื้นผิว (เช่น **TestTexture.bmp**).

## นำเข้า Namespaces

ในไฟล์ C# ของคุณ ให้นำเข้า namespaces ที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหาไทป์ที่เราจะใช้ได้จากที่ไหน:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

แทนที่ **Your Document Directory** ด้วยโฟลเดอร์ที่คุณต้องการให้ไฟล์ PS ที่สร้างขึ้นถูกบันทึก.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง Output Stream สำหรับเอกสาร PS

บล็อกนี้เปิดไฟล์สตรีม, ตั้งค่าขนาดหน้า (A4 เป็นค่าเริ่มต้น), และสร้างอินสแตนซ์ **PsDocument** ใหม่ที่เราจะวาดบนมัน.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 3: ใช้ลวดลายการทำลายพื้นผิวแบบต่อกัน

ที่นี่เราจะโหลดบิตแมป, ห่อมันด้วย **TextureBrush**, ปรับขยายแนวนอนตามต้องการ, และบอก **PsDocument** ให้ใช้แปรงนี้สำหรับการวาดต่อไป.

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

## ขั้นตอนที่ 4: สร้างเส้นทางสี่เหลี่ยมและเติม

สี่เหลี่ยมง่าย ๆ ถูกกำหนดและเติมด้วยแปรงพื้นผิวที่เราตั้งค่าไว้ก่อนหน้า.

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

## ขั้นตอนที่ 5: ตั้งค่า Stroke และวาด

เราดึงสีปัจจุบัน (แปรงพื้นผิว), สร้างปากกาสีแดงสำหรับเส้นขอบ, และวาดกรอบสี่เหลี่ยม.

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

## ขั้นตอนที่ 6: เติมและ Stroke ข้อความด้วยลวดลายพื้นผิว

ขั้นตอนนี้แสดงความสามารถ **เติมและ Stroke ข้อความ**: ตัวอักษร “ABC” ถูกเติมด้วยแปรงพื้นผิวและจากนั้นวาดเส้นขอบ, ให้ผลลัพธ์ภาพที่โดดเด่น.

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

## ขั้นตอนที่ 7: บันทึกและปิดเอกสาร

การปิดหน้าเสร็จสิ้นคำสั่งการวาด, และ `Save()` จะเขียนไฟล์ PostScript ลงดิสก์.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

## ปัญหาที่พบบ่อยและวิธีแก้

- **พื้นผิวดูถูกยืดออกผิดรูป** – ปรับค่า `Matrix` เพื่อควบคุมการสเกลในทิศทาง X/Y.  
- **ไม่พบภาพ** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและชื่อไฟล์ตรงกันอย่างแม่นยำ รวมถึงตัวพิมพ์ใหญ่/เล็ก.  
- **สีดูผิด** – จำไว้ว่า PostScript ใช้สีในอิสระอุปกรณ์; ตรวจสอบว่าคุณใช้วัตถุ `Color` ที่แมปสีได้อย่างถูกต้อง.  

## คำถามที่พบบ่อย

**Q:** ฉันสามารถใช้รูปแบบภาพอื่นสำหรับลวดลายพื้นผิวได้หรือไม่?  
**A:** ใช่, รูปแบบใดก็ได้ที่ `System.Drawing.Bitmap` รองรับ (BMP, PNG, JPEG, GIF, ฯลฯ) ทำงานได้  

**Q:** Aspose.Page เข้ากันได้กับ .NET Core หรือไม่?  
**A:** แน่นอน. ไลบรารีทำงานบน .NET Framework, .NET Core, และ .NET 5/6.  

**Q:** ฉันจะเปลี่ยนขนาดของสี่เหลี่ยมที่มีพื้นผิวอย่างไร?  
**A:** ปรับค่า `RectangleF` ในขั้นตอนการสร้างสี่เหลี่ยม (เช่น `new RectangleF(0, 0, 300, 150)`).  

**Q:** ฉันสามารถใช้หลายลวดลายพื้นผิวในเอกสารเดียวได้หรือไม่?  
**A:** ใช่. เพียงสร้าง `TextureBrush` ใหม่ด้วยภาพที่แตกต่างและเรียก `SetPaint` อีกครั้งก่อนวาดรูปหรือข้อความต่อไป.  

**Q:** ฉันจะหา ตัวอย่างเพิ่มเติมและอ้างอิง API ได้จากที่ไหน?  
**A:** เยี่ยมชม [Aspose.Page Forum](https://forum.aspose.com/c/page/39) เพื่อรับความช่วยเหลือจากชุมชนและ [documentation](https://reference.aspose.com/page/net/) อย่างเป็นทางการสำหรับการใช้งาน API อย่างละเอียด.  

## สรุป

ตอนนี้คุณรู้วิธี **สร้างเอกสาร PostScript .NET** และใช้ลวดลายการทำลายพื้นผิวแบบต่อกัน, รวมถึงวิธี **เติมและ Stroke ข้อความ** ด้วยพื้นผิวนั้นแล้ว. ทดลองกับภาพต่าง ๆ, เมทริกซ์สเกล, และ primitive การวาดเพื่อสร้างไฟล์ PS สไตล์กำหนดเองสำหรับรายงาน, ใบปลิว, หรือผลลัพธ์ที่ต้องการกราฟิกจำนวนมาก.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}