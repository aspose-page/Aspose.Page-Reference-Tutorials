---
title: เพิ่มข้อความด้วย Unicode String ไปยัง PostScript (PS) ด้วย Aspose.Page
linktitle: เพิ่มข้อความด้วยสตริง Unicode ลงใน PostScript (PS)
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีเพิ่มข้อความ Unicode ลงในไฟล์ PostScript โดยใช้ Aspose.Page สำหรับ .NET ปรับปรุงการจัดการเอกสารได้อย่างง่ายดาย
weight: 11
url: /th/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มข้อความด้วย Unicode String ไปยัง PostScript (PS) ด้วย Aspose.Page

## การแนะนำ

ในขอบเขตของการจัดการเอกสาร Aspose.Page สำหรับ .NET มีความโดดเด่นในฐานะไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงรูปแบบเอกสารต่างๆ ได้ หนึ่งในคุณสมบัติอันทรงพลังของมันคือความสามารถในการเพิ่มข้อความโดยใช้สตริง Unicode ลงในไฟล์ PostScript (PS) ในบทช่วยสอนนี้ เราจะสำรวจคำแนะนำทีละขั้นตอนในการทำงานนี้ให้สำเร็จ โดยมอบประสบการณ์ที่ราบรื่นสำหรับนักพัฒนาที่ทำงานกับ Aspose.Page

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
-  ติดตั้ง Aspose.Page สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Page สำหรับเอกสาร .NET](https://reference.aspose.com/page/net/).
- สภาพแวดล้อมการพัฒนาที่ตั้งค่าด้วยการกำหนดค่าที่จำเป็น

## นำเข้าเนมสเปซ

ในโค้ด C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นสำหรับการใช้ Aspose.Page สำหรับฟังก์ชัน .NET:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารและโฟลเดอร์แบบอักษร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## ขั้นตอนที่ 2: สร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // สร้างตัวเลือกการบันทึกด้วยขนาด A4
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (สามารถตั้งค่าตัวเลือกเพิ่มเติมได้ที่นี่)
    
    // สร้างเอกสาร PS 1 หน้าใหม่
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (ขั้นตอนต่อไปจะอธิบายไว้ด้านล่าง)
    
    // บันทึกเอกสาร
    document.Save();
}
```

## ขั้นตอนที่ 3: เพิ่มข้อความ Unicode ด้วยแบบอักษรที่กำหนดเอง

```csharp
string str = "試してみます.";  // ข้อความยูนิโค้ด
int fontSize = 48;

// การใช้แบบอักษรที่กำหนดเองสำหรับการกรอกข้อความ
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## ขั้นตอนที่ 4: ปิดหน้าปัจจุบัน

```csharp
document.ClosePage();
```

## ขั้นตอนที่ 5: จบและบันทึกเอกสาร

```csharp
document.Save();
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายขั้นตอนการเพิ่มข้อความ Unicode ลงในเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ .NET แล้ว นักพัฒนาสามารถปรับปรุงเวิร์กโฟลว์การจัดการเอกสารของตนโดยใช้ประโยชน์จากความสามารถอันทรงพลัง ทำให้มั่นใจได้ถึงความยืดหยุ่นและความแม่นยำ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่

คำตอบ 1: Aspose.Page ได้รับการออกแบบมาสำหรับ .NET เป็นหลัก แต่มีเวอร์ชันอื่นๆ สำหรับ Java ให้ใช้งาน

### คำถามที่ 2: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A2: เยี่ยมเลย[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อขอรับใบอนุญาตชั่วคราว

### คำถามที่ 3: มีฟอรัมชุมชนสำหรับการสนทนา Aspose.Page หรือไม่

 A3: ใช่ เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อสนับสนุนชุมชน

### คำถามที่ 4: Aspose.Page สำหรับ .NET ทำงานกับรูปแบบใดได้บ้าง

A4: Aspose.Page รองรับรูปแบบต่างๆ รวมถึง XPS, PS, EPS, PDF และอื่นๆ

### คำถามที่ 5: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของข้อความที่เพิ่มเข้ามาได้หรือไม่

A5: ได้ คุณสามารถกำหนดแบบอักษร ขนาด สี และคุณสมบัติอื่นๆ ของข้อความใน Aspose.Page ได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
