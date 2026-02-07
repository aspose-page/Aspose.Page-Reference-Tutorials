---
date: 2026-02-07
description: เรียนรู้วิธีปรับขนาดสี่เหลี่ยมด้วย Aspose.Page สำหรับ Java, วิธีการย้ายตำแหน่งรูปร่าง,
  และการใช้การแปลงเชิงเส้นเพื่อสร้างเอกสาร PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: วิธีปรับขนาดสี่เหลี่ยมโดยใช้ Aspose.Page สำหรับ Java
url: /th/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการปรับขนาดสี่เหลี่ยมผืนผ้าด้วย Aspose.Page สำหรับ Java

## บทนำ
ยินดีต้อนรับสู่คู่มือที่ครอบคลุมในการใช้คุณสมบัติที่ทรงพลังของ **Aspose.Page for Java** เพื่อทำการแปลงหน้าต่างต่าง ๆ ในบทเรียนนี้คุณจะได้เรียนรู้ **how to scale rectangle**, การแปลรูปทรง, การหมุนวัตถุ, และเทคนิค **apply affine transform** ขณะสร้าง **PostScript document** ความสามารถเหล่านี้ช่วยให้คุณสร้างแอปพลิเคชัน Java ที่มีกราฟิกเข้มข้นโดยไม่ต้องจัดการกับโค้ดการเรนเดอร์ระดับต่ำ

## คำตอบสั้น
- **How do I scale a rectangle in Java with Aspose.Page?** ใช้เมธอด `document.scale()` ก่อนวาดรูปทรง  
- **Can I move (translate) a shape without affecting other graphics?** ใช่—บันทึกสถานะกราฟิก, เรียก `document.translate(x, y)`, วาด, แล้วกู้คืนสถานะ  
- **What class creates a PostScript file?** `PsDocument` ร่วมกับ `PsSaveOptions`  
- **Do I need a license for production use?** จำเป็นต้องมีใบอนุญาต Aspose.Page ที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์  
- **Which Java version is supported?** Aspose.Page ทำงานกับ Java 8 และรุ่นต่อไป  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในคู่มือแบบขั้นตอน โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)  
- สภาพแวดล้อมการพัฒนา Java (IDE) ตั้งค่าไว้บนเครื่องของคุณ  

## นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ ให้นำเข้าแพ็กเกจที่จำเป็นเพื่อใช้ Aspose.Page for Java:

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
การปรับขนาดสี่เหลี่ยมผืนผ้าจะเปลี่ยนขนาดของมันตามแกน X และ Y ในขณะที่คงรูปทรงไว้ Aspose.Page เปิดเผยเมธอด `scale(float sx, float sy)` ซึ่งทำการ **affine transform** กับสถานะกราฟิกปัจจุบัน นี่คือเทคนิคหลักที่อยู่เบื้องหลังคีย์เวิร์ด **how to scale rectangle**

## วิธีการแปลรูปทรงด้วย Aspose.Page
การแปล (translation) จะย้ายรูปทรงไปยังตำแหน่งใหม่โดยไม่เปลี่ยนแปลงขนาดของมัน นี่คือสาระสำคัญของ **how to translate shape** โดยการบันทึกสถานะกราฟิก, ใช้ `translate(dx, dy)`, วาด, แล้วกู้คืนสถานะ คุณจะทำให้วัตถุอื่นไม่ถูกกระทบ  

## ตัวอย่าง 1: ไม่มีการแปลง
ตัวอย่างแรกวาดสี่เหลี่ยมผืนผ้าง่าย ๆ โดยไม่มีการแปลงใด ๆ ใช้เป็นฐานสำหรับเปรียบเทียบกับตัวอย่างต่อไป

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

## ตัวอย่าง 2: การแปล (Translation)
ที่นี่เราจะแสดง **how to translate shape** โดยย้ายบริบทกราฟิกไปทางขวา 250 หน่วยก่อนวาดสี่เหลี่ยมผืนผ้าครั้งที่สอง

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

## ตัวอย่าง 3: การปรับขนาด (Scaling)
ตัวอย่างนี้ตอบคำถามหลัก **how to scale rectangle** เราจะย่อสี่เหลี่ยมผืนผ้าให้เหลือ 50 % ของความกว้างเดิมและ 75 % ของความสูงเดิม

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

## วิธีการหมุนรูปทรงใน Java (rotate shape java)
การหมุนเป็นการดำเนินการ affine ที่พบบ่อยอีกอย่างหนึ่ง แม้ว่าตัวอย่างโค้ดสำหรับการหมุนจะถูกละไว้เพื่อความกระชับ รูปแบบก็เหมือนกัน: บันทึกสถานะกราฟิก, เรียก `document.rotate(angle)`, วาดรูปทรง, แล้วกู้คืน นี่แสดงให้เห็น **rotate shape java** และ **how to rotate rectangle** ในการปฏิบัติ  

## ทำไมเรื่องนี้ถึงสำคัญ – ประโยชน์ในโลกจริง
- **Device‑independent output** – เขียนครั้งเดียวและสร้าง PostScript หรือ XPS โดยไม่ต้องปรับแต่งตามแพลตฟอร์ม  
- **Fine‑grained control** – รวมการแปล, การปรับขนาด, การตัดเฉือน (shearing), และการหมุนเพื่อให้ตรงกับข้อกำหนดการจัดวางที่แม่นยำ  
- **Performance‑oriented** – API ที่มีค่าโอเวอร์เฮดต่ำ เหมาะสำหรับการประมวลผลแบบแบตช์ของเอกสารขนาดใหญ่  

## กรณีการใช้งานทั่วไป
- การสร้างใบแจ้งหนี้ที่พิมพ์ได้ – ตัวอย่างเช่น โซลูชัน **printable invoice java** ที่วางโลโก้และบาร์โค้ดอย่างแม่นยำ  
- การสร้างแผนภาพเทคนิคที่ต้องการการปรับขนาดและตำแหน่งที่แม่นยำ  
- การอัตโนมัติการผลิตรายงานหลายหน้าในรูปแบบ PostScript  

## ปัญหาทั่วไปและวิธีแก้
- **Transformation not resetting** – ควรใช้ `document.writeGraphicsSave()` คู่กับ `document.writeGraphicsRestore()` เสมอเพื่อหลีกเลี่ยงผลกระทบที่ไม่ต้องการ  
- **Unexpected colors** – ตรวจสอบว่าคุณตั้งค่าสีหลังการแปลงแต่ละครั้ง; สถานะกราฟิกจะไม่เก็บการตั้งค่าสีก่อนหน้าหลังการกู้คืน  
- **File size too large** – ใช้ `PsSaveOptions` เพื่อเปิดการบีบอัดหรือ ลดความละเอียดของภาพเมื่อฝังกราฟิกแบบเรสเตอร์  

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page for Java กับรูปแบบเอกสารอื่นได้หรือไม่?
Aspose.Page มุ่งเน้นที่การจัดการหน้าสำหรับรูปแบบ PostScript และ XPS เป็นหลัก  

### ฉันจะหา ตัวอย่างและเอกสารเพิ่มเติมสำหรับ Aspose.Page for Java ได้จากที่ไหน?
เยี่ยมชม [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) เพื่อข้อมูลที่ครอบคลุม  

### มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?
ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](https://releases.aspose.com/)  

### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
รับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)  

### ฉันจะหาการสนับสนุนจากชุมชนหรือถามคำถามเกี่ยวกับ Aspose.Page for Java ได้จากที่ไหน?
เยี่ยมชม [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) เพื่อการสนทนาชุมชน  

## คำถามที่พบบ่อย

**Q: ความแตกต่างระหว่าง `translate` กับ `scale` คืออะไร?**  
A: `translate` ย้ายจุดกำเนิดของระบบพิกัด, ส่วน `scale` เปลี่ยนขนาดของวัตถุที่วาดตามแกน X และ/หรือ Y  

**Q: ฉันสามารถรวมการแปลงหลายอย่างในสถานะกราฟิกเดียวได้หรือไม่?**  
A: ใช่—โดยเรียก `translate`, `scale`, `rotate`, หรือ `shear` ต่อเนื่องกันก่อนวาด คุณจะสร้างการแปลง affine แบบรวม  

**Q: ฉันจะรีเซ็ตการแปลงหลังจากวาดรูปทรงได้อย่างไร?**  
A: ใช้ `document.writeGraphicsRestore()` เพื่อกลับสู่สถานะกราฟิกที่บันทึกไว้ก่อนหน้า  

**Q: สามารถหมุนสี่เหลี่ยมผืนผ้ารอบศูนย์กลางได้หรือไม่?**  
A: แน่นอน. แปลสี่เหลี่ยมผืนผ้าไปยังจุดกำเนิด, ใช้ `rotate(angle)`, แล้วแปลกลับก่อนวาด  

**Q: Aspose.Page รองรับการทำ anti‑aliasing เพื่อกราฟิกที่เรียบเนียนหรือไม่?**  
A: ใช่—ตั้งค่าตัวเลือกการเรนเดอร์ที่เหมาะสมใน `PsSaveOptions` เพื่อเปิดใช้งาน anti‑aliasing  

---

**อัปเดตล่าสุด:** 2026-02-07  
**ทดสอบด้วย:** Aspose.Page for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}