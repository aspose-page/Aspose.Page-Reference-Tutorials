---
date: 2026-04-03
description: เรียนรู้วิธีเพิ่มสี่เหลี่ยมโปร่งใสและใช้ Grid Visual Brush ใน .NET ด้วย
  Aspose.Page เพื่อสร้างเอกสาร XPS ที่น่าตื่นตาตื่นใจ
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: ใช้แปรงภาพกริด
second_title: Aspose.Page .NET API
title: เพิ่มสี่เหลี่ยมโปร่งใสด้วย Grid Visual Brush (.NET)
url: /th/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มสี่เหลี่ยมโปร่งใสโดยใช้ Grid Visual Brush (.NET)

## บทนำ

หากคุณกำลังมองหา **การเพิ่มสี่เหลี่ยมโปร่งใส** ลงในเอกสาร XPS พร้อมกับใช้ Grid Visual Brush ที่มีสไตล์ คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะอธิบายขั้นตอนที่จำเป็นด้วย Aspose.Page for .NET เพื่อให้คุณสร้างเอกสารที่มีภาพสวยงามและโดดเด่นได้ เมื่อเสร็จคุณจะได้ตัวอย่างที่ทำงานได้สมบูรณ์ซึ่งแสดงเทคนิคทั้งสองในกระบวนการที่ง่ายต่อการทำตาม

## คำตอบอย่างรวดเร็ว
- **สี่เหลี่ยมโปร่งใสทำหน้าที่อะไร?** มันเพิ่มชั้นครึ่งโปร่งที่ทำให้เนื้อหาพื้นหลังมองเห็นได้ผ่าน  
- **API ใดสร้าง brush?** `XpsDocument.CreateVisualBrush` สร้าง Grid Visual Brush  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ใช้เวลานานเท่าไหร่ในการทำตาม?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน  

## สี่เหลี่ยมโปร่งใสใน XPS คืออะไร
สี่เหลี่ยมโปร่งใสคือรูปทรงที่สีเติมมีค่าอัลฟา (alpha) น้อยกว่า 1.0 ทำให้กราฟิกพื้นหลังมองเห็นได้บางส่วน เหมาะสำหรับการไฮไลท์ส่วนต่าง ๆ โดยไม่บังพื้นหลังอย่างเต็มที่

## ทำไมต้องใช้ Grid Visual Brush
Grid Visual Brush ช่วยให้คุณทำการเรียงภาพเวกเตอร์ขนาดเล็กเป็นกระเบื้องบนพื้นที่ขนาดใหญ่ สร้างลวดลายเช่นกริด, Hatch หรือเทกซ์เจอร์ที่กำหนดเอง การผสานกับสี่เหลี่ยมโปร่งใสทำให้ได้เอฟเฟกต์ภาพหลายชั้นที่เบาและไม่ขึ้นกับความละเอียด

## ข้อกำหนดเบื้องต้น
ก่อนที่จะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:
- **Aspose.Page for .NET** – คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/net/).
- สภาพแวดล้อมการพัฒนา .NET (Visual Studio, VS Code หรือ IDE ใด ๆ ที่คุณชอบ).
- โฟลเดอร์ที่ไฟล์ XPS ที่สร้างขึ้นจะถูกบันทึก.

## นำเข้า Namespaces
ในไฟล์ C# ของคุณ ให้นำเข้า Namespaces ที่จำเป็น:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

ตอนนี้เราจะแบ่งโซลูชันเป็นขั้นตอนที่ชัดเจนและเป็นลำดับเลข

## ขั้นตอนที่ 1: เริ่มต้น XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

เราเริ่มด้วยการสร้างอินสแตนซ์ `XpsDocument` ซึ่งจะเก็บการดำเนินการวาดทั้งหมดต่อไป

## ขั้นตอนที่ 2: สร้าง Magenta Grid Geometry

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Geometry นี้กำหนดโครงร่างของกริดที่ visual brush จะเติม

## ขั้นตอนที่ 3: ออกแบบ Magenta Grid VisualBrush

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

ที่นี่เราวาดแผ่นสีมะกอกขนาดเล็กที่จะทำซ้ำทั่วกริด

## ขั้นตอนที่ 4: ใช้ VisualBrush กับ Grid

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

การเรียก `CreateVisualBrush` เชื่อมแผ่นสีมะกอกกับ grid geometry และเปิดใช้งานการทำเป็นกระเบื้อง

## ขั้นตอนที่ 5: เพิ่ม Grid ลงใน Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

เราวางกริดที่ทำเป็นกระเบื้องลงบน canvas และใช้การแปลงการย้ายตำแหน่งเพื่อให้ปรากฏที่ตำแหน่งที่ต้องการ

## ขั้นตอนที่ 6: เพิ่มสี่เหลี่ยมโปร่งใส

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

ในขั้นตอนนี้เราจะ **เพิ่มสี่เหลี่ยมโปร่งใส** (รูปสีแดงที่มี `Opacity = 0.7f`). ปรับค่าความโปร่งใสเพื่อควบคุมระดับการมองทะลุของสี่เหลี่ยม

## ขั้นตอนที่ 7: บันทึกเอกสาร

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

ไฟล์ XPS จะถูกเขียนไปยังโฟลเดอร์ที่คุณระบุไว้ก่อนหน้า

## กรณีการใช้งานทั่วไป
- **การไฮไลท์รายงาน:** วางสี่เหลี่ยมครึ่งโปร่งเหนือเพื่อเน้นแผนภูมิหรือ ตาราง.  
- **เอฟเฟกต์ลายน้ำ:** ผสานกริดที่ทำเป็นกระเบื้องกับการซ้อนทับโปร่งใสเพื่อสร้างแบรนด์อย่างละเอียดอ่อน.  
- **PDF/XPS เชิงโต้ตอบ:** ใช้ลวดลายเป็นพื้นหลังของฟิลด์ฟอร์มขณะยังคงทำให้ UI อ่านได้.

## เคล็ดลับการแก้ไขปัญหา
- **Opacity ไม่แสดง?** ตรวจสอบให้แน่ใจว่าโปรแกรมดูของคุณรองรับความโปร่งใสของ XPS; โปรแกรมดูเก่าอาจละเลยคุณสมบัติ `Opacity`.  
- **ขนาดกระเบื้องไม่ถูกต้อง?** ตรวจสอบให้แน่ใจว่า source rectangle (`new RectangleF(0f, 0f, 10f, 10f)`) มีขนาดตรงกับแผ่นเวกเตอร์.  
- **ไฟล์ไม่บันทึก?** ตรวจสอบอีกครั้งว่า `dataDir` ชี้ไปยังไดเรกทอรีที่มีอยู่และสามารถเขียนได้.

## คำถามที่พบบ่อย
**ถาม: ฉันสามารถใช้ Aspose.Page for .NET ในแอปพลิเคชันเว็บและเดสก์ท็อปได้หรือไม่?**  
ตอบ: ใช่, ไลบรารีทำงานได้กับทุกประเภทแอปพลิเคชัน .NET.

**ถาม: มีเวอร์ชันทดลองให้ใช้ก่อนซื้อหรือไม่?**  
ตอบ: แน่นอน, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีได้จาก [ที่นี่](https://releases.aspose.com/).

**ถาม: ฉันจะหาแหล่งสนับสนุนเพิ่มเติมหรือการสนทนาชุมชนได้จากที่ไหน?**  
ตอบ: เยี่ยมชม [Aspose.Page Forum](https://forum.aspose.com/c/page/39) เพื่อรับความช่วยเหลือจากชุมชนและวิศวกรของ Aspose.

**ถาม: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับการประเมินผลได้อย่างไร?**  
ตอบ: คุณสามารถรับไลเซนส์ชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/).

**ถาม: มีเอกสารอื่น ๆ สำหรับ Aspose.Page for .NET ที่สามารถเข้าถึงได้หรือไม่?**  
ตอบ: สำรวจเอกสารที่ครอบคลุมได้จาก [ที่นี่](https://reference.aspose.com/page/net/).

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}