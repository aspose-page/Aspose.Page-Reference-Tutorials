---
date: 2026-10-20
description: เรียนรู้วิธีการปรับขนาดสี่เหลี่ยมด้วย Aspose.Page for Java, วิธีการย้ายตำแหน่งรูปร่าง,
  และการใช้ affine transform เพื่อสร้างเอกสาร PostScript
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: การแปลงในการจัดการหน้า Java
og_description: เรียนรู้วิธีการปรับขนาดสี่เหลี่ยม, ย้ายตำแหน่งรูปร่าง, และใช้ affine
  transform ด้วย Aspose.Page for Java เพื่อสร้างไฟล์ PostScript อย่างมีประสิทธิภาพ
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: วิธีการปรับขนาดสี่เหลี่ยมด้วย Aspose.Page for Java – คู่มือขั้นตอนโดยละเอียด
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: วิธีการปรับขนาดสี่เหลี่ยมโดยใช้ Aspose.Page for Java
url: /th/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการปรับขนาดสี่เหลี่ยมโดยใช้ Aspose.Page for Java

## บทนำ
ในคู่มือนี้คุณจะได้ค้นพบ **วิธีการปรับขนาดสี่เหลี่ยม** ด้วย Aspose.Page for Java พร้อมทั้งเรียนรู้วิธีการแปลตำแหน่งรูปร่าง, หมุนกราฟิก, และใช้การแปลงเชิง affine เพื่อสร้างผลลัพธ์ PostScript คุณภาพสูง เทคนิคเหล่านี้ช่วยให้คุณสร้างกราฟิกที่ซับซ้อนและอิสระต่ออุปกรณ์โดยไม่ต้องเขียนโค้ดการเรนเดอร์ระดับต่ำ ทำให้แอปพลิเคชัน Java ของคุณมีประสิทธิภาพและบำรุงรักษาง่ายขึ้น

## คำตอบอย่างรวดเร็ว
`scale(sx, sy)` ปรับขนาดบริบทกราฟิกตามปัจจัยแนวนอนและแนวตั้งที่กำหนด  

- **ฉันจะปรับขนาดสี่เหลี่ยมใน Java ด้วย Aspose.Page อย่างไร?** เรียกเมธอด `scale(sx, sy)` บนบริบทกราฟิกก่อนวาดสี่เหลี่ยม  
- **ฉันสามารถย้าย (แปล) รูปร่างโดยไม่กระทบกราฟิกอื่นได้หรือไม่?** ได้—ห่อการแปลด้วยการเรียก `writeGraphicsSave()` และ `writeGraphicsRestore()`  
- **คลาสใดสร้างไฟล์ PostScript?** ใช้ `PsDocument` ร่วมกับ `PsSaveOptions`  
- **ฉันต้องมีใบอนุญาตสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีใบอนุญาต Aspose.Page ที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์  
- **รองรับเวอร์ชัน Java ใด?** Aspose.Page ทำงานกับ Java 8 ขึ้นไป

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบว่าคุณมี:

- ความเข้าใจพื้นฐานที่มั่นคงเกี่ยวกับไวยากรณ์ Java และแนวคิดเชิงวัตถุ  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)  
- IDE สำหรับ Java (IntelliJ IDEA, Eclipse หรือ VS Code) ที่ตั้งค่าให้รวมไฟล์ JAR ของไลบรารีใน classpath

## นำเข้าแพ็กเกจ
`PsDocument` เป็นคลาสหลักที่ใช้สร้างเอกสาร PostScript, ส่วน `PsSaveOptions` กำหนดวิธีการบันทึกเอกสาร  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## “how to scale rectangle” คืออะไรใน Aspose.Page?
เมธอด `scale(float sx, float sy)` ใช้การแปลงเชิง affine เพื่อปรับขนาดสเกลของสถานะกราฟิกปัจจุบัน, ทำให้การวาดต่อไปถูกปรับขนาดตามปัจจัย `sx` (แนวนอน) และ `sy` (แนวตั้ง) นี่คือการดำเนินการหลักที่อยู่เบื้องหลังคีย์เวิร์ด **how to scale rectangle** โดยการใช้การแปลงนี้ก่อนการวาด, รูปร่างใด ๆ เช่น สี่เหลี่ยม จะถูกเรนเดอร์ด้วยมิติใหม่พร้อมคงอัตราส่วนเดิม

## วิธีการแปลตำแหน่งรูปร่างด้วย Aspose.Page
`writeGraphicsSave()` บันทึกสถานะกราฟิกปัจจุบันและ `writeGraphicsRestore()` คืนค่าสถานะนั้น, ทำให้การแปลงมีผลเฉพาะกับรูปร่างที่ต้องการเท่านั้น การแปลตำแหน่ง (`translate(dx, dy)`) ย้ายจุดกำเนิดของระบบพิกัดโดยไม่เปลี่ยนขนาดวัตถุ โดยการห่อ `translate(dx, dy)` ด้วย `writeGraphicsSave()` / `writeGraphicsRestore()` คุณจะทำให้เฉพาะรูปร่างที่ต้องการเคลื่อนที่ ส่วนกราฟิกอื่นคงที่, ให้การควบคุมที่แม่นยำต่อแต่ละองค์ประกอบ

## ตัวอย่างที่ 1: ไม่มีการแปลงรูป
ตัวอย่างแรกวาดสี่เหลี่ยมโดยไม่มีการแปลงใด ๆ เพื่อเป็นฐานเปรียบเทียบกับตัวอย่างต่อไป  

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## ตัวอย่างที่ 2: การแปลตำแหน่ง
ในตัวอย่างนี้เราย้ายบริบทกราฟิก 250 หน่วยไปทางขวาก่อนวาดสี่เหลี่ยมที่สอง, แสดง **วิธีการแปลตำแหน่งรูปร่าง**  

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## ตัวอย่างที่ 3: การปรับขนาด
ที่นี่เราตอบคำถามหลัก **how to scale rectangle** สี่เหลี่ยมถูกลดลงเหลือ 50 % ของความกว้างเดิมและ 75 % ของความสูงเดิมโดยใช้คำสั่ง `scale(0.5f, 0.75f)`  

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## วิธีการหมุนรูปร่างใน Java (rotate shape java)
`rotate(angle)` หมุนระบบพิกัดตามมุมที่กำหนดเป็นองศา โหลด `PsDocument` ของคุณ, เรียก `rotate(angle)` บนสถานะกราฟิก, วาดรูปร่าง, แล้วคืนค่าสถานะก่อนหน้า รูปแบบนี้ทำให้ **rotate shape java** และ **how to rotate rectangle** ทำงานในบล็อกเดียวที่สามารถนำกลับใช้ใหม่ได้, ช่วยให้คุณหมุนกราฟิกรอบจุดใดก็ได้ที่ต้องการ

## ทำไมเรื่องนี้สำคัญ – ประโยชน์ในโลกจริง
- **ผลลัพธ์อิสระต่ออุปกรณ์** – Aspose.Page สามารถสร้างไฟล์ PostScript และ XPS ที่แสดงผลเหมือนกันบนเครื่องพิมพ์หรือโปรแกรมดูใด ๆ, ลดความจำเป็นในการปรับแต่งตามแพลตฟอร์ม  
- **การควบคุมละเอียด** – ผสานการแปล, ปรับขนาด, การเฉือน, และการหมุนเพื่อให้ตรงตามข้อกำหนดการจัดวาง; API รองรับการแปลงมากกว่า 20 แบบต่อหน้า  
- **ประสิทธิภาพสูง** – ไลบรารีประมวลผลเอกสารด้วยหน่วยความจำต่ำกว่า 10 MB สำหรับรายงาน 100‑หน้าแบบทั่วไป, ทำให้งานแบตช์ทำงานเร็วและขยายขนาดได้

## กรณีการใช้งานทั่วไป
- **ใบแจ้งหนี้ที่พิมพ์ได้** – วางโลโก้, บาร์โค้ด, และตารางอย่างแม่นยำโดยใช้การปรับขนาดและการแปลตำแหน่งให้สอดคล้องกับแนวทางแบรนด์ขององค์กร  
- **แผนภาพเทคนิค** – สร้างสเคมาที่แต่ละส่วนต้องปรับขนาดและตำแหน่งอย่างสัดส่วน  
- **รายงานหลายหน้าอัตโนมัติ** – สร้างรายงาน PostScript ที่ต้องการการปรับขนาดสม่ำเสมอระหว่างหน้า, เช่น สเปควิศวกรรม

## ปัญหาที่พบบ่อยและวิธีแก้
- **การแปลงไม่รีเซ็ต** – ต้องจับคู่ `writeGraphicsSave()` กับ `writeGraphicsRestore()` เสมอ; มิฉะนั้นการวาดต่อไปจะสืบทอดการแปลงที่ไม่ต้องการ  
- **สีไม่คาดคิด** – ตั้งสี (paint) หลังการแปลงแต่ละครั้ง เพราะสถานะกราฟิกไม่เก็บข้อมูลสีหลังการคืนค่า  
- **ขนาดไฟล์ใหญ่เกินไป** – เปิดการบีบอัดใน `PsSaveOptions` และจำกัดความละเอียดของภาพเรสเตอร์ที่ฝังไว้เพื่อให้ไฟล์สุดท้ายอยู่ต่ำกว่า 5 MB สำหรับเอกสาร 50‑หน้าทั่วไป

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Page for Java กับรูปแบบเอกสารอื่นได้หรือไม่?
Aspose.Page มุ่งเน้นการจัดการหน้าสำหรับรูปแบบ PostScript และ XPS, แต่ยังมีความสามารถจำกัดในการส่งออกเป็น PDF

### ฉันจะหา ตัวอย่างและเอกสารเพิ่มเติมสำหรับ Aspose.Page for Java ได้ที่ไหน?
เยี่ยมชม [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) เพื่อดูคู่มือครบถ้วน, เอกสารอ้างอิง API, และโครงการตัวอย่าง

### มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?
ใช่, คุณสามารถเข้าถึงการทดลองใช้ฟรีได้จากหน้า **Aspose free trial download**: [Aspose free trial download](https://releases.aspose.com/)

### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
ขอรับใบอนุญาตชั่วคราวผ่านหน้า **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/)

### ฉันจะหาแหล่งสนับสนุนจากชุมชนหรือถามคำถามเกี่ยวกับ Aspose.Page for Java ได้ที่ไหน?
เยี่ยมชม [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) เพื่อเข้าร่วมการสนทนาชุมชน, ตัวอย่างโค้ด, และเคล็ดลับการแก้ปัญหา

## คำถามที่พบบ่อย

**Q: ความแตกต่างระหว่าง `translate` กับ `scale` คืออะไร?**  
A: `translate` ย้ายจุดกำเนิดของระบบพิกัด, ส่วน `scale` เปลี่ยนขนาดของวัตถุที่วาดตามแกน X และ/หรือ Y

**Q: ฉันสามารถรวมการแปลงหลายอย่างในสถานะกราฟิกเดียวได้หรือไม่?**  
A: ได้—โดยเรียก `translate`, `scale`, `rotate`, หรือ `shear` ตามลำดับก่อนการวาด, คุณจะสร้างการแปลงเชิง affine ร่วมกัน

**Q: ฉันจะรีเซ็ตการแปลงหลังวาดรูปร่างอย่างไร?**  
A: ใช้ `writeGraphicsRestore()` เพื่อกลับสู่สถานะกราฟิกที่บันทึกไว้ก่อนหน้า

**Q: สามารถหมุนสี่เหลี่ยมรอบศูนย์กลางได้หรือไม่?**  
A: แน่นอน. ย้ายสี่เหลี่ยมไปที่จุดกำเนิด, ใช้ `rotate(angle)`, แล้วย้ายกลับก่อนวาด

**Q: Aspose.Page รองรับการทำ anti‑aliasing เพื่อกราฟิกที่เรียบเนียนหรือไม่?**  
A: รองรับ—ตั้งค่าตัวเลือกการเรนเดอร์ที่เหมาะสมใน `PsSaveOptions` เพื่อเปิดใช้งาน anti‑aliasing

---

**Last Updated:** 2026-10-20  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [How to Draw Rectangle in Java PostScript with Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Create Radial Gradient in PostScript with Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Postscript Page Manipulation](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}