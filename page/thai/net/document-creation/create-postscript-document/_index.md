---
title: สร้างเอกสาร PostScript ด้วย Aspose.Page สำหรับ .NET
linktitle: สร้างเอกสาร PostScript
second_title: Aspose.Page .NET API
description: เรียนรู้วิธีสร้างเอกสาร PostScript ใน .NET โดยใช้ Aspose.Page ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น ดาวน์โหลดไลบรารีและเริ่มจัดการไฟล์ PostScript ได้อย่างง่ายดาย
weight: 11
url: /th/net/document-creation/create-postscript-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร PostScript ด้วย Aspose.Page สำหรับ .NET

## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการสร้างเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ .NET! Aspose.Page เป็น API ที่ทรงพลังที่ช่วยให้คุณจัดการและสร้างไฟล์ PostScript ภายในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างเอกสาร PostScript โดยแบ่งแต่ละตัวอย่างออกเป็นขั้นตอนโดยละเอียด

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Page สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Page สำหรับ .NET Library แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/net/).

- สภาพแวดล้อม .NET: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อม .NET ที่ใช้งานได้บนเครื่องของคุณ

- โปรแกรมแก้ไขข้อความหรือ IDE: ใช้โปรแกรมแก้ไขข้อความที่คุณต้องการหรือสภาพแวดล้อมการพัฒนาแบบรวม (IDE) สำหรับการเขียนโค้ด

ตอนนี้ เรามาเริ่มด้วยคำแนะนำทีละขั้นตอนกันดีกว่า!

## นำเข้าเนมสเปซ

ในขั้นตอนแรกนี้ เราจำเป็นต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานที่ Aspose.Page มอบให้ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.IO;
```

เนมสเปซเหล่านี้จะให้การเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการสร้างและบันทึกเอกสาร PostScript

ตอนนี้ เรามาแจกแจงตัวอย่างที่ให้ไว้เป็นขั้นตอนโดยละเอียด:

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

```csharp
string dir = "Your Document Directory";
```

แทนที่ "Your Document Directory" ด้วยเส้นทางที่คุณต้องการบันทึกเอกสาร PostScript

## ขั้นตอนที่ 2: สร้างกระแสเอาต์พุต

```csharp
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
```

ข้อมูลโค้ดนี้ตั้งค่าสตรีมเอาต์พุตสำหรับเอกสาร PostScript โดยระบุชื่อไฟล์และสร้างเอกสาร

## ขั้นตอนที่ 3: สร้างตัวเลือกการบันทึก

```csharp
PsSaveOptions options = new PsSaveOptions();
```

ที่นี่ เราสร้างอินสแตนซ์ของ PsSaveOptions เพื่อตั้งค่าตัวเลือกต่างๆ สำหรับการบันทึกเอกสาร PostScript

## ขั้นตอนที่ 4: ตั้งค่าขนาดหน้าและระยะขอบ

```csharp
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT);
options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_ZERO);
```

ปรับขนาดหน้าและระยะขอบตามความต้องการของคุณ

## ขั้นตอนที่ 5: ตั้งค่าโฟลเดอร์แบบอักษรเพิ่มเติม

```csharp
options.AdditionalFontsFolders = new string[] { dir };
```

ระบุโฟลเดอร์แบบอักษรเพิ่มเติมหากคุณวางแผนที่จะใช้แบบอักษรที่อยู่ในโฟลเดอร์ที่ไม่ใช่ระบบ

## ขั้นตอนที่ 6: สร้างเอกสารหลายหน้า

```csharp
bool multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

สร้างเอกสาร PostScript แบบหลายหน้าใหม่โดยเปิดหนึ่งหน้า

## ขั้นตอนที่ 7: ปิดและบันทึก

```csharp
document.ClosePage();
document.Save();
```

ปิดหน้าปัจจุบันและบันทึกเอกสาร

ยินดีด้วย! คุณสร้างเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ .NET สำเร็จแล้ว

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนสำคัญในการสร้างเอกสาร PostScript โดยใช้ Aspose.Page สำหรับไลบรารี .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A1: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/page/net/).

### คำถามที่ 2: ฉันจะดาวน์โหลด Aspose.Page สำหรับ .NET ได้อย่างไร

 A2: คุณสามารถดาวน์โหลดได้จาก[ลิงค์นี้](https://releases.aspose.com/page/net/).

### คำถามที่ 3: ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A3: คุณสามารถซื้อใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).

### คำถามที่ 4: Aspose.Page สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 A4: ใช่ คุณสามารถค้นหารุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A5: รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
