---
date: 2025-12-11
description: เรียนรู้วิธีวาดรูปสี่เหลี่ยมใน Java PostScript ด้วย Aspose.Page คู่มือขั้นตอนนี้แสดงวิธีตั้งค่าสีทาสี
  ตั้งค่าสีสี่เหลี่ยมใน Java และสร้างกราฟิกที่สดใส
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: วิธีวาดสี่เหลี่ยมใน Java PostScript ด้วย Aspose.Page
url: /th/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีวาดสี่เหลี่ยมใน Java PostScript ด้วย Aspose.Page

## บทนำ
หากคุณต้องการ **วิธีวาดสี่เหลี่ยม** ภายในไฟล์ Java PostScript คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายการใช้ Aspose.Page for Java เพื่อเพิ่มสี่เหลี่ยมสีสัน, ควบคุมการเติมสีและเส้นขอบ, และบันทึกผลลัพธ์เป็นเอกสาร PostScript คุณจะได้เห็นอย่างชัดเจน **วิธีตั้งค่า paint**, วิธีกำหนดรูปทรงของสี่เหลี่ยม, และทำไมวิธีนี้จึงเหมาะสำหรับการสร้างกราฟิกที่พิมพ์ได้โดยอัตโนมัติ

## คำตอบสั้น
- **What library is required?** Aspose.Page for Java  
- **Can I change rectangle colors?** ใช่ – ใช้ `setPaint` กับ `java.awt.Color` ใดก็ได้  
- **Do I need a license for development?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **Which page size is used in the example?** A4 (ค่าเริ่มต้นของ `PsSaveOptions`)  
- **Is the code compatible with Java 8+?** แน่นอน – ใช้คลาสมาตรฐานของ AWT  

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มทำตามบทแนะนำนี้ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมอยู่:
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java  
- ติดตั้งไลบรารี Aspose.Page for Java หากยังไม่ได้ติดตั้ง ให้ดาวน์โหลดจาก [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)  
- มีสภาพแวดล้อมการพัฒนา Java ตั้งค่าไว้บนเครื่องของคุณ  

## นำเข้าแพ็กเกจ
ในโครงการ Java ของคุณ ให้เริ่มด้วยการนำเข้าแพ็กเกจที่จำเป็น:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## วิธีวาดสี่เหลี่ยมใน Java PostScript
ด้านล่างเป็นขั้นตอนการทำงานทั้งหมดที่แบ่งเป็นขั้นตอนชัดเจน แต่ละขั้นตอนจะมีคำอธิบายสั้น ๆ ตามด้วยบล็อกโค้ดต้นฉบับ (ไม่เปลี่ยนแปลง)

### ขั้นตอนที่ 1: ตั้งค่า Paint สำหรับเติมสี่เหลี่ยม  
**วิธีตั้งค่า paint** – เราเลือกสีส้มเป็นสีเติมสำหรับสี่เหลี่ยมแรก

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### ขั้นตอนที่ 2: ตั้งค่า Paint สำหรับเส้นขอบสี่เหลี่ยม  
**Set rectangle color java** – ตอนนี้เราจะเปลี่ยนสี paint เป็นสีแดงและกำหนดความกว้างของเส้นขอบ

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### ขั้นตอนที่ 3: ปิดหน้าเดิมและบันทึกเอกสาร  
หลังจากวาดเสร็จ เราจะปิดหน้าและบันทึกไฟล์

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## ทำไมต้องใช้ Aspose.Page สำหรับกราฟิกสี่เหลี่ยม?
- **Cross‑platform**: สร้าง PostScript มาตรฐานที่ทำงานได้กับเครื่องพิมพ์ทุกเครื่อง  
- **Fine‑grained control**: สามารถตั้งค่าสีเติม, สีเส้นขอบ, และความกว้างของเส้นได้อย่างอิสระ  
- **No external dependencies**: ใช้เฉพาะคลาสเรขาคณิตของ AWT ที่มีมาในตัว  

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **File path errors** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`)  
- **License exceptions** – เวอร์ชันทดลองจะเพิ่มลายน้ำ; ควรซื้อไลเซนส์เต็มสำหรับการใช้งานจริง  
- **Color visibility** – เครื่องพิมพ์บางรุ่นอาจตีความค่า RGB แตกต่างกัน; ควรทดสอบด้วยสี่เหลี่ยมสีดำง่าย ๆ ก่อน  

## สรุป
ในคู่มือนี้เราได้สาธิต **วิธีวาดสี่เหลี่ยม** ในเอกสาร Java PostScript, ครอบคลุม **วิธีตั้งค่า paint**, และแสดง **Set rectangle color java** ด้วย Aspose.Page คุณสามารถทดลองสร้างรูปทรง, สี, และสไตล์เส้นต่าง ๆ เพื่อสร้างกราฟิกที่พิมพ์ได้สวยงามสำหรับรายงาน, ใบแจ้งหนี้, หรือการพิมพ์แบบกำหนดเองได้ตามต้องการ  

## คำถามที่พบบ่อย

### สามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?
Aspose.Page รองรับหลัก ๆ คือ Java แต่ก็มีไลบรารีที่คล้ายกันสำหรับภาษาอื่น ๆ  

### มีเวอร์ชันทดลองของ Aspose.Page for Java หรือไม่?
มี – คุณสามารถสำรวจคุณสมบัติของ Aspose.Page for Java ได้จาก [free trial version](https://releases.aspose.com/)  

### จะหาแหล่งช่วยเหลือและการสนทนาเพิ่มเติมได้ที่ไหน?
เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อเข้าร่วมชุมชนและขอความช่วยเหลือ  

### จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
รับไลเซนส์ชั่วคราวได้ที่ [here](https://purchase.aspose.com/temporary-license/)  

### จะซื้อเวอร์ชันที่มีไลเซนส์ของ Aspose.Page for Java ได้ที่ไหน?
ซื้อเวอร์ชันที่มีไลเซนส์ได้ที่ [here](https://purchase.aspose.com/buy)  

**Additional Q&A**

**Q:** *Can I change the rectangle size dynamically?*  
**A:** ใช่ – เพียงแก้ไขพารามิเตอร์ `Rectangle2D.Float(x, y, width, height)` ก่อนเรียก `fill` หรือ `draw`  

**Q:** *Is it possible to add text inside the rectangle?*  
**A:** แน่นอน หลังจากวาดสี่เหลี่ยมแล้ว ให้ใช้ `document.drawString(...)` พร้อมฟอนต์และตำแหน่งที่ต้องการ  

**Q:** *Does Aspose.Page support other shapes like circles or polygons?*  
**A:** ใช่, API มีเมธอดเช่น `drawEllipse` และ `drawPolygon` สำหรับกราฟิกเวกเตอร์หลากหลายรูปแบบ  

---

**อัปเดตล่าสุด:** 2025-12-11  
**ทดสอบกับ:** Aspose.Page for Java 24.12 (latest)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}