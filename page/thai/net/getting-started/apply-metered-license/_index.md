---
date: 2026-01-28
description: เรียนรู้วิธีแปลง EPS เป็น PNG ด้วย Aspose.Page สำหรับ .NET และใช้ใบอนุญาตแบบมิเตอร์เพื่อการประมวลผลเอกสารที่ราบรื่น
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: แปลง EPS เป็น PNG และใช้ใบอนุญาตแบบมีการวัดกับ Aspose.Page สำหรับ .NET
url: /th/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง EPS เป็น PNG และใช้ใบอนุญาตแบบ Metered กับ Aspose.Page สำหรับ .NET

## บทนำ

ปลดล็อกศักยภาพเต็มของ Aspose.Page สำหรับ .NET ด้วยการ **แปลง EPS เป็น PNG** และการใช้ใบอนุญาตแบบ Metered บทแนะนำนี้จะพาคุณผ่านทุกขั้นตอน ตั้งแต่การโหลดไฟล์ EPS ไปจนถึงการบันทึกเป็นภาพ PNG—เพื่อให้คุณสามารถประมวลผลเอกสารได้อย่างมีประสิทธิภาพและไม่มีลายน้ำการประเมิน

## คำตอบสั้น
- **บทแนะนำนี้ครอบคลุมอะไร?** การแปลงไฟล์ EPS เป็นภาพ PNG และการใช้ใบอนุญาตแบบ Metered กับ Aspose.Page สำหรับ .NET  
- **ต้องมีใบอนุญาตหรือไม่?** ใช่ จำเป็นต้องใช้ใบอนุญาตแบบ Metered สำหรับการใช้งานในสภาพแวดล้อมการผลิต  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **ใช้เวลานำไปใช้งานเท่าไหร่?** ประมาณ 10–15 นาทีสำหรับการแปลงพื้นฐาน  
- **สามารถรันบน Linux/macOS ได้หรือไม่?** แน่นอน—Aspose.Page รองรับหลายแพลตฟอร์ม

## “แปลง EPS เป็น PNG” คืออะไร?
การแปลง EPS เป็น PNG หมายถึงการทำ rasterization ไฟล์ Encapsulated PostScript (EPS) ที่เป็นเวกเตอร์ให้เป็นภาพบิตแมพ PNG ซึ่งมีประโยชน์เมื่อคุณต้องการแสดงหรือฝังกราฟิกในหน้าเว็บ รายงาน หรือคอมโพเนนต์ UI ที่ไม่รองรับ EPS

## ทำไมต้องใช้ใบอนุญาตแบบ Metered สำหรับการแปลง EPS เป็นภาพ?
ใบอนุญาตแบบ Metered ให้คุณจ่ายเฉพาะหน้าที่ประมวลผลเท่านั้น เหมาะกับงานที่มีปริมาณเปลี่ยนแปลงได้ นอกจากนี้ยังลบแบนเนอร์สีแดงของการประเมินออก ทำให้ผลลัพธ์สะอาดสำหรับผู้ใช้ปลายทาง

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

- ใบอนุญาต Aspose.Page สำหรับ .NET ที่ถูกต้อง: คุณสามารถรับได้จาก [purchase.aspose.com](https://purchase.aspose.com/buy)  
- ไลบรารี Aspose.Page ติดตั้งแล้ว: ดูที่ [documentation](https://reference.aspose.com/page/net/) สำหรับคำแนะนำการติดตั้ง  
- สภาพแวดล้อมการพัฒนา .NET: ตรวจสอบว่าคุณมีสภาพแวดล้อม .NET ทำงานอยู่บนเครื่องของคุณ

## นำเข้า Namespaces

ในโครงการ .NET ของคุณ ให้นำเข้า namespaces ที่จำเป็นเพื่อเข้าถึงฟังก์ชันของ Aspose.Page:

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

## วิธีแปลง EPS เป็น PNG ด้วยใบอนุญาตแบบ Metered?

ต่อไปนี้เป็นคู่มือแบบขั้นตอนที่ครอบคลุมทุกอย่างที่คุณต้องการรู้

### ขั้นตอนที่: ตั้งค่า Metered Public และ Private Keys

สร้างอินสแตนซ์ของคลาส `Aspose.Page.Metered` และตั้งค่า public key กับ private key ของคุณ แทนที่ `<type public key here>` และ `<type private key here>` ด้วยคีย์จริงของคุณ

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### ขั้นตอนที่ 2: โหลดไฟล์ EPS และสร้าง Document

ระบุพาธไปยังไฟล์ EPS ของคุณและสร้างสตรีมเพื่ออ่านเนื้อหา จากนั้นสร้างอินสแตนซ์ของคลาส `PsDocument` จากสตรีมนั้น

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### ขั้นตอนที่ 3: แปลง EPS เป็นภาพ PNG

สร้าง `ImageDevice` เพื่อแปลงไฟล์ EPS เป็นภาพ PNG บันทึกไฟล์ EPS เป็นภาพโดยใช้ `ImageSaveOptions`

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### ขั้นตอนที่ 4: ดึง Image Bytes

รับอาร์เรย์ไบต์ของภาพ ซึ่งแต่ละอาร์เรย์แทนหนึ่งหน้า ในกรณีนี้เรามีหนึ่งหน้า

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### ขั้นตอนที่ 5: บันทึก Image Bytes ไปยังไฟล์

บันทึกไบต์ของภาพลงไฟล์ เพื่อยืนยันการแปลงจาก EPS เป็น PNG สำเร็จ

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### ขั้นตอนที่ 6: ตรวจสอบใบอนุญาตแบบ Metered

ตรวจสอบด้วยตาเห็นว่าใบอนุญาตแบบ Metered ถูกนำไปใช้สำเร็จหรือไม่ หากภาพที่ได้ไม่มีข้อความประเมินสีแดง แสดงว่าใบอนุญาตทำงานอย่างถูกต้อง

ตอนนี้คุณพร้อมใช้ความสามารถเต็มรูปแบบของ Aspose.Page สำหรับ .NET พร้อมใบอนุญาตแบบ Metered แล้ว!

## ปัญหาและวิธีแก้ทั่วไป

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|----------|
| แบนเนอร์การประเมินสีแดงยังปรากฏอยู่ | ไม่ได้ตั้งค่าใบอนุญาตหรือคีย์ไม่ถูกต้อง | ตรวจสอบคีย์สาธารณะ/ส่วนตัวอีกครั้งและตรวจสอบว่าได้เรียก `SetMeteredKey` ก่อนการประมวลผลเอกสารใด ๆ |
| ไม่มีไฟล์ผลลัพธ์ถูกสร้าง | เส้นทาง `dataDir` ไม่ถูกต้องหรือไม่มีสิทธิ์ไฟล์ | ตรวจสอบว่าไดเรกทอรีมีอยู่และแอปพลิเคชันมีสิทธิ์เขียน |
| หลายหน้าไม่ได้บันทึก | เขียนเฉพาะหน้าหนึ่งแรกเท่านั้น | วนลูปผ่าน `imagesBytes` และเขียนแต่ละอาเรย์เป็นไฟล์ PNG แยกต่างหาก |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ใบอนุญาตแบบ Metered ใน pipeline CI/CD ได้หรือไม่?**  
**A:** ใช่ คุณสามารถเก็บคีย์อย่างปลอดภัย (เช่น ในตัวแปรสภาพแวดล้อม) และเรียก `SetMeteredKey` ระหว่างกระบวนการสร้าง

**Q: Aspose.Page รองรับการคงรักษาโปรไฟล์สีเมื่อแปลงเป็น PNG หรือไม่?**  
**A:** ผลลัพธ์ PNG จะรักษาข้อมูลสีเดิมไว้ แต่คุณสามารถปรับแต่งเพิ่มเติมได้ผ่าน `ImageSaveOptions`

**Q: สามารถแปลง EPS เป็นรูปแบบ raster อื่น (JPEG, BMP) ได้หรือไม่?**  
**A:** แน่นอน—เพียงเปลี่ยน `ImageSaveOptions` ไปเป็นรูปแบบที่ต้องการ

**Q: ขนาดไฟล์ EPS สูงสุดที่รองรับคือเท่าไหร่?**  
**A:** Aspose.Page สามารถจัดการไฟล์ขนาดใหญ่ได้ แต่การใช้หน่วยความจำจะเพิ่มตามความละเอียดของภาพ ควรประมวลผลหน้าเป็นหน้าเมื่อจัดการกับเอกสารขนาดใหญ่มาก

**Q: จะดึงจำนวนหน้าของไฟล์ EPS ได้อย่างโปรแกรมmatically อย่างไร?**  
**A:** ใช้ `document.PagesCount` หลังจากโหลด `PsDocument`

## FAQ's

### Q1: วิธีการขอรับใบอนุญาตแบบ Metered สำหรับ Aspose.Page สำหรับ .NET?

A1: เยี่ยมชม [purchase.aspose.com](https://purchase.aspose.com/buy) เพื่อรับใบอนุญาตที่ถูกต้อง

### Q2: จะหาเอกสารประกอบของ Aspose.Page สำหรับ .NET ได้จากที่ไหน?

A2: ดูที่ [Aspose.Page .NET](https://reference.aspose.com/page/net/) สำหรับเอกสารครบถ้วน

### Q3: มีฟอรั่มสำหรับการสนทนาและสนับสนุน Aspose.Page หรือไม่?

A3: มีครับ เยี่ยมชม [forum](https://forum.aspose.com/c/page/39) เพื่อเข้าร่วมชุมชนและขอความช่วยเหลือ

### Q4: สามารถทดลองใช้ Aspose.Page สำหรับ .NET ก่อนซื้อได้หรือไม่?

A4: แน่นอน! เข้าถึงเวอร์ชันทดลองฟรีได้ที่ [here](https://releases.aspose.com/)

### Q5: จะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ .NET ได้อย่างไร?

A5: เยี่ยมชม [temporary license/](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราว

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**อัปเดตล่าสุด:** 2026-01-28  
**ทดสอบด้วย:** Aspose.Page 24.12 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}