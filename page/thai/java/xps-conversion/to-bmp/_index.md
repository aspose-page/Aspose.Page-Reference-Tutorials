---
date: 2026-03-08
description: เรียนรู้วิธีแปลง XPS เป็น BMP ใน Java และตั้งค่าความละเอียดของ BMP ด้วยไลบรารีการแปลงภาพ
  Aspose.Page สำหรับ Java คู่มือนี้ครอบคลุมการสร้างผลลัพธ์คุณภาพสูงและเคล็ดลับที่เป็นมิตรต่อหน่วยความจำ
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: แปลง XPS เป็น BMP ใน Java – ตั้งค่าความละเอียดเพื่อผลลัพธ์คุณภาพสูง
url: /th/java/xps-conversion/to-bmp/
weight: 10
---

 "Solution". Translate to Thai "ปัญหา", "วิธีแก้". But need to keep pipe separators.

Also list items.

Make sure code block placeholders remain unchanged.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XPS เป็น BMP ใน Java

## คำนำ
ยินดีต้อนรับสู่คู่มือขั้นตอนโดยละเอียดเกี่ยวกับการ **แปลง XPS เป็น BMP** ใน Java และการตั้งค่าความละเอียดเพื่อคุณภาพภาพที่ดีที่สุดด้วย Aspose.Page ไม่ว่าคุณจะสร้าง pipeline การพิมพ์, สร้าง thumbnail, หรือจำเป็นต้องใช้กราฟิกความละเอียดสูง การควบคุม DPI จะให้ความยืดหยุ่นในการตอบสนองทุกความต้องการของคุณ

## คำตอบสั้น
- **ควรใช้ไลบรารีอะไร?** Aspose.Page for Java เป็น **java image conversion library** ที่ครบถ้วนที่สุดสำหรับ XPS → BMP  
- **ฉันสามารถควบคุมคุณภาพภาพได้หรือไม่?** ใช่ – ใช้ `BmpSaveOptions` เพื่อ **ตั้งค่าความละเอียด BMP** และโหมด smoothing  
- **จะหลีกเลี่ยง OutOfMemoryError Java เมื่อประมวลผลไฟล์ XPS ขนาดใหญ่ได้อย่างไร?** เรนเดอร์หน้าเป็นส่วน ๆ หรือเพิ่ม heap ของ JVM (`-Xmx`)  
- **ต้องการแปลงเฉพาะหน้าบางหน้าเท่านั้นหรือไม่?** ได้เลย, `options.setPageNumbers()` ให้คุณเลือกหน้าที่ต้องการได้อย่างแม่นยำ  
- **รองรับเวอร์ชัน Java ใดบ้าง?** ทุกเวอร์ชัน Java สมัยใหม่ (8 ขึ้นไป) ทำงานได้อย่างราบรื่น

## จุดประสงค์ของการตั้งค่าความละเอียดคืออะไร?
ความละเอียดกำหนดจำนวนจุดต่อหนึ่งนิ้ว (DPI) ในภาพ BMP ที่สร้างขึ้น DPI ที่สูงขึ้นจะให้ภาพคมชัดยิ่งขึ้น ซึ่งจำเป็นสำหรับการพิมพ์หรือการทำงานกราฟิกที่ต้องการรายละเอียด การปรับความละเอียดทำให้คุณควบคุมคุณภาพผลลัพธ์ของกระบวนการ **convert xps to bmp** ได้อย่างเต็มที่

## ทำไมต้องใช้ Aspose.Page สำหรับการแปลง XPS → BMP?
- **ความแม่นยำสูง** – รักษาคุณภาพเวกเตอร์ของ XPS ดั้งเดิม  
- **การควบคุมละเอียด** – สามารถตั้งค่า DPI, smoothing, และเลือกหน้าที่ต้องการแปลงได้  
- **ไม่มีการพึ่งพาไลบรารีภายนอก** – เป็น Java แท้ ๆ ไม่ต้องใช้ native libraries  
- **ขยายได้** – ทำงานได้ทั้งเอกสารหน้าเดียวและไฟล์ XPS หลายหน้าขนาดใหญ่  

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มกระบวนการแปลง ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
- **สภาพแวดล้อมการพัฒนา Java** – มี Java 8 หรือใหม่กว่าอยู่บนเครื่องของคุณ  
- **Aspose.Page for Java Library** – ดาวน์โหลดและเพิ่มไลบรารี Aspose.Page for Java ลงในโปรเจกต์ของคุณ คุณสามารถหาไลบรารีได้ [ที่นี่](https://releases.aspose.com/page/java/)  
- **ไฟล์ XPS ตัวอย่าง** – เตรียมไฟล์ XPS ตัวอย่างที่ต้องการแปลงเป็น BMP  

## นำเข้าแพ็กเกจ
เพิ่มแพ็กเกจ Aspose.Page ที่จำเป็นในโค้ด Java ของคุณ:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## วิธีตั้งค่าความละเอียดสำหรับการแปลง XPS เป็น BMP
ต่อไปนี้เป็นขั้นตอนสั้น ๆ ที่จัดลำดับเป็นหมายเลข แสดงให้เห็นว่าต้องตั้งค่าความละเอียดที่ไหนและอย่างไร รวมถึงวิธี **แปลงเฉพาะหน้า** ด้วย

### ขั้นตอนที่ 1: โหลดเอกสาร XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### ขั้นตอนที่ 2: เริ่มต้น Options (ความละเอียดและการเลือกหน้า)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### ขั้นตอนที่ 3: สร้าง Rendering Device
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### ขั้นตอนที่ 4: บันทึกเอกสารโดยใช้ Options
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### ขั้นตอนที่ 5: วนลูปผ่านภาพที่เรนเดอร์และเขียนไฟล์
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

ทำซ้ำขั้นตอนเหล่านี้สำหรับการปรับแต่งหรือการแก้ไขเพิ่มเติมที่คุณอาจต้องการในกระบวนการแปลง

## วิธีหลีกเลี่ยง OutOfMemoryError Java เมื่อแปลงไฟล์ XPS ขนาดใหญ่
- **ประมวลผลเป็นส่วน** – ตัวอย่างนี้ได้เรนเดอร์เอกสารเป็นส่วน (`device.getResult()`) ซึ่งช่วยลดความกดดันของหน่วยความจำ  
- **เพิ่ม heap ของ JVM** – ใช้พารามิเตอร์ `-Xmx` (เช่น `-Xmx2g`) เพื่อจัดสรรหน่วยความจำเพิ่มเติมสำหรับเอกสารขนาดใหญ่  
- **ปล่อยทรัพยากร** – เรียก `document.close()` เมื่อทำงานเสร็จเพื่อคืนทรัพยากร native  

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **BMP คุณภาพต่ำ** | ตรวจสอบว่า `options.setResolution()` ตั้งค่าเป็นค่า ≥ 300 DPI |
| **แปลงได้เพียงบางส่วนของเอกสาร** | ตรวจสอบว่า `options.setPageNumbers()` ครอบคลุมดัชนีหน้าที่ต้องการทั้งหมด |
| **OutOfMemoryError กับไฟล์ XPS ขนาดใหญ่** | ประมวลผลเอกสารเป็นส่วนย่อยหรือเพิ่มขนาด heap ของ JVM (`-Xmx`) |
| **ไม่พบไฟล์** | ตรวจสอบเส้นทาง `dataDir` อีกครั้งและยืนยันว่าไฟล์ XPS อินพุตมีอยู่จริง |

## คำถามที่พบบ่อย
### ถ: ฉันสามารถปรับความละเอียดของภาพ BMP ได้หรือไม่?
ตอบ: ได้, คุณสามารถปรับความละเอียดได้โดยแก้ไขพารามิเตอร์ `options.setResolution()` ในโค้ด

### ถ: Aspose.Page รองรับเวอร์ชัน Java ต่าง ๆ หรือไม่?
ตอบ: รองรับ, Aspose.Page ทำงานได้กับหลายเวอร์ชันของ Java เพียงตรวจสอบว่าคุณติดตั้งเวอร์ชันที่เข้ากันได้

### ถ: ฉันจะทำการแปลงไฟล์ XPS จากช่วงหน้าที่กำหนดได้อย่างไร?
ตอบ: ใช้เมธอด `options.setPageNumbers()` เพื่อระบุหมายเลขหน้าที่ต้องการแปลง

### ถ: มีรูปแบบเอาต์พุตอื่น ๆ ที่ Aspose.Page รองรับหรือไม่?
ตอบ: มี, Aspose.Page รองรับรูปแบบเอาต์พุตหลายรูปแบบ โปรดดูเอกสารเพื่อรายการที่ครบถ้วน

### ถ: จะหาแหล่งช่วยเหลือหรือสนับสนุนเพิ่มเติมได้จากที่ไหน?
ตอบ: เยี่ยมชม [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชนและการสนทนาต่าง ๆ

---

**อัปเดตล่าสุด:** 2026-03-08  
**ทดสอบกับ:** Aspose.Page for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}