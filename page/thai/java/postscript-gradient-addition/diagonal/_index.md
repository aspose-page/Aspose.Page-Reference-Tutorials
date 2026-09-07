---
date: 2026-09-04
description: เรียนรู้วิธีเพิ่มไล่สีใน Java PostScript ด้วย Aspose.Page Java โดยสร้างการเปลี่ยนสีแนวทแยงด้วย
  LinearGradientPaint เพื่อให้เอกสารมีสีสันสดใส
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'วิธีเพิ่มไล่สี: ไล่สีแนวทแยงใน Java PostScript โดยใช้ Aspose.Page Java'
og_description: เรียนรู้วิธีเพิ่มไล่สีใน Java PostScript โดยใช้ Aspose.Page Java คู่มือนี้จะแสดงวิธีสร้างไล่สีแนวทแยงด้วย
  LinearGradientPaint เพียงไม่กี่ขั้นตอน
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: วิธีเพิ่มไล่สีใน Java PostScript ด้วย Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'วิธีเพิ่มไล่สี: ไล่สีแนวทแยงใน Java PostScript โดยใช้ Aspose.Page Java'
url: /th/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไล่ระดับสีแนวทแยงใน Java PostScript ด้วย Aspose.Page Java

## บทนำ
หากคุณต้องการเพิ่มความสวยงามให้ไฟล์ PostScript ด้วยการไล่ระดับสีแนวทแยงที่เรียบเนียน, **Aspose.Page Java** ทำให้ทำได้อย่างง่ายดายอย่างน่าแปลกใจ ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีเพิ่มเอฟเฟกต์ไล่ระดับสี** ทีละขั้นตอน โดยใช้คลาส `LinearGradientPaint` จาก Java 2D เมื่อเสร็จคุณจะมีโค้ดสั้นที่พร้อมรันซึ่งสร้างเอกสาร PostScript พร้อมไล่ระดับสีแนวทแยงที่สดใส และคุณจะเข้าใจว่าทำไมวิธีนี้จึงดูแลรักษาได้ง่ายกว่าการเขียนคำสั่ง PostScript ดิบด้วยตนเอง

## วิธีเพิ่มไล่ระดับสีใน Java PostScript
การเพิ่มไล่ระดับสีอาจฟังดูเหมือนเป็นงานด้านกราฟิกเท่านั้น, แต่ด้วย Aspose.Page คุณจะได้การควบคุมเต็มที่ต่อคำสั่ง PostScript ภายในขณะที่ยังใช้ Java อย่างเดียว ส่วนนี้จะอธิบายว่าทำไมวิธีนี้ถึงได้ผลและคุณจะได้อะไรบ้างเมื่อเทียบกับการเขียนคำสั่ง PostScript ดิบด้วยตนเอง

## คำตอบสั้น
- **ต้องการไลบรารีอะไร?** Aspose.Page for Java.  
- **คลาสใดสร้างไล่ระดับสี?** `LinearGradientPaint`.  
- **สามารถเปลี่ยนสีได้หรือไม่?** ใช่ – แก้ไขอาร์เรย์ `Color[]`.  
- **ต้องการไลเซนส์สำหรับการผลิตหรือไม่?** ต้องมีไลเซนส์เชิงพาณิชย์; มีการทดลองใช้ฟรี.  
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** ประมาณ 10 นาทีสำหรับไล่ระดับสีพื้นฐาน.

## Aspose.Page Java คืออะไร?
Aspose.Page Java เป็น API ที่ครบวงจรที่ช่วยให้นักพัฒนาสามารถสร้าง, แก้ไข, และแปลงไฟล์ PostScript และ PDF ได้โดยไม่ต้องใช้ซอฟต์แวร์ภายนอก ไลบรารีนี้รองรับ **รูปแบบการเข้าและออกกว่า 50 รูปแบบ** และสามารถประมวลผลเอกสารที่มี **มากกว่า 500 หน้า** พร้อมรักษาการใช้หน่วยความจำให้อยู่ต่ำกว่า 100 MB.

## ทำไมต้องใช้ไล่ระดับสีแนวทแยง?
ไล่ระดับสีแนวทแยงเพิ่มความลึกและความน่าสนใจให้กับแผนภูมิ, แบนเนอร์, หรือองค์ประกอบกราฟิกใด ๆ ที่ต้องการลุคทันสมัย เนื่องจากไล่ระดับสีวิ่งจากมุมหนึ่งไปยังอีกมุมหนึ่ง มันจึงเหมาะสำหรับพื้นหลัง, สกินของปุ่ม, และรูปทรงตกแต่งต่าง ๆ ให้ผลลัพธ์ที่เป็นมืออาชีพโดยไม่ต้องใช้รูปภาพเสริมเพิ่มเติม.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

- Java Development Kit (JDK) 8 หรือสูงกว่า.  
- IDE เช่น Eclipse, IntelliJ IDEA, หรือ VS Code.  
- ไลบรารี **Aspose.Page for Java** – ดาวน์โหลดเวอร์ชันล่าสุดจาก [official download page](https://releases.aspose.com/page/java/).

## นำเข้าแพ็กเกจ
แพ็กเกจ `java.awt` ให้คลาสกราฟิกหลัก, ส่วนแพ็กเกจ `com.aspose.page` ให้คุณเข้าถึง API เฉพาะของ PostScript

คลาส `LinearGradientPaint` เป็นสะพานของ Aspose.Page ไปสู่ฟังก์ชันไล่ระดับสีของ Java 2D.  
`AffineTransform` ช่วยให้สามารถหมุนและปรับสเกลของไล่ระดับสีให้เรียงแนวทแยงได้.

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ขั้นตอนที่ 1: สร้าง output stream สำหรับเอกสาร PostScript
แรกสุด, กำหนดโฟลเดอร์ที่ไฟล์จะถูกบันทึกและเปิด `FileOutputStream`. สตรีมนี้รับข้อมูล PostScript ที่สร้างขึ้น.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## ขั้นตอนที่ 2: สร้าง save options ด้วยขนาด A4
`PsSaveOptions` ให้คุณกำหนดขนาดหน้า, ความละเอียด, และการตั้งค่าอื่น ๆ ของการส่งออก ที่นี่เราใช้ขนาด A4 เริ่มต้น ซึ่งคือ 595 × 842 จุดที่ 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## ขั้นตอนที่ 3: สร้างเอกสาร PS ใหม่
คลาส `PsDocument` แทนเอกสาร PostScript และให้เมธอดสำหรับสร้างหน้าและวาดกราฟิก  
สร้างอินสแตนซ์ของ `PsDocument` ด้วยการใช้ output stream และ save options. ธง `false` บอกคอนสตรัคเตอร์ว่าไม่ให้เปิดหน้าใหม่โดยอัตโนมัติ – เราจะทำในภายหลัง.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## ขั้นตอนที่ 4: สร้างสี่เหลี่ยม
กำหนดสี่เหลี่ยมที่จะรับการเติมไล่ระดับสี ตำแหน่งของสี่เหลี่ยม (200, 100) และขนาด (200 × 100) ถูกเลือกเพื่อให้ไล่ระดับสีมองเห็นได้ชัดเจน.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## ขั้นตอนที่ 5: สร้างการแปลงไล่ระดับสี
`AffineTransform` ช่วยให้เราหมุน, ปรับสเกล, และแปลตำแหน่งของไล่ระดับสีเพื่อให้วิ่งแนวทแยงผ่านสี่เหลี่ยม คณิตศาสตร์ด้านล่างคำนวณความยาวด้านตรงข้ามของสามเหลี่ยมมุมฉากและปรับอัตราส่วนสเกลตามนั้น.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## ขั้นตอนที่ 6: สร้าง Linear Gradient Paint แนวทแยง
`LinearGradientPaint` เป็นคลาสหลักที่สร้างการเปลี่ยนสี มันครอบคลุมจากมุมบนซ้ายของสี่เหลี่ยมไปยังมุมล่างขวา โดยใช้การแปลงที่กำหนดไว้ก่อนหน้า `MultipleGradientPaint.CycleMethod.NO_CYCLE` ทำให้ไล่ระดับสีไม่ทำซ้ำ.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## ขั้นตอนที่ 7: ตั้งค่า paint และเติมสี่เหลี่ยม
ใช้ gradient paint กับเอกสารและเติมรูปสี่เหลี่ยม ขั้นตอนนี้จะเรนเดอร์การไล่ระดับสีแนวทแยงบนหน้า PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## ขั้นตอนที่ 8: ปิดหน้าปัจจุบันและบันทึกเอกสาร
สุดท้าย, ปิดหน้า, ทำการ flush สตรีม, และบันทึกไฟล์ ไฟล์ `DiagonalGradient_outPS.ps` ที่ได้สามารถเปิดด้วยโปรแกรมดู PostScript ใดก็ได้.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## ปัญหาทั่วไปและเคล็ดลับ
- **ไล่ระดับสีดูแบน** – ตรวจสอบมุมการหมุนอีกครั้ง; การหมุน 45° จะสร้างแนวทแยงที่แท้จริง.  
- **สีดูจาง** – ตรวจสอบว่าคุณใช้ `MultipleGradientPaint.ColorSpaceType.SRGB` เพื่อการเรนเดอร์สีที่แม่นยำ.  
- **เกิดข้อผิดพลาดไฟล์ไม่พบ** – ยืนยันว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน.  
- **เอกสารขนาดใหญ่ทำให้หน่วยความจำพุ่งสูง** – ใช้ `PsSaveOptions.setCompress(true)` เพื่อลดการใช้หน่วยความจำ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ไลบรารีนี้สำหรับการดำเนินการกราฟิกอื่น ๆ ใน Java ได้หรือไม่?**  
A: ใช่, Aspose.Page for Java มีชุดเต็มของ primitive การวาด, การแสดงผลข้อความ, และความสามารถในการจัดการภาพ.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Page Java หรือไม่?**  
A: แน่นอน. คุณสามารถดาวน์โหลดรุ่นทดลองที่ทำงานเต็มรูปแบบจาก [Aspose free trial page](https://releases.aspose.com/).

**Q: ฉันจะหาเอกสารสำหรับ Aspose.Page Java ได้จากที่ไหน?**  
A: การอ้างอิง API อย่างเป็นทางการมีให้ที่ [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: ฉันจะซื้อไลเซนส์สำหรับ Aspose.Page Java ได้อย่างไร?**  
A: สามารถซื้อไลเซนส์ได้โดยตรงจาก [Aspose purchase portal](https://purchase.aspose.com/buy).

**Q: ต้องการความช่วยเหลือหรือมีคำถาม?**  
A: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) ที่ดำเนินการโดยชุมชนเพื่อรับความช่วยเหลือจากวิศวกรของ Aspose และนักพัฒนาคนอื่น ๆ.

---

**อัปเดตล่าสุด:** 2026-09-04  
**ทดสอบด้วย:** Aspose.Page for Java 24.12 (latest)  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้าง Radial Gradient ใน PostScript ด้วย Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [วิธีเพิ่ม Gradient ใน Java PostScript ด้วย Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [สร้าง PostScript Gradient ใน Java – เพิ่ม Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}