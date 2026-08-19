---
date: 2026-03-05
description: เรียนรู้วิธีตั้งค่าสีพื้นหลังใน Java และเพิ่มภาพโปร่งใสลงใน PostScript
  ด้วย Aspose.Page for Java แปลง PNG เป็น PostScript อย่างง่ายดาย.
linktitle: Add Transparent Image in Java PostScript
second_title: Aspose.Page Java API
title: 'ตั้งค่าสีพื้นหลังใน Java: เพิ่มภาพโปร่งใสใน PS'
url: /th/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าสีพื้นหลัง Java: เพิ่มภาพโปร่งใสใน PS

## Introduction
หากคุณต้องการ **set background color java** ขณะทำงานกับ Java PostScript การเพิ่มภาพโปร่งใสสามารถทำให้เอกสารของคุณดูเรียบหรูและเป็นมืออาชีพได้ ในบทแนะนำนี้เราจะพาคุณผ่านกระบวนการทั้งหมดของการตั้งค่าสีพื้นหลัง, การแปลง PNG เป็น PostScript, และการวาดภาพที่ทึบและโปร่งใสโดยใช้ไลบรารี Aspose.Page for Java เมื่อเสร็จคุณจะสามารถ **add image to postscript** ไฟล์ด้วยการควบคุมความทึบแสงได้เต็มที่

## Quick Answers
- **What library handles transparency in Java PostScript?** Aspose.Page for Java.  
- **Can I set a background color before drawing images?** Yes – use `document.setPaint()` and `fill()`.  
- **How do I convert PNG to PostScript?** Load the PNG with `ImageIO.read()` and draw it with `drawImage` or `drawTransparentImage`.  
- **Is opacity supported for images?** Use `drawTransparentImage` to specify an opacity value (0‑255).  
- **Do I need a license for production use?** A valid Aspose.Page for Java license is required; a free trial is available.

## Prerequisites
ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK)** – ติดตั้งเวอร์ชันล่าสุดแล้ว  
2. **Aspose.Page for Java** – ดาวน์โหลดจาก [website](https://releases.aspose.com/page/java/)  
3. **Document Directory** – โฟลเดอร์ที่คุณจะบันทึกไฟล์ PostScript  
4. **Translucent Image File** – เช่น `mask1.png` ซึ่งเราจะใช้เพื่อสาธิตการทำให้โปร่งใส

## Import Packages
ในโปรเจกต์ Java ของคุณ ให้นำเข้าคลาสที่จำเป็น บล็อกนี้จะคงไว้เช่นเดิม:

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

## Step 1: Set Background Color Java
ที่นี่เราจะสร้างเอกสาร เลือกขนาด A4 และเติมสี่เหลี่ยมสีแดงเพื่อแสดงความแตกต่างของพื้นหลัง

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

## Step 2: Translate Coordinates
ย้ายเคอร์เซอร์การวาดไปยังตำแหน่งที่สะดวกบนหน้า ก่อนวางภาพ

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

## Step 3: Create Image Object
โหลดไฟล์ PNG (ขั้นตอน **convert png to postscript** ของเรา)

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

## Step 4: Add Opaque Image
วาดภาพตามปกติ—นี่เป็นการสาธิต **add image to postscript** โดยไม่มีความโปร่งใส

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

## Step 5: Add Transparent Image (draw image with opacity)
ตอนนี้เราจะใช้ `drawTransparentImage` เพื่อเรนเดอร์ PNG เดียวกันด้วยความทึบเต็ม (255) ปรับค่าตามต้องการเพื่อควบคุมความโปร่งใส

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

## Step 6: Save and Close
สรุปเอกสารและปล่อยทรัพยากร

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## Why This Matters
การตั้งค่าสีพื้นหลังด้วย Java จะให้แคนวาสที่ช่วยเน้นกราฟิกที่วางทับได้ การผสานกับ **draw image with opacity** ทำให้คุณสร้างลายน้ำ, โลโก้ หรือโมเก็ต UI โดยตรงใน PostScript โดยไม่ต้องใช้เครื่องมือแก้ไขภายนอก

## Common Issues & Tips
- **Image not appearing transparent:** ตรวจสอบว่า PNG มีช่อง alpha จริงหรือไม่  
- **Incorrect colors:** จำไว้ว่าสี่เหลี่ยมพื้นหลังถูกวาดก่อนภาพ; ปรับค่า `Color` ให้ตรงกับการออกแบบของคุณ  
- **Performance:** สำหรับเอกสารขนาดใหญ่ ให้ใช้ตัวอย่าง `AffineTransform` เพียงตัวเดียวเพื่อ ลดการสร้างอ็อบเจ็กต์ใหม่

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java with other Java libraries?**  
A: ใช่, Aspose.Page for Java สามารถผสานรวมกับไลบรารี Java อื่น ๆ ได้อย่างราบรื่นเพื่อเพิ่มความสามารถในการประมวลผลเอกสาร

**Q: Is a free trial available for Aspose.Page for Java?**  
A: ใช่, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.Page for Java ได้จาก [here](https://releases.aspose.com/)

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: คุณสามารถรับใบอนุญาตชั่วคราวได้จาก [this link](https://purchase.aspose.com/temporary-license/)

**Q: Are there any forums for Aspose.Page for Java support?**  
A: มี, เยี่ยมชม [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา

**Q: Where can I find the documentation for Aspose.Page for Java?**  
A: ดูเอกสารอย่างละเอียดใน [documentation](https://reference.aspose.com/page/java/) เพื่อข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Page for Java

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}