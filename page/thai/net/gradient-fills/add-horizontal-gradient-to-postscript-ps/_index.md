---
title: เพิ่มการไล่ระดับสีแนวนอนให้กับ PostScript (PS) ด้วย Aspose.Page
linktitle: เพิ่มการไล่ระดับสีแนวนอนให้กับ PostScript (PS)
second_title: Aspose.Page .NET API
description: ปรับปรุงเอกสาร PostScript ด้วยการไล่ระดับสีแนวนอนที่น่าทึ่งโดยใช้ Aspose.Page สำหรับ .NET ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเราเพื่อการใช้งานที่ราบรื่น
type: docs
weight: 12
url: /th/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
---
## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการเพิ่มการไล่ระดับสีแนวนอนให้กับเอกสาร PostScript (PS) โดยใช้ Aspose.Page สำหรับ .NET Aspose.Page เป็นไลบรารีอันทรงพลังที่อำนวยความสะดวกในการจัดการเอกสารในรูปแบบต่างๆ ช่วยให้นักพัฒนามีเครื่องมือที่จำเป็นในการสร้าง แก้ไข และเรนเดอร์เอกสารได้อย่างราบรื่น

ในบทช่วยสอนนี้ เราจะมุ่งเน้นไปที่การปรับปรุงเอกสาร PostScript ของคุณโดยผสมผสานการไล่ระดับสีแนวนอนที่สะดุดตา เราจะแนะนำคุณตลอดแต่ละขั้นตอนของกระบวนการ เพื่อให้มั่นใจว่าคุณมีความเข้าใจที่ชัดเจนในการใช้งาน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับไลบรารี .NET: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Page สำหรับ .NET ที่รวมอยู่ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้จาก[Aspose.Page สำหรับเอกสาร .NET](https://reference.aspose.com/page/net/).

- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีเพื่อจัดเก็บเอกสารของคุณ และแทนที่ "ไดเร็กทอรีเอกสารของคุณ" ในโค้ดที่ให้มาด้วยเส้นทางจริง

ตอนนี้ เรามาสำรวจวิธีการเพิ่มการไล่ระดับสีแนวนอนให้กับเอกสาร PostScript ทีละขั้นตอนกัน

## นำเข้าเนมสเปซ

ก่อนที่คุณจะเริ่มต้น จำเป็นต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันที่ Aspose.Page มอบให้ เพิ่มเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของโค้ดของคุณ:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // สร้างตัวเลือกการบันทึกด้วยขนาด A4
    PsSaveOptions options = new PsSaveOptions();

    // สร้างเอกสาร PS 1 หน้าใหม่
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 2: กำหนดสี่เหลี่ยมและสีไล่ระดับสี

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // สร้างเส้นทางกราฟิกจากสี่เหลี่ยมแรก
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //สร้างแปรงไล่ระดับสีเชิงเส้นโดยมีสี่เหลี่ยมเป็นสีขอบเขต เริ่มต้น และสิ้นสุด
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## ขั้นตอนที่ 3: ตั้งค่าการแปลงสำหรับแปรง

```csharp
    // สร้างการแปลงร่างสำหรับแปรง ส่วนประกอบมาตราส่วน X และ Y จะต้องเท่ากับความกว้างและความสูงของสี่เหลี่ยมผืนผ้าตามลำดับ
    // ส่วนประกอบการแปลเป็นการชดเชยของสี่เหลี่ยม
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // ตั้งค่าการแปลงร่าง
    brush.Transform = brushTransform;
```

## ขั้นตอนที่ 4: ตั้งค่าสีและเติมสี่เหลี่ยม

```csharp
    // เซ็ตสี
    document.SetPaint(brush);

    // เติมสี่เหลี่ยม
    document.Fill(path);
```

## ขั้นตอนที่ 5: กรอกข้อความด้วยการไล่ระดับสี

```csharp
    // เติมข้อความด้วยการไล่ระดับสี
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## ขั้นตอนที่ 6: ตั้งค่าเส้นขีดและข้อความโครงร่าง

```csharp
    // ตั้งค่าจังหวะปัจจุบัน
    document.SetStroke(new Pen(brush, 5));
    // ร่างข้อความด้วยการไล่ระดับสี
    document.OutlineText("ABC", font, 200, 400);
```

## ขั้นตอนที่ 7: ปิดหน้าปัจจุบันและบันทึกเอกสาร

```csharp
    // ปิดหน้าปัจจุบัน
    document.ClosePage();

    // บันทึกเอกสาร
    document.Save();
}
```

ยินดีด้วย! คุณได้เพิ่มการไล่ระดับสีแนวนอนลงในเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงกระบวนการปรับปรุงเอกสาร PostScript ของคุณด้วยการไล่ระดับสีแนวนอนโดยใช้ Aspose.Page สำหรับไลบรารี .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณจะได้รับข้อมูลเชิงลึกอันมีค่าในการใช้ประโยชน์จากเครื่องมืออันทรงพลังนี้สำหรับการจัดการเอกสาร

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้การไล่ระดับสีกับรูปร่างอื่นนอกเหนือจากสี่เหลี่ยมได้หรือไม่

 A1: ได้ คุณสามารถใช้การไล่ระดับสีกับรูปร่างต่างๆ ได้โดยใช้ Aspose.Page ปรับเปลี่ยน`GraphicsPath` สร้างสรรค์ให้เหมาะกับรูปร่างเฉพาะของคุณ

### คำถามที่ 2: ฉันจะเปลี่ยนสีไล่ระดับสีได้อย่างไร

 A2: ปรับ`Color.FromArgb` ค่าใน`LinearGradientBrush` การสร้างอินสแตนซ์เพื่อให้ได้สีไล่ระดับสีที่ต้องการ

### คำถามที่ 3: Aspose.Page เข้ากันได้กับรูปแบบเอกสารที่แตกต่างกันหรือไม่

A3: Aspose.Page รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง XPS, PS, PDF และอื่นๆ โปรดดูเอกสารประกอบสำหรับรายการที่ครอบคลุม

### คำถามที่ 4: ฉันสามารถใช้ Aspose.Page สำหรับโครงการเชิงพาณิชย์ได้หรือไม่

 A4: ใช่ Aspose.Page มาพร้อมกับตัวเลือกใบอนุญาตเชิงพาณิชย์ เยี่ยม[ที่นี่](https://purchase.aspose.com/buy) เพื่อดูรายละเอียด

### คำถามที่ 5: มีฟอรัมชุมชนสำหรับผู้ใช้ Aspose.Page หรือไม่

 A5: ใช่ เข้าร่วมชุมชน Aspose.Page ที่[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับผู้ใช้รายอื่นและขอความช่วยเหลือ