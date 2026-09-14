---
date: 2026-09-14
description: เรียนรู้วิธีสร้าง postscript gradient java ด้วย Aspose.Page คู่มือแบบขั้นตอนนี้จะแสดงวิธีเพิ่ม
  vertical gradient ไปยังไฟล์ PostScript เพียงไม่กี่บรรทัดของโค้ด Java
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: เพิ่ม Vertical Gradient ใน Java PostScript
og_description: เรียนรู้วิธีสร้าง postscript gradient java ด้วย Aspose.Page คู่มือแบบขั้นตอนนี้จะแสดงวิธีเพิ่ม
  vertical gradient ไปยังไฟล์ PostScript เพียงไม่กี่บรรทัดของโค้ด Java
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: สร้าง postscript gradient java – vertical gradient
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: สร้าง postscript gradient java – vertical gradient
url: /th/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง postscript gradient java – gradient แนวตั้ง

## บทนำ
Aspose.Page for Java เป็นไลบรารีที่ช่วยให้คุณสร้างและจัดการไฟล์ PostScript และ PDF อย่างโปรแกรมเมติก ในบทเรียนที่ครอบคลุมนี้คุณจะได้เรียนรู้วิธี **create postscript gradient java** ด้วยไลบรารีนี้ การเพิ่ม gradient แนวตั้งสามารถทำให้เอกสารของคุณดูมีชีวิตชีวาและเป็นมืออาชีพมากขึ้น และด้วยเพียงไม่กี่บรรทัดของโค้ดคุณก็จะได้ผลลัพธ์ภาพที่น่าทึ่ง เราจะพาคุณผ่านแต่ละขั้นตอน อธิบายเหตุผลที่แต่ละส่วนสำคัญ และให้เคล็ดลับปฏิบัติเพื่อหลีกเลี่ยงข้อผิดพลาดทั่วไป เมื่อจบคู่มือคุณจะสามารถสร้างไฟล์ PostScript ที่มีการเปลี่ยนสีแนวตั้งอย่างราบรื่นและดึงดูดสายตา

## คำตอบสั้น
- **What library is needed?** Aspose.Page for Java  
- **Can I customize colors?** Yes, any `java.awt.Color` can be used  
- **Is rotation supported?** Yes, you can rotate the gradient with an `AffineTransform`  
- **What output format is produced?** A standard PostScript (.ps) file  
- **Do I need a license for production?** Yes, a commercial license is required  

## ทำไมต้องเพิ่ม gradient แนวตั้งในเอกสาร PostScript?
การเพิ่ม gradient แนวตั้งทำให้หน้าของคุณมีความลึก เพิ่มลำดับชั้นของภาพ และทำให้ขนาดไฟล์ต่ำลง เนื่องจาก gradient ถูกกำหนดในรูปแบบเวกเตอร์แทนการใช้ภาพแรสเตอร์ เทคนิคนี้เหมาะสำหรับหัวรายงาน คู่มือเทคนิค หรือโบรชัวร์ใด ๆ ที่ต้องการลุคทันสมัยโดยไม่เสียความสามารถในการขยายขนาด

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มทำตามบทเรียน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for Java release page](https://releases.aspose.com/page/java/)

## นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ ให้นำเข้าแพ็กเกจที่จำเป็นเพื่อเริ่มต้น:
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

ตอนนี้เราจะเดินผ่านกระบวนการเพิ่ม gradient แนวตั้งทีละขั้นตอน

## วิธีสร้าง postscript gradient java
โหลดสภาพแวดล้อม Java ของคุณ สร้างอินสแตนซ์ `PsSaveOptions` แล้วเรียก `Document.save` – นี่คือลำดับหลักที่สร้างไฟล์ PostScript พร้อม gradient แนวตั้ง API จะจัดการการไล่สี การแปลงพิกัด และการ flush หน้าให้คุณ ดังนั้นคุณเพียงแค่ต้องกำหนดสี่เหลี่ยมและพารามิเตอร์ของ gradient

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ
อ็อบเจกต์ `File` แทนโฟลเดอร์ที่ผลลัพธ์จะถูกเขียน ไดเรกทอรีต้องมีอยู่ก่อนที่สตรีมจะเปิด มิฉะนั้นจะเกิด `IOException`
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้าง output stream สำหรับเอกสาร PostScript
`FileOutputStream` เขียนข้อมูล PostScript แบบไบนารีลงดิสก์ การใช้บล็อก `try‑with‑resources` รับประกันว่าสตรีมจะถูกปิดแม้เกิดข้อยกเว้น
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### ขั้นตอนที่ 3: สร้าง save options ด้วยขนาด A4
`PsSaveOptions` ให้คุณระบุขนาดหน้า DPI และการฝังฟอนต์ การตั้งค่าขนาดเป็น A4 (595 × 842 points) ตรงกับเอกสารที่พิมพ์ส่วนใหญ่
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### ขั้นตอนที่ 4: สร้างเอกสาร PS ใหม่
`Document` เป็นอ็อบเจกต์ระดับบนที่แทนไฟล์ PostScript หนึ่งไฟล์ในหน่วยความจำ คำสั่งวาดทั้งหมดจะถูกส่งไปยังอ็อบเจกต์นี้
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### ขั้นตอนที่ 5: สร้างสี่เหลี่ยม
`Rectangle2D.Double` กำหนดพื้นที่ที่จะถูกเติมด้วย gradient พิกัดของสี่เหลี่ยมแสดงเป็น points (1 point = 1/72 inch)
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### ขั้นตอนที่ 6: ตั้งค่าสีและอัตราส่วนสำหรับ gradient
อาร์เรย์ `float[]` กำหนดตำแหน่งของแต่ละสี (จาก 0.0 ถึง 1.0) อ็อบเจกต์ `Color` เก็บค่า RGB จริง คุณสามารถใช้ `java.awt.Color` ใดก็ได้ที่ต้องการ
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### ขั้นตอนที่ 7: สร้างการแปลง gradient
`AffineTransform` ปรับสเกลและหมุน gradient สำหรับ gradient แนวตั้งบริสุทธิ์คุณเพียงต้องสเกลแกน Y; สามารถเพิ่มการหมุนในภายหลังได้หากต้องการ
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### ขั้นตอนที่ 8: สร้าง vertical linear gradient paint
`LinearGradientPaint` เชื่อมต่อสี่เหลี่ยม จุดสีหยุด และการแปลง วัตถุนี้จะถูกส่งต่อไปยังกราฟิกคอนเท็กซ์ต่อไป
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### ขั้นตอนที่ 9: ตั้งค่า paint และเติมสี่เหลี่ยม
`Graphics2D.setPaint` ใช้ gradient และ `fill` จะเรนเดอร์มันภายในสี่เหลี่ยมที่คุณกำหนดไว้ก่อนหน้า
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### ขั้นตอนที่ 10: ปิดหน้าและบันทึกเอกสาร
การเรียก `document.save` จะเขียนสตรีม PostScript ทั้งหมดไปยังไฟล์ผลลัพธ์และปล่อยทรัพยากรเนทีฟทั้งหมด
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

ขอแสดงความยินดี! คุณได้เพิ่ม gradient แนวตั้งในเอกสาร Java PostScript ของคุณสำเร็จโดยใช้ Aspose.Page for Java

## ปัญหาที่พบบ่อยและวิธีแก้
- **Gradient appears flat:** ตรวจสอบให้แน่ใจว่าการสเกลของ `AffineTransform` ตรงกับขนาดของสี่เหลี่ยม  
- **Colors look washed out:** ยืนยันว่าคุณใช้ `ColorSpaceType` ที่ถูกต้อง (SRGB) และอาร์เรย์ fractions เรียงจาก 0.0 ถึง 1.0  
- **File not generated:** ตรวจสอบว่าไดเรกทอรีผลลัพธ์ (`dataDir`) มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน

## คำถามที่พบบ่อย
**Q: Can I use Aspose.Page for Java with other Java libraries?**  
A: ใช่, Aspose.Page for Java ถูกออกแบบให้ทำงานร่วมกับไลบรารี Java อื่น ๆ เช่น Apache Commons หรือ Spring อย่างราบรื่น  

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: มี คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีได้จาก [free trial download page](https://releases.aspose.com/)  

**Q: Where can I find additional documentation?**  
A: เอกสารรายละเอียดเพิ่มเติมมีให้ที่ [Aspose.Page Java API reference](https://reference.aspose.com/page/java/)  

**Q: How can I purchase Aspose.Page for Java?**  
A: คุณสามารถซื้อ Aspose.Page for Java ได้ที่ [Aspose.Page purchase page](https://purchase.aspose.com/buy)  

**Q: Is there a forum for Aspose.Page discussions?**  
A: มี คุณสามารถเข้าร่วมฟอรั่มชุมชนได้ที่ [Aspose.Page community forum](https://forum.aspose.com/c/page/39)  

## คำถามที่พบบ่อยเพิ่มเติม

**Q: Can I create other gradient directions (horizontal, diagonal)?**  
A: แน่นอน ปรับจุดเริ่มต้นและจุดสิ้นสุดใน `LinearGradientPaint` และเปลี่ยนมุมการหมุนใน `AffineTransform`  

**Q: Does this work with PDF output as well?**  
A: โลจิก gradient เดียวกันสามารถใช้ได้เมื่อบันทึกเป็น PDF โดยใช้ `PdfSaveOptions` แทน `PsSaveOptions`  

**Q: How do I change the gradient size dynamically?**  
A: คำนวณขนาดสี่เหลี่ยมในเวลารันไทม์และส่งค่าที่ได้ไปยังคอนสตรัคเตอร์ของ `Rectangle2D` และ `AffineTransform`

---

**อัปเดตล่าสุด:** 2026-09-14  
**ทดสอบด้วย:** Aspose.Page for Java 24.11 (latest)  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้าง Radial Gradient ใน PostScript ด้วย Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [วิธีแปลง PostScript เป็น PDF ด้วย Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page Transparency Tutorial – เพิ่ม Transparency ใน Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}