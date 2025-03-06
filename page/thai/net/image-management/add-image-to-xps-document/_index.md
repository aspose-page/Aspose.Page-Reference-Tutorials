---
title: เพิ่มรูปภาพลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET
linktitle: เพิ่มรูปภาพลงในเอกสาร XPS
second_title: Aspose.Page .NET API
description: สำรวจการรวมรูปภาพเข้ากับเอกสาร XPS เข้ากับ Aspose.Page สำหรับ .NET ได้อย่างราบรื่น ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อประสบการณ์การพัฒนาที่ราบรื่น
weight: 11
url: /th/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรูปภาพลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

ในโลกของการพัฒนา .NET การรวมรูปภาพไว้ในเอกสาร XPS ถือเป็นข้อกำหนดทั่วไป Aspose.Page สำหรับ .NET ช่วยให้กระบวนการนี้ง่ายขึ้น โดยนำเสนอชุดเครื่องมืออันทรงพลังเพื่อจัดการและปรับปรุงเอกสาร XPS ได้อย่างง่ายดาย บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนในการเพิ่มรูปภาพลงในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Page สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[เอกสาร Aspose.Page .NET](https://reference.aspose.com/page/net/).

2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio

3. รูปภาพตัวอย่าง: มีไฟล์รูปภาพตัวอย่าง (เช่น "QL_logo_color.tif") ที่คุณต้องการเพิ่มลงในเอกสาร XPS

## นำเข้าเนมสเปซ

เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ .NET ของคุณ เนมสเปซเหล่านี้มีความสำคัญต่อการใช้คุณสมบัติที่ Aspose.Page สำหรับ .NET มอบให้

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

เริ่มต้นด้วยการระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ ขั้นตอนนี้ช่วยให้แน่ใจว่าโปรเจ็กต์ของคุณทราบตำแหน่งและบันทึกไฟล์

```csharp
// เอ็กซ์สตาร์ท:1
string dataDir = "Your Document Directory";
// สิ้นสุด:1
```

## ขั้นตอนที่ 2: สร้างเอกสาร XPS

สร้างเอกสาร XPS ใหม่โดยใช้ Aspose.Page สำหรับ .NET

```csharp
// เอ็กซ์สตาร์ท:1
XpsDocument doc = new XpsDocument();
// สิ้นสุด:1
```

## ขั้นตอนที่ 3: เพิ่มรูปภาพลงในเอกสาร XPS

ตอนนี้ มาเพิ่มรูปภาพลงในเอกสาร XPS กันดีกว่า ในตัวอย่างนี้ เราจะใช้รูปภาพตัวอย่างชื่อ "QL_logo_color.tif"

```csharp
// เอ็กซ์สตาร์ท:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// สิ้นสุด:1
```

## ขั้นตอนที่ 4: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์

บันทึกเอกสาร XPS ด้วยรูปภาพที่เพิ่ม

```csharp
// เอ็กซ์สตาร์ท:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// สิ้นสุด:1
```

ตอนนี้ คุณได้เพิ่มรูปภาพลงในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว!

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีใช้ประโยชน์จาก Aspose.Page สำหรับ .NET เพื่อรวมรูปภาพลงในเอกสาร XPS ได้อย่างราบรื่น คำแนะนำทีละขั้นตอนนี้ช่วยให้มั่นใจได้ถึงกระบวนการบูรณาการที่ราบรื่น ช่วยเพิ่มขีดความสามารถในการพัฒนา .NET ของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page สำหรับ .NET เข้ากันได้กับเวอร์ชันเฟรมเวิร์ก .NET ล่าสุดหรือไม่

 คำตอบ 1: Aspose.Page สำหรับ .NET ได้รับการออกแบบมาให้เข้ากันได้กับเวอร์ชันเฟรมเวิร์ก .NET ที่หลากหลาย รวมถึงเวอร์ชันล่าสุดด้วย อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/page/net/) สำหรับรายละเอียดเฉพาะ

### คำถามที่ 2: ฉันสามารถใช้ Aspose.Page สำหรับ .NET ทั้งในสภาพแวดล้อม Windows และ Linux ได้หรือไม่

ตอบ 2: ใช่ Aspose.Page สำหรับ .NET ไม่ขึ้นอยู่กับแพลตฟอร์ม ทำให้เหมาะสำหรับใช้ทั้งในสภาพแวดล้อม Windows และ Linux

### คำถามที่ 3: มีตัวเลือกสิทธิ์การใช้งานสำหรับ Aspose.Page สำหรับ .NET หรือไม่

 A3: ได้ คุณสามารถสำรวจตัวเลือกใบอนุญาตและทำการซื้อได้[ที่นี่](https://purchase.aspose.com/buy).

### คำถามที่ 4: Aspose.Page สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 A4: ได้ คุณสามารถลองใช้ Aspose.Page สำหรับ .NET ได้ฟรีโดยเข้าไปที่[ทดลองฟรี](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะขอความช่วยเหลือหรือมีส่วนร่วมกับชุมชนสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A5: เยี่ยมชม[Aspose.Page สำหรับฟอรัม .NET](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและรับการสนับสนุน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
