---
title: เพิ่มการไล่ระดับสีในแนวทแยงใน PostScript (PS) ด้วย Aspose.Page .NET
linktitle: เพิ่มการไล่ระดับสีในแนวทแยงใน PostScript (PS)
second_title: Aspose.Page .NET API
description: สำรวจความเรียบง่ายของการเพิ่มความไล่ระดับสีในแนวทแยงให้กับเอกสาร PostScript ใน .NET ด้วย Aspose.Page ยกระดับโครงการของคุณด้วยองค์ประกอบภาพแบบไดนามิก
type: docs
weight: 10
url: /th/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
---
## การแนะนำ

การเพิ่มการไล่ระดับสีในแนวทแยงให้กับเอกสาร PostScript (PS) สามารถทำให้โปรเจ็กต์ของคุณดึงดูดสายตาและความคิดสร้างสรรค์ได้ Aspose.Page สำหรับ .NET มอบโซลูชันที่ราบรื่นสำหรับการรวมคุณสมบัตินี้เข้ากับแอปพลิเคชันของคุณ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มการไล่ระดับสีในแนวทแยงให้กับเอกสาร PS โดยใช้ Aspose.Page ทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Page สำหรับ .NET Library แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).

- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีสำหรับเอกสารของคุณที่จะบันทึกไฟล์ PS เอาต์พุต

ตอนนี้เรามาดูคำแนะนำทีละขั้นตอนกันดีกว่า

## นำเข้าเนมสเปซ

ประการแรก ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ เนมสเปซเหล่านี้มีความสำคัญอย่างยิ่งต่อการทำงานกับฟังก์ชัน Aspose.Page

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: สร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript

```csharp
// เอ็กซ์สตาร์ท:1
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
//สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## ขั้นตอนที่ 2: สร้างตัวเลือกการบันทึกด้วยขนาด A4

```csharp
	//สร้างตัวเลือกการบันทึกด้วยขนาด A4
	PsSaveOptions options = new PsSaveOptions();
```

## ขั้นตอนที่ 3: สร้างเอกสาร PS แบบ 1 หน้าใหม่

```csharp
	// สร้างเอกสาร PS 1 หน้าใหม่
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 4: กำหนดพารามิเตอร์สี่เหลี่ยมผืนผ้า

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## ขั้นตอนที่ 5: สร้างเส้นทางกราฟิก

```csharp
	//สร้างเส้นทางกราฟิกจากสี่เหลี่ยมแรก
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## ขั้นตอนที่ 6: สร้างแปรงไล่ระดับสีเชิงเส้น

```csharp
	//สร้างแปรงไล่ระดับสีเชิงเส้นโดยมีสี่เหลี่ยมเป็นสีขอบเขต เริ่มต้น และสิ้นสุด
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## ขั้นตอนที่ 7: สร้างการแปลงสำหรับแปรง

```csharp
	//สร้างการแปลงร่างสำหรับแปรง ส่วนประกอบมาตราส่วน X และ Y จะต้องเท่ากับความกว้างและความสูงของสี่เหลี่ยมผืนผ้าตามลำดับ
	// ส่วนประกอบการแปลเป็นการชดเชยของสี่เหลี่ยม
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## ขั้นตอนที่ 8: ใช้การเปลี่ยนแปลงกับแปรง

```csharp
	//หมุนการไล่ระดับสี จากนั้นปรับขนาดและแปลเพื่อให้มองเห็นการเปลี่ยนสีในสี่เหลี่ยมที่ต้องการ
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## ขั้นตอนที่ 9: ตั้งค่าการแปลงเป็นแปรง

```csharp
	//ตั้งค่าการแปลงร่าง
	brush.Transform = brushTransform;
```

## ขั้นตอนที่ 10: ตั้งค่าสีและเติมสี่เหลี่ยม

```csharp
	//เซ็ตสี
	document.SetPaint(brush);

	//เติมสี่เหลี่ยม
	document.Fill(path);
```

## ขั้นตอนที่ 11: ปิดหน้าปัจจุบัน

```csharp
	//ปิดหน้าปัจจุบัน
	document.ClosePage();
```

## ขั้นตอนที่ 12: บันทึกเอกสาร

```csharp
	//บันทึกเอกสาร
	document.Save();
}
// สิ้นสุด:1
```

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะเพิ่มการไล่ระดับสีในแนวทแยงให้กับเอกสาร PostScript ได้สำเร็จโดยใช้ Aspose.Page สำหรับ .NET

## บทสรุป

การปรับปรุงเอกสาร PS ของคุณด้วยการไล่ระดับสีในแนวทแยงสามารถทำให้โปรเจ็กต์ของคุณดูน่าดึงดูดและมีชีวิตชีวา Aspose.Page สำหรับ .NET ช่วยให้กระบวนการนี้ง่ายขึ้น ช่วยให้นักพัฒนาสามารถรวมคุณสมบัตินี้เข้ากับแอปพลิเคชันของตนได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page เข้ากันได้กับกรอบงาน .NET ทั้งหมดหรือไม่

คำตอบ 1: Aspose.Page รองรับเฟรมเวิร์ก .NET ที่หลากหลาย ทำให้มั่นใจได้ถึงความเข้ากันได้กับสภาพแวดล้อมการพัฒนาที่หลากหลาย

### คำถามที่ 2: ฉันสามารถปรับแต่งสีไล่ระดับสีใน Aspose.Page ได้หรือไม่

A2: ใช่ Aspose.Page ให้ความยืดหยุ่นในการเลือกและปรับแต่งสีไล่ระดับสีตามความต้องการของโครงการของคุณ

### คำถามที่ 3: Aspose.Page มีเวอร์ชันทดลองใช้งานหรือไม่

 A3: ได้ คุณสามารถสำรวจฟีเจอร์ของ Aspose.Page ได้ด้วยการดาวน์โหลดเวอร์ชันทดลอง[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 4: ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร

 A4: รับใบอนุญาตชั่วคราวสำหรับ Aspose.Page[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อปลดล็อคคุณสมบัติเพิ่มเติม

### คำถามที่ 5: ฉันจะหาการสนับสนุนชุมชนสำหรับ Aspose.Page ได้ที่ไหน

 A5: มีส่วนร่วมกับชุมชน Aspose.Page บน[ฟอรั่ม](https://forum.aspose.com/c/page/39) เพื่อขอความช่วยเหลือและหารือ