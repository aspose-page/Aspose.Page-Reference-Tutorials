---
date: 2026-03-29
description: เรียนรู้วิธีใช้แปรงไลเนียร์กราเดียนต์ใน C# เพื่อสร้างความโปร่งใสเทียมใน
  PostScript ด้วย Aspose.Page สำหรับ .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: แปรงไลเนียร์เกรเดียนท์ C# สำหรับการทำเทียมความโปร่งใสใน PS
url: /th/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปรงไลเนียร์กราเดียนท์ C# สำหรับการทำให้โปร่งใสเทียมใน PostScript (PS)

## บทนำ

หากคุณต้องการเพิ่มเอฟเฟกต์การมองผ่านอย่างละเอียดให้กับไฟล์ PostScript (PS) ของคุณ, **linear gradient brush C#** คือเครื่องมือที่สมบูรณ์แบบ Aspose.Page for .NET ทำให้การวาดสี่เหลี่ยมด้วยการเติมกราเดียนท์แบบ opaque และ translucent เป็นเรื่องง่าย, ให้เอกสารของคุณดูทันสมัยและมีเลเยอร์หลายชั้น ในบทเรียนนี้เราจะอธิบายขั้นตอนที่จำเป็นเพื่อสร้างการทำให้โปร่งใสเทียมโดยใช้ linear gradient brush ใน C#.

## คำตอบด่วน
- **ไลบรารีใดที่ให้บริการ linear gradient brush?** Aspose.Page for .NET
- **คลาสกราฟิกใดสร้างกราเดียนท์?** `LinearGradientBrush`
- **ฉันสามารถควบคุมความทึบของแต่ละสีได้หรือไม่?** Yes, using `Color.FromArgb(alpha, …)`
- **ต้องใช้ไลเซนส์สำหรับการผลิตหรือไม่?** A valid Aspose.Page license is required
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Linear Gradient Brush C# คืออะไร?

`LinearGradientBrush` คืออ็อบเจ็กต์ GDI+ ที่วาดการเปลี่ยนแปลงสีอย่างราบรื่นระหว่างสองสีตามเส้นตรง เมื่อคุณระบุค่าแอลฟา (0‑255) สำหรับแต่ละสี, คุณสามารถสร้างกราเดียนท์แบบ translucent — ซึ่งเป็นสิ่งที่เราต้องการสำหรับการทำให้โปร่งใสเทียมใน PostScript.

## ทำไมต้องใช้ Linear Gradient Brush C# สำหรับการทำให้โปร่งใสเทียม?

- **การควบคุมความทึบแบบละเอียด:** ปรับค่าแอลฟาของแต่ละสีเพื่อให้ได้ระดับการมองผ่านที่ต้องการ.  
- **การเรนเดอร์ที่ไม่ขึ้นกับอุปกรณ์:** แปรงทำงานเช่นเดียวกันบนหน้าจอ, PDF, EPS, และเอาต์พุต PS.  
- **API ที่ง่าย:** เพียงไม่กี่บรรทัดของโค้ด C# สามารถสร้างเอฟเฟกต์ภาพระดับมืออาชีพ.

## ข้อกำหนดเบื้องต้น

ก่อนที่จะลงลึกในโค้ด, ตรวจสอบให้แน่ใจว่าคุณมี:

- ติดตั้ง Aspose.Page for .NET แล้ว. คุณสามารถดาวน์โหลดได้จาก [Aspose.Page documentation](https://reference.aspose.com/page/net/).
- โฟลเดอร์ที่สามารถเขียนได้สำหรับบันทึกเอกสาร PostScript ที่สร้างขึ้น.

เมื่อคุณมีเครื่องมือที่จำเป็นแล้ว, มาเริ่มสร้างสี่เหลี่ยมที่ทำให้โปร่งใสเทียมกันเถอะ.

## นำเข้า Namespaces

ก่อนที่เราจะเริ่ม, ให้นำเข้า namespaces ที่ประกอบด้วยคลาสที่เราจะใช้:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: สร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript

เราจะเริ่มด้วยการสร้างไฟล์สตรีมที่จะเก็บไฟล์ PS ที่ได้, จากนั้นทำการ initialise `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 2: สร้างสี่เหลี่ยมที่มีการเติมกราเดียนท์ **opaque**

ที่นี่เราสร้าง `LinearGradientBrush` ที่สีของมันเป็นแบบ opaque เต็มที่ (alpha = 255). สี่เหลี่ยมนี้จะทำหน้าที่เป็นเลเยอร์พื้นหลัง.

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

## ขั้นตอนที่ 3: สร้างสี่เหลี่ยมที่มีการเติมกราเดียนท์ **translucent**

ตอนนี้เราจะใช้ **linear gradient brush C#** ที่ค่าตัวแอลฟาน้อยกว่า 255 (เช่น 150 และ 50). สิ่งนี้ทำให้สี่เหลี่ยมมีการมองผ่านบางส่วน, สร้างเอฟเฟกต์การทำให้โปร่งใสเทียม.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## ขั้นตอนที่ 4: ปิดหน้าและบันทึกเอกสาร

สุดท้ายเราปิดหน้าและเขียนไฟล์ PS ลงดิสก์.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

โดยทำตามสี่ขั้นตอนนี้คุณสามารถผสานสี่เหลี่ยมแบบ opaque และ translucent อย่างราบรื่น, สร้างเอฟเฟกต์การทำให้โปร่งใสเทียมที่น่าเชื่อถือในเอาต์พุต PostScript ใด ๆ.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| สีปรากฏเป็น opaque ทั้งหมด | ค่าแอลฟาถูกตั้งเป็น 255 โดยบังเอิญ | ใช้ `Color.FromArgb(alpha, …)` โดยที่ `alpha` < 255 |
| กราเดียนท์ถูกยืดออกไม่ถูกต้อง | เมทริกซ์การแปลงไม่ถูกต้อง | ตรวจสอบพารามิเตอร์เมทริกซ์ให้ตรงกับขนาดสี่เหลี่ยม |
| ไฟล์เอาต์พุตว่างเปล่า | สตรีมไม่ได้ปิดหรือไม่ได้เรียก `Save()` | ตรวจสอบให้แน่ใจว่า `document.ClosePage()` และ `document.Save()` ถูกเรียกภายในบล็อก `using` |

## คำถามที่พบบ่อย

**Q: Aspose.Page รองรับทุกเวอร์ชันของ .NET หรือไม่?**  
A: Aspose.Page for .NET รองรับหลายเวอร์ชันของ .NET framework, ทำให้มีความยืดหยุ่นและง่ายต่อการรวมเข้ากับระบบ.

**Q: ฉันสามารถใช้ pseudo‑transparency กับรูปทรงอื่น ๆ นอกจากสี่เหลี่ยมได้หรือไม่?**  
A: ได้, หลักการเดียวกันสามารถนำไปใช้กับรูปทรงใด ๆ โดยปรับ `GraphicsPath` ให้เหมาะสม.

**Q: ฉันจะหา ตัวอย่างและเอกสารเพิ่มเติมได้จากที่ไหน?**  
A: สำรวจ [Aspose.Page documentation](https://reference.aspose.com/page/net/) เพื่อดูตัวอย่างที่ครอบคลุมและอ้างอิง API อย่างละเอียด.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Page หรือไม่?**  
A: มี, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.Page ได้จาก [this link](https://releases.aspose.com/).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page ได้อย่างไร?**  
A: เยี่ยมชม [this link](https://purchase.aspose.com/temporary-license/) เพื่อรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page.

**อัปเดตล่าสุด:** 2026-03-29  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}