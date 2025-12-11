---
date: 2025-12-07
description: เรียนรู้วิธีการปรับขนาดสี่เหลี่ยม, ย้ายรูปทรง, และใช้การแปลงแอฟฟินใน
  Java ด้วย Aspose.Page เพื่อสร้างเอกสาร PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: วิธีปรับขนาดสี่เหลี่ยมและใช้การแปลงด้วย Aspose.Page
url: /th/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีปรับขนาดสี่เหลี่ยมและใช้การแปลงกับ Aspose.Page

## บทนำ
ยินดีต้อนรับสู่คู่มือฉบับสมบูรณ์ในการใช้คุณสมบัติที่ทรงพลังของ **Aspose.Page for Java** เพื่อทำการแปลงหน้าในรูปแบบต่าง ๆ ในบทเรียนนี้คุณจะได้เรียนรู้ **how to scale rectangle**, การแปลรูปทรง, การหมุนวัตถุ, และเทคนิค **apply affine transform** ขณะสร้าง **PostScript document** ความสามารถเหล่านี้ช่วยให้คุณสร้างแอปพลิเคชัน Java ที่มีกราฟิกหนาแน่นโดยไม่ต้องจัดการกับโค้ดการเรนเดอร์ระดับต่ำ

## คำตอบสั้น
- **ฉันจะปรับขนาดสี่เหลี่ยมใน Java ด้วย Aspose.Page อย่างไร?** ใช้เมธอด `document.scale()` ก่อนวาดรูปทรง  
- **ฉันสามารถย้าย (แปล) รูปทรงโดยไม่กระทบกราฟิกอื่นได้หรือไม่?** ได้—บันทึกสถานะกราฟิก, เรียก `document.translate(x, y)`, วาด, แล้วคืนสถานะเดิม  
- **คลาสใดสร้างไฟล์ PostScript?** `PsDocument` ร่วมกับ `PsSaveOptions`  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ Aspose.Page ที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์  
- **รองรับเวอร์ชัน Java ใด?** Aspose.Page ทำงานกับ Java 8 ขึ้นไป

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในขั้นตอนต่าง ๆ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งานแล้ว:

- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)  
- มี Integrated Development Environment (IDE) สำหรับ Java ตั้งค่าไว้บนเครื่องของคุณ

## นำเข้าแพ็กเกจ
ในโครงการ Java ของคุณ ให้นำเข้าแพ็กเกจที่จำเป็นเพื่อใช้ Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## “how to scale rectangle” ใน Aspose.Page คืออะไร?
การปรับขนาดสี่เหลี่ยมหมายถึงการเปลี่ยนขนาดตามแกน X และ Y ในขณะที่รักษารูปร่างเดิมไว้ Aspose.Page มีเมธอด `scale(float sx, float sy)` ซึ่งทำการ **affine transform** กับสถานะกราฟิกปัจจุบัน นี่คือเทคนิคหลักที่อยู่เบื้องหลังคีย์เวิร์ด **how to scale rectangle**

## วิธีแปลรูปทรงด้วย Aspose.Page
การแปล (translation) ย้ายรูปทรงไปยังตำแหน่งใหม่โดยไม่เปลี่ยนขนาดของมัน นี่คือสาระของ **how to translate shape** โดยบันทึกสถานะกราฟิก, ใช้ `translate(dx, dy)`, วาดรูป, แล้วคืนสถานะเดิม คุณจึงไม่กระทบวัตถุอื่น

## ตัวอย่างที่ 1: ไม่มีการแปลง
ตัวอย่างแรกวาดสี่เหลี่ยมง่าย ๆ โดยไม่มีการแปลงใด ๆ ใช้เป็นฐานเปรียบเทียบกับตัวอย่างต่อไป

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

## ตัวอย่างที่ 2: การแปล (Translation)
ที่นี่เราจะแสดง **how to translate shape** โดยย้ายบริบทกราฟิกไปทางขวา 250 หน่วยก่อนวาดสี่เหลี่ยมที่สอง

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

## ตัวอย่างที่ 3: การปรับขนาด (Scaling)
ตัวอย่างนี้ตอบคำถามหลัก **how to scale rectangle** เราจะลดสี่เหลี่ยมลงเหลือ 50 % ของความกว้างเดิมและ 75 % ของความสูงเดิม

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

## วิธีหมุนรูปทรงใน Java (rotate shape java)
การหมุนเป็นการดำเนินการเชิง affine อีกประเภทหนึ่ง แม้ว่าตัวอย่างโค้ดสำหรับการหมุนจะถูกละเว้นเพื่อความกระชับ รูปแบบการทำงานเหมือนเดิม: บันทึกสถานะกราฟิก, เรียก `document.rotate(angle)`, วาดรูป, แล้วคืนสถานะ นี่แสดงให้เห็น **rotate shape java** และ **how to rotate rectangle** ในการปฏิบัติ

## ทำไมต้องใช้ Aspose.Page สำหรับการแปลงเหล่านี้?
- **Device‑independent**: เขียนครั้งเดียว, สร้าง PostScript หรือ XPS ได้โดยไม่ต้องเขียนโค้ดเฉพาะแพลตฟอร์ม  
- **Fine‑grained control**: การเข้าถึงสถานะกราฟิกโดยตรงทำให้คุณผสานการแปล, การปรับขนาด, การเฉือน, และการหมุนได้อย่างอิสระ  
- **Performance**: API ที่มีค่าโอเวอร์เฮดต่ำ เหมาะสำหรับการประมวลผลชุดของเอกสารขนาดใหญ่  

## กรณีการใช้งานทั่วไป
- สร้างใบแจ้งหนี้ที่พิมพ์ได้พร้อมบาร์โค้ดและโลโก้ที่เปลี่ยนแปลงได้  
- สร้างแผนผังเทคนิคที่ต้องการการปรับขนาดและตำแหน่งที่แม่นยำ  
- อัตโนมัติการผลิตรายงานหลายหน้าในรูปแบบ PostScript  

## สรุป
ในบทเรียนนี้ เราได้สำรวจการแปลงต่าง ๆ ในการจัดการหน้า Java ด้วย Aspose.Page for Java โดยเน้นที่ **how to scale rectangle**, **how to translate shape**, และการดำเนินการเชิง affine อื่น ๆ ด้วยการทำตามตัวอย่างเหล่านี้ คุณสามารถเพิ่มความสามารถในการจัดการหน้าของแอปพลิเคชัน Java ของคุณและ **create PostScript document** ที่ตรงตามมาตรฐานการเผยแพร่ระดับมืออาชีพ

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page for Java กับรูปแบบเอกสารอื่นได้หรือไม่?
Aspose.Page มุ่งเน้นที่การจัดการหน้าสำหรับรูปแบบ PostScript และ XPS เป็นหลัก  

### ฉันจะหา ตัวอย่างและเอกสารเพิ่มเติมสำหรับ Aspose.Page for Java ได้จากที่ไหน?
เยี่ยมชม [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) เพื่อข้อมูลที่ครบถ้วน  

### มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?
มี คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](httpshttps://releases.aspose.com/)  

### ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
รับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)  

### ฉันจะหาชุมชนสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.Page for Java ได้จากที่ไหน?
เยี่ยมชม [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) เพื่อการสนทนากับชุมชน  

## Frequently Asked Questions

**Q: ความแตกต่างระหว่าง `translate` กับ `scale` คืออะไร?**  
A: `translate` ย้ายจุดกำเนิดของระบบพิกัด, ส่วน `scale` ปรับขนาดวัตถุที่วาดตามแกน X และ/หรือ Y  

**Q: ฉันสามารถรวมการแปลงหลายอย่างในสถานะกราฟิกเดียวได้หรือไม่?**  
A: ได้—โดยเรียก `translate`, `scale`, `rotate`, หรือ `shear` ตามลำดับก่อนวาด คุณจะได้การแปลงเชิง affine ที่รวมกัน  

**Q: ฉันจะรีเซ็ตการแปลงหลังจากวาดรูปทรงอย่างไร?**  
A: ใช้ `document.writeGraphicsRestore()` เพื่อคืนสู่สถานะกราฟิกที่บันทึกไว้ก่อนหน้า  

**Q: สามารถหมุนสี่เหลี่ยมรอบศูนย์กลางของมันได้หรือไม่?**  
A: แน่นอน ย้ายสี่เหลี่ยมไปยังจุดกำเนิด, ใช้ `rotate(angle)`, แล้วย้ายกลับตำแหน่งเดิมก่อนวาด  

**Q: Aspose.Page รองรับการทำ anti‑aliasing เพื่อกราฟิกที่เรียบเนียนหรือไม่?**  
A: รองรับ—ตั้งค่าตัวเลือกการเรนเดอร์ที่เหมาะสมใน `PsSaveOptions` เพื่อเปิดใช้งาน anti‑aliasing  

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}