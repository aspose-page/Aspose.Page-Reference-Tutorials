---
date: 2026-02-18
description: เรียนรู้วิธีวาดรูปสี่เหลี่ยมใน Java PostScript ด้วย Aspose.Page คู่มือแบบขั้นตอนนี้แสดงวิธีตั้งค่า
  Paint, ตั้งค่าสีสี่เหลี่ยมใน Java, และสร้างกราฟิกที่มีสีสันสดใสพร้อมอธิบายวิธีวาดสี่เหลี่ยมอย่างมีประสิทธิภาพ.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: วิธีวาดสี่เหลี่ยมใน Java PostScript ด้วย Aspose.Page
url: /th/java/postscript-shapes/add-rectangle/
weight: 11
---

6-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

Then closing shortcodes.

Make sure to keep markdown formatting.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีวาดสี่เหลี่ยมใน Java PostScript ด้วย Aspose.Page

## Introduction
หากคุณต้องการ **วิธีวาดสี่เหลี่ยม** ภายในไฟล์ Java PostScript คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายการใช้ Aspose.Page for Java เพื่อเพิ่มสี่เหลี่ยมสีสันต่าง ๆ ควบคุมการเติมสีและการวาดเส้นขอบ และบันทึกผลลัพธ์เป็นเอกสาร PostScript คุณจะได้เห็น **วิธีตั้งค่า paint**, วิธีกำหนดเรขาคณิตของสี่เหลี่ยม, และทำไมวิธีนี้จึงเหมาะสำหรับการสร้างกราฟิกที่พิมพ์ได้โดยอัตโนมัติ ในตอนท้ายของคู่มือคุณจะเข้าใจบริบทกว้างของเทคนิค **draw rectangle java** และวิธีที่พวกมันเข้ากับกระบวนการ **java awt rectangle drawing** 

## Quick Answers
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for Java  
- **ฉันสามารถเปลี่ยนสีสี่เหลี่ยมได้หรือไม่?** ใช่ – ใช้ `setPaint` กับ `java.awt.Color` ใดก็ได้  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีได้สำหรับการทดสอบ; ต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **ขนาดหน้าที่ใช้ในตัวอย่างคืออะไร?** A4 (ค่าเริ่มต้น `PsSaveOptions`)  
- **โค้ดนี้เข้ากันได้กับ Java 8+ หรือไม่?** แน่นอน – ใช้คลาส AWT มาตรฐาน  

## What Is “How to Draw Rectangle” in PostScript?
การวาดสี่เหลี่ยมในเอกสาร PostScript หมายถึงการกำหนดพื้นที่สี่เหลี่ยมและเติมสี, วาดเส้นขอบ, หรือทั้งสองอย่าง ด้วย Aspose.Page คุณสามารถทำได้โดยใช้คลาส **java awt rectangle drawing** ที่คุ้นเคย ซึ่งทำให้โค้ดอ่านง่ายและบำรุงรักษาได้  

## Why Use Aspose.Page for Rectangle Graphics?
- **ข้ามแพลตฟอร์ม**: สร้าง PostScript มาตรฐานที่ทำงานกับเครื่องพิมพ์ใดก็ได้  
- **การควบคุมละเอียด**: คุณสามารถตั้งค่าสีเติม, สีเส้นขอบ, และความกว้างของเส้นแยกกันได้  
- **ไม่มีการพึ่งพาภายนอก**: ใช้เฉพาะคลาสเรขาคณิตของ AWT ที่มีอยู่แล้ว จึงไม่ต้องการไลบรารีกราฟิกเพิ่มเติม  

## Prerequisites
ก่อนเริ่มทำตามบทแนะนำ โปรดตรวจสอบว่าคุณมีเงื่อนไขต่อไปนี้พร้อมอยู่แล้ว:
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว หากยังไม่มี ดาวน์โหลดได้จาก [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)  
- มีสภาพแวดล้อมการพัฒนา Java ตั้งค่าไว้บนเครื่องของคุณ  

## Import Packages
ในโปรเจกต์ Java ของคุณ ให้เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็น การนำเข้าต่าง ๆ นี้จะให้คุณเข้าถึงคลาส `Color`, `BasicStroke`, และ `Rectangle2D` ของ AWT รวมถึงคลาสการจัดการเอกสารหลักของ Aspose.Page  

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step‑by‑Step Guide to Draw Rectangle in Java PostScript

### Step 1: Set Paint for Filling Rectangle  
**How to set paint** – เราเลือกสีส้มเป็นสีเติมสำหรับสี่เหลี่ยมแรก ส่วนนี้แสดงความสามารถของ **set rectangle color java**  

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

### Step 2: Set Paint for Stroking Rectangle  
**Set rectangle color java** – ตอนนี้เราจะเปลี่ยนสีเป็นสีแดงและกำหนดความกว้างของเส้นขอบ ส่วนนี้ของตัวอย่างแสดงวิธี **draw rectangle java** ด้วยความหนาของเส้นที่กำหนดเอง  

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Step 3: Close Current Page and Save Document  
หลังจากวาดเสร็จ เราจะปิดหน้าและบันทึกไฟล์ การปิดหน้าจะทำให้คำสั่งวาดทั้งหมดถูกส่งออกไปยังสตรีม PostScript  

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Common Use Cases for Rectangle Drawing
- **การสร้างใบแจ้งหนี้หรือใบเสร็จ** – สี่เหลี่ยมทำหน้าที่เป็นกรอบหรือไฮไลท์ส่วนต่าง ๆ  
- **การสร้างป้าย** – วาดกล่องสีเพื่อแยกข้อมูลสินค้า  
- **แผนภูมิแบบง่าย** – ใช้สี่เหลี่ยมเติมสีเป็นองค์ประกอบของแผนภูมิบาร์  
- **ฟอร์มพิมพ์แบบกำหนดเอง** – ผสานสี่เหลี่ยมกับข้อความเพื่อสร้างฟิลด์ฟอร์ม  

## Common Issues & Tips
- **ข้อผิดพลาดของเส้นทางไฟล์** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`)  
- **ข้อยกเว้นไลเซนส์** – รุ่นทดลองจะใส่ลายน้ำ; ควรได้รับไลเซนส์เต็มสำหรับการใช้งานจริง  
- **การมองเห็นสี** – เครื่องพิมพ์บางรุ่นอาจตีความค่า RGB แตกต่างกัน; ทดสอบด้วยสี่เหลี่ยมสีดำง่าย ๆ ก่อน  
- **การใช้หน่วยความจำ** – สำหรับเอกสารขนาดใหญ่ ควรทำการ flush สตรีมหลังจากแต่ละหน้า (`document.closePage()`)  

## Frequently Asked Questions

**Q:** *ฉันสามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?*  
A: Aspose.Page รองรับ Java เป็นหลัก แต่มีไลบรารีที่คล้ายกันสำหรับภาษาอื่น ๆ  

**Q:** *มีรุ่นทดลองของ Aspose.Page for Java ให้ใช้งานหรือไม่?*  
A: มี คุณสามารถสำรวจคุณสมบัติของ Aspose.Page for Java ได้จาก [free trial version](https://releases.aspose.com/)  

**Q:** *จะหาแหล่งช่วยเหลือและการสนทนาเพิ่มเติมได้จากที่ไหน?*  
A: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อเข้าร่วมชุมชนและขอความช่วยเหลือ  

**Q:** *จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?*  
A: รับไลเซนส์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/)  

**Q:** *จะซื้อเวอร์ชันที่มีไลเซนส์ของ Aspose.Page for Java ได้จากที่ไหน?*  
A: ซื้อเวอร์ชันที่มีไลเซนส์ได้จาก [here](https://purchase.aspose.com/buy)  

**Additional Q&A**

**Q:** *ฉันสามารถเปลี่ยนขนาดสี่เหลี่ยมแบบไดนามิกได้หรือไม่?*  
A: ได้ – เพียงแก้ไขพารามิเตอร์ `Rectangle2D.Float(x, y, width, height)` ก่อนเรียก `fill` หรือ `draw`  

**Q:** *สามารถใส่ข้อความภายในสี่เหลี่ยมได้หรือไม่?*  
A: แน่นอน หลังจากวาดสี่เหลี่ยมแล้ว ใช้ `document.drawString(...)` พร้อมฟอนต์และตำแหน่งที่ต้องการ  

**Q:** *Aspose.Page รองรับรูปทรงอื่น ๆ เช่น วงกลมหรือหลายเหลี่ยมหรือไม่?*  
A: รองรับ API มีเมธอดเช่น `drawEllipse` และ `drawPolygon` สำหรับกราฟิกเวกเตอร์หลากหลายรูปแบบ  

## Conclusion
ในคู่มือนี้เราได้สาธิต **วิธีวาดสี่เหลี่ยม** ในเอกสาร Java PostScript, ครอบคลุม **วิธีตั้งค่า paint**, และแสดงวิธี **set rectangle color java** ด้วย Aspose.Page ตอนนี้คุณมีพื้นฐานที่มั่นคงสำหรับการสร้างกราฟิกที่พิมพ์ได้อย่างมีสีสัน ไม่ว่าจะเป็นการสร้างใบแจ้งหนี้, ป้าย, หรือฟอร์มแบบกำหนดเอง อย่ากลัวที่จะทดลองใช้สีต่าง ๆ, สไตล์เส้น, และรูปทรง AWT เพิ่มเติมเพื่อทำให้ผลลัพธ์ของคุณสมบูรณ์ยิ่งขึ้น  

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}