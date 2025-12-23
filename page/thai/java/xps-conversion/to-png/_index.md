---
date: 2025-12-23
description: '**แปลง XPS เป็น PNG** อย่างง่ายดายใน Java ด้วย Aspose.Page. คู่มือนี้แสดงวิธีเรนเดอร์
  XPS ไปเป็นไฟล์ภาพด้วยโซลูชันที่เชื่อถือได้และเป็นมิตรต่อผู้พัฒนา.'
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: แปลง XPS เป็น PNG ใน Java
url: /th/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XPS เป็น PNG ใน Java

## บทนำ
ในโลกที่เปลี่ยนแปลงอย่างรวดเร็วของการพัฒนาซอฟต์แวร์ ความต้องการ **แปลง XPS เป็น PNG** (XML Paper Specification ไปยัง Portable Network Graphics) เกิดขึ้นบ่อยครั้ง เพื่อทำงานนี้อย่างราบรื่นใน Java, Aspose.Page มีโซลูชันที่ทรงพลัง ในบทเรียนนี้ เราจะอธิบายขั้นตอนการแปลง XPS เป็น PNG ด้วย Aspose.Page for Java.

## คำตอบสั้น
- **ไลบรารีที่จัดการการแปลงคืออะไร?** Aspose.Page for Java  
- **รูปแบบที่เกี่ยวข้องคืออะไร?** XPS (ต้นฉบับ) → PNG (ผลลัพธ์)  
- **ต้องการใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์  
- **สามารถตั้งความละเอียดของภาพได้หรือไม่?** ใช่, โดยใช้ `PngSaveOptions.setResolution()`  
- **สามารถเลือกหน้าเฉพาะได้หรือไม่?** แน่นอน – ระบุหมายเลขหน้าภายในอ็อบเจ็กต์ options  

## ทำไมต้องแปลง XPS เป็น PNG?
การเรนเดอร์ XPS เป็นไฟล์ภาพเป็นประโยชน์เมื่อคุณต้องการแสดงเอกสารบนเว็บ, ฝังลงในรายงาน, หรือสร้างภาพย่อเพื่อการพรีวิว PNG มีการบีบอัดแบบไม่มีการสูญเสียและรองรับโดยเบราว์เซอร์หลายตัว ทำให้เป็นตัวเลือกที่เหมาะสำหรับการแสดงผลภาพคุณภาพสูงของเนื้อหา XPS.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในบทเรียน โปรดตรวจสอบว่าคุณได้เตรียมสิ่งต่อไปนี้เรียบร้อยแล้ว:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ  
2. Aspose.Page for Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page คุณสามารถหา link ดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/page/java/)  
3. Integrated Development Environment (IDE): เลือก IDE ที่รองรับ Java เช่น IntelliJ IDEA หรือ Eclipse  

## วิธีแปลง XPS เป็น PNG ใน Java
ด้านล่างเป็นคู่มือแบบขั้นตอนที่อธิบาย **วิธีแปลง XPS** เป็นภาพ PNG พร้อมตัวอย่างโค้ดที่คุณสามารถคัดลอกไปใช้ในโปรเจกต์ของคุณได้โดยตรง.

### นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ ให้นำเข้าแพ็กเกจที่จำเป็นเพื่อใช้ฟังก์ชันของ Aspose.Page เพิ่มบรรทัด import ด้านล่างนี้ที่ส่วนต้นของไฟล์ Java ของคุณ:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดโฟลเดอร์ที่บรรจุไฟล์ XPS ต้นฉบับของคุณและที่ที่จะบันทึกไฟล์ PNG

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: โหลดเอกสาร XPS
สร้างอินสแตนซ์ `XpsDocument` ที่โหลดไฟล์ XPS ต้นฉบับ

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### ขั้นตอนที่ 3: เริ่มต้น Options
กำหนดค่า options สำหรับการส่งออก PNG ที่นี่คุณสามารถตั้งค่าการทำให้เรียบ, ความละเอียด, และระบุหน้าที่ต้องการเรนเดอร์

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### ขั้นตอนที่ 4: สร้างอุปกรณ์เรนเดอร์
สร้าง `ImageDevice` ที่จะเก็บข้อมูลภาพที่เรนเดอร์แล้ว

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### ขั้นตอนที่ 5: บันทึกและทำซ้ำ
เรนเดอร์เอกสาร XPS แล้วเขียนแต่ละ byte array ของ PNG ที่สร้างขึ้นไปยังไฟล์บนดิสก์

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

โดยทำตามขั้นตอนเหล่านี้ คุณสามารถ **เรนเดอร์ XPS เป็นไฟล์ภาพ** ในรูปแบบ PNG ได้อย่างง่ายดายด้วย Aspose.Page for Java.

## สรุป
สรุปแล้ว Aspose.Page for Java ทำให้กระบวนการแปลง XPS เป็น PNG ง่ายขึ้น ให้เครื่องมือที่เชื่อถือได้และมีประสิทธิภาพสำหรับนักพัฒนา นำไลบรารีนี้ไปใช้ในโปรเจกต์ Java ของคุณเพื่อทำให้การจัดการเอกสารเป็นเรื่องราบรื่น

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page for Java ในโครงการเชิงพาณิชย์ได้หรือไม่?
ใช่, Aspose.Page เป็นผลิตภัณฑ์เชิงพาณิชย์ คุณสามารถดูข้อมูลการให้ใบอนุญาตได้ [ที่นี่](https://purchase.aspose.com/buy).

### มีการทดลองใช้ฟรีหรือไม่?
ใช่, คุณสามารถทดลองใช้เวอร์ชันฟรีได้ [ที่นี่](https://releases.aspose.com/).

### ฉันจะหาเอกสารสำหรับ Aspose.Page for Java ได้จากที่ไหน?
เอกสารที่ครอบคลุมสามารถเข้าถึงได้ [ที่นี่](https://reference.aspose.com/page/java/).

### ฉันจะขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้อย่างไร?
คุณสามารถรับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

### มีฟอรั่มชุมชนสำหรับการสนทนาเกี่ยวกับ Aspose.Page หรือไม่?
ใช่, เยี่ยมชมฟอรั่มชุมชนได้ [ที่นี่](https://forum.aspose.com/c/page/39).

## คำถามที่พบบ่อยเพิ่มเติม

**Q: ฉันสามารถแปลงเฉพาะหน้าที่เลือกจากไฟล์ XPS ได้หรือไม่?**  
A: แน่นอน ใช้เมธอด `setPageNumbers` ใน `PngSaveOptions` เพื่อระบุหน้าที่ต้องการเรนเดอร์  

**Q: ความละเอียดของภาพที่แนะนำสำหรับ PNG คุณภาพสูงคือเท่าไหร่?**  
A: ความละเอียด 300 dpi เป็นสมดุลที่ดีระหว่างคุณภาพและขนาดไฟล์ แต่คุณสามารถปรับได้ผ่าน `options.setResolution()`  

**Q: API รองรับการแปลงแบบหลายเธรดสำหรับเอกสารขนาดใหญ่หรือไม่?**  
A: ใช่, คุณสามารถเรียกใช้ตรรกะการแปลงในเธรดขนาน โดยแต่ละเธรดจัดการหน้าหรือส่วนของเอกสารที่แตกต่างกัน  

**Q: ฉันจะจัดการการใช้หน่วยความจำเมื่อแปลงไฟล์ XPS ขนาดใหญ่มากอย่างไร?**  
A: ประมวลผลหน้าตามลำดับและปล่อย `FileOutputStream` หลังจากเขียนแต่ละไฟล์ ตามตัวอย่างโค้ด  

**Q: มีวิธีใดในการเพิ่มเมตาดาต้ากำหนดเองลงในไฟล์ PNG ที่สร้างขึ้นหรือไม่?**  
A: แม้ว่า `PngSaveOptions` จะไม่เปิดเผยฟิลด์เมตาดาต้าโดยตรง คุณสามารถประมวลผลต่อ PNG ด้วยไลบรารีภาพมาตรฐานเพื่อฝังเมตาดาต้า  

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}