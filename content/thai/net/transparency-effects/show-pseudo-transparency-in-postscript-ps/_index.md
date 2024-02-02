---
title: แสดงความโปร่งใสหลอกใน PostScript (PS) ด้วย Aspose.Page
linktitle: แสดงความโปร่งใสหลอกใน PostScript (PS)
second_title: Aspose.Page .NET API
description: สำรวจพลังของความโปร่งใสหลอกใน PostScript ด้วย Aspose.Page สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อให้ได้เอกสารที่สวยงามน่าทึ่ง
type: docs
weight: 13
url: /th/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## การแนะนำ

คุณต้องการปรับปรุงรูปลักษณ์ที่สวยงามของเอกสาร PostScript (PS) ของคุณโดยผสมผสานความโปร่งใสหลอกเข้าด้วยกันหรือไม่? Aspose.Page สำหรับ .NET มอบโซลูชันอันทรงพลังเพื่อให้บรรลุผลนี้ได้อย่างง่ายดาย ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการแสดงความโปร่งใสหลอกใน PostScript โดยใช้ Aspose.Page

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- Aspose.Page สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เอกสาร Aspose.Page](https://reference.aspose.com/page/net/).

- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีเพื่อจัดเก็บเอกสาร PostScript ของคุณ

ตอนนี้คุณมีเครื่องมือที่จำเป็นในคลังแสงแล้ว มาดูวิธีแสดงความโปร่งใสหลอกใน PostScript โดยใช้ Aspose.Page กันดีกว่า

## นำเข้าเนมสเปซ

ก่อนที่จะเจาะลึกตัวอย่าง ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็น:

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
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//สร้างตัวเลือกการบันทึกด้วยขนาด A4
	PsSaveOptions options = new PsSaveOptions();

	// สร้างเอกสาร PS 1 หน้าใหม่
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 2: สร้างสี่เหลี่ยมผืนผ้าด้วยการเติมไล่ระดับสีทึบแสง

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## ขั้นตอนที่ 3: สร้างสี่เหลี่ยมผืนผ้าด้วยการเติมไล่ระดับสีแบบโปร่งแสง

```csharp
	offsetX = 350;

	//สร้างเส้นทางกราฟิกจากสี่เหลี่ยมแรก
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//สร้างสีแปรงไล่ระดับสีเชิงเส้นซึ่งความโปร่งใสไม่ใช่ 255 แต่เป็น 150 และ 50 ดังนั้นจึงโปร่งแสง
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## ขั้นตอนที่ 4: ปิดหน้าปัจจุบันและบันทึกเอกสาร

```csharp
	document.ClosePage();
	document.Save();
}
// สิ้นสุด:1
```

ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถรวมความโปร่งใสเสมือนเข้ากับเอกสาร PostScript ของคุณได้อย่างราบรื่นโดยใช้ Aspose.Page สำหรับ .NET

## บทสรุป

โดยสรุป Aspose.Page สำหรับ .NET นำเสนอวิธีที่ตรงไปตรงมาและมีประสิทธิภาพในการปรับปรุงองค์ประกอบภาพของเอกสาร PostScript ของคุณ ขั้นตอนที่อธิบายไว้ข้างต้นเป็นแนวทางที่ชัดเจนสำหรับการผสมผสานความโปร่งใสหลอกๆ เข้าด้วยกัน ซึ่งช่วยให้คุณสร้างผลงานที่ดูน่าทึ่งได้

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page เข้ากันได้กับ .NET ทุกเวอร์ชันหรือไม่

คำตอบ 1: Aspose.Page สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET เวอร์ชันต่างๆ ทำให้มั่นใจได้ถึงความยืดหยุ่นและความสะดวกในการบูรณาการ

### คำถามที่ 2: ฉันสามารถใช้ความโปร่งใสหลอกกับรูปร่างอื่นนอกเหนือจากสี่เหลี่ยมได้หรือไม่

A2: ได้ หลักการเดียวกันนี้สามารถนำไปใช้กับรูปร่างอื่นๆ ได้ด้วยการปรับ GraphicsPath ให้สอดคล้องกัน

### คำถามที่ 3: ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน

 A3: สำรวจ[เอกสาร Aspose.Page](https://reference.aspose.com/page/net/) สำหรับตัวอย่างที่ครอบคลุมและเอกสารประกอบโดยละเอียด

### คำถามที่ 4: Aspose.Page มีรุ่นทดลองใช้ฟรีหรือไม่

 A4: ได้ คุณสามารถเข้าถึง Aspose.Page รุ่นทดลองใช้ฟรีได้จาก[ลิงค์นี้](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร

 A5: เยี่ยมเลย[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page