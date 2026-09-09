---
date: 2026-09-09
description: เรียนรู้วิธีสร้างไล่ระดับสีใน Java PostScript และเพิ่มไล่ระดับสีให้กับรูปทรงโดยใช้
  Aspose.Page. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนพร้อมโค้ดและเคล็ดลับ.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript ไล่ระดับสีแบบรัศมีกับ Aspose.Page
og_description: เรียนรู้วิธีสร้างไล่ระดับสีใน Java PostScript และเพิ่มไล่ระดับสีให้กับรูปทรงโดยใช้
  Aspose.Page. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนพร้อมโค้ดและเคล็ดลับ.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: วิธีสร้างไล่ระดับสีใน Java PostScript ด้วยการเติมแบบรัศมี
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: วิธีสร้างไล่ระดับสีใน Java PostScript ด้วยการเติมแบบรัศมี
url: /th/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างไล่ระดับสีใน Java PostScript ด้วยการเติมแบบรัศมี

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีสร้างไล่ระดับสี** กราฟิกในเอกสาร PostScript ด้วย Java และ Aspose.Page เราจะอธิบายทุกขั้นตอน—from การตั้งค่าโครงการจนถึงการเรนเดอร์วงกลมที่เติมด้วยไล่ระดับสีแบบรัศมีที่เรียบเนียน—เพื่อให้คุณสามารถ **เพิ่มไล่ระดับสีให้กับรูปทรง** ได้ทันทีและยกระดับคุณภาพภาพของแอปพลิเคชัน Java ของคุณ

## คำตอบอย่างรวดเร็ว
- **บทเรียนนี้สร้างอะไร?** ไฟล์ PostScript (`.ps`) ที่มีวงกลมเติมด้วยไล่ระดับสีแบบรัศมี.  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java (รุ่นล่าสุด).  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างที่ทำงานได้.  
- **ต้องการไลเซนส์หรือไม่?** จำเป็นต้องมีไลเซนส์ชั่วคราวหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์; เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา.  
- **สามารถใช้โค้ดนี้กับ PDF หรือ SVG ได้หรือไม่?** ได้—Aspose.Page รองรับหลายรูปแบบการส่งออกโดยต้องเปลี่ยนแปลงเพียงเล็กน้อย.

## วิธีเติมรูปทรงด้วยไล่ระดับสีใน PostScript
คุณสามารถเติมรูปทรงด้วยไล่ระดับสีแบบรัศมีใน PostScript ได้โดยการสร้าง `PsDocument` กำหนด `RadialGradientPaint` แล้วนำไปใช้กับรูปทรงเป้าหมายและสุดท้ายบันทึกเอกสาร กระบวนการทำงานสั้นนี้ช่วยให้คุณสร้างกราฟิกเวกเตอร์ที่ดูเป็นมืออาชีพโดยไม่ต้องใช้ภาพราสเตอร์ และโค้ดเดียวกันสามารถนำไปใช้ซ้ำสำหรับการส่งออกเป็น PDF หรือ SVG ได้ กระบวนการนี้ง่ายและทำงานสม่ำเสมอในทุกรูปแบบที่รองรับ

## ไล่ระดับสีแบบรัศมีคืออะไร?
ไล่ระดับสีแบบรัศมีเปลี่ยนสีจากจุดศูนย์กลางออกไปด้านนอก สร้างการผสมสีที่เรียบและเป็นวงกลม เหมาะสำหรับไฮไลท์ พื้นหลังปุ่ม หรือภาพใด ๆ ที่ต้องการเอฟเฟกต์ “แสงเรืองแสง” ธรรมชาติ โดยการปรับสีสต็อปและรัศมี คุณสามารถจำลองแสง, ความลึก, และคุณสมบัติของวัสดุในรูปแบบเวกเตอร์บริสุทธิ์

## ทำไมต้องใช้ Aspose.Page สำหรับไล่ระดับสีแบบรัศมี?
Aspose.Page ช่วยให้คุณสร้างกราฟิกเวกเตอร์ที่อิสระต่ออุปกรณ์ด้วย API ของ Java เพียงชุดเดียว รองรับรูปแบบเข้าและออกกว่า 50 รูปแบบ—รวมถึง PostScript, PDF, และ SVG—พร้อมรักษาความแม่นยำของสีและการแอนติเอเลียสสำหรับผลลัพธ์ความละเอียดสูง ไลบรารีนี้ยังมีคลาสไล่ระดับสีที่ใช้งานง่าย ทำให้เอฟเฟ็กต์ภาพซับซ้อนสามารถนำไปใช้ได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มลงมือทำ โปรดตรวจสอบว่าคุณมี:

- ความคุ้นเคยพื้นฐานกับการเขียนโปรแกรม Java.  
- JDK 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ.  
- ไลบรารี Aspose.Page for Java (ดาวน์โหลดจาก [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## นำเข้าแพ็กเกจ
ก่อนอื่นให้นำเข้าคลาสที่เราต้องการใช้ ซึ่งรวมถึงประเภทกราฟิก AWT มาตรฐานและ API ของ Aspose.Page

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดโฟลเดอร์ที่ไฟล์ PostScript ที่สร้างขึ้นจะถูกบันทึกไว้ แทนที่ตัวแสดงตำแหน่งด้วยพาธจริงบนระบบของคุณ

```java
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างสตรีมเอาต์พุต
`FileOutputStream` เขียนไบต์ดิบลงไฟล์ ทำให้สามารถบันทึกข้อมูลไบนารีได้ การเปิดสตรีมที่มุ่งเป้าไปยังไฟล์ `.ps` จะทำให้ Aspose.Page ส่งข้อมูล PostScript ที่สร้างขึ้นโดยตรงไปยังดิสก์

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## ขั้นตอนที่ 3: สร้างตัวเลือกการบันทึก
`PsSaveOptions` กำหนดวิธีการบันทึกไฟล์ PostScript รวมถึงขนาดหน้าและการบีบอัด คุณสามารถปรับแต่งการตั้งค่าเหล่านี้ได้ แต่ค่าเริ่มต้นก็เพียงพอสำหรับตัวอย่างนี้

```java
PsSaveOptions options = new PsSaveOptions();
```

## ขั้นตอนที่ 4: สร้างเอกสาร ps
`PsDocument` แทนเอกสาร PostScript ในหน่วยความจำและให้เมธอดสำหรับเพิ่มหน้าและกราฟิก

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 5: สร้างวงกลม
`Ellipse2D.Float` อธิบายรูปทรงวงรี; เมื่อความกว้าง = ความสูง จะกลายเป็นวงกลมที่สมบูรณ์แบบ วัตถุนี้จะทำหน้าที่เป็นผ้าใบสำหรับการเติมไล่ระดับสีของเรา

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## วิธีวาดวงกลมด้วยไล่ระดับสี
เพื่อวาดวงกลมด้วยไล่ระดับสีแบบรัศมี คุณโหลด `RadialGradientPaint` เข้าไปในคอนเท็กซ์กราฟิกแล้วเติมวงรีที่กำหนดไว้ก่อนหน้านี้ การดำเนินการเดียวนี้จะทาสีรูปทรงด้วยการเปลี่ยนสีอย่างเรียบจากศูนย์กลางออกสู่ขอบ สร้างเอฟเฟกต์ที่ดูน่าสนใจ

## ขั้นตอนที่ 6: กำหนดสีไล่ระดับสี
เตรียมอาเรย์สองชุด: หนึ่งสำหรับสีที่จะปรากฏในไล่ระดับสีและอีกหนึ่งสำหรับตำแหน่งเศษส่วนที่สอดคล้องกัน (0 = ศูนย์กลาง, 1 = ขอบ)

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## ขั้นตอนที่ 7: สร้าง AffineTransform
`AffineTransform` เป็นเมทริกซ์ที่สามารถแปล, หมุน, ยืด, หรือบิดวัตถกราฟิกได้ ที่นี่มันทำการสเกลและแปลไล่ระดับสีเพื่อให้พอดีภายในวงกลมอย่างแม่นยำ

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## ขั้นตอนที่ 8: สร้าง RadialGradientPaint
`RadialGradientPaint` สร้างไล่ระดับสีแบบรัศมีบนพื้นฐานของจุดศูนย์กลาง, รัศมี, และสีสต็อป

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## ขั้นตอนที่ 9: ตั้งสีและเติมวงกลม
นำ `RadialGradientPaint` ไปใช้กับเอกสารและเติมวงกลมที่กำหนดไว้ก่อนหน้านี้ นี่คือหัวใจของ **radial gradient example** ของเราและแสดงให้เห็นว่า **fill shape with gradient** ทำอย่างไร

```java
document.setPaint(paint);
document.fill(circle);
```

## ขั้นตอนที่ 10: ปิดหน้าและบันทึกเอกสาร
สรุปหน้าปัจจุบัน, เขียนเนื้อหาไปยังดิสก์, และปิดสตรีม ไฟล์ PostScript ของคุณพร้อมสำหรับการดูด้วยโปรแกรมดู PS ใดก็ได้

```java
document.closePage();
document.save();
```

ยินดีด้วย! คุณได้สร้างตัวอย่างไล่ระดับสีแบบรัศมีใน Java PostScript ด้วย Aspose.Page สำเร็จแล้ว คุณมีรูปแบบที่นำกลับมาใช้ใหม่สำหรับ **fill shape with gradient** ที่สามารถปรับใช้กับรูปทรงอื่นและรูปแบบการส่งออกอื่น ๆ ได้

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|---------|----------|
| **FileNotFoundException** เมื่อเปิดสตรีมเอาต์พุต | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และคุณมีสิทธิ์เขียน. |
| ไล่ระดับสีดูแบนหรือหายไป | ตรวจสอบให้แน่ใจว่าอาเรย์ `fractions` มีความยาวเท่ากับอาเรย์ `colors` และ `AffineTransform` ปรับสเกลอย่างถูกต้อง. |
| สีแสดงกลับหัว | สลับลำดับของสีในอาเรย์ `colors` หรือปรับพิกัดของจุด `focus`. |

## คำถามที่พบบ่อย

**ถาม: ฉันจะหาเอกสารสำหรับ Aspose.Page for Java ได้จากที่ไหน?**  
ตอบ: เอกสารอ้างอิง API เต็มรูปแบบมีให้ใน [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).

**ถาม: ฉันจะดาวน์โหลด Aspose.Page for Java ได้อย่างไร?**  
ตอบ: ดาวน์โหลด JAR ล่าสุดจาก [releases page](https://releases.aspose.com/page/java/).

**ถาม: มีรุ่นทดลองฟรีหรือไม่?**  
ตอบ: มี—ดาวน์โหลดรุ่นทดลองจาก [Aspose free trial download page](https://releases.aspose.com/).

**ถาม: ฉันสามารถขอรับไลเซนส์ชั่วคราวสำหรับการทดสอบได้หรือไม่?**  
ตอบ: แน่นอน, ขอรับได้จาก [temporary license page](https://purchase.aspose.com/temporary-license/).

**ถาม: ฉันจะหาแหล่งสนับสนุนจากชุมชนได้จากที่ไหน?**  
ตอบ: เข้าร่วมการสนทนาที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## สรุป
ในคู่มือนี้เราได้สร้าง **radial gradient example** ที่สมบูรณ์สำหรับเอกสาร PostScript ด้วย Aspose.Page for Java โดยทำตามขั้นตอนต่าง ๆ คุณจึงมีรูปแบบที่นำกลับมาใช้ใหม่สำหรับ **fill shape with gradient** ซึ่งสามารถปรับใช้กับ PDF, SVG หรือรูปแบบอื่นใดที่ Aspose.Page รองรับ ทดลองเปลี่ยนสี, รัศมี, และรูปทรงต่าง ๆ เพื่อเพิ่มคุณค่าให้กับโครงการกราฟิก Java ของคุณ

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [Create Texture Pattern in PostScript with Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}