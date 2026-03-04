---
date: 2025-12-21
description: เรียนรู้วิธีตั้งค่าความละเอียดเมื่อแปลง XPS เป็น BMP ใน Java ด้วย Aspose.Page
  คู่มือการแปลงภาพใน Java นี้รับประกันผลลัพธ์คุณภาพสูง.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: วิธีตั้งความละเอียดเมื่อแปลง XPS เป็น BMP ใน Java
url: /th/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XPS เป็น BMP ใน Java

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำขั้นตอนต่อขั้นตอนนี้เกี่ยวกับ **วิธีการตั้งค่าความละเอียด** คุณจะต้องทำไฟล์ XPS (XML Paper Specification) ของ BMP (Bitmap) ใน Java ด้วย Aspose.Page Aspose.Page สำหรับ Java เป็นไลบรารีซึ่งให้คุณสมบัติครบถ้วนสำหรับเอกสาร XPS ในบทแนะนำเรื่องนี้พาคุณผ่านการแปลงไฟล์ XPS เป็นภาพ BMP ในเรื่องนั้น

## คำตอบด่วน
- **ฉันควรใช้ไลบรารีใด** Aspose.Page สำหรับ Java มีคุณสมบัติการแปลง XPS→BMP ที่สมบูรณ์ที่สุด
- **ฉันสามารถควบคุมคุณภาพของภาพได้หรือไม่** ได้ – ใช้ `BmpSaveOptions` เพื่อตั้งค่าความละเอียดและโหมดการปรับให้เรียบ
- **ฉันต้องแปลงเฉพาะบางหน้าหรือไม่** แน่นอนว่า `options.setPageNumbers()` ให้คุณเลือกหน้าที่แน่นอนได้
- **นี่คือการแปลงรูปภาพ Java จริงหรือไม่** API เรนเดอร์หน้า XPS เป็นข้อมูลบิตแมปโดยตรง ดังนั้นจึงไม่จำเป็นต้องใช้รูปแบบระดับกลาง
- **รองรับ Java เวอร์ชันใดบ้าง** Java เวอร์ชันใหม่ๆ ทั้งหมด (8 ขึ้นไป) สามารถใช้งานร่วมกันได้

## จุดประสงค์ของการตั้งค่าความละเอียดคืออะไร?

ความละเอียดจะกำหนดจำนวนจุดต่อนิ้ว (DPI) ในภาพ BMP ที่สร้างขึ้น DPI ที่สูงขึ้นจะให้ภาพที่คมชัดกว่า ซึ่งจำเป็นสำหรับการพิมพ์หรืองานกราฟิกที่มีรายละเอียด การปรับความละเอียดจะช่วยให้คุณควบคุมคุณภาพของผลลัพธ์จากเวิร์กโฟลว์ **java convert xps** ได้อย่างเต็มที่

## ทำไมต้องใช้ Aspose.Page สำหรับการแปลง XPS→BMP?

- **ความละเอียดสูง** – รักษาคุณภาพเวกเตอร์ของ XPS ต้นฉบับไว้
- **การควบคุมที่ละเอียด** – คุณสามารถตั้งค่า DPI การปรับความเรียบ และแม้แต่เลือกหน้าเฉพาะที่จะแปลงได้
- **ไม่มีการพึ่งพาภายนอก** – ใช้ Java ล้วนๆ ไม่จำเป็นต้องใช้ไลบรารีเนทีฟ
- **ปรับขนาดได้** – ใช้งานได้ทั้งเอกสารหน้าเดียวและไฟล์ XPS หลายหน้าขนาดใหญ่

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มกระบวนการแปลง โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- **สภาพแวดล้อมการพัฒนา Java** – ติดตั้ง Java 8 หรือเวอร์ชันที่ใหม่กว่าบนเครื่องของคุณ

- **ไลบรารี Aspose.Page สำหรับ Java** – ดาวน์โหลดและรวมไลบรารี Aspose.Page สำหรับ Java ในโครงการของคุณ คุณสามารถค้นหาไลบรารีได้ [ที่นี่](https://releases.aspose.com/page/java/)

- **ไฟล์ XPS ตัวอย่าง** – เตรียมเอกสาร XPS ตัวอย่างที่คุณต้องการแปลงเป็น BMP

## นำเข้าแพ็กเกจ
รวมแพ็กเกจ Aspose.Page ที่จำเป็นในโค้ด Java ของคุณ:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## วิธีตั้งค่าความละเอียดสำหรับการแปลง XPS เป็น BMP
ด้านล่างนี้เป็นคำแนะนำแบบย่อที่มีหมายเลขกำกับ ซึ่งแสดงให้เห็นอย่างชัดเจนว่าควรตั้งค่าความละเอียดที่ใดและอย่างไร รวมถึงวิธีการ **แปลงหน้าเฉพาะ**

### ขั้นตอนที่ 1: โหลดเอกสาร XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### ขั้นตอนที่ 2: กำหนดค่าเริ่มต้น (ความละเอียดและการเลือกหน้า)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### ขั้นตอนที่ 3: สร้างอุปกรณ์แสดงผล
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### ขั้นตอนที่ 4: บันทึกเอกสารโดยใช้ตัวเลือก
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### ขั้นตอนที่ 5: วนลูปผ่านภาพที่แสดงผลและเขียนไฟล์
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

ทำซ้ำขั้นตอนเหล่านี้สำหรับการปรับแต่งหรือแก้ไขเพิ่มเติมใดๆ ที่คุณอาจต้องการในกระบวนการแปลง

## ปัญหาและวิธีแก้ไขทั่วไป
| ปัญหา | วิธีแก้ไข |

-------|----------|

| **ไฟล์ BMP คุณภาพต่ำ** | ตรวจสอบว่า `options.setResolution()` ถูกตั้งค่าเป็นค่า ≥300 DPI |

| **แปลงเอกสารได้เพียงบางส่วน** | ตรวจสอบให้แน่ใจว่า `options.setPageNumbers()` รวมดัชนีหน้าทั้งหมดที่ต้องการ |

| **ข้อผิดพลาด OutOfMemoryError กับไฟล์ XPS ขนาดใหญ่** | ประมวลผลเอกสารในส่วนย่อยๆ หรือเพิ่มขนาดฮีป JVM (`-Xmx`) |

| **ไม่พบไฟล์** | ตรวจสอบเส้นทาง `dataDir` อีกครั้ง และตรวจสอบว่าไฟล์ XPS อินพุตมีอยู่จริง |

## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งความละเอียดของภาพ BMP ได้หรือไม่?

ตอบ: ใช่ คุณสามารถปรับความละเอียดได้โดยการแก้ไขพารามิเตอร์ `options.setResolution()` ในโค้ด

### ถาม: Aspose.Page เข้ากันได้กับ Java เวอร์ชันต่างๆ หรือไม่?
ตอบ: ใช่ Aspose.Page รองรับ Java เวอร์ชันต่างๆ มากมาย โปรดตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งเวอร์ชันที่เข้ากันได้แล้ว

### ถาม: ฉันจะแปลงไฟล์ XPS จากช่วงหน้าเฉพาะได้อย่างไร?
ตอบ: ใช้เมธอด `options.setPageNumbers()` เพื่อระบุหมายเลขหน้าที่คุณต้องการแปลง

### ถาม: Aspose.Page รองรับรูปแบบเอาต์พุตอื่นๆ หรือไม่?
ตอบ: ใช่ Aspose.Page รองรับรูปแบบเอาต์พุตต่างๆ โปรดดูเอกสารประกอบสำหรับรายการที่ครอบคลุม

### ถาม: ฉันจะหาความช่วยเหลือหรือการสนับสนุนเพิ่มเติมได้ที่ไหน?
ตอบ: โปรดไปที่ [ฟอรัม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อขอรับการสนับสนุนและพูดคุยในชุมชน


---

**อัปเดตล่าสุด:** 2025-12-21
**ทดสอบด้วย:** Aspose.Page for Java 24.12
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}