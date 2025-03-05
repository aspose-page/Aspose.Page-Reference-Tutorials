---
title: เพิ่มข้อความลงในเอกสาร PostScript (PS) ด้วย Aspose.Page
linktitle: เพิ่มข้อความลงในเอกสาร PostScript (PS)
second_title: Aspose.Page .NET API
description: เสริมทักษะการพัฒนา .NET ของคุณโดยการเรียนรู้การเพิ่มข้อความลงในเอกสาร PostScript (PS) โดยใช้ Aspose.Page สำรวจตัวอย่างทีละขั้นตอนและปลดปล่อยพลังของการจัดการเอกสาร
type: docs
weight: 10
url: /th/net/text-manipulation/add-text-to-postscript-ps-document/
---
## การแนะนำ

ในโลกแบบไดนามิกของการพัฒนา .NET การจัดการและการปรับปรุงเอกสาร PostScript (PS) ถือเป็นข้อกำหนดทั่วไป Aspose.Page สำหรับ .NET มีชุดเครื่องมืออันทรงพลังเพื่อเพิ่มข้อความลงในเอกสาร PS ของคุณได้อย่างง่ายดาย บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการ เพื่อให้มั่นใจว่าคุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับโปรเจ็กต์ของคุณได้อย่างราบรื่น

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Page ที่รวมอยู่ในโปรเจ็กต์ .NET ของคุณ คุณสามารถดาวน์โหลดได้จาก[เอกสาร Aspose.Page .NET](https://reference.aspose.com/page/net/).

- Document Directory: ตั้งค่าไดเร็กทอรีที่จะจัดเก็บเอกสารของคุณ ซึ่งจะเรียกว่า "ไดเรกทอรีเอกสารของคุณ" ในตัวอย่าง

- โฟลเดอร์แบบอักษร: สร้างโฟลเดอร์เพื่อจัดเก็บแบบอักษรที่กำหนดเอง ซึ่งเรียกว่า "ไดเรกทอรีเอกสารของคุณ" ในตัวอย่าง

## นำเข้าเนมสเปซ

ก่อนที่จะเริ่มต้น อย่าลืมรวมเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: สร้างสตรีมเอาท์พุตสำหรับเอกสาร PS

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 2: กรอกข้อความด้วยแบบอักษรของระบบ

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## ขั้นตอนที่ 3: กรอกข้อความด้วยแบบอักษรที่กำหนดเอง

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## ขั้นตอนที่ 4: ร่างข้อความด้วยแบบอักษรของระบบ

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## ขั้นตอนที่ 5: ร่างข้อความด้วยแบบอักษรที่กำหนดเอง

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## ขั้นตอนที่ 6: ปิดและบันทึก

```csharp
document.ClosePage();
document.Save();
}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มข้อความลงในเอกสาร PostScript (PS) โดยใช้ Aspose.Page สำหรับ .NET เรียบร้อยแล้ว รู้สึกอิสระที่จะสำรวจคุณสมบัติเพิ่มเติมและปรับปรุงความสามารถในการจัดการเอกสารของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page กับไลบรารี .NET อื่นๆ ได้หรือไม่

ตอบ 1: ใช่ Aspose.Page ทำงานร่วมกับไลบรารี .NET อื่นๆ ได้อย่างราบรื่น ทำให้เกิดสภาพแวดล้อมที่หลากหลายสำหรับการจัดการเอกสาร

### คำถามที่ 2: แบบอักษรแบบกำหนดเองจำเป็นสำหรับกระบวนการนี้หรือไม่

คำตอบ 2: แม้ว่าคุณสามารถใช้แบบอักษรของระบบได้ แต่การรวมแบบอักษรแบบกำหนดเองเข้าด้วยกันจะช่วยให้มีความยืดหยุ่นและมีตัวเลือกการออกแบบมากขึ้น

### คำถามที่ 3: Aspose.Page เหมาะสำหรับการประมวลผลเอกสารขนาดใหญ่หรือไม่

A3: แน่นอน! Aspose.Page ได้รับการออกแบบมาเพื่อรองรับการประมวลผลเอกสารขนาดใหญ่อย่างมีประสิทธิภาพและเชื่อถือได้

### คำถามที่ 4: ฉันสามารถแก้ไขตำแหน่งของข้อความในเอกสาร PS ได้หรือไม่

A4: แน่นอน! ปรับพิกัดในตัวอย่างที่ให้มาเพื่อเปลี่ยนตำแหน่งของข้อความที่เพิ่ม

### คำถามที่ 5: ฉันจะขอความช่วยเหลือเกี่ยวกับคำถามที่เกี่ยวข้องกับ Aspose.Page ได้ที่ไหน

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและขอคำแนะนำจากผู้เชี่ยวชาญ