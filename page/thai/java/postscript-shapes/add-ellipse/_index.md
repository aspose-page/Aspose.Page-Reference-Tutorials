---
date: 2026-02-18
description: เรียนรู้วิธีตั้งค่าสีทาและสร้างวงรี PostScript ใน Java ด้วย Aspose.Page
  คู่มือนี้แสดงวิธีเติมสีวงรีใน Java, วาดเส้นขอบวงรี, และตั้งความหนาของเส้น.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: ตั้งค่าสีเพื่อวาดวงรี PostScript ใน Java
url: /th/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าสีสีทาเพื่อวาดวงรี PostScript ใน Java

## บทนำ
หากคุณต้องการ **ตั้งค่าสีสีทา** ขณะวาดกราฟิกเวกเตอร์ ไลบรารี Aspose.Page for Java จะให้คุณควบคุมทุกเส้นและการเติมอย่างเต็มที่ ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **ตั้งค่าสีสีทา**, **fill ellipse Java**, และ **draw ellipse outline** ด้วยขั้นตอนที่ง่ายและเป็นระบบ เมื่อเสร็จแล้วคุณจะสามารถเพิ่มวงรี PostScript คุณภาพสูงลงในใบแจ้งหนี้ รายงาน หรือเอกสารที่ต้องพิมพ์ใด ๆ

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดที่ดีที่สุดสำหรับวาดกราฟิก PostScript ใน Java?** Aspose.Page for Java.  
- **ฉันสามารถเติมวงรีด้วยสีทาเดียวได้หรือไม่?** ได้ – ใช้ `document.setPaint(Color.YOUR_COLOR)` ก่อน `fill`.  
- **ฉันจะวาดเพียงเส้นขอบของวงรีอย่างไร?** ตั้งค่าสีสีทาและ stroke แล้วเรียก `document.draw(...)`.  
- **ต้องใช้ไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์; มีไลเซนส์ชั่วคราวสำหรับการทดสอบ.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** ทุก runtime Java 8+ ทำงานได้กับรุ่น Aspose.Page ปัจจุบัน.

## วงรี PostScript คืออะไร?
วงรี PostScript คือรูปทรงเวกเตอร์ที่กำหนดโดยสี่เหลี่ยมขอบเขต ต่างจากภาพราสเตอร์ที่ขยายแล้วสูญเสียคุณภาพ วงรีนี้จึงเหมาะสำหรับการพิมพ์ความละเอียดสูงและการแปลงเป็น PDF

## ทำไมต้องใช้ Aspose.Page เพื่อสร้างวงรี PostScript?
- **ควบคุมเต็มรูปแบบ** ของ primitive การวาด (เส้น, โค้ง, วงรี).  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS.  
- **ไม่มีการพึ่งพาภายนอก** – API Java แท้ ๆ ไม่ต้องใช้โค้ดเนทีฟ.  
- **ผสานรวมง่าย** กับแอปพลิเคชัน Java ที่มีอยู่และเครื่องมือ build ต่าง ๆ.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณมี:

1. สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ (JDK 8 หรือใหม่กว่า).  
2. ไลบรารี Aspose.Page for Java ที่เพิ่มเข้าในโปรเจกต์ของคุณ คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/page/java/)**.  

## นำเข้าแพ็กเกจ
ในไฟล์ซอร์ส Java ของคุณ ให้นำเข้าคลาสที่จำเป็นสำหรับการวาดและบันทึกเนื้อหา PostScript

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## วิธีตั้งค่าสีสีทาสำหรับวงรี
การตั้งค่าสีสีทาเป็นขั้นตอนแรกก่อนทำการเติมหรือ stroke ใด ๆ เมธอด `setPaint` จะกำหนดสีที่ใช้สำหรับคำสั่งการวาดถัดไป

### ขั้นตอนที่ 1: ตั้งค่าเอกสาร PostScript
สร้าง output stream, กำหนดขนาดหน้า, และสร้างอินสแตนซ์ `PsDocument`

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

### ขั้นตอนที่ 2: วิธีเติมวงรี – ใช้ set paint color
เพื่อ **fill ellipse** คุณต้องเรียก `setPaint` ด้วยสีเติมที่ต้องการก่อน แล้วจึงเรียก `fill` พร้อมอินสแตนซ์ `Ellipse2D`

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### ขั้นตอนที่ 3: วาดเส้นขอบวงรีและตั้งความหนา stroke
หลังจากเติมแล้ว คุณสามารถเปลี่ยนสีสีทาเป็นสีอื่น, กำหนด `BasicStroke` เพื่อควบคุมความกว้างของเส้น, แล้ววาดเส้นขอบวงรี

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### ขั้นตอนที่ 4: ปิดและบันทึกเอกสาร
สรุปหน้ากระดาษและเขียนไฟล์ PostScript ลงดิสก์

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

ตอนนี้คุณมีไฟล์ PostScript ที่มีวงรีสองรูป – หนึ่งเติมสีส้มและอีกหนึ่งเป็นเส้นขอบสีแดง คุณสามารถทดลองเปลี่ยนพิกัด, ขนาด, และสีต่าง ๆ เพื่อให้ตรงกับความต้องการออกแบบของคุณได้

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- **เส้นทางไฟล์ไม่ถูกต้อง** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่น (`/` หรือ `\\`) ที่เหมาะกับ OS ของคุณ.  
- **ไม่มีไลเซนส์** – หากไม่มีไลเซนส์ที่ถูกต้อง ไลบรารีจะทำงานในโหมดประเมินผลและอาจใส่ลายน้ำ.  
- **สีไม่ถูกนำไปใช้** – จำไว้ว่าให้ตั้ง `document.setPaint(...)` *ก่อน* ทุกการเรียก `fill` หรือ `draw`; การตั้งค่าสีสีทาไม่คงอยู่ข้ามการดำเนินการแยกต่างหากโดยอัตโนมัติ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Page for Java ร่วมกับไลบรารี Java อื่นได้หรือไม่?**  
A: ได้, Aspose.Page for Java ถูกออกแบบให้ผสานรวมอย่างราบรื่นกับไลบรารี Java อื่น ๆ.

**Q: ฉันจะขอไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: รับไลเซนส์ชั่วคราว **[ที่นี่](https://purchase.aspose.com/temporary-license/)** เพื่อการทดสอบ.

**Q: Aspose.Page เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่?**  
A: แน่นอน! เยี่ยมชม **[ที่นี่](https://purchase.aspose.com/buy)** เพื่อดูตัวเลือกไลเซนส์สำหรับการใช้งานเชิงพาณิชย์.

**Q: ฉันจะหาที่ปรึกษาหรือพูดคุยเกี่ยวกับคำถามที่เกี่ยวกับ Aspose.Page ได้ที่ไหน?**  
A: เข้าร่วมชุมชนที่ **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** เพื่อการสนทนาและความช่วยเหลือ.

**Q: มีแหล่งข้อมูลฟรีเพื่อเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Page for Java หรือไม่?**  
A: ใช้ **[free trial](https://releases.aspose.com/)** และสำรวจตัวอย่างในเอกสาร.

## สรุป
Aspose.Page for Java ทำให้การ **ตั้งค่าสีสีทา**, **fill ellipse**, และ **draw ellipse outline** เป็นเรื่องง่าย – ไม่ว่าคุณจะต้องการรูปทรงเติมสีเรียบง่ายหรือกราฟิกที่มี stroke ซับซ้อน ด้วยขั้นตอนข้างต้นคุณสามารถเพิ่มกราฟิกเวกเตอร์ระดับมืออาชีพลงในเอกสารที่ต้องพิมพ์ใด ๆ ได้อย่างรวดเร็ว สำหรับการสำรวจเพิ่มเติม – เช่น การรวมหลายรูปทรง, การใช้ gradient, หรือการแปลงเป็น PDF – โปรดดู **[documentation](https://reference.aspose.com/page/java/)** อย่างเป็นทางการ

---

**อัปเดตล่าสุด:** 2026-02-18  
**ทดสอบด้วย:** Aspose.Page for Java 24.11  
**ผู้เขียน:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}