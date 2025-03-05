---
title: ใช้ Grid Visual Brush กับ Aspose.Page สำหรับ .NET
linktitle: ใช้ Grid Visual Brush
second_title: Aspose.Page .NET API
description: สำรวจโลกแบบไดนามิกของการประมวลผลเอกสารใน .NET ด้วย Aspose.Page เรียนรู้วิธีใช้ Grid Visual Brush เพื่อให้เอกสารดูสวยงามน่าทึ่ง
type: docs
weight: 10
url: /th/net/visual-brushes/apply-grid-visual-brush/
---
## การแนะนำ

ในโลกของการพัฒนา .NET Aspose.Page มีความโดดเด่นในฐานะเครื่องมืออันทรงพลังในการจัดการงานประมวลผลเอกสาร คุณสมบัติที่น่าสนใจประการหนึ่งที่มีให้คือความสามารถในการใช้ Grid Visual Brush ซึ่งนำมิติใหม่มาสู่เอกสารของคุณ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้งาน Magenta Grid Visual Brush ทีละขั้นตอนโดยใช้ Aspose.Page สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีและตั้งค่าในสภาพแวดล้อม .NET ของคุณ คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/net/).

- สภาพแวดล้อมการพัฒนา: เตรียมสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้ และความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

- Document Directory: สร้างไดเร็กทอรีสำหรับเอกสารของคุณที่จะบันทึกไฟล์ที่ประมวลผล

## นำเข้าเนมสเปซ

ในโค้ด C# ของคุณ คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อใช้คุณสมบัติ Aspose.Page อย่างมีประสิทธิภาพ:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: เริ่มต้น XpsDocument

```csharp
// เอ็กซ์สตาร์ท:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// สิ้นสุด:3
```

 ที่นี่เราสร้างอินสแตนซ์ของ`XpsDocument` เพื่อทำงานกับเอกสาร XPS

## ขั้นตอนที่ 2: สร้างเรขาคณิตกริดสีม่วงแดง

```csharp
// เอ็กซ์สตาร์ท:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// สิ้นสุด:4
```

ขั้นตอนนี้เกี่ยวข้องกับการสร้างเรขาคณิตของเส้นทางสำหรับตารางสีม่วงแดง

## ขั้นตอนที่ 3: ออกแบบ Magenta Grid VisualBrush

```csharp
// เอ็กซ์สตาร์ท:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// สิ้นสุด:5
```

ที่นี่ เราออกแบบลักษณะการมองเห็นของตารางสีม่วงแดงโดยใช้กราฟิกแบบเวกเตอร์

## ขั้นตอนที่ 4: ใช้ VisualBrush กับ Grid

```csharp
// เอ็กซ์สตาร์ท:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// สิ้นสุด:6
```

ใช้วิชวลบรัชกับเส้นทางกริด เพื่อให้แน่ใจว่าจะเรียงกันอย่างเหมาะสม

## ขั้นตอนที่ 5: เพิ่มตารางลงใน Canvas

```csharp
// เอ็กซ์สตาร์ท:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// สิ้นสุด:7
```

เพิ่มตารางลงบนผืนผ้าใบ โดยระบุการเปลี่ยนแปลงที่จำเป็น

## ขั้นตอนที่ 6: ปรับปรุงด้วยสี่เหลี่ยมสีแดง

```csharp
// เอ็กซ์สตาร์ท:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f;
// สิ้นสุด:8
```

เพิ่มความดึงดูดสายตาด้วยการเพิ่มสี่เหลี่ยมโปร่งใสสีแดง

## ขั้นตอนที่ 7: บันทึกเอกสาร

```csharp
// เอ็กซ์สตาร์ท:9
doc.Save(dataDir + "AddGrid_out.xps");
// สิ้นสุด:9
```

บันทึกเอกสาร XPS ที่เป็นผลลัพธ์ในไดเร็กทอรีที่คุณระบุ

## บทสรุป

ยินดีด้วย! คุณใช้ Grid Visual Brush กับเอกสารของคุณโดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว เทคนิคนี้สามารถปรับปรุงองค์ประกอบภาพของเอกสารของคุณได้อย่างมาก โดยมอบประสบการณ์ผู้ใช้แบบไดนามิกและน่าดึงดูด

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET ทั้งในแอปพลิเคชันบนเว็บและเดสก์ท็อปได้หรือไม่

A1: ใช่ Aspose.Page สำหรับ .NET มีความหลากหลายและสามารถใช้ได้ในแอปพลิเคชันประเภทต่างๆ

### คำถามที่ 2: มีเวอร์ชันทดลองใช้ก่อนซื้อหรือไม่

 A2: คุณสามารถเข้าถึงการทดลองใช้ฟรีได้อย่างแน่นอน[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 3: ฉันจะรับการสนับสนุนเพิ่มเติมหรือการสนทนาในชุมชนได้จากที่ไหน

 A3: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการอภิปรายและการสนับสนุน

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A4: คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: มีเอกสารอะไรบ้างสำหรับ Aspose.Page สำหรับ .NET

 A5: สำรวจเอกสารประกอบที่ครอบคลุม[ที่นี่](https://reference.aspose.com/page/net/).