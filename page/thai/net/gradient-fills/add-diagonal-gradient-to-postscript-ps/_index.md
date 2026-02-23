---
date: 2026-02-23
description: เรียนรู้วิธีเพิ่มไล่สีในไฟล์ PostScript, บันทึกไฟล์ PostScript ด้วยขนาดหน้า
  A4, และเติมไล่สีให้สี่เหลี่ยมโดยใช้ Aspose.Page สำหรับ .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: วิธีเพิ่มไล่สี – ไล่สีแนวทแยงใน PostScript (PS) ด้วย Aspose.Page .NET
url: /th/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม Gradient: Gradient แนวทแยงมุมใน PostScript (PS) ด้วย Aspose.Page .NET

## บทนำ

การเพิ่ม gradient แนวทแยงมุมลงในเอกสาร PostScript (PS) สามารถปรับปรุงความสวยงามของภาพได้อย่างมาก โดยเฉพาะเมื่อคุณต้องการเอฟเฟกต์ **how to add gradient** ในรายงานทางเทคนิค โบรชัวร์ หรือแอปพลิเคชันที่ใช้กราฟิกเป็นหลัก ในบทแนะนำนี้คุณจะได้เห็นขั้นตอนการเพิ่ม gradient ลงในไฟล์ PostScript ตั้งค่าขนาดหน้า A4 และเติมสี่เหลี่ยมด้วยการเปลี่ยนสีอย่างราบรื่นโดยใช้ Aspose.Page สำหรับ .NET

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.Page for .NET  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **ฉันสามารถเปลี่ยนทิศทางของ gradient ได้หรือไม่?** Yes – rotate the brush transform as shown in the code  
- **ฉันจะบันทึกผลลัพธ์อย่างไร?** Use `PsDocument.Save()` which writes a PostScript file to disk  
- **ต้องการใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** Yes, a commercial license unlocks full functionality  

## Gradient แนวทแยงมุมใน PostScript คืออะไร?

Gradient แนวทแยงมุมคือการเปลี่ยนสีเชิงเส้นที่วิ่งเป็นมุม (โดยทั่วไป 45°) ผ่านรูปทรง ใน PostScript สิ่งนี้ทำได้โดยการใช้ `LinearGradientBrush` พร้อมเมทริกซ์การแปลงที่กำหนดเองซึ่งหมุน ปรับขนาด และแปลตำแหน่ง gradient ให้ตรงกับสี่เหลี่ยมที่ต้องการ

## ทำไมต้องใช้ Aspose.Page สำหรับการเติม gradient?

Aspose.Page ทำให้ซับซ้อนของคำสั่ง PostScript ระดับต่ำเป็นนามธรรม ทำให้คุณสามารถทำงานกับออบเจ็กต์กราฟิก .NET ที่คุ้นเคย คุณสามารถสร้างการเติมที่ซับซ้อน ตั้งค่าขนาดหน้า และส่งออกโดยตรงเป็น **save PostScript file** โดยไม่ต้องจัดการกับไวยากรณ์ PS ดิบ

## ข้อกำหนดเบื้องต้น

- **Aspose.Page for .NET Library** – ดาวน์โหลดได้ที่ [here](https://releases.aspose.com/page/net/).  
- **Document Directory** – โฟลเดอร์ที่ไฟล์ `*.ps` ที่สร้างขึ้นจะถูกเขียนลงไป

ตอนนี้เราได้ครอบคลุมพื้นฐานแล้ว ให้เราดำเนินการตามขั้นตอนการทำงานทีละขั้นตอน

## นำเข้า Namespaces

ขั้นแรก ให้นำเข้า namespaces ที่ให้คุณเข้าถึงอุปกรณ์ EPS, ยูทิลิตี้การวาด, และคลาส I/O

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: สร้าง Output Stream สำหรับเอกสาร PostScript (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## ขั้นตอนที่ 2: ตั้งค่าขนาดหน้า A4 (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## ขั้นตอนที่ 3: สร้าง PS Document หน้าเดียวใหม่

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 4: กำหนดพารามิเตอร์ของสี่เหลี่ยม

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## ขั้นตอนที่ 5: สร้าง Graphics Path

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## ขั้นตอนที่ 6: สร้าง Linear Gradient Brush (เติม Gradient ให้สี่เหลี่ยม)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## ขั้นตอนที่ 7: สร้าง Transform สำหรับ Brush

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## ขั้นตอนที่ 8: ใช้การแปลงกับ Brush (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## ขั้นตอนที่ 9: ตั้งค่า Transform ให้ Brush

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## ขั้นตอนที่ 10: ตั้งค่า Paint และเติมสี่เหลี่ยม

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## ขั้นตอนที่ 11: ปิดหน้าปัจจุบัน

```csharp
	//Close current page
	document.ClosePage();
```

## ขั้นตอนที่ 12: บันทึกเอกสาร (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## วิธีบันทึกไฟล์ PostScript

`PsDocument.Save()` จะเขียนเนื้อหา PostScript ที่สมบูรณ์ลงในสตรีมที่คุณเปิดใน **Step 1** หลังจากบล็อก `using` สิ้นสุด ไฟล์ `DiagonaGradient_outPS.ps` จะพร้อมใช้งานในไดเรกทอรีที่คุณระบุ

## กรณีการใช้งานทั่วไป

- **Technical documentation** ที่ต้องการเงาพื้นหลังแบบละเอียดอ่อน.  
- **Marketing brochures** ที่ gradient แนวทแยงมุมเพิ่มลุคทันสมัย.  
- **Automated report generators** ที่สร้างไฟล์ PS ที่พิมพ์ได้แบบอัตโนมัติ.

## การแก้ไขปัญหาและเคล็ดลับ

- **Incorrect colors** – ตรวจสอบค่า ARGB ที่ส่งให้ `LinearGradientBrush` อีกครั้ง.  
- **Gradient not visible** – ตรวจสอบว่าเมทริกซ์การแปลงหมุนและปรับขนาดอย่างถูกต้อง; คำสั่ง `Rotate(-45)` ตั้งมุมแนวทแยง.  
- **File not created** – ยืนยันว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน.

## คำถามที่พบบ่อย

**Q: Aspose.Page รองรับทุก .NET framework หรือไม่?**  
A: Aspose.Page รองรับช่วงเวอร์ชัน .NET ที่กว้าง ตั้งแต่ .NET Framework 4.5+ ถึง .NET 6+ เพื่อให้เข้ากันได้อย่างกว้างขวาง  

**Q: ฉันสามารถปรับแต่งสี gradient ใน Aspose.Page ได้หรือไม่?**  
A: ได้ คุณสามารถระบุสี ARGB ใดก็ได้เมื่อสร้าง `LinearGradientBrush` ทำให้คุณควบคุมสีเริ่มต้นและสิ้นสุดได้อย่างเต็มที่  

**Q: มีเวอร์ชันทดลองของ Aspose.Page หรือไม่?**  
A: มี คุณสามารถสำรวจคุณสมบัติของ Aspose.Page ได้โดยดาวน์โหลดเวอร์ชันทดลองจาก [here](https://releases.aspose.com/).  

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร?**  
A: รับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้จาก [here](https://purchase.aspose.com/temporary-license/) เพื่อเปิดใช้งานความสามารถเพิ่มเติมในช่วงการประเมิน  

**Q: ฉันจะหาแหล่งสนับสนุนจากชุมชนสำหรับ Aspose.Page ได้จากที่ไหน?**  
A: เข้าร่วมกับชุมชน Aspose.Page ใน [forum](https://forum.aspose.com/c/page/39) เพื่อรับความช่วยเหลือและการสนทนา  

---

**อัปเดตล่าสุด:** 2026-02-23  
**ทดสอบด้วย:** Aspose.Page for .NET (latest stable release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}