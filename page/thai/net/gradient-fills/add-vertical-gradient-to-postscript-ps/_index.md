---
date: 2026-02-25
description: เรียนรู้วิธีใช้แปรงไลเนียร์กราเดียนต์ของ C# เพื่อเพิ่มกราเดียนต์ให้กับไฟล์
  PS และเติมสี่เหลี่ยมด้วยกราเดียนต์โดยใช้ Aspose.Page สำหรับ .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: C# Linear Gradient Brush – เพิ่มไล่สีแนวตั้งใน PostScript (PS) ด้วย Aspose.Page
url: /th/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – เพิ่ม Gradient แนวตั้งใน PostScript (PS) ด้วย Aspose.Page

## บทนำ

ในด้านการจัดการและสร้างเอกสาร, **Aspose.Page for .NET** โดดเด่นในฐานะเครื่องมือที่ทรงพลังสำหรับนักพัฒนา. ในคู่มือนี้คุณจะได้เรียนรู้วิธี **เพิ่ม gradient ให้ไฟล์ PS** โดยใช้ **C# linear gradient brush** เพื่อ **เติมสี่เหลี่ยมด้วย gradient**. เมื่อจบบทเรียนนี้คุณจะมีความเข้าใจที่ชัดเจนและเป็นขั้นตอนเกี่ยวกับโค้ดที่จำเป็นและเหตุผลที่เทคนิคนี้สร้าง gradient แนวตั้งที่เรียบเนียนในผลลัพธ์ PostScript ของคุณ.

## คำตอบด่วน
- **C# linear gradient brush ทำอะไร?** มันสร้างการเปลี่ยนแปลงสีอย่างราบรื่นระหว่างหลายสีทั่วรูปทรง.
- **สามารถใช้กับ .NET เวอร์ชันใดก็ได้หรือไม่?** ใช่, Aspose.Page รองรับ .NET Framework 4.5+ และ .NET Core/5+.
- **ต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการสร้างที่ไม่ใช่การประเมิน.
- **Gradient นี้เป็นแนวตั้งจริงหรือไม่?** แปรงถูกหมุน 90°, ทำให้แนวการไหลเป็นแนวตั้ง.
- **ไฟล์ผลลัพธ์บันทึกไว้ที่ไหน?** ที่พาธที่คุณระบุใน `dataDir` (เช่น `VerticalGradient_outPS.ps`).

## C# Linear Gradient Brush คืออะไร?

**C# linear gradient brush** คืออ็อบเจกต์ของ GDI+ (`LinearGradientBrush`) ที่วาดการเปลี่ยนแปลงสีเชิงเส้นระหว่างจุดที่กำหนด. เมื่อรวมกับ Drawing API ของ Aspose.Page, มันทำให้คุณสามารถเรนเดอร์ gradient ที่ซับซ้อนได้โดยตรงในเอกสาร PostScript (PS).

## ทำไมต้องใช้ Linear Gradient Brush สำหรับ PostScript?

- **คุณภาพสูง:** Gradient ถูกเรนเดอร์ระดับเครื่องพิมพ์, รักษาความแม่นยำ.
- **การควบคุมเต็มรูปแบบ:** คุณสามารถตั้งค่า color stops ที่กำหนดเอง, การหมุน, และการสเกล.
- **โค้ดใช้ซ้ำได้:** โลจิกของแปรงเดียวกันทำงานได้กับ PDF, SVG, และรูปแบบอื่นที่ Aspose.Page รองรับ.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามบทเรียน, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อม:

- Aspose.Page for .NET: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Page แล้ว. คุณสามารถค้นหาแหล่งข้อมูลและเอกสารที่จำเป็นได้ [ที่นี่](https://reference.aspose.com/page/net/).
- Development Environment: ตั้งค่าสภาพแวดล้อมการพัฒนาที่เหมาะสม, รวมถึง Integrated Development Environment (IDE) สำหรับการพัฒนา .NET.
- Basic Understanding: ทำความคุ้นเคยกับพื้นฐานของการพัฒนา .NET, รวมถึงการทำงานกับ streams, graphics paths, และการจัดการสี.

## นำเข้า Namespaces

ในโปรเจกต์ C# ของคุณ, ให้รวม namespaces ที่จำเป็นที่ส่วนต้นของไฟล์โค้ด:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

เริ่มต้นด้วยการระบุพาธไปยังไดเรกทอรีเอกสารของคุณ. นี่คือที่ตั้งที่ไฟล์ PS ของคุณจะถูกบันทึก.

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง Output Stream สำหรับเอกสาร PostScript

สร้าง output stream สำหรับเอกสาร PostScript โดยใช้คลาส `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## ขั้นตอนที่ 3: สร้าง Save Options และเอกสาร PS

สร้าง save options ขนาด A4 และเริ่มต้นเอกสาร PS ใหม่ที่มี 1 หน้า.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 4: กำหนดขนาดสี่เหลี่ยม

ระบุขนาดและตำแหน่งของสี่เหลี่ยมที่ gradient แนวตั้งจะถูกนำไปใช้.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## ขั้นตอนที่ 5: สร้าง Graphics Path

สร้าง graphics path จากสี่เหลี่ยมที่กำหนด.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## ขั้นตอนที่ 6: กำหนดสี Interpolation

สร้างอาเรย์ของสี interpolation และตำแหน่งสำหรับ gradient.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## ขั้นตอนที่ 7: สร้าง Linear Gradient Brush

สร้าง linear gradient brush โดยใช้สี่เหลี่ยมเป็นขอบเขต, สีเริ่มต้นและสีสิ้นสุด.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## ขั้นตอนที่ 8: ตั้งค่า Brush Transform

กำหนดการแปลงสำหรับแปรง, ทำให้ส่วนสเกล X และ Y ตรงกับความกว้างและความสูงของสี่เหลี่ยม.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## ขั้นตอนที่ 9: ตั้งค่า Paint และเติมสี่เหลี่ยม

ตั้งค่า paint สำหรับเอกสาร, และ **fill rectangle with gradient** โดยใช้ path ที่กำหนดไว้ก่อนหน้า.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## ขั้นตอนที่ 10: ปิดหน้าเอกสารปัจจุบันและบันทึกเอกสาร

ปิดหน้าปัจจุบันและบันทึกเอกสาร PostScript.

```csharp
document.ClosePage();
document.Save();
```

ยินดีด้วย! คุณได้ **เพิ่ม gradient แนวตั้งในเอกสาร PostScript** อย่างสำเร็จโดยใช้ **C# linear gradient brush** กับ Aspose.Page for .NET. ทดลองปรับพารามิเตอร์และสีต่าง ๆ เพื่อสร้างเอฟเฟกต์ภาพที่หลากหลายในเอกสารของคุณ.

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| Gradient ปรากฏเป็นแนวนอน | การหมุนแปรงไม่ได้ถูกนำไปใช้ | ตรวจสอบให้แน่ใจว่าได้เรียก `brushTransform.Rotate(90);` ก่อนกำหนดค่าให้ `brush.Transform`. |
| สีดูจาง | output stream ความละเอียดต่ำ | ใช้ `PsSaveOptions` ความละเอียดสูงขึ้นหรือเพิ่มขนาดเอกสาร. |
| ไฟล์ผลลัพธ์ว่าง | Stream ไม่ได้ flush | ตรวจสอบว่าได้เรียก `document.Save();` นอกบล็อก `using`. |

## คำถามที่พบบ่อย

**Q1: สามารถใช้ gradient หลายชุดในพื้นที่ต่าง ๆ ของเอกสารเดียวกันได้หรือไม่?**  
A: ได้, คุณสามารถทำได้. เพียงทำซ้ำขั้นตอนสำหรับแต่ละพื้นที่พร้อมขนาดและโทนสีที่กำหนด.

**Q2: จะรวมโค้ดนี้เข้ากับโปรเจกต์ .NET ที่มีอยู่ของฉันอย่างไร?**  
A: คัดลอกและวางโค้ดลงในไฟล์โปรเจกต์ของคุณและตรวจสอบว่าคุณได้อ้างอิงไลบรารี Aspose.Page แล้ว.

**Q3: มีประเภท gradient อื่น ๆ ที่ Aspose.Page for .NET รองรับหรือไม่?**  
A: Aspose.Page รองรับประเภท gradient ต่าง ๆ รวมถึง radial และ path gradients. ดูเอกสารสำหรับรายละเอียดเพิ่มเติม.

**Q4: สามารถใช้ Aspose.Page สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ได้, คุณสามารถเยี่ยมชม [ที่นี่](https://purchase.aspose.com/buy) เพื่อสำรวจตัวเลือกการให้ลิขสิทธิ์.

**Q5: มีฟอรั่มชุมชนสำหรับ Aspose.Page ที่ฉันสามารถขอความช่วยเหลือได้หรือไม่?**  
A: แน่นอน! ไปที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับนักพัฒนาคนอื่นและรับความช่วยเหลือ.

---

**อัปเดตล่าสุด:** 2026-02-25  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}