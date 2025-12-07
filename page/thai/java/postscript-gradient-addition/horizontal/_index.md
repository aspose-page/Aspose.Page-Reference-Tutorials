---
date: 2025-12-07
description: เรียนรู้วิธีเพิ่มไล่สีแนวนอนใน Java PostScript โดยใช้ Linear Gradient
  Paint Java กับ Aspose.Page สำหรับ Java.
language: th
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: เพิ่มการไล่สีใน Java PostScript ด้วย Linear Gradient Paint Java
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มการไล่สีใน Java PostScript ด้วย Linear Gradient Paint Java

## บทนำ
ในบทแนะนำที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีสร้างการไล่สีแนวนอนที่สวยงามในเอกสาร PostScript โดยใช้ **Linear Gradient Paint Java** Aspose.Page for Java ทำให้การทำงานกับ PostScript, PDF และรูปแบบเวกเตอร์อื่น ๆ เป็นเรื่องง่าย และคลาส `LinearGradientPaint` ให้คุณควบคุมการเปลี่ยนสีได้อย่างละเอียด เมื่อจบคู่มือคุณจะสามารถเรนเดอร์การไล่สีบนรูปทรง **และ** ข้อความ ทำให้เอกสารของคุณดูเป็นมืออาชีพและดึงดูดสายตา

## คำตอบอย่างรวดเร็ว
- **What library is required?** Aspose.Page for Java (supports Linear Gradient Paint Java).  
- **How long does implementation take?** About 10‑15 minutes for a basic gradient.  
- **Do I need a license?** A temporary or full license is required for production use.  
- **Which JDK version works?** Java 8 or newer.  
- **Can I use the gradient on both shapes and text?** Yes – you can fill shapes and stroke or fill text with the same gradient.

## ข้อกำหนดเบื้องต้น
ก่อนจะลงมือเขียนโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้จาก [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นในโปรเจกต์ Java ของคุณ การนำเข้าต่าง ๆ นี้จะทำให้คุณเข้าถึง primitive ของกราฟิก, การจัดการไล่สี, และ API ของ Aspose.Page

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
ตั้งค่า output stream, เอกสาร, และสี่เหลี่ยมที่จะเป็นพื้นที่สำหรับการไล่สี

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

## ขั้นตอนที่ 2: สร้าง Horizontal Linear Gradient Paint
ที่นี่เราจะสร้างอ็อบเจกต์ **Linear Gradient Paint Java** ที่กำหนดการเปลี่ยนสีแนวนอน `AffineTransform` จะสเกลการไล่สีให้ตรงกับความกว้างและความสูงของสี่เหลี่ยม

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
ตอนนี้ให้เติมสี่เหลี่ยมด้วยการไล่สีที่เรากำหนดไว้

```java
// Fill the rectangle
document.fill(rectangle);
```

## ขั้นตอนที่ 4: เติมข้อความด้วยการไล่สี
คุณสามารถใช้การไล่สีเดียวกันกับข้อความเพื่อสร้างเอฟเฟกต์ที่โดดเด่น

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## ขั้นตอนที่ 5: วาดขอบข้อความด้วยการไล่สี
สุดท้ายให้วาดขอบข้อความโดยใช้การไล่สีเป็นสีของเส้นขอบ

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| Gradient appears stretched | Incorrect `AffineTransform` scaling | Ensure the transform’s width and height match the rectangle’s dimensions (200 × 100 in the example). |
| Colors look faded | Alpha values set too low | Increase the alpha component (the fourth value in `new Color(r,g,b,alpha)`). |
| Text is not visible | Paint not set before drawing text | Call `document.setPaint(paint)` **before** any `fillAndStrokeText` or `outlineText` calls. |

## คำถามที่พบบ่อย
### Can I use Aspose.Page for Java in commercial projects?
Yes, Aspose.Page for Java can be used in commercial projects. For licensing details, visit [Aspose.Purchase](https://purchase.aspose.com/buy).

### Is there a free trial available?
Yes, you can access a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).

### Where can I find additional documentation and support?
Visit the [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) for comprehensive resources. For community support, check the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

### How can I obtain a temporary license?
You can obtain a temporary license from [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### What are the system requirements for Aspose.Page for Java?
Refer to the [documentation](https://reference.aspose.com/page/java/) for detailed system requirements.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}