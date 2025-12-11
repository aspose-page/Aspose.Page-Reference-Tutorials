---
date: 2025-12-11
description: เรียนรู้วิธีสร้างวงรี PostScript ใน Java ด้วย Aspose.Page คู่มือขั้นตอนนี้จะแสดงวิธีเติมสีให้วงรีและวาดวงรีโดยใช้
  Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: วิธีสร้างวงรี PostScript ใน Java ด้วย Aspose.Page
url: /th/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างวงรี PostScript ใน Java ด้วย Aspose.Page

## บทนำ
การสร้าง **PostScript ellipse** ด้วยโปรแกรมมิ่งทำให้คุณควบคุมกราฟิกเวกเตอร์ได้อย่างละเอียดในรายงาน ใบแจ้งหนี้ หรือเอกสารที่ต้องพิมพ์ใด ๆ ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **สร้าง PostScript ellipse** ด้วยไลบรารี Aspose.Page for Java, เติมสีให้วงรี, และวาดเส้นขอบวงรี เมื่อจบคุณจะพร้อมฝังกราฟิกแบบกำหนดเองโดยตรงลงในผลลัพธ์ PostScript ของคุณ.

## คำตอบสั้น
- **ไลบรารีที่ดีที่สุดสำหรับการวาดกราฟิก PostScript ใน Java คืออะไร?** Aspose.Page for Java.  
- **ฉันสามารถเติมสีทึบให้กับวงรีได้หรือไม่?** ใช่ – ใช้ `document.setPaint(Color.YOUR_COLOR)` ก่อน `fill`.  
- **ฉันจะวาดเฉพาะเส้นขอบของวงรีได้อย่างไร?** ตั้งค่าสีและเส้นขอบ แล้วเรียก `document.draw(...)`.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์; มีไลเซนส์ชั่วคราวสำหรับการทดสอบ.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** ทุก runtime Java 8 ขึ้นไปทำงานได้กับรุ่น Aspose.Page ปัจจุบัน.

## PostScript ellipse คืออะไร?
PostScript ellipse คือรูปทรงเวกเตอร์ที่กำหนดโดยสี่เหลี่ยมขอบเขต. แตกต่างจากภาพราสเตอร์, มันสามารถขยายโดยไม่สูญเสียคุณภาพ, ทำให้เหมาะสำหรับการพิมพ์ความละเอียดสูงและการแปลงเป็น PDF.

## ทำไมต้องใช้ Aspose.Page เพื่อสร้าง PostScript ellipse?
- **การควบคุมเต็มรูปแบบ** บน primitive การวาด (เส้น, โค้ง, วงรี).  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS.  
- **ไม่มีการพึ่งพาภายนอก** – API Java แท้, ไม่มีโค้ดเนทีฟ.  
- **การผสานรวมที่ง่าย** กับแอปพลิเคชัน Java ที่มีอยู่และเครื่องมือสร้าง.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ให้ตรวจสอบว่าคุณมี:

1. สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ (JDK 8 หรือใหม่กว่า).  
2. ไลบรารี Aspose.Page for Java ที่เพิ่มเข้าในโครงการของคุณ. คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/page/java/)**.  

## นำเข้าแพ็กเกจ
ในไฟล์ซอร์ส Java ของคุณ, ให้ import คลาสที่จำเป็นสำหรับการวาดและบันทึกเนื้อหา PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าเอกสาร PostScript
สร้าง output stream, กำหนดขนาดหน้า, และสร้างอินสแตนซ์ของ `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### ขั้นตอนที่ 2: เติมสีให้วงรี
ตั้งค่าสี (paint) เป็นสีเติมที่ต้องการและเรียก `fill` พร้อมอินสแตนซ์ของ `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### ขั้นตอนที่ 3: วาดเส้นขอบวงรี
สลับสี (paint) ไปเป็นสีเส้นขอบ, กำหนด `BasicStroke` สำหรับความหนาของเส้น, และวาดเส้นขอบของวงรี.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### ขั้นตอนที่ 4: ปิดและบันทึกเอกสาร
สรุปหน้าสุดท้ายและเขียนไฟล์ PostScript ลงดิสก์.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

ตอนนี้คุณมีไฟล์ PostScript ที่มีวงรีสองรูป—หนึ่งเติมสีส้มและอีกหนึ่งมีเส้นขอบสีแดง. คุณสามารถทดลองเปลี่ยนพิกัด, ขนาด, และสีต่าง ๆ เพื่อให้ตรงกับความต้องการออกแบบของคุณ.

## ปัญหาที่พบบ่อยและการแก้ไขข้อผิดพลาด
- **เส้นทางไฟล์ไม่ถูกต้อง** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่น (`/` หรือ `\\`) ที่เหมาะกับ OS ของคุณ.  
- **ไม่มีไลเซนส์** – หากไม่มีไลเซนส์ที่ถูกต้อง, ไลบรารีจะทำงานในโหมดประเมินผลและอาจเพิ่มลายน้ำ.  
- **สีไม่ถูกนำไปใช้** – จำไว้ว่าให้ตั้งค่า `document.setPaint(...)` *ก่อน* ทุกการเรียก `fill` หรือ `draw`; การตั้งค่าสีจะไม่คงอยู่ระหว่างการดำเนินการแยกต่างหากโดยอัตโนมัติ.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Page for Java ร่วมกับไลบรารี Java อื่น ๆ ได้หรือไม่?**  
ตอบ: ใช่, Aspose.Page for Java ถูกออกแบบให้ผสานรวมอย่างราบรื่นกับไลบรารี Java อื่น ๆ.

**ถาม: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
ตอบ: รับไลเซนส์ชั่วคราว **[ที่นี่](https://purchase.aspose.com/temporary-license/)** เพื่อการทดสอบ.

**ถาม: Aspose.Page เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่?**  
ตอบ: แน่นอน! เยี่ยมชม **[ที่นี่](https://purchase.aspose.com/buy)** เพื่อสำรวจตัวเลือกไลเซนส์สำหรับการใช้งานเชิงพาณิชย์.

**ถาม: ฉันจะหาความช่วยเหลือหรือสนทนาเกี่ยวกับ Aspose.Page ได้จากที่ไหน?**  
ตอบ: เข้าร่วมชุมชนที่ **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** เพื่อการสนทนาและความช่วยเหลือ.

**ถาม: มีแหล่งข้อมูลฟรีใด ๆ ที่จะเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Page for Java หรือไม่?**  
ตอบ: ใช้ **[การทดลองใช้งานฟรี](https://releases.aspose.com/)** และสำรวจตัวอย่างในเอกสารประกอบ.

## สรุป
Aspose.Page for Java ทำให้การ **สร้าง PostScript ellipse** เป็นเรื่องง่าย ไม่ว่าจะต้องการรูปทรงเติมสีแบบง่ายหรือเส้นขอบซับซ้อน. ด้วยขั้นตอนข้างต้นคุณสามารถเพิ่มกราฟิกเวกเตอร์ระดับมืออาชีพลงในเอกสารที่ต้องพิมพ์ได้อย่างรวดเร็ว. สำหรับการสำรวจเพิ่มเติม—เช่น การรวมหลายรูปทรง, การใช้กราเดียนต์, หรือการแปลงเป็น PDF—ดูที่ **[เอกสารประกอบอย่างเป็นทางการ](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
