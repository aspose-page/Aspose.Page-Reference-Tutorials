---
date: 2025-12-18
description: เรียนรู้วิธีสร้างเอกสาร PostScript ด้วย Java และเพิ่มภาพโปร่งใสโดยใช้
  Aspose.Page for Java คู่มือนี้แสดงวิธีเพิ่มภาพลงใน PostScript อย่างง่ายดาย
linktitle: Create PostScript Document Java – Add Transparent Image
second_title: Aspose.Page Java API
title: สร้างเอกสาร PostScript ด้วย Java – เพิ่มภาพโปร่งใส
url: /th/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรูปภาพโปร่งใสใน Java PostScript

## บทนำ
ในโลกของ Java PostScript การเพิ่มความสวยงามให้กับเอกสารมักเกี่ยวข้องกับการใส่รูปภาพโปร่งใส บทเรียนนี้จะสอนคุณผ่านกระบวนการ **create postscript document java** พร้อมการใช้กราฟิกโปร่งใสด้วยไลบรารี Aspose.Page for Java ที่ทรงพลัง คุณจะได้เห็นวิธีการเพิ่มรูปภาพลงใน PostScript, กำหนดตำแหน่งอย่างแม่นยำ, และควบคุมความโปร่งใสเพื่อให้ได้ผลลัพธ์ระดับมืออาชีพ

## คำตอบสั้น
- **บทเรียนนี้ครอบคลุมอะไร?** การเพิ่ม PNG โปร่งใสลงในเอกสาร PostScript ด้วย Aspose.Page for Java  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java (ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ)  
- **ต้องมีลิขสิทธิ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ชั่วคราวหรือเต็มสำหรับการใช้งานจริง; มีรุ่นทดลองฟรีให้ใช้  
- **ใช้รูปแบบไฟล์อื่นได้หรือไม่?** ใช่, แต่ PNG ที่มีช่องอัลฟาจะให้ผลลัพธ์โปร่งใสดีที่สุด  
- **ใช้เวลานานแค่ไหนในการทำ?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน

## PostScript document ใน Java คืออะไร?
PostScript document คือไฟล์ภาษาการอธิบายหน้า (page description language) ที่บรรยายข้อความ, กราฟิก, และรูปภาพ ด้วย Java คุณสามารถสร้างไฟล์เหล่านี้โดยโปรแกรมได้ ทำให้คุณควบคุมการจัดวางและการเรนเดอร์ได้อย่างเต็มที่ คำหลัก **create postscript document java** สะท้อนความสามารถนี้

## ทำไมต้องเพิ่มรูปภาพโปร่งใส?
รูปภาพโปร่งใสช่วยให้คุณวางกราฟิกทับโดยไม่บังเนื้อหาที่อยู่ด้านล่าง เหมาะสำหรับลายน้ำ, โลโก้, หรือองค์ประกอบตกแต่ง การผสมผสานความโปร่งใสกับการกำหนดตำแหน่งที่แม่นยำจะทำให้เอกสารดูเรียบหรูและสอดคล้องกับแบรนด์

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามบทเรียนนี้ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:
1. Java Development Kit (JDK): ตรวจสอบว่าคุณติดตั้ง JDK เวอร์ชันล่าสุดบนเครื่องของคุณ  
2. Aspose.Page for Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page for Java จาก [website](https://releases.aspose.com/page/java/)  
3. Document Directory: สร้างโฟลเดอร์บนระบบของคุณเพื่อเก็บเอกสาร Java PostScript  
4. Translucent Image File: เตรียมไฟล์รูปภาพโปร่งใส (เช่น "mask1.png") เพื่อใช้ในบทเรียน

## การนำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ ให้นำเข้าแพ็กเกจที่จำเป็นเพื่อใช้ฟังก์ชันของ Aspose.Page for Java ด้านล่างเป็นบล็อกการนำเข้าที่ต้องใช้อย่างครบถ้วน

```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## วิธีสร้าง **create postscript document java** พร้อมรูปภาพโปร่งใส
ต่อไปนี้คือขั้นตอนแบบละเอียด แต่ละขั้นมีคำอธิบายสั้น ๆ ตามด้วยบล็อกโค้ดต้นฉบับ (ไม่เปลี่ยนแปลง)

### ขั้นตอนที่ 1: ตั้งค่าสีพื้นหลัง
เราจะเริ่มโดยสร้างเอกสาร PostScript, เปิดสตรีมเอาต์พุต, และวาดสี่เหลี่ยมสีแดงเป็นตัวอ้างอิงสำหรับรูปภาพโปร่งใส

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Add a red rectangle under images for visual contrast
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```

### ขั้นตอนที่ 2: แปลพิกัด
ก่อนวาด เราจะย้ายจุดกำเนิดไปยังตำแหน่งที่สะดวกบนหน้าเพื่อให้รูปภาพปรากฏตรงที่ต้องการ

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

### ขั้นตอนที่ 3: สร้างอ็อบเจกต์รูปภาพ
โหลดไฟล์ PNG ที่มีช่องอัลฟา รูปภาพนี้จะใช้สำหรับการเรนเดอร์ทั้งแบบทึบและแบบโปร่งใส

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

### ขั้นตอนที่ 4: วาดรูปภาพทึบ
แรกเริ่มเราวาดรูปภาพเป็นบิตแมป RGB ปกติ เพื่อแสดงความแตกต่างเมื่อเรานำความโปร่งใสมาใช้ในขั้นต่อไป

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

### ขั้นตอนที่ 5: วาดรูปภาพโปร่งใส
ต่อมาเราวาดรูปภาพเดียวกันโดยกำหนดค่า opacity (255 = ทึบเต็ม, 0 = โปร่งใสเต็ม) คุณสามารถปรับค่าระหว่าง 0‑255 เพื่อควบคุมระดับความโปร่งใส ที่นี่ใช้ค่า 255 เพื่อแสดงผลเต็มทึบ แต่คุณสามารถลดค่าเพื่อให้เห็นเอฟเฟกต์โปร่งใสได้

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

### ขั้นตอนที่ 6: บันทึกและปิด
สุดท้ายเราจะคืนสถานะกราฟิก, ปิดหน้า, และบันทึกเอกสารลงดิสก์

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## ปัญหาที่พบบ่อยและวิธีแก้
- **FileNotFoundException** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและไฟล์ `mask1.png` มีอยู่จริง  
- **ImageIO.read returns null** – ตรวจสอบว่า PNG มีรูปแบบที่ถูกต้องและไม่เสียหาย  
- **Transparent image appears opaque** – ปรับพารามิเตอร์ที่สามของ `drawTransparentImage` (0 = โปร่งใสเต็ม, 255 = ทึบเต็ม)

## คำถามที่พบบ่อย
### สามารถใช้ Aspose.Page for Java ร่วมกับไลบรารี Java อื่นได้หรือไม่?
ได้, Aspose.Page for Java สามารถผสานรวมกับไลบรารี Java อื่น ๆ ได้อย่างราบรื่นเพื่อเพิ่มความสามารถในการประมวลผลเอกสาร

### มีรุ่นทดลองฟรีสำหรับ Aspose.Page for Java หรือไม่?
มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Page for Java ได้จาก [here](https://releases.aspose.com/)

### จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้จาก [this link](https://purchase.aspose.com/temporary-license/)

### มีฟอรั่มสนับสนุน Aspose.Page for Java หรือไม่?
มี, เยี่ยมชม [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชนและการสนทนาต่าง ๆ

### จะหาเอกสารอ้างอิงของ Aspose.Page for Java ได้ที่ไหน?
ดูเอกสารอย่างละเอียดได้ที่ [documentation](https://reference.aspose.com/page/java/)

## สรุป
ยินดีด้วย! คุณได้เรียนรู้วิธี **create postscript document java** และการเพิ่มรูปภาพโปร่งใสด้วย Aspose.Page for Java แล้ว ทดลองใช้รูปภาพ, ระดับความโปร่งใส, และตำแหน่งต่าง ๆ เพื่อสร้างเอกสารที่สวยงามและสอดคล้องกับแบรนด์ของคุณ

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}