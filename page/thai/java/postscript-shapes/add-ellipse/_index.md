---
date: 2026-10-31
description: เรียนรู้วิธีการตั้งสี paint และเติม ellipse ใน Java PostScript ด้วย Aspose.Page
  คู่มือนี้แสดงวิธีการเติม ellipse, วาดเส้นขอบ ellipse, และตั้งค่า stroke thickness
  ด้วยขั้นตอนโค้ดที่ชัดเจน
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: เพิ่ม Ellipse ใน Java PostScript
og_description: เรียนรู้วิธีการเติม ellipse และตั้งสี paint ใน Java PostScript ด้วย
  Aspose.Page ปฏิบัติตามโค้ดขั้นตอนต่อขั้นตอนเพื่อวาด ellipse ที่เติมสีและมีเส้นขอบในไม่กี่วินาที
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: วิธีการเติม ellipse และตั้งสี paint ใน Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: วิธีการเติม ellipse และตั้งสี paint ใน Java PostScript
url: /th/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเติมวงรีและตั้งสีการวาดใน Java PostScript

## บทนำ
หากคุณต้องการ **ตั้งสีการวาด** ขณะวาดกราฟิกเวกเตอร์ ไลบรารี Aspose.Page for Java จะให้การควบคุมเต็มรูปแบบต่อทุกเส้นและการเติม ในบทเรียนนี้คุณจะได้ค้นพบวิธี **ตั้งสีการวาด**, **เติมวงรี**, และ **วาดโครงวงรี** ด้วยวิธีการแบบง่าย ๆ ทีละขั้นตอน เมื่อเสร็จแล้วคุณจะสามารถเพิ่มวงรี PostScript คุณภาพสูงลงในใบแจ้งหนี้ รายงาน หรือเอกสารที่พิมพ์ได้ใด ๆ

## คำตอบสั้น
- **ไลบรารีใดดีที่สุดสำหรับการวาดกราฟิก PostScript ใน Java?** Aspose.Page for Java.  
- **ฉันสามารถเติมวงรีด้วยสีทึบได้หรือไม่?** ใช่ – ใช้ `document.setPaint(Color.YOUR_COLOR)` ก่อน `fill`.  
- **ฉันวาดเฉพาะโครงของวงรีได้อย่างไร?** ตั้งสีและเส้น แล้วเรียก `document.draw(...)`.  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์; มีลิขสิทธิ์ชั่วคราวสำหรับการทดสอบ.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** ทุก runtime Java 8+ ทำงานได้กับรุ่น Aspose.Page ปัจจุบัน.

## วงรี PostScript คืออะไร?
วงรี PostScript คือรูปทรงเวกเตอร์ที่กำหนดโดยสี่เหลี่ยมขอบเขต ไม่เหมือนภาพราสเตอร์ที่สูญเสียคุณภาพเมื่อขยาย มันสามารถปรับขนาดได้โดยไม่เสียคุณภาพ ทำให้เหมาะสำหรับการพิมพ์ความละเอียดสูงและการแปลงเป็น PDF เนื่องจากรูปทรงนี้อธิบายด้วยคณิตศาสตร์ จึงสามารถเรนเดอร์ได้ทุกขนาดหรือความละเอียดโดยคงขอบคมและเส้นโค้งเรียบ

## ทำไมต้องใช้ Aspose.Page เพื่อสร้างวงรี PostScript?
Aspose.Page ให้การควบคุมที่แน่นอนต่อทุก primitive การวาด รองรับ **ระบบปฏิบัติการหลัก 3 ระบบ (Windows, Linux, macOS)**, **ไม่มีการพึ่งพา native ใด ๆ**, และสามารถเรนเดอร์ **primitive เวกเตอร์กว่า 50 ชนิดต่อวินาที** บนเซิร์ฟเวอร์ทั่วไป ไลบรารีเป็น Java แท้ ๆ ทำให้คุณสามารถฝังไว้ในแอปพลิเคชัน Java 8+ ใดก็ได้โดยไม่ต้องใช้ไลบรารี native เพิ่มเติม

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

1. สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ (JDK 8 หรือใหม่กว่า).  
2. ไลบรารี Aspose.Page for Java ถูกเพิ่มเข้าไปในโปรเจกต์ของคุณ คุณสามารถดาวน์โหลดได้ **[จากหน้ารีลีสของ Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  

## การนำเข้าแพ็กเกจ
ในไฟล์ซอร์ส Java ของคุณ ให้นำเข้าคลาสที่จำเป็นสำหรับการวาดและบันทึกเนื้อหา PostScript

แพ็กเกจ `java.awt` มีประเภทกราฟิกพื้นฐานเช่น `Color`, `Ellipse2D`, และ `BasicStroke` แพ็กเกจ `com.aspose.page` มีคลาส `PsDocument` ที่เขียนเอาต์พุต PostScript

- **`Color`** – แสดงสี sRGB ที่ใช้สำหรับการทาดสี.  
- **`Ellipse2D`** – อธิบายรูปทรงวงรีที่กำหนดโดยสี่เหลี่ยมขอบเขต.  
- **`BasicStroke`** – กำหนดความกว้างของเส้น, รูปแบบ dash, และสไตล์ปลายเส้นสำหรับการวาดโครง.  
- **`PsDocument`** – แทนเอกสาร PostScript และให้เมธอดสำหรับวาดกราฟิกและจัดการหน้า.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## วิธีตั้งสีการวาดสำหรับวงรี
ขั้นตอนแรกคือบอกเอกสารว่าจะใช้สีใดสำหรับการดำเนินการวาดครั้งต่อไป เมธอด `setPaint` จะตั้งค่าสีทึบที่จะนำไปใช้กับการเติมหรือเส้นตามที่เรียกต่อไป

### ขั้นตอนที่ 1: ตั้งค่าเอกสาร PostScript
สร้าง output stream, กำหนดขนาดหน้า, และสร้างอินสแตนซ์ `PsDocument`

`PsDocument` เป็นคลาสหลักที่แทนไฟล์ PostScript ในหน่วยความจำ คำสั่งวาดทั้งหมดจะผ่านอ็อบเจกต์นี้ และมันจัดการเลย์เอาต์หน้า, การจัดการทรัพยากร, และการสร้างไฟล์ขั้นสุดท้าย

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

### ขั้นตอนที่ 2: เติมวงรี – ใช้การตั้งสีการวาด
เพื่อ **เติมวงรี** คุณต้องเรียก `setPaint` ด้วยสีเติมที่ต้องการก่อน แล้วจึงเรียก `fill` พร้อมอินสแตนซ์ `Ellipse2D`

`setPaint` ตั้งค่าสีการวาดปัจจุบันที่ใช้สำหรับการเติมหรือเส้นต่อไป  
`Ellipse2D` กำหนดขอบเขตเรขาคณิตของวงรี; ตัวสร้างรับพิกัด X‑Y ของมุมบนซ้ายพร้อมความกว้างและความสูง

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### ขั้นตอนที่ 3: วาดโครงวงรีและตั้งความหนาเส้น
หลังจากเติมแล้ว คุณสามารถเปลี่ยนสีการวาดเป็นสีอื่น, กำหนด `BasicStroke` เพื่อควบคุมความกว้างของเส้น, แล้ววาดโครงวงรี

`BasicStroke` ระบุความกว้างของเส้น, รูปแบบ dash, และสไตล์ปลายเส้นสำหรับการวาดโครง โดยการปรับคุณสมบัติ `width` คุณจะควบคุมความหนาของขอบวงรีได้

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### ขั้นตอนที่ 4: ปิดและบันทึกเอกสาร
สรุปหน้าและเขียนไฟล์ PostScript ลงดิสก์

การเรียก `document.close()` จะทำการ flush คำสั่งวาดที่ค้างอยู่ทั้งหมดและปล่อยทรัพยากร ไฟล์ `.ps` ที่ได้สามารถเปิดด้วยโปรแกรมดู PostScript ใดก็ได้หรือแปลงเป็น PDF

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

ตอนนี้คุณมีไฟล์ PostScript ที่มีวงรีสองวง – หนึ่งเติมสีส้มและอีกหนึ่งเป็นโครงสีแดง คุณสามารถทดลองเปลี่ยนพิกัด, ขนาด, และสีต่าง ๆ เพื่อให้ตรงกับความต้องการออกแบบของคุณได้

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- **เส้นทางไฟล์ไม่ถูกต้อง** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่น (`/` หรือ `\\`) ที่เหมาะกับระบบปฏิบัติการของคุณ.  
- **ไม่มีลิขสิทธิ์** – หากไม่มีลิขสิทธิ์ที่ถูกต้อง ไลบรารีจะทำงานในโหมดประเมินผลและอาจใส่ลายน้ำ.  
- **สีไม่ถูกนำไปใช้** – จำไว้ว่าให้ตั้ง `document.setPaint(...)` *ก่อน* ทุกการเรียก `fill` หรือ `draw`; การตั้งสีจะไม่คงอยู่ข้ามการดำเนินการแยกต่างหากโดยอัตโนมัติ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Page for Java ร่วมกับไลบรารี Java อื่นได้หรือไม่?**  
A: ใช่, Aspose.Page for Java ถูกออกแบบให้รวมกับไลบรารี Java อื่นได้อย่างราบรื่น

**Q: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: รับลิขสิทธิ์ชั่วคราว **[จากหน้าลิขสิทธิ์ชั่วคราวของ Aspose](https://purchase.aspose.com/temporary-license/)** เพื่อการทดสอบ

**Q: Aspose.Page เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่?**  
A: แน่นอน! เยี่ยมชม **[หน้าการซื้อของ Aspose](https://purchase.aspose.com/buy)** เพื่อสำรวจตัวเลือกลิขสิทธิ์สำหรับการใช้งานเชิงพาณิชย์

**Q: ฉันจะหาแหล่งช่วยเหลือหรือสนทนาเกี่ยวกับ Aspose.Page ได้ที่ไหน?**  
A: เข้าร่วมชุมชนที่ **[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39)** เพื่อการสนทนาและรับความช่วยเหลือ

**Q: มีแหล่งข้อมูลฟรีเพื่อเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Page for Java หรือไม่?**  
A: ใช้ **[หน้า trial ฟรีของ Aspose](https://releases.aspose.com/)** และสำรวจตัวอย่างในเอกสาร

## สรุป
Aspose.Page for Java ทำให้การ **ตั้งสีการวาด**, **เติมวงรี**, และ **วาดโครงวงรี** เป็นเรื่องง่าย—ไม่ว่าคุณต้องการรูปทรงเติมสีง่าย ๆ หรือกราฟิกที่มีเส้นซับซ้อน ด้วยขั้นตอนข้างต้นคุณสามารถเพิ่มกราฟิกเวกเตอร์ระดับมืออาชีพลงในเอกสารที่พิมพ์ได้อย่างรวดเร็ว หากต้องการสำรวจเพิ่มเติม เช่น การรวมหลายรูปทรง, การใช้ gradient, หรือการแปลงเป็น PDF ให้ดูเอกสาร **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)** อย่างเป็นทางการ

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [How to Draw Rectangle in Java PostScript with Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [How to Add Unicode Text in Java PostScript with Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Create Radial Gradient in PostScript with Aspose.Page for Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}