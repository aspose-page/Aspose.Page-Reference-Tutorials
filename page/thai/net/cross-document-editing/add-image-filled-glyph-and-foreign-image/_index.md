---
date: 2026-01-07
description: เรียนรู้วิธีสร้างเอกสาร XPS ด้วย .NET โดยใช้ Aspose.Page คู่มือนี้แสดงการเพิ่ม
  glyph ที่เติมด้วยภาพและภาพจากแหล่งอื่นเพื่อทำให้ภาพเอกสารมีความหลากหลายมากขึ้น
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: สร้างเอกสาร XPS ด้วย .NET และ Aspose.Page – Glyph ที่เติมด้วยภาพและภาพต่างประเทศ
url: /th/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร XPS .NET ด้วย Aspose.Page – Glyph เติมภาพและภาพอื่น

## บทนำ

หากคุณต้องการ **สร้างเอกสาร XPS .NET** ที่ดูเรียบหรูและเป็นมืออาชีพ Aspose.Page จะมอบเครื่องมือให้คุณฝังภาพโดยตรงลงใน glyphs และใช้ทรัพยากรกราฟิกซ้ำกันในหลายเอกสาร ในบทเรียนนี้เราจะสร้างไฟล์ XPS สองไฟล์ เติม glyphs ด้วย image brush แล้วนำ brush นั้นไปใช้ซ้ำในเอกสารที่สอง เมื่อเสร็จคุณจะเข้าใจว่าการทำเช่นนี้ช่วยประหยัดหน่วยความจำ ลดความซับซ้อนของการจัดสไตล์ และเปิดโอกาสสร้างสรรค์สำหรับรายงาน ใบแจ้งหนี้ หรือเนื้อหาที่ต้องพิมพ์ใด ๆ

## คำตอบอย่างรวดเร็ว
- **บทเรียนนี้ครอบคลุมอะไร?** การเพิ่ม glyph ที่เติมด้วยภาพและการใช้ซ้ำในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET  
- **คีย์เวิร์ดหลักที่มุ่งหมายคืออะไร?** `create xps document .net`  
- **ข้อกำหนดเบื้องต้น?** สภาพแวดล้อมการพัฒนา .NET, Aspose.Page for .NET, และโฟลเดอร์สำหรับไฟล์ XPS ของคุณ  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10‑15 นาทีสำหรับต้นแบบที่ทำงานได้  
- **สามารถใช้รูปแบบภาพอื่นได้หรือไม่?** ได้ – ทุกรูปแบบที่ .NET’s `System.Drawing.Image` รองรับ  

## ข้อกำหนดเบื้องต้น

ก่อนจะเริ่มเขียนโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

- **Aspose.Page for .NET** – ดาวน์โหลดไลบรารีเวอร์ชันล่าสุดจาก [here](https://releases.aspose.com/page/net/)  
- **สภาพแวดล้อมการพัฒนา** – Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ .NET 6+)  
- **Document Directory** – สร้างโฟลเดอร์บนเครื่องของคุณเพื่อเก็บภาพต้นฉบับและไฟล์ XPS ที่สร้างขึ้น; เราจะอ้างถึงโฟลเดอร์นี้ว่า **Your Document Directory** ในโค้ดตัวอย่าง  

## นำเข้า Namespaces

เริ่มต้นด้วยการเรียกใช้ namespaces ที่จำเป็นสำหรับการทำงานกับวัตถุ XPS และยูทิลิตี้การวาดภาพ

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: สร้างเอกสาร XPS แรก

เราจะเริ่มด้วยการสร้างเอกสาร XPS ว่างเปล่าที่จะเป็นที่เก็บ glyph ที่เติมด้วยภาพ

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### ขั้นตอนที่ 2: เพิ่ม Glyph ลงในเอกสารแรก

ต่อไปให้เพิ่ม glyph (อักขระข้อความ) ที่เราจะเติมด้วย image brush ในภายหลัง

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### ขั้นตอนที่ 3: เติม Glyph ด้วย Image Brush

ที่นี่เราจะสร้าง `ImageBrush` จากไฟล์ TIFF ที่อยู่ในโฟลเดอร์ข้อมูลของเราและนำไปใช้กับ glyph การตั้งค่า brush เป็น tile mode ทำให้ภาพทำซ้ำหากพื้นที่ glyph มากกว่าขนาดภาพ

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### ขั้นตอนที่ 4: สร้างเอกสาร XPS ที่สอง

ต่อไปเราจะสร้างเอกสาร XPS ที่สองเพื่อใช้สไตล์ glyph และ image brush จากเอกสารแรกซ้ำกัน

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### ขั้นตอนที่ 5: เพิ่ม Glyph ด้วยฟอนต์จากเอกสารแรก

เราจะเพิ่ม glyph ลงในเอกสารที่สองโดยใช้ฟอนต์อ็อบเจ็กต์เดียวกันจากเอกสารแรก เพื่อให้การแสดงผลตรงกันระหว่างไฟล์ทั้งสอง

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### ขั้นตอนที่ 6: สร้าง Image Brush จากการเติมของเอกสารแรก

แทนที่จะโหลดภาพใหม่ เราจะคัดลอก brush จาก `glyphs1` แล้วกำหนดให้กับ `glyphs2` ซึ่งแสดงให้เห็นว่าคุณสามารถ **สร้างเอกสาร XPS .NET** ที่แชร์ทรัพยากรได้อย่างมีประสิทธิภาพ

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### ขั้นตอนที่ 7: บันทึกเอกสาร

สุดท้ายให้บันทึกไฟล์ XPS ทั้งสองลงดิสก์ คุณสามารถเปิดดูด้วย XPS viewer ใดก็ได้เพื่อสังเกตเอฟเฟกต์ glyph ที่เติมภาพ

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## ทำไมต้องใช้ glyph เติมภาพเมื่อคุณสร้างเอกสาร XPS .NET?

- **Visual Impact** – แปลงข้อความธรรมดาให้เป็นองค์ประกอบกราฟิกที่มีความละเอียดสูงโดยไม่ต้องแปลงหน้าเป็น raster ทั้งหน้า  
- **Resource Reuse** – แชร์ brushes และ fonts ข้ามหลายเอกสาร ลดการใช้หน่วยความจำ  
- **Flexibility** – สามารถ tile, stretch หรือ rotate image brush เพื่อสร้างลวดลายหรือแบรนด์ที่กำหนดเอง  

## ปัญหาทั่วไปและเคล็ดลับ

- **File Path Errors** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`\` หรือ `/`) ที่เหมาะกับระบบปฏิบัติการของคุณ  
- **Unsupported Image Formats** – Aspose.Page ทำงานได้ดีที่สุดกับ TIFF, PNG, และ JPEG ควรแปลงรูปแบบอื่นก่อนใช้งาน  
- **TileMode Not Applied** – ตรวจสอบว่าคุณได้แคสต์เป็น `XpsImageBrush` ก่อนตั้งค่า `TileMode` มิฉะนั้นคุณสมบัตินี้จะถูกละเลย  

## คำถามที่พบบ่อย

### Q1: ฉันสามารถใช้รูปแบบภาพต่าง ๆ เพื่อเติม glyph ได้หรือไม่?

**A:** ได้, Aspose.Page รองรับ TIFF, PNG, JPEG, BMP, และ GIF เพียงระบุส่วนขยายไฟล์ที่ถูกต้องในคำเรียก `CreateImageBrush`

### Q2: ฉันจะปรับแต่งลักษณะของ glyph เพิ่มเติมได้อย่างไร?

**A:** สำรวจคุณสมบัติเพิ่มเติมบน `XpsGlyphs` เช่น `Opacity`, `RenderTransform`, และ `Stroke` เพื่อปรับการเรนเดอร์ให้ละเอียดขึ้น

### Q3: Aspose.Page เหมสำหรับจัดการชุดเอกสารขนาดใหญ่หรือไม่?

**A:** แน่นอน. ไลบรารีได้รับการปรับให้ทำงานในสถานการณ์ประสิทธิภาพสูงและสามารถประมวลผลไฟล์ XPS จำนวนหลายพันไฟล์ในงานแบตช์ได้

### Q4: ฉันสามารถใช้สไตล์ต่าง ๆ กับ glyph แต่ละตัวได้หรือไม่?

**A:** ได้. แต่ละอินสแตนซ์ของ `XpsGlyphs` สามารถมี fill, stroke, และ transformation ของตนเอง ทำให้คุณควบคุมได้อย่างละเอียด

### Q5: ประโยชน์ของการใช้ Aspose.Page เมื่อเทียบกับเครื่องมือประมวลผลเอกสารอื่น ๆ คืออะไร?

**A:** Aspose.Page มี API ครบวงจร ฟรีจากลิขสิทธิ์ สำหรับการสร้าง, แก้ไข, และแปลง XPS พร้อมเอกสารอธิบายละเอียดและการสนับสนุนตลอด 24 ชั่วโมง

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}