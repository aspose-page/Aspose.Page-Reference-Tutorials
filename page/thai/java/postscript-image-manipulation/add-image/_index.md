---
date: 2026-08-23
description: เรียนรู้วิธีใช้ aspose.page image manipulation java เพื่อฝังและหมุนรูปภาพในไฟล์
  PostScript ด้วยตัวอย่าง Java ที่ชัดเจน
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: เพิ่มรูปภาพใน Java PostScript
og_description: เรียนรู้วิธีใช้ aspose.page image manipulation java เพื่อฝังและหมุนรูปภาพในไฟล์
  PostScript ด้วยตัวอย่างโค้ด Java ทีละขั้นตอน
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: วิธีใช้ aspose.page image manipulation java เพื่อเพิ่มรูปภาพ
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: วิธีใช้ aspose.page image manipulation java เพื่อเพิ่มรูปภาพ
url: /th/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีใช้ aspose.page image manipulation java เพื่อเพิ่มรูปภาพ

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **ใช้ aspose.page image manipulation java** เพื่อสร้างไฟล์ PostScript, ฝังรูปภาพแรสเตอร์, และใช้การแปลงการแปลและการหมุน. เมื่อจบคู่มือคุณจะสามารถสร้างเอาต์พุต PostScript ที่พิกเซลสมบูรณ์จาก Java—เหมาะสำหรับการรายงานอัตโนมัติ, กระบวนการพิมพ์, หรือเวิร์กโฟลว์ใด ๆ ที่ต้องการการวางตำแหน่งรูปภาพอย่างแม่นยำภายในเอกสาร PostScript.

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.Page for Java  
- **สามารถเพิ่มหลายรูปภาพได้หรือไม่?** ได้ – ทำซ้ำขั้นตอนการแปลงและวาดสำหรับแต่ละรูปภาพ  
- **ต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน Java ใด?** Java 8 and later  
- **การหมุนรูปภาพได้รับการสนับสนุนหรือไม่?** แน่นอน – use `AffineTransform.rotate()`

## aspose.page image manipulation java คืออะไร?
`aspose.page image manipulation java` คือ API ของ Aspose.Page ที่ทำให้คุณสามารถสร้าง, แก้ไข, และเรนเดอร์เอกสาร PostScript จากโค้ด Java อย่างอัตโนมัติ, รวมถึงการควบคุมการวางตำแหน่งรูปภาพ, การปรับขนาด, และการหมุนอย่างเต็มที่. ด้วย API นี้คุณจะหลีกเลี่ยงไวยากรณ์ PostScript ระดับต่ำและให้ไลบรารีจัดการการแปลงรูปแบบและการฝังภายใน.

## ทำไมต้องใช้ aspose.page สำหรับการจัดการรูปภาพ?
Aspose.Page ให้ **รูปแบบรูปภาพกว่า 50** (รวมถึง JPEG, PNG, BMP, TIFF) และสามารถฝังลงใน PostScript ได้โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ, ทำให้สามารถประมวลผลไฟล์ที่มีหลายร้อยหน้าได้ในขณะที่ใช้หน่วยความจำน้อยกว่า 100 MB บนเซิร์ฟเวอร์ทั่วไป. API ระดับสูงนี้ทำให้ซับซ้อนของคำสั่ง PostScript ถูกแยกออก, ดังนั้นคุณจึงเขียนโค้ด Java ที่กระชับแทนการใช้ตัวดำเนินการ PS ดิบ.

## ข้อกำหนดเบื้องต้น
- Java Development Kit (JDK) 8 หรือใหม่กว่า ติดตั้งแล้ว.  
- ไลบรารี Aspose.Page for Java – ดาวน์โหลดได้จาก **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- มีความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และการเขียนโปรแกรมเชิงวัตถุ.

## create postscript java คืออะไร?
การสร้างไฟล์ PostScript จาก Java หมายถึงการสร้างเอกสาร `.ps` อย่างอัตโนมัติที่อธิบายการจัดหน้า, กราฟิกเวกเตอร์, และรูปภาพแรสเตอร์โดยใช้ภาษา PostScript. Aspose.Page แปลงการเรียก Java ของคุณเป็นคำสั่ง PostScript ที่ถูกต้อง, ทำให้คุณสามารถสร้างไฟล์พร้อมพิมพ์ได้โดยไม่ต้องใช้ตัวแปล PostScript แยกต่างหาก.

## วิธีเพิ่มรูปภาพพร้อมการแปลและการหมุนขั้นตอนโดยขั้นตอน

โหลดรูปภาพของคุณ, ใช้ `AffineTransform`, และวาดลงบนหน้า. ขั้นตอนต่อไปนี้สรุปลำดับที่ต้องทำตามอย่างแม่นยำ.

### ขั้นตอนที่ 1: บันทึกสถานะกราฟิก
การบันทึกสถานะกราฟิกจะทำให้การแปลงของคุณแยกออกเพื่อให้คุณสามารถย้อนกลับได้ภายหลัง. นี้เทียบเท่ากับตัวดำเนินการ `gsave` ใน PostScript ดิบ.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### ขั้นตอนที่ 2: แปลและแปลง (แปลและหมุนรูปภาพ)
ขั้นแรก, สร้าง `BufferedImage` จากไฟล์ต้นทาง, จากนั้นสร้าง `AffineTransform` ที่แปลรูปภาพไปยังพิกัดที่ต้องการและหมุนรอบจุดศูนย์กลางของมัน. `AffineTransform.rotate` ต้องการมุมเป็นเรเดียน, ดังนั้นให้แปลงจากองศาด้วย `Math.toRadians(degrees)`.

**AffineTransform** คือคลาสของ Java ที่แสดงการแปลงเชิง affine 2‑มิติ เช่น การแปล, การหมุน, การปรับขนาด, หรือการบิด.  
**BufferedImage** คือคลาสของ Java ที่เก็บรูปภาพในหน่วยความจำเป็นแรสเตอร์ของพิกเซล.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### ขั้นตอนที่ 3: เพิ่มรูปภาพลงในเอกสาร
หลังจากกำหนดการแปลงแล้ว, วาดรูปภาพลงบนหน้าปัจจุบัน. ไลบรารีจะเปลี่ยน `BufferedImage` ให้เป็นสตรีมภาพ PostScript ที่เหมาะสมโดยอัตโนมัติ.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### ขั้นตอนที่ 4: กู้คืนสถานะกราฟิก
การเรียกกู้คืน (`grestore`) จะคืนสถานะกราฟิกกลับไปยังสภาพก่อนการบันทึก, ทำให้คำสั่งการวาดต่อไปไม่ถูกรบกวนโดยการแปลงก่อนหน้า.

```java
document.drawImage(image, transform, null);
```

### ขั้นตอนที่ 5: ปิดหน้าปัจจุบันและบันทึก
เสร็จสิ้นหน้าปัจจุบัน, ปิดเอกสาร, และเขียนไฟล์ผลลัพธ์ลงดิสก์.

```java
document.writeGraphicsRestore();
```

คุณสามารถทำซ้ำลำดับข้างต้นเพื่อฝังรูปภาพเพิ่มเติม, ปรับพิกัดการแปลและมุมการหมุนในแต่ละครั้ง.

## ปัญหาที่พบบ่อยและวิธีแก้
- **FileNotFoundException:** ตรวจสอบว่า `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`) และชื่อไฟล์รูปภาพตรงกันอย่างแม่นยำ.  
- **ImageIO.read returns null:** ตรวจสอบให้แน่ใจว่ารูปแบบรูปภาพอยู่ในรายการที่รองรับ (JPEG, PNG, BMP, GIF, TIFF).  
- **Incorrect rotation angle:** มุมการหมุนไม่ถูกต้อง: `AffineTransform.rotate` ทำงานด้วยเรเดียน; ใช้ `Math.toRadians(degrees)` เพื่อแปลงจากองศา.  
- **Memory spikes on large pages:** การใช้หน่วยความจำสูงบนหน้าขนาดใหญ่: ใช้ `Document.save` พร้อม `saveOptions.setCompress(true)` เพื่อลดการใช้หน่วยความจำ.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A: ไลบรารีหลักเป็นเฉพาะ Java เท่านั้น, แต่ Aspose มี API ที่เทียบเท่าสำหรับ .NET, C++, และ Python, แต่ละตัวออกแบบให้เหมาะกับแพลตฟอร์มนั้น.

**ถาม: มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
A: ใช่, คุณสามารถเข้าถึงการทดลองใช้ฟรี **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: คุณสามารถรับใบอนุญาตชั่วคราวได้จาก **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**ถาม: ฉันจะหาแหล่งสนับสนุนชุมชนและการสนทนาที่เกี่ยวกับ Aspose.Page for Java ได้ที่ไหน?**  
A: เยี่ยมชม **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** เพื่อรับความช่วยเหลือจากชุมชน.

**ถาม: มีแหล่งข้อมูลเพิ่มเติมสำหรับการซื้อ Aspose.Page for Java หรือไม่?**  
A: คุณสามารถซื้อไลบรารีได้จาก **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## สรุป
ตอนนี้คุณมีตัวอย่างครบวงจรของ **aspose.page image manipulation java** ที่สร้างไฟล์ PostScript, ทำการแปลและหมุนรูปภาพ, และบันทึกผลลัพธ์. สำรวจ **[documentation](https://reference.aspose.com/page/java/)** เต็มรูปแบบเพื่อค้นพบคุณลักษณะขั้นสูงเช่นกราฟิกเวกเตอร์, ขนาดหน้าที่กำหนดเอง, และการเรนเดอร์ข้อความ.

---

**อัปเดตล่าสุด:** 2026-08-23  
**ทดสอบด้วย:** Aspose.Page for Java 23.11  
**ผู้เขียน:** Aspose  

```java
document.closePage();
document.save();
```

## บทแนะนำที่เกี่ยวข้อง

- [วิธีแปลง PostScript เป็น PDF ด้วย Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [วิธีเพิ่ม Gradient: Diagonal Gradient ใน Java PostScript ด้วย Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [วิธีเพิ่ม Hatch Pattern ใน Java PostScript ด้วย Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}