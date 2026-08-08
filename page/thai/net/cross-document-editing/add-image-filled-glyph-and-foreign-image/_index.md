---
date: 2026-06-30
description: เรียนรู้วิธีสร้าง XPS Document .NET และเพิ่ม Image Filled Glyph หรือ
  Foreign Image ด้วย Aspose.Page for .NET เพียงไม่กี่ขั้นตอนง่าย ๆ
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: เพิ่ม Image Filled Glyph & Foreign Image
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: สร้าง XPS Document .NET – เพิ่ม Image Filled Glyph & Foreign Image ด้วย Aspose.Page
url: /th/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร XPS .NET – เพิ่ม Glyph ที่เติมด้วยภาพและภาพจากแหล่งอื่นด้วย Aspose.Page

## บทนำ

ในการพัฒนา .NET, งาน **create XPS document .NET** เป็นเรื่องทั่วไปเมื่อคุณต้องการกราฟิกคุณภาพสูงที่ไม่ขึ้นกับความละเอียด. Aspose.Page for .NET ทำให้เรื่องนี้ง่ายและให้คุณเพิ่มไฟล์ XPS ด้วย glyph ที่เติมด้วยภาพหรือดึงภาพจากเอกสาร XPS อื่น. เมื่อจบบทเรียนนี้คุณจะรู้วิธีสร้างเอกสาร XPS สองไฟล์, เติม glyph ด้วยภาพ, และใช้ภาพเหล่านั้นซ้ำในหลายเอกสาร—เหมาะสำหรับการสร้างใบแจ้งหนี้, ใบรับรอง, หรือผลลัพธ์ที่มีภาพมาก.

## คำตอบอย่างรวดเร็ว
- **What does Aspose.Page support?** รองรับรูปแบบภาพกว่า 25 รูปแบบและความสามารถในการประมวลผลไฟล์ XPS ขนาดสูงสุด 500 MB โดยไม่ต้องโหลดเต็มหน่วยความจำ.  
- **How many lines of code to add an image‑filled glyph?** เพียงสองบรรทัด: สร้าง `ImageBrush` แล้วกำหนดให้กับ `Glyph`.  
- **Do I need a license for production?** ใช่, ใบอนุญาตเชิงพาณิชย์จะลบลายน้ำการประเมินผลออก.  
- **Which .NET versions are compatible?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I reuse fonts from another XPS?** แน่นอน – คุณสามารถนำเข้าชุดฟอนต์จากเอกสารแรกไปยังเอกสารที่สองได้.

## คุณสร้างเอกสาร XPS ด้วย Aspose.Page .NET อย่างไร?
โหลดไลบรารี Aspose.Page, สร้างอินสแตนซ์ของ `XpsDocument`, เพิ่มหน้า, และเรียก `Save` – นั่นคือขั้นตอนการทำงานทั้งหมดในสามคำสั่งสั้น ๆ. API จะจัดการขนาดหน้า, DPI, และการจัดการทรัพยากรโดยอัตโนมัติ, ดังนั้นคุณไม่จำเป็นต้องจัดการโครงสร้าง XPS ระดับต่ำด้วยตนเอง. วิธีนี้สามารถขยายจากโบรชัวร์หน้าเดียวไปจนถึงแคตาล็อกหลายร้อยหน้า.

## ข้อกำหนดเบื้องต้น
Before you start, ensure you have:

- **Aspose.Page for .NET** – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/net/).  
- **A .NET IDE** – Visual Studio, Rider, หรือ VS Code พร้อมส่วนขยาย C#.  
- **A folder for your documents** – เราจะเรียกมันว่า **Your Document Directory** ในโค้ดตัวอย่าง.

## นำเข้า Namespaces
`Aspose.Page.XPS` namespace ให้คลาสหลักของเอกสาร XPS, ส่วน `Aspose.Page.XPS.XpsModel` มีองค์ประกอบโมเดลเช่น glyphs และ brushes. นำเข้าพวกมันที่ส่วนหัวของไฟล์ของคุณ:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Glyph ที่เติมด้วยภาพคืออะไร?
Glyph คือรูปทรงเวกเตอร์ที่สามารถเรนเดอร์ด้วยสีทึบ, การไล่สี, หรือ image brush. เมื่อคุณใช้ `ImageBrush`, ภายในของ glyph จะถูกทาด้วยภาพที่กำหนด, ทำให้ได้เอฟเฟกต์ภาพที่ซับซ้อนโดยไม่ต้องแปลงหน้าเป็น raster ทั้งหน้า.

## ขั้นตอนที่ 1: สร้างเอกสาร XPS แรก
`XpsDocument` แสดงถึงแพคเกจ XPS และเป็นจุดเริ่มต้นสำหรับการสร้างและบันทึกไฟล์ XPS. เริ่มต้นด้วยการสร้างเอกสาร XPS แรกที่จะเป็นที่เก็บ glyph ที่เติมด้วยภาพ.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## ขั้นตอนที่ 2: เพิ่ม Glyph ไปยังเอกสารแรก
`XpsGlyphs` กำหนดคอลเลกชันของ glyph (อักขระข้อความ) ที่สามารถวางบนหน้า. เพิ่ม glyph ไปยังเอกสารแรก, ระบุฟอนต์, ขนาด, สไตล์, และตำแหน่ง.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## ขั้นตอนที่ 3: เติม Glyph ด้วย Image Brush
`ImageBrush` ทาพื้นที่ด้วยภาพ, ทำให้รูปแบบหรือรูปภาพเติมเต็มรูปทรง. เติม glyph ด้วย image brush, ใช้ภาพจากไดเรกทอรีข้อมูลของคุณ.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## ขั้นตอนที่ 4: สร้างเอกสาร XPS ที่สอง
`XpsDocument` ใช้สร้างไฟล์ XPS ใหม่ที่สามารถมีหน้า, ทรัพยากร, และเนื้อหา. ตอนนี้สร้างเอกสาร XPS ที่สองที่จะรวม glyph จากเอกสารแรก.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## ขั้นตอนที่ 5: เพิ่ม Glyph ด้วยฟอนต์จากเอกสารแรก
`Font` แสดงถึงแบบอักษรที่ใช้ในการเรนเดอร์ข้อความในเอกสาร XPS. เพิ่ม glyph ไปยังเอกสารที่สอง, ใช้ฟอนต์ที่ดึงจากเอกสารแรก. การแชร์ชุดฟอนต์ช่วยให้ขนาดไฟล์เล็กและรักษาความสอดคล้องของภาพ.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## ขั้นตอนที่ 6: สร้าง Image Brush จากการเติมของเอกสารแรก
`ImageBrush` สามารถสร้างจากการเติมที่มีอยู่เพื่อใช้ภาพเดียวกันในหลายเอกสาร. สร้าง image brush จากการเติมของเอกสารแรกและใช้มันเติม glyph ในเอกสารที่สอง. เทคนิค “foreign image” นี้ทำให้คุณใช้ผลงานศิลปะซ้ำโดยไม่ต้องทำซ้ำไฟล์ต้นฉบับ.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## ขั้นตอนที่ 7: บันทึกเอกสาร
`Save` เขียนแพคเกจ XPS ไปยังไฟล์, ฝังทรัพยากรทั้งหมด. บันทึกเอกสาร XPS ทั้งสอง (แรกและที่สอง) ไปยังโฟลเดอร์ผลลัพธ์. เมธอด `Save` เขียนแพคเกจ XPS, ฝังทรัพยากรทั้งหมดและรักษา glyph ที่เติมด้วยภาพ.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| **Image not appearing inside glyph** | `ImageBrush` ถูกสร้างด้วย URI ที่ไม่ถูกต้องหรือขนาดภาพเกินขอบเขตของ glyph. | ตรวจสอบเส้นทางภาพ, และอาจตั้งค่า `ImageBrush.Stretch = Stretch.Uniform`. |
| **Fonts missing in the second document** | ทรัพยากรฟอนต์ไม่ได้ถูกส่งออกจาก XPS แรก. | ใช้ `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` ก่อนเพิ่ม glyph. |
| **Performance slowdown on large files** | โหลดภาพขนาดใหญ่เข้าสู่หน่วยความจำสำหรับแต่ละ glyph. | ใช้ `ImageBrush` ตัวเดียวสำหรับทุก glyph, หรือทำการ down‑sample ภาพก่อนใช้. |

## คำถามที่พบบ่อย

### Q1: ฉันสามารถใช้รูปแบบภาพต่าง ๆ สำหรับเติม glyph ได้หรือไม่?
A1: ใช่, Aspose.Page รองรับ PNG, JPEG, BMP, GIF, TIFF, และอื่น ๆ—รวมกว่า 25 รูปแบบทั้งหมด.

### Q2: ฉันจะปรับแต่งลักษณะของ glyph เพิ่มเติมได้อย่างไร?
A2: สำรวจคุณสมบัติเช่น `Glyph.Stroke`, `Glyph.FillOpacity`, และ `Glyph.Transform` เพื่อปรับเส้นขอบ, ความโปร่งแสง, และการหมุน.

### Q3: Aspose.Page เหมาะสำหรับจัดการชุดเอกสารขนาดใหญ่หรือไม่?
A3: แน่นอน. ไลบรารีนี้ประมวลผลไฟล์ XPS หลายร้อยหน้าโดยใช้การสตรีม, ทำให้การใช้หน่วยความจำต่ำกว่า 100 MB แม้สำหรับเอกสาร 500 หน้า.

### Q4: ฉันสามารถใช้สไตล์ต่าง ๆ กับ glyph แต่ละตัวได้หรือไม่?
A4: ใช่, แต่ละอินสแตนซ์ของ `Glyph` มีคุณสมบัติ `Fill`, `Stroke`, และ `Transform` ของตนเอง, ทำให้สามารถสไตล์แต่ละ glyph ได้.

### Q5: ประโยชน์ของการใช้ Aspose.Page เมื่อเทียบกับเครื่องมือ XPS อื่นคืออะไร?
A5: Aspose.Page รองรับรูปแบบภาพกว่า 25 รูปแบบ, ประมวลผลไฟล์ขนาดสูงสุด 500 MB โดยไม่ต้องโหลดเต็มหน่วยความจำ, และให้ API ที่เป็น .NET‑native 100 % — ไม่ต้องพึ่งพา COM interop หรือเครื่องมือภายนอก.

---

**อัปเดตล่าสุด:** 2026-06-30  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [สร้างเอกสาร XPS – Aspose.Page for .NET](/page/net/document-creation/)
- [เพิ่มภาพไปยังเอกสาร XPS ด้วย Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [เพิ่ม Glyph Clone และเปลี่ยนสีด้วย Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}