---
title: ใช้ Texture Tiling Pattern กับ PostScript (PS) ด้วย Aspose.Page
linktitle: ใช้รูปแบบการปูกระเบื้องพื้นผิวกับ PostScript (PS)
second_title: Aspose.Page .NET API
description: ปรับปรุงเอกสาร PostScript (PS) ของคุณด้วยรูปแบบการเรียงต่อกันของพื้นผิวโดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อสัมผัสความสร้างสรรค์
type: docs
weight: 10
url: /th/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนแบบทีละขั้นตอนเกี่ยวกับวิธีใช้รูปแบบการเรียงพื้นผิวกับเอกสาร PostScript (PS) โดยใช้ Aspose.Page สำหรับ .NET Aspose.Page เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณทำงานกับเอกสารได้หลายรูปแบบ และในบทช่วยสอนนี้ เราจะสำรวจวิธีปรับปรุงเอกสาร PS ของคุณโดยการเพิ่มรูปแบบการเรียงต่อกันของพื้นผิว

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- [วิชวลสตูดิโอ](https://visualstudio.microsoft.com/) ติดตั้งบนเครื่องของคุณ
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
-  ดาวน์โหลดและติดตั้ง[Aspose.Page สำหรับไลบรารี .NET](https://releases.aspose.com/page/net/).
- ไฟล์รูปภาพสำหรับรูปแบบพื้นผิว (เช่น "TestTexture.bmp")

## นำเข้าเนมสเปซ

ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

เราจะแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการ

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
```

ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Document Directory" ด้วยเส้นทางที่คุณต้องการบันทึกเอกสาร PS ของคุณ

## ขั้นตอนที่ 2: สร้างสตรีมเอาท์พุตสำหรับเอกสาร PS

```csharp
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // สร้างตัวเลือกการบันทึกด้วยขนาด A4
    PsSaveOptions options = new PsSaveOptions();

    // สร้างเอกสาร PS 1 หน้าใหม่
    PsDocument document = new PsDocument(outPsStream, options, false);
```

ขั้นตอนนี้ตั้งค่าสตรีมเอาท์พุตสำหรับเอกสาร PS รวมถึงการกำหนดขนาดเอกสาร

## ขั้นตอนที่ 3: ใช้รูปแบบการปูกระเบื้องพื้นผิว

```csharp
// สร้างวัตถุบิตแมปจากไฟล์รูปภาพ
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // สร้างแปรงพื้นผิวจากภาพ
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //เพิ่มมาตราส่วนในทิศทาง X ให้กับรูปแบบ
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // ตั้งค่าแปรงพื้นผิวนี้เป็นสีปัจจุบัน
    document.SetPaint(brush);
}
```

ขั้นตอนนี้เกี่ยวข้องกับการสร้างแปรงพื้นผิวจากรูปภาพและตั้งค่าเป็นสีปัจจุบันสำหรับเอกสาร

## ขั้นตอนที่ 4: สร้างเส้นทางสี่เหลี่ยมผืนผ้าและเติม

```csharp
// สร้างเส้นทางรูปสี่เหลี่ยมผืนผ้า
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// เติมสี่เหลี่ยม
document.Fill(path);
```

ที่นี่ เรากำหนดเส้นทางรูปสี่เหลี่ยมผืนผ้าและเติมด้วยแปรงพื้นผิวที่ตั้งไว้ก่อนหน้านี้

## ขั้นตอนที่ 5: ตั้งค่า Stroke และ Draw

```csharp
// รับทาสีปัจจุบัน
Brush paint = document.GetPaint();

// ตั้งค่าจังหวะสีแดง
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// ขีดสี่เหลี่ยม
document.Draw(path);
```

ขั้นตอนนี้เกี่ยวข้องกับการตั้งค่าคุณสมบัติเส้นโครงร่างและการวาดรูปสี่เหลี่ยมที่มีโครงร่าง

## ขั้นตอนที่ 6: เติมและร่างข้อความด้วยรูปแบบพื้นผิว

```csharp
// เติมข้อความด้วยลวดลายพื้นผิว
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// ข้อความเค้าร่างที่มีลวดลายพื้นผิว
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

สุดท้ายนี้ เราจะเติมและจัดเค้าร่างข้อความด้วยรูปแบบพื้นผิว เพื่อเพิ่มความสวยงามให้กับเอกสารของคุณ

## ขั้นตอนที่ 7: บันทึกและปิดเอกสาร

```csharp
// ปิดหน้าปัจจุบัน
document.ClosePage();

// บันทึกเอกสาร
document.Save();
```

ตรวจสอบให้แน่ใจว่าได้ปิดหน้าปัจจุบันและบันทึกเอกสารเพื่อใช้การเปลี่ยนแปลง

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีใช้รูปแบบการเรียงต่อกันของพื้นผิวกับเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว ทดลองใช้รูปภาพและรูปแบบต่างๆ เพื่อปรับแต่งเอกสาร PS ของคุณเพิ่มเติม

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้รูปแบบภาพอื่นสำหรับรูปแบบพื้นผิวได้หรือไม่

A1: ใช่ Aspose.Page รองรับรูปแบบรูปภาพที่หลากหลาย ตรวจสอบความเข้ากันได้กับเอกสารประกอบของห้องสมุด

### คำถามที่ 2: Aspose.Page เข้ากันได้กับ .NET Core หรือไม่

A2: ใช่ Aspose.Page เข้ากันได้กับทั้ง .NET Framework และ .NET Core

### คำถามที่ 3: ฉันจะปรับขนาดของสี่เหลี่ยมผืนผ้าที่มีพื้นผิวได้อย่างไร

 A3: ปรับเปลี่ยนขนาดใน`RectangleF` พารามิเตอร์ระหว่างการสร้างเส้นทาง

### คำถามที่ 4: ฉันสามารถเพิ่มรูปแบบพื้นผิวหลายรูปแบบลงในเอกสารเดียวได้หรือไม่

A4: ได้ คุณสามารถทำซ้ำขั้นตอนนี้ด้วยรูปภาพและเส้นทางที่แตกต่างกันได้

### คำถามที่ 5: ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนได้จากที่ไหน

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนชุมชนและการสำรวจ[เอกสารประกอบ](https://reference.aspose.com/page/net/).
