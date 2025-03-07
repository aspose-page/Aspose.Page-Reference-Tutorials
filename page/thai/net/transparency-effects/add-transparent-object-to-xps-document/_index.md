---
title: เพิ่มวัตถุโปร่งใสให้กับเอกสาร XPS ด้วย Aspose.Page
linktitle: เพิ่มวัตถุโปร่งใสลงในเอกสาร XPS
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีเพิ่มวัตถุโปร่งใสลงในเอกสาร XPS ใน .NET โดยใช้ Aspose.Page เพิ่มความดึงดูดสายตาด้วยคำแนะนำทีละขั้นตอน
weight: 11
url: /th/net/transparency-effects/add-transparent-object-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มวัตถุโปร่งใสให้กับเอกสาร XPS ด้วย Aspose.Page

## การแนะนำ

ในบทช่วยสอนนี้ เราจะสำรวจวิธีเพิ่มวัตถุโปร่งใสให้กับเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET ความโปร่งใสในเอกสาร XPS สามารถเพิ่มความดึงดูดสายตาและถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ เราจะแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้ เพื่อให้เกิดความชัดเจนและเข้าใจง่าย

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Page สำหรับเอกสาร .NET](https://reference.aspose.com/page/net/).

## นำเข้าเนมสเปซ

ในการเริ่มต้น ให้รวมเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

ตอนนี้ เรามาดำเนินการตามคำแนะนำทีละขั้นตอนกันดีกว่า

## ขั้นตอนที่ 1: สร้างเอกสาร XPS ใหม่

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// สร้างเอกสาร XPS ใหม่
XpsDocument doc = new XpsDocument();
```

รหัสนี้เริ่มต้นเอกสาร XPS ใหม่โดยใช้ Aspose.Page สำหรับ .NET

## ขั้นตอนที่ 2: แสดงให้เห็นถึงความโปร่งใส

```csharp
// เพียงเพื่อแสดงความโปร่งใส
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

เส้นเหล่านี้สร้างเส้นทางโปร่งใสเพื่อแสดงเอฟเฟกต์ของความโปร่งใสในเอกสาร

## ขั้นตอนที่ 3: สร้างเส้นทางด้วยเรขาคณิตสี่เหลี่ยมผืนผ้าปิด

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

ที่นี่ เราสร้างเส้นทางที่มีรูปทรงสี่เหลี่ยมปิด ตั้งค่าแปรงทึบสีน้ำเงินเพื่อเติมเต็ม และเพิ่มลงในหน้าปัจจุบัน

## ขั้นตอนที่ 4: จัดการเส้นทางและสี

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

ขั้นตอนนี้สาธิตวิธีการจัดการเส้นทางและสีที่สามารถเปลี่ยนแปลงได้

## ขั้นตอนที่ 5: โคลนและแปลงเส้นทาง

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

โคลนและเปลี่ยนเส้นทาง เปลี่ยนสีของเส้นทางโคลน

## ขั้นตอนที่ 6: ทำซ้ำและแก้ไขเส้นทาง

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

ทำซ้ำขั้นตอนนี้โดยสร้างเส้นทางใหม่ตามเส้นทางก่อนหน้าพร้อมการแก้ไข

## ขั้นตอนที่ 7: จัดการความทึบ

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

สาธิตวิธีจัดการความทึบอย่างอิสระสำหรับเส้นทางต่างๆ

## ขั้นตอนที่ 8: บันทึกเอกสาร XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

สุดท้าย ให้บันทึกเอกสาร XPS ที่เป็นผลลัพธ์ด้วยความโปร่งใสที่ใช้

## บทสรุป

การเพิ่มวัตถุโปร่งใสให้กับเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET มอบวิธีการที่หลากหลายในการปรับปรุงการนำเสนอด้วยภาพ ทดลองกับรูปทรงเรขาคณิต สี และความทึบต่างๆ เพื่อให้ได้ผลลัพธ์ตามที่ต้องการ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ความโปร่งใสกับวัตถุใดๆ ในเอกสาร XPS ได้หรือไม่

A1: ได้ ความโปร่งใสสามารถนำไปใช้กับวัตถุต่างๆ เช่น เส้นทาง รูปร่าง และรูปภาพในเอกสาร XPS

### คำถามที่ 2: ฉันจะปรับความทึบขององค์ประกอบเฉพาะได้อย่างไร

A2: คุณสามารถตั้งค่าคุณสมบัติความทึบของ Fill หรือ Stroke เพื่อปรับความโปร่งใสขององค์ประกอบเฉพาะได้

### คำถามที่ 3: Aspose.Page เข้ากันได้กับ .NET Core หรือไม่

A3: ใช่ Aspose.Page รองรับ .NET Core ทำให้สามารถพัฒนาข้ามแพลตฟอร์มได้

### คำถามที่ 4: ฉันสามารถส่งออกเอกสาร XPS ไปเป็นรูปแบบอื่นโดยใช้ Aspose.Page ได้หรือไม่

A4: Aspose.Page มีฟังก์ชันในการส่งออกเอกสาร XPS เป็นรูปแบบต่างๆ รวมถึง PDF และรูปภาพ

### คำถามที่ 5: ฉันจะรับการสนับสนุนเพิ่มเติมและการสนทนาในชุมชนได้จากที่ไหน

 A5: สำหรับการสนับสนุนเพิ่มเติมและการสนทนาในชุมชน โปรดไปที่[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
