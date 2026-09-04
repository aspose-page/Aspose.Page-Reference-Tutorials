---
date: 2026-09-04
description: เรียนรู้วิธีสร้าง horizontal gradient java ในไฟล์ PostScript ด้วย Linear
  Gradient Paint Java พร้อม Aspose.Page for Java ขั้นตอนโค้ดทีละขั้นตอน ปัญหาที่พบบ่อย
  และคำถามที่พบบ่อย
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: สร้าง horizontal gradient java ใน PostScript ด้วย Aspose
og_description: สร้าง horizontal gradient java ใน PostScript ด้วย Linear Gradient
  Paint Java บทแนะนำ Aspose.Page นี้จะแสดงขั้นตอนที่แน่นอน ข้อกำหนดเบื้องต้น และเคล็ดลับการแก้ปัญหา
  ภายในเวลาไม่เกิน 15 นาที
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: สร้าง horizontal gradient java ใน PostScript ด้วย Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: สร้าง horizontal gradient java ใน PostScript ด้วย Aspose
url: /th/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มการไล่สีแนวนอนใน Java PostScript โดยใช้ Linear Gradient Paint

## บทนำ
ในบทแนะนำเชิงลึกนี้คุณจะได้เรียนรู้ **วิธีสร้างการไล่สีแนวนอนใน Java** ในเอกสาร PostScript โดยใช้คลาส **Linear Gradient Paint Java** ที่มาพร้อมกับ Aspose.Page for Java เราจะเดินผ่านทุกขั้นตอน—ตั้งแต่การตั้งค่าโครงการจนถึงการเรนเดอร์การไล่สีบนรูปทรงและข้อความ—เพื่อให้คุณสร้างกราฟิกที่ดูเรียบหรูพร้อมพิมพ์ได้ในไม่กี่นาที ไม่ว่าคุณจะกำลังสร้างเครื่องมือรายงาน, เครื่องมืออัตโนมัติการออกแบบ, หรือไดรเวอร์เครื่องพิมพ์แบบกำหนดเอง คู่มือนี้จะให้โค้ดที่คุณต้องการอย่างแม่นยำ

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for Java (รวม Linear Gradient Paint Java).  
- **การทำงานใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับการไล่สีแนวนอนพื้นฐาน.  
- **ฉันต้องการใบอนุญาตหรือไม่?** จำเป็นต้องมีใบอนุญาตชั่วคราวหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์.  
- **เวอร์ชัน JDK ที่ใช้ได้คืออะไร?** Java 8 หรือใหม่กว่า.  
- **ฉันสามารถใช้การไล่สีบนรูปทรงและข้อความได้หรือไม่?** ใช่ – อินสแตนซ์ `LinearGradientPaint` เดียวกันสามารถเติมรูปทรงและใช้กับเส้นขอบหรือการเติมของข้อความได้.

## การไล่สีแนวนอนคืออะไรและทำไมต้องใช้?
การไล่สีแนวนอนผสมสีจากขอบซ้ายของวัตถุไปยังขอบขวา สร้างการเปลี่ยนแปลงที่เรียบเนียนซึ่งเพิ่มความลึกและความน่าสนใจทางสายตา เหมาะสำหรับส่วนประกอบ UI สมัยใหม่, หัวข้อที่เน้น, หรือการเงาเบื้องหลังอย่างละเอียดในรายงาน PDF หรือ PostScript การใช้ **Linear Gradient Paint Java** ทำให้คุณควบคุมสีเริ่มต้นและสีสิ้นสุด, ความทึบแสง, และการสเกลได้อย่างแม่นยำ เพื่อให้ผลลัพธ์คมชัดบนอุปกรณ์หรือเครื่องพิมพ์ใดก็ได้

## ข้อกำหนดเบื้องต้น
ก่อนจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณแล้ว  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้จาก [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นในโครงการ Java ของคุณ การนำเข้าต่าง ๆ นี้จะให้คุณเข้าถึง primitive ของกราฟิก, การจัดการไล่สี, และ API ของ Aspose.Page  

`PsDocument` class แสดงถึงเอกสาร PostScript ที่คุณสามารถวาดกราฟิกลงไปได้  

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ขั้นตอนที่ 1: สร้างสี่เหลี่ยม
แรกสุด ตั้งค่าการสตรีมผลลัพธ์, เอกสาร, และสี่เหลี่ยมที่จะเป็นที่เก็บการไล่สี  

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## ขั้นตอนที่ 2: สร้าง Linear Gradient Paint แนวนอน
`LinearGradientPaint` คือคลาสหลักที่กำหนดการเปลี่ยนแปลงสีเชิงเส้น  

คลาส `LinearGradientPaint` แสดงถึงอ็อบเจ็กต์สีที่เรนเดอร์การไล่สีตามเส้นตรง; คุณระบุจุดเริ่มต้น/สิ้นสุด, จุดสีหยุด, และ `AffineTransform` ทางเลือกเพื่อสเกลให้เข้ากับรูปทรงของคุณ  

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## ขั้นตอนที่ 3: เติมสี่เหลี่ยม
ตอนนี้เติมสี่เหลี่ยมด้วยการไล่สีที่เรากำหนดไว้  

```java
// Fill the rectangle
document.fill(rectangle);
```

## ขั้นตอนที่ 4: เติมข้อความด้วยการไล่สี
คุณยังสามารถใช้การไล่สีเดียวกันกับข้อความ เพื่อสร้างเอฟเฟกต์ภาพที่โดดเด่น  

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## ขั้นตอนที่ 5: วาดเส้นขอบข้อความด้วยการไล่สี
สุดท้าย ให้ร่างเส้นขอบข้อความโดยใช้การไล่สีเป็นสีเส้นขอบ  

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| การไล่สีดูบิดเบี้ยว | การสเกล `AffineTransform` ไม่ถูกต้อง | ตรวจสอบให้แน่ใจว่าความกว้างและความสูงของการแปลงตรงกับขนาดของสี่เหลี่ยม (200 × 100 ในตัวอย่าง) |
| สีดูจาง | ค่าความโปร่งใส (alpha) ตั้งค่าต่ำเกินไป | เพิ่มค่า alpha (ค่าที่สี่ใน `new Color(r,g,b,alpha)`) |
| ข้อความไม่แสดง | ไม่ได้ตั้งค่า Paint ก่อนวาดข้อความ | เรียก `document.setPaint(paint)` **ก่อน** การเรียก `fillAndStrokeText` หรือ `outlineText` ใด ๆ |

## คำถามที่พบบ่อย
**Q:** ฉันสามารถใช้ Aspose.Page for Java ในโครงการเชิงพาณิชย์ได้หรือไม่?  
**A:** ใช่, Aspose.Page for Java สามารถใช้ในโครงการเชิงพาณิชย์ได้ สำหรับรายละเอียดการให้ใบอนุญาต โปรดเยี่ยมชมหน้า [Aspose.Purchase](https://purchase.aspose.com/buy)

**Q:** มีการทดลองใช้ฟรีหรือไม่?  
**A:** มี, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.Page for Java ได้ที่หน้า [Aspose.Page for Java free trial](https://releases.aspose.com/)

**Q:** ฉันจะหาเอกสารและการสนับสนุนเพิ่มเติมได้จากที่ไหน?  
**A:** เยี่ยมชม [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) เพื่อรับทรัพยากรที่ครบถ้วน สำหรับความช่วยเหลือจากชุมชน ตรวจสอบที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39)

**Q:** ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร?  
**A:** คุณสามารถรับใบอนุญาตชั่วคราวได้จากหน้า [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/)

**Q:** ความต้องการระบบสำหรับ Aspose.Page for Java คืออะไร?  
**A:** ดูที่ [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) สำหรับรายละเอียดความต้องการระบบ

---

**อัปเดตล่าสุด:** 2026-09-04  
**ทดสอบกับ:** Aspose.Page for Java 24.11  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างการไล่สี PostScript ใน Java – เพิ่มการไล่สีแนวตั้ง](/page/java/postscript-gradient-addition/vertical/)
- [วิธีเพิ่มการไล่สี: การไล่สีแนวทแยงใน Java PostScript โดยใช้ Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [สร้างการไล่สี PostScript – การไล่สีรัศมีใน Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}