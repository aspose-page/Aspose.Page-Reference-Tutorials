---
title: ใช้สิทธิ์การใช้งาน Metered กับ Aspose.Page สำหรับ .NET
linktitle: ใช้ใบอนุญาตมิเตอร์
second_title: Aspose.Page .NET API
description: สำรวจการบูรณาการอย่างราบรื่นของ Aspose.Page สำหรับ .NET พร้อมด้วยคำแนะนำทีละขั้นตอนเกี่ยวกับการใช้ใบอนุญาตแบบคิดค่าบริการตามปริมาณข้อมูล เพิ่มประสิทธิภาพการประมวลผลเอกสารได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/net/getting-started/apply-metered-license/
---
## การแนะนำ

ปลดล็อกศักยภาพเต็มรูปแบบของ Aspose.Page สำหรับ .NET โดยการใช้ใบอนุญาตแบบคิดค่าบริการตามปริมาณข้อมูล บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนการตั้งค่าและการใช้สิทธิ์การใช้งานแบบคิดค่าบริการตามปริมาณข้อมูล เพื่อให้มั่นใจว่าการใช้งานไลบรารี .NET อันทรงพลังนี้ราบรื่นและเหมาะสมที่สุด

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการตามขั้นตอนต่างๆ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  ใบอนุญาต Aspose.Page ที่ถูกต้องสำหรับ .NET: คุณสามารถขอรับได้จาก[buy.aspose.com](https://purchase.aspose.com/buy).
-  ติดตั้งไลบรารี Aspose.Page แล้ว: โปรดดูที่[เอกสารประกอบ](https://reference.aspose.com/page/net/) สำหรับคำแนะนำในการติดตั้ง
- สภาพแวดล้อมการพัฒนา .NET: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อม .NET ที่ใช้งานได้บนเครื่องของคุณ

## นำเข้าเนมสเปซ

ในโปรเจ็กต์ .NET ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## ขั้นตอนที่ 1: ตั้งค่าคีย์สาธารณะและคีย์ส่วนตัวแบบมิเตอร์

 เริ่มต้น`Aspose.Page.Metered` และตั้งค่าคีย์สาธารณะและคีย์ส่วนตัวแบบมิเตอร์ แทนที่`<type public key here>` และ`<type private key here>` ด้วยกุญแจจริงของคุณ

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## ขั้นตอนที่ 2: โหลดไฟล์ EPS และสร้างเอกสาร

 ระบุเส้นทางไปยังไฟล์ EPS ของคุณและสร้างสตรีมเพื่ออ่านเนื้อหา จากนั้นสร้างอินสแตนซ์ของ`PsDocument` คลาสจากสตรีม

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## ขั้นตอนที่ 3: แปลง EPS เป็นรูปภาพ PNG

 สร้าง`ImageDevice` สำหรับการแปลงไฟล์ EPS เป็นภาพ PNG บันทึกไฟล์ EPS เป็นรูปภาพโดยใช้นามสกุลไฟล์`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## ขั้นตอนที่ 4: ดึงข้อมูลไบต์รูปภาพ

รับไบต์ของรูปภาพ โดยที่แต่ละอาร์เรย์ไบต์แทนหนึ่งหน้า ในกรณีนี้เรามีหนึ่งหน้า

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## ขั้นตอนที่ 5: บันทึกไบต์รูปภาพลงในไฟล์

บันทึกไบต์ของรูปภาพเป็นไฟล์ เพื่อให้มั่นใจว่าการแปลงจาก EPS เป็น PNG ได้สำเร็จ

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## ขั้นตอนที่ 6: ตรวจสอบใบอนุญาตแบบมิเตอร์

ตรวจสอบด้วยสายตาว่าใช้ใบอนุญาตแบบมิเตอร์สำเร็จหรือไม่ หากภาพที่ได้ไม่มีข้อความการประเมินสีแดง แสดงว่ามีการใช้ใบอนุญาตแบบมิเตอร์โดยไม่มีปัญหาใดๆ

ตอนนี้คุณพร้อมที่จะใช้ประโยชน์จากความสามารถเต็มรูปแบบของ Aspose.Page สำหรับ .NET ด้วยใบอนุญาตแบบมิเตอร์แล้ว!

## บทสรุป

คำแนะนำทีละขั้นตอนนี้ช่วยให้คุณมีความรู้ในการใช้ใบอนุญาตแบบคิดค่าบริการตามปริมาณข้อมูลได้อย่างราบรื่นโดยใช้ Aspose.Page สำหรับ .NET ปรับปรุงความสามารถในการประมวลผลเอกสารของคุณและสำรวจคุณสมบัติมากมายที่นำเสนอโดยไลบรารีอันทรงพลังนี้

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันจะได้รับใบอนุญาตแบบคิดค่าบริการตามปริมาณข้อมูลสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A1: เยือน[buy.aspose.com](https://purchase.aspose.com/buy) เพื่อรับใบอนุญาตที่ถูกต้อง

### คำถามที่ 2: ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ .NET ได้ที่ไหน

 A2: อ้างอิงถึง[Aspose.เพจ .NET](https://reference.aspose.com/page/net/) สำหรับเอกสารที่ครอบคลุม

### คำถามที่ 3: มีฟอรัมสำหรับการสนทนาและการสนับสนุน Aspose.Page หรือไม่

 A3: ใช่ เยี่ยมเลย[ฟอรั่ม](https://forum.aspose.com/c/page/39) เพื่อมีส่วนร่วมกับชุมชนและขอความช่วยเหลือ

### คำถามที่ 4: ฉันสามารถลองใช้ Aspose.Page สำหรับ .NET ก่อนซื้อได้หรือไม่

 A4: แน่นอน! เข้าถึงการทดลองใช้ฟรีได้ที่[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร

 A5: เยี่ยมเลย[ใบอนุญาตชั่วคราว/](https://purchase.aspose.com/temporary-license/) เพื่อขอรับใบอนุญาตชั่วคราว