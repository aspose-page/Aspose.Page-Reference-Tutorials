---
title: แก้ไขเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET
linktitle: แก้ไขเอกสาร XPS
second_title: Aspose.Page .NET API
description: สำรวจพลังของ Aspose.Page สำหรับ .NET เพื่อแก้ไขเอกสาร XPS ได้อย่างง่ายดาย ปฏิบัติตามคำแนะนำทีละขั้นตอนของเรา ปรับปรุงการประมวลผลเอกสารของคุณ และเพิ่มข้อความลายเซ็นส่วนตัว
weight: 12
url: /th/net/document-creation/modify-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แก้ไขเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีแก้ไขเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET Aspose.Page เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาทำงานกับไฟล์ XPS ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มข้อความลายเซ็น "ยืนยันแล้ว" ไปยังหน้าที่ระบุในเอกสาร XPS

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- Aspose.Page สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Page แล้ว คุณสามารถค้นหาเอกสาร[ที่นี่](https://reference.aspose.com/page/net/).

-  ดาวน์โหลดไฟล์ที่จำเป็น: ดาวน์โหลดไฟล์ที่จำเป็น รวมถึงเอกสาร XPS อินพุตจากไฟล์[กำหนดหน้าการเผยแพร่](https://releases.aspose.com/page/net/).

-  Document Directory: ตั้งค่าไดเร็กทอรีสำหรับเอกสารของคุณและอัปเดต`dir` ตัวแปรในโค้ดด้วยเส้นทางที่เหมาะสม

ตอนนี้คุณได้ตั้งค่าทุกอย่างเรียบร้อยแล้ว มาดูคำแนะนำทีละขั้นตอนกันดีกว่า

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็นสำหรับ Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## ขั้นตอนที่ 1: เปิดสตรีมเอกสาร XPS

```csharp
// เอ็กซ์สตาร์ท:3
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dir = "Your Document Directory";
// เปิดสตรีมของไฟล์ XPS
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // สร้างเอกสาร PS จากสตรีม
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // ไปยังขั้นตอนต่อไป...
}
// สิ้นสุด:3
```

## ขั้นตอนที่ 2: สร้างข้อความลายเซ็น

```csharp
// เอ็กซ์สตาร์ท:4
// สร้างการเติมข้อความลายเซ็น
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// ไปยังขั้นตอนต่อไป...
// สิ้นสุด:4
```

## ขั้นตอนที่ 3: กำหนดหน้าและเพิ่มลายเซ็น

```csharp
// เอ็กซ์สตาร์ท:5
// กำหนดเพจที่จะกำหนดลายเซ็น
int[] pageNumbers = new int[] {1, 2, 3};

//สำหรับทุกลายเซ็นชุดเพจที่กำหนดไว้ "ยืนยัน" ที่พิกัด x=650 และ y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // กำหนดเพจที่ใช้งานอยู่
    document.SelectActivePage(pageNumbers[i]);

    // สร้างวัตถุร่ายมนตร์
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // กำหนดการเติมร่ายมนตร์
    glyphs.Fill = textFill;
}
// ไปยังขั้นตอนต่อไป...
// สิ้นสุด:5
```

## ขั้นตอนที่ 4: บันทึกการเปลี่ยนแปลงในเอกสาร XPS

```csharp
// เอ็กซ์สตาร์ท:6
// บันทึกเอกสาร XPS ที่เปลี่ยนแปลง
document.Save(dir + "input1_out.xps");
// สิ้นสุด:6
```

ยินดีด้วย! คุณแก้ไขเอกสาร XPS สำเร็จแล้วโดยใช้ Aspose.Page สำหรับ .NET รู้สึกอิสระที่จะสำรวจคุณสมบัติและฟังก์ชันเพิ่มเติมที่นำเสนอโดย Aspose.Page เพื่อปรับปรุงการประมวลผลเอกสารของคุณ

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนสำคัญในการแก้ไขเอกสาร XPS โดยใช้ Aspose.Page สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถรวมข้อความลายเซ็นลงในหน้าเฉพาะได้อย่างราบรื่น เพิ่มสัมผัสที่เป็นส่วนตัวให้กับเอกสารของคุณ

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Page เข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุดหรือไม่

A1: ใช่ Aspose.Page ได้รับการอัปเดตเป็นประจำเพื่อรองรับเฟรมเวิร์ก .NET ล่าสุด

### คำถามที่ 2: ฉันสามารถปรับแต่งแบบอักษรและสไตล์ของข้อความที่เพิ่มได้หรือไม่

A2: แน่นอน! คุณสามารถแก้ไขแบบอักษร สไตล์ และคุณลักษณะอื่นๆ ได้ตามความต้องการของคุณ

### คำถามที่ 3: มีข้อจำกัดเกี่ยวกับขนาดเอกสารที่ Aspose.Page สามารถจัดการได้หรือไม่

A3: Aspose.Page ได้รับการออกแบบมาเพื่อจัดการเอกสารที่มีขนาดแตกต่างกัน แต่ขอแนะนำให้ตรวจสอบเอกสารประกอบเพื่อดูรายละเอียดเฉพาะเสมอ

### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร

 A4: คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 5: ฉันจะขอความช่วยเหลือหรือติดต่อกับชุมชน Aspose ได้ที่ไหน

 A5: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อถามคำถามและมีส่วนร่วมกับชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
