---
date: 2026-03-13
description: เรียนรู้วิธีแปลง XPS เป็น JPEG ใน Java ด้วย Aspose.Page Java คู่มือแบบขั้นตอนนี้จะแสดงให้คุณเห็นวิธีแปลง
  XPS เป็น JPEG อย่างมีประสิทธิภาพโดยใช้ไลบรารี Aspose.Page Java
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: วิธีแปลง XPS เป็น JPEG ใน Java โดยใช้ Aspose.Page Java
url: /th/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง XPS เป็น JPEG ใน Java ด้วย Aspose.Page Java

## แนะนำ Aspose.Page Java
ในบทเรียนนี้ **คุณจะได้เรียนรู้วิธีแปลง XPS เป็น JPEG** ด้วยไลบรารี **Aspose.Page Java** การแปลงไฟล์ XPS เป็นภาพ JPEG เป็นความต้องการที่พบบ่อยเมื่อคุณต้องการแสดงหน้าของเอกสารเป็นกราฟิกแบบแรสเตอร์ในพอร์ทัลเว็บ, ตัวดูบนเดสก์ท็อป, หรือเป็นไฟล์แนบอีเมล เราจะอธิบายโค้ดทุกบรรทัด, ทำไมการตั้งค่าแต่ละอย่างถึงสำคัญ, และแชร์เคล็ดลับที่ใช้งานได้จริง เพื่อให้คุณสามารถฝังกระบวนการแปลงนี้เข้าไปในแอปพลิเคชัน Java ของคุณได้อย่างมั่นใจ

## คำตอบสั้น
- **ไลบรารีที่ใช้ในการแปลงคืออะไร?** Aspose.Page Java  
- **ฉันสามารถเลือกหน้าเฉพาะได้หรือไม่?** ใช่ – ใช้ `setPageNumbers` ใน `JpegSaveOptions`  
- **คุณภาพภาพที่ฉันสามารถควบคุมได้มีอะไรบ้าง?** โหมดการทำให้เรียบ, ความละเอียด, และการตั้งค่าคุณภาพ JPEG  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์ (มีการทดลองใช้ฟรี)  
- **โค้ดนี้เข้ากันได้กับ Java 8 หรือไม่?** แน่นอน – API ทำงานกับ Java 8 และใหม่กว่า  

## XPS คืออะไรและทำไมต้องแปลง XPS เป็น JPEG?
XPS (XML Paper Specification) เป็นรูปแบบเอกสารแบบจัดตำแหน่งคงที่ที่คล้ายกับ PDF การแปลง XPS เป็น JPEG มีประโยชน์เมื่อคุณต้องการภาพแรสเตอร์สำหรับภาพย่อ, ไฟล์แนบอีเมล, หรือเมื่อรวมกับระบบที่รับไฟล์รูปภาพเท่านั้น JPEG ให้สมดุลที่ดีระหว่างคุณภาพภาพและขนาดไฟล์ ทำให้เหมาะสำหรับการแสดงตัวอย่างบนเว็บ

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกไปในโค้ด, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **สภาพแวดล้อมการพัฒนา Java** – JDK 8 หรือใหม่กว่า ติดตั้งและกำหนดค่าแล้ว.  
- **Aspose.Page สำหรับ Java** – ดาวน์โหลดไลบรารีล่าสุดจากเว็บไซต์อย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/page/java/).  
- **เอกสาร XPS ตัวอย่าง** – ไฟล์ XPS ที่คุณต้องการแปลงเป็นภาพ JPEG.  

## นำเข้าแพ็กเกจ
เริ่มต้นโดยการนำเข้าคลาสที่จำเป็นเข้าสู่ไฟล์ซอร์ส Java ของคุณ:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## ขั้นตอนที่ 1: กำหนดเส้นทางและโหลดเอกสาร XPS
กำหนดไดเรกทอรีที่มีไฟล์ XPS ต้นฉบับของคุณและสร้างอินสแตนซ์ `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **เคล็ดลับมืออาชีพ:** ใช้ `Paths.get()` จาก `java.nio.file` เพื่อจัดการเส้นทางที่ไม่ขึ้นกับแพลตฟอร์ม.

## ขั้นตอนที่ 2: กำหนดค่า JPEG Save Options
กำหนดวิธีการเรนเดอร์ภาพ JPEG — ความละเอียด, การทำให้เรียบ, และหน้าที่จะส่งออก:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` สร้างผลลัพธ์ความละเอียดสูงที่เหมาะกับการพิมพ์.  
- `setPageNumbers` ให้คุณเลือกเฉพาะหน้าที่ต้องการ ช่วยประหยัดเวลาและหน่วยความจำ.  

## ขั้นตอนที่ 3: สร้างอุปกรณ์การเรนเดอร์
`ImageDevice` จะบันทึกหน้าที่เรนเดอร์เป็นอาเรย์ของไบต์:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## ขั้นตอนที่ 4: เรนเดอร์เอกสาร XPS เป็น JPEG
เรียกใช้เมธอด `save`, ส่งอุปกรณ์และตัวเลือกที่คุณกำหนดค่าไว้:

```java
document.save(device, options);
```

ในขั้นตอนนี้ `device` จะเก็บอาเรย์สองมิติที่แต่ละองค์ประกอบเป็นหน้าที่เข้ารหัสเป็น JPEG.

## ขั้นตอนที่ 5: วนลูปผลลัพธ์และเขียนไฟล์
วนลูปผ่านหน้าที่เรนเดอร์และเขียนแต่ละอาเรย์ไบต์ลงในไฟล์ JPEG แยกกัน:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

แต่ละไฟล์จะถูกตั้งชื่อเป็น `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, ทำให้คุณระบุเอกสารต้นฉบับและหมายเลขหน้าได้ง่าย.

## กรณีการใช้งานทั่วไป
- **สร้างภาพย่อ** สำหรับระบบจัดการเอกสาร.  
- **ฝังตัวอย่างหน้า** ในแอปพลิเคชันเว็บที่รองรับเฉพาะรูปแบบภาพ.  
- **ประมวลผลเป็นชุด** ไฟล์ XPS ขนาดใหญ่เป็น JPEG เพื่อการเก็บถาวรหรือการรายงาน.  

## ปัญหาทั่วไปและการแก้ไขปัญหา
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| **ไฟล์ JPEG ว่างเปล่า** | สตรีมเอาต์พุตไม่ได้ทำการ flush หรือ close อย่างถูกต้อง | ตรวจสอบว่า `imageStream.close()` ถูกเรียกภายในลูปภายใน (ตามที่แสดง). |
| **ข้อผิดพลาด Out‑of‑memory** บนไฟล์ XPS ขนาดใหญ่ | การเรนเดอร์ทุกหน้าในครั้งเดียวใช้ RAM มากเกินไป | ประมวลผลหน้าเป็นชุดเล็ก ๆ หรือเพิ่มขนาด heap ของ JVM (`-Xmx`). |
| **หน้าที่หายไป** | `setPageNumbers` ไม่รวมหน้าที่ต้องการ | ตรวจสอบว่าอาร์เรย์หมายเลขหน้า ตรงกับดัชนีหน้าของ XPS จริง (เริ่มจาก 1). |

## คำถามที่พบบ่อย

### Q: Aspose.Page เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่?
A: ใช่, Aspose.Page เป็นผลิตภัณฑ์เชิงพาณิชย์ที่มีตัวเลือกการให้ใบอนุญาต ตรวจสอบ [ที่นี่](https://purchase.aspose.com/buy) สำหรับรายละเอียด.

### Q: ฉันสามารถทดลองใช้ Aspose.Page ก่อนซื้อได้หรือไม่?
A: ใช่, คุณสามารถรับการทดลองใช้ฟรี [ที่นี่](https://releases.aspose.com/).

### Q: ฉันสามารถหาเอกสารประกอบของ Aspose.Page ได้ที่ไหน?
A: เอกสารประกอบสามารถเข้าถึงได้ [ที่นี่](https://reference.aspose.com/page/java/).

### Q: ฉันจะรับการสนับสนุนสำหรับ Aspose.Page อย่างไร?
A: เยี่ยมชม [Aspose.Page Forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชน.

### Q: ฉันต้องการใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่?
A: ใช่, คุณสามารถรับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

## สรุป
คุณได้เรียนรู้ **วิธีแปลง XPS เป็น JPEG** ด้วย **Aspose.Page Java** แล้ว ด้วยการทำตามคู่มือแบบขั้นตอนต่อขั้นตอนนี้ คุณสามารถผสานกระบวนการแปลงนี้เข้าไปในแอปพลิเคชัน Java ใดก็ได้ — ไม่ว่าจะเป็นเครื่องมือเดสก์ท็อป, บริการเว็บ, หรือยูทิลิตี้ประมวลผลเป็นชุด อย่าลังเลที่จะทดลองความละเอียดต่าง ๆ, การเลือกหน้า, และรูปแบบภาพ เพื่อให้ตรงกับความต้องการของโครงการของคุณ

---

**อัปเดตล่าสุด:** 2026-03-13  
**ทดสอบกับ:** Aspose.Page 24.11 for Java (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}