---
date: 2025-12-04
description: เรียนรู้วิธีแปลง PS เป็น PNG ใน Java ด้วย Aspose.Page คู่มือขั้นตอนต่อขั้นตอน
  ข้อกำหนดเบื้องต้น คำถามที่พบบ่อย และตัวอย่างโค้ดสำหรับการแปลง PostScript เป็นภาพอย่างราบรื่น
linktitle: How to Convert PS to PNG in Java Using Aspose.Page
second_title: Aspose.Page Java API
title: วิธีแปลง PS เป็น PNG ใน Java ด้วย Aspose.Page
url: /th/java/postscript-conversion/to-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง PS เป็น PNG ใน Java ด้วย Aspose.Page

## บทนำ
หากคุณต้องการ **แปลง PS เป็น PNG** อย่างรวดเร็วและเชื่อถือได้ Aspose.Page for Java มี API ที่ใช้งานง่ายซึ่งจัดการขั้นตอนที่ซับซ้อนทั้งหมด ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมด—from การตั้งค่าโปรเจกต์จนถึงการสร้างภาพ PNG คุณภาพสูงจากไฟล์ PostScript (.ps) เมื่อเสร็จแล้วคุณจะเข้าใจว่าทำไมวิธีนี้จึงเหมาะสำหรับการประมวลผลเอกสารบนเซิร์ฟเวอร์, การแปลงเป็นชุด, หรือแอปพลิเคชัน Java ใด ๆ ที่ทำงานกับไฟล์กราฟิก

## คำตอบสั้น
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java (เวอร์ชันล่าสุด)  
- **สามารถแปลงหลายหน้าได้หรือไม่?** ได้ — แต่ละหน้าจะถูกบันทึกเป็นไฟล์ PNG แยกกัน  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้ไลเซนส์ทดลองฟรีสำหรับการประเมิน; ต้องมีลิขสิทธิ์สำหรับการใช้งานจริง  
- **รองรับรูปแบบภาพใดบ้าง?** PNG, JPEG, BMP, GIF, TIFF (ที่นี่แสดง PNG)  
- **เวลาการทำงานโดยประมาณ?** ประมาณ 10‑15 นาทีสำหรับการแปลงพื้นฐาน

## การแปลง PS เป็น PNG คืออะไร?
PostScript (PS) เป็นภาษาการอธิบายหน้า (page description language) ที่ใช้หลัก ๆ สำหรับการพิมพ์ การแปลงไฟล์ PS เป็น PNG จะเปลี่ยนคำอธิบายนั้นให้เป็นภาพเรสเตอร์ที่สามารถแสดงในเว็บเบราว์เซอร์, ฝังในเอกสาร, หรือประมวลผลต่อด้วยเครื่องมือแก้ไขภาพได้

## ทำไมต้องใช้ Aspose.Page for Java?
- **ไม่มีการพึ่งพาไลบรารีภายนอก** — Java แท้, ไม่ต้องใช้ไบนารีเนทีฟ  
- **การเรนเดอร์ที่แม่นยำ** — รักษาแบบอักษร, เวกเตอร์, และสีได้ครบถ้วน  
- **การจัดการข้อผิดพลาด** — สามารถปิดการแจ้งเตือนข้อผิดพลาดเล็กน้อยเพื่อให้การแปลงดำเนินต่อได้  
- **ขยายได้** — เหมาะสำหรับไฟล์เดี่ยวหรือการทำงานเป็นชุดขนาดใหญ่

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมี:

- **ไลบรารี Aspose.Page for Java** ที่รวมไว้ในโปรเจกต์ของคุณ ดาวน์โหลดได้จาก [releases page](https://releases.aspose.com/page/java/)  
- **ไฟล์ PostScript** (`.ps`) ที่วางไว้ในโฟลเดอร์ที่รู้จักบนระบบไฟล์ของคุณ  
- **Java 8+** ที่ติดตั้งและตั้งค่าในสภาพแวดล้อมการพัฒนา

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: นำเข้าแพ็กเกจที่จำเป็น
เริ่มต้นโดยนำเข้าคลาสที่ต้องใช้ในไฟล์ซอร์ส Java เพื่อทำงานกับสตรีม, API ของ Aspose EPS, และรูปแบบภาพ

```java
// Import necessary packages
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
import com.aspose.page.ImageFormat;
```

### ขั้นตอนที่ 2: ตั้งค่าโฟลเดอร์เอกสารและเลือกรูปแบบภาพ
กำหนดตำแหน่งที่ไฟล์ PS ต้นทางอยู่และระบุว่าต้องการผลลัพธ์เป็น PNG

```java
// Set the path to the documents directory
String dataDir = "Your Document Directory";
// Initialize image format
ImageFormat imageFormat = ImageFormat.PNG;
```

### ขั้นตอนที่ 3: เริ่มต้นสตรีมอินพุตของ PostScript
เปิดสตรีมสำหรับไฟล์ `.ps` และสร้างอินสแตนซ์ `PsDocument` ที่ Aspose จะทำการเรนเดอร์

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### ขั้นตอนที่ 4: ตั้งค่าตัวเลือกการแปลง
คุณสามารถบอก Aspose ให้ละเว้นข้อผิดพลาดที่ไม่สำคัญซึ่งอาจทำให้การแปลงหยุดกลางคันได้

```java
// Set conversion options
boolean suppressErrors = true;
ImageSaveOptions options = new ImageSaveOptions(suppressErrors);
```

### ขั้นตอนที่ 5: สร้าง Image Device
`ImageDevice` ทำหน้าที่เป็นปลายทางที่รับหน้าที่เรสเตอร์ไลซ์

```java
// Create ImageDevice
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### ขั้นตอนที่ 6: ดำเนินการแปลง
เรียกเมธอด `save` เพื่อเรนเดอร์เอกสาร PS ไปยังอุปกรณ์ภาพ บล็อก `try/finally` รับประกันว่าสตรีมอินพุตจะถูกปิด

```java
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### ขั้นตอนที่ 7: บันทึกไฟล์ PNG ที่สร้างขึ้น
แต่ละหน้าจะถูกเก็บเป็นอาร์เรย์ไบต์ภายในอุปกรณ์ ให้วนลูปผ่านอาร์เรย์เหล่านั้น เขียนแต่ละอาร์เรย์ลงไฟล์ PNG แยกกัน และตั้งชื่อไฟล์ตามลำดับ

```java
byte[][] imagesBytes = device.getImagesBytes();
int i = 0;
for (byte [] imageBytes : imagesBytes) {
    String imagePath = dataDir + "PSToImage" + i + "." + imageFormat.toString().toLowerCase();
    FileOutputStream fs = new FileOutputStream(imagePath);
    try {
        fs.write(imageBytes, 0, imageBytes.length);
    } catch (IOException ex) {
        System.out.println(ex.getMessage());
    } finally {
        fs.close();
    }
    i++;
}
```

### ขั้นตอนที่ 8: ตรวจสอบข้อผิดพลาด (ถ้าต้องการ)
หากคุณเปิดใช้งานการละเว้นข้อผิดพลาด คุณยังสามารถตรวจสอบคำเตือนที่เกิดขึ้นระหว่างการเรนเดอร์ได้

```java
if (suppressErrors) {
    for (Exception ex : options.getExceptions()) {
        System.out.println(ex.getMessage());
    }
}
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **ไม่มีไฟล์ผลลัพธ์สร้างขึ้น** | เส้นทาง `dataDir` ไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ตรวจสอบว่าโฟลเดอร์มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน |
| **ฟอนต์หาย** | ฟอนต์ที่ใช้ในไฟล์ PS ไม่ได้ถูกโหลดโดย Aspose | ใช้ `options.setAdditionalFontsFolders(...)` เพื่อชี้ไปยังโฟลเดอร์ฟอนต์ของคุณ |
| **การเรนเดอร์หน้าไม่สมบูรณ์** | `suppressErrors` ตั้งเป็น `false` ทำให้หยุดเมื่อเจอข้อผิดพลาดเล็กน้อย | ตั้ง `suppressErrors = true` หรือดูรายละเอียดใน `options.getExceptions()` |

## คำถามที่พบบ่อย

**Q: สามารถแปลงไฟล์ PS ที่มีข้อผิดพลาดเล็กน้อยได้หรือไม่?**  
A: ได้ — ตั้งค่า `suppressErrors` เป็น `true` ใน `ImageSaveOptions` เพื่อให้การแปลงดำเนินต่อแม้มีปัญหาไม่สำคัญ

**Q: จะเพิ่มการสนับสนุนรูปแบบภาพอื่น เช่น JPEG ได้อย่างไร?**  
A: เปลี่ยน `ImageFormat.PNG` เป็น `ImageFormat.JPEG` (หรือ enum ที่รองรับอื่น) แล้วปรับนามสกุลไฟล์ในลูปบันทึก

**Q: สามารถกำหนดขนาดภาพแบบกำหนดเองได้หรือไม่?**  
A: สามารถตั้งค่าความกว้างและความสูงของ `ImageDevice` ก่อนเรียก `document.save(...)`

**Q: จะหาเอกสาร API รายละเอียดเพิ่มเติมได้จากที่ไหน?**  
A: เยี่ยมชม [documentation](https://reference.aspose.com/page/java/) อย่างเป็นทางการและฟอรั่ม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับความช่วยเหลือจากชุมชน

**Q: ต้องการลิขสิทธิ์สำหรับการสร้างบิลด์พัฒนาไหม?**  
A: ไลเซนส์ทดลองฟรีใช้ได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมจริง

## สรุป
คุณได้มีสูตรครบถ้วนและพร้อมใช้งานสำหรับ **การแปลง PS เป็น PNG** ใน Java ด้วย Aspose.Page แล้ว ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถผสานการเรนเดอร์ PostScript เข้าไปในแอปพลิเคชัน Java ใดก็ได้ — ไม่ว่าจะเป็นเว็บเซอร์วิสที่สร้างภาพย่อ, ตัวประมวลผลชุดสำหรับคลังข้อมูล, หรือเครื่องมือเดสก์ท็อปที่แสดงงานพิมพ์

---

**อัปเดตล่าสุด:** 2025-12-04  
**ทดสอบกับ:** Aspose.Page for Java 24.11 (เวอร์ชันล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}