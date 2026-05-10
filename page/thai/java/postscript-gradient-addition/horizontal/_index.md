---
date: 2026-02-13
description: เรียนรู้วิธีเพิ่มไล่สีใน Java PostScript ด้วย Linear Gradient Paint Java
  พร้อม Aspose.Page สำหรับ Java.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: วิธีเพิ่มการไล่สีใน Java PostScript ด้วย Linear Gradient Paint
url: /th/java/postscript-gradient-addition/horizontal/
weight: 11
---

ที่ครอบคลุมนี้ คุณจะได้ค้นพบ **วิธีเพิ่ม gradient** ในเอกสาร PostScript ด้วย Java."

Continue.

We need to translate rest.

Proceed step by step.

Also list under Quick Answers: translate each question and answer.

E.g., "- **What library is required?** Aspose.Page for Java (supports Linear Gradient Paint Java)." => "- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for Java (supports Linear Gradient Paint Java)."

Similarly others.

Now table: translate Issue, Why It Happens, Fix headings. Keep content translation.

Now FAQ: translate Q and A.

Make sure to keep URLs unchanged.

Also "Last Updated:" etc.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม Gradient ใน Java PostScript ด้วย Linear Gradient Paint

## บทนำ
ในบทแนะนำที่ครอบคลุมนี้ คุณจะได้ค้นพบ **วิธีเพิ่ม gradient** ในเอกสาร PostScript ด้วย Java เราจะอธิบายขั้นตอนการสร้าง gradient แนวนอนที่สวยงามโดยใช้ **Linear Gradient Paint Java** ซึ่งเป็นคลาสที่ให้คุณควบคุมการเปลี่ยนสีแบบพิกเซล‑เพอร์เฟค ด้วย Aspose.Page for Java คุณสามารถเรนเดอร์ gradient บนทั้งรูปทรง **และ** ข้อความ ทำให้เอกสารของคุณดูเรียบหรูและดึงดูดสายตา

## คำตอบสั้น
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for Java (supports Linear Gradient Paint Java).  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10‑15 นาทีสำหรับ gradient พื้นฐาน  
- **ต้องมีลิขสิทธิ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ชั่วคราวหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์  
- **เวอร์ชัน JDK ที่ทำงานได้?** Java 8 หรือใหม่กว่า  
- **สามารถใช้ gradient กับรูปทรงและข้อความได้หรือไม่?** ใช่ – คุณสามารถเติมรูปทรงและ stroke หรือ fill ข้อความด้วย gradient เดียวกันได้  

## Gradient แนวนอนคืออะไรและทำไมต้องใช้?
Gradient แนวนอนผสานสีอย่างราบรื่นจากซ้ายไปขวาบนรูปทรงหรือข้อความ เหมาะสำหรับสร้างองค์ประกอบ UI สมัยใหม่, หัวข้อที่เน้น, หรือเอฟเฟกต์พื้นหลังแบบละเอียดในรายงาน การใช้ **Linear Gradient Paint Java** ทำให้คุณกำหนดสีเริ่มต้นและสีสุดท้าย, ความทึบ, และการสเกลได้อย่างแม่นยำ เพื่อให้ผลลัพธ์คมชัดบนอุปกรณ์ใดก็ได้

## ข้อกำหนดเบื้องต้น
ก่อนจะลงมือเขียนโค้ด ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:

- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้จาก [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นในโปรเจกต์ Java ของคุณ การนำเข้าเหล่านี้ทำให้คุณเข้าถึง primitive ด้านกราฟิก, การจัดการ gradient, และ API ของ Aspose.Page

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
ตั้งค่า output stream, document, และสี่เหลี่ยมที่จะเป็นที่เก็บ gradient

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
ที่นี่เราจะสร้างอ็อบเจ็กต์ **Linear Gradient Paint Java** ที่กำหนดการเปลี่ยนสีแนวนอน `AffineTransform` จะสเกล gradient ให้ตรงกับความกว้างและความสูงของสี่เหลี่ยม

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

## ขั้นตอนที่ 3: เติมสี่เหลี่ยมด้วย Gradient
ตอนนี้ให้เติมสี่เหลี่ยมด้วย gradient ที่เรากำหนดไว้

```java
// Fill the rectangle
document.fill(rectangle);
```

## ขั้นตอนที่ 4: เติมข้อความด้วย Gradient
คุณสามารถใช้ gradient เดียวกันกับข้อความเพื่อสร้างเอฟเฟกต์ที่โดดเด่น

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## ขั้นตอนที่ 5: วาดขอบข้อความด้วย Gradient
สุดท้ายให้วาดขอบข้อความโดยใช้ gradient เป็นสีของ stroke

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| Gradient ดูบิดเบี้ยว | การสเกล `AffineTransform` ไม่ถูกต้อง | ตรวจสอบให้แน่ใจว่าความกว้างและความสูงของการแปลงตรงกับขนาดของสี่เหลี่ยม (200 × 100 ในตัวอย่าง) |
| สีดูจาง | ค่า Alpha ตั้งค่าต่ำเกินไป | เพิ่มค่า alpha (ค่าที่สี่ใน `new Color(r,g,b,alpha)`) |
| ข้อความไม่แสดง | ไม่ได้ตั้งค่า Paint ก่อนวาดข้อความ | เรียก `document.setPaint(paint)` **ก่อน** เรียก `fillAndStrokeText` หรือ `outlineText` ใด ๆ |

## คำถามที่พบบ่อย
**ถาม:** สามารถใช้ Aspose.Page for Java ในโครงการเชิงพาณิชย์ได้หรือไม่?  
**ตอบ:** ใช่, Aspose.Page for Java สามารถใช้ในโครงการเชิงพาณิชย์ได้ สำหรับรายละเอียดลิขสิทธิ์ โปรดเยี่ยมชม [Aspose.Purchase](https://purchase.aspose.com/buy)

**ถาม:** มีรุ่นทดลองฟรีหรือไม่?  
**ตอบ:** มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Page for Java [ที่นี่](https://releases.aspose.com/)

**ถาม:** จะหาเอกสารเพิ่มเติมและการสนับสนุนได้จากที่ไหน?  
**ตอบ:** เยี่ยมชม [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) เพื่อรับทรัพยากรครบถ้วน สำหรับการสนับสนุนจากชุมชน ให้ตรวจสอบ [Aspose.Page forum](https://forum.aspose.com/c/page/39)

**ถาม:** จะขอรับลิขสิทธิ์ชั่วคราวได้อย่างไร?  
**ตอบ:** คุณสามารถขอรับลิขสิทธิ์ชั่วคราวจาก [Aspose.Purchase](https://purchase.aspose.com/temporary-license/)

**ถาม:** ความต้องการระบบสำหรับ Aspose.Page for Java มีอะไรบ้าง?  
**ตอบ:** ดูรายละเอียดใน [documentation](https://reference.aspose.com/page/java/) สำหรับความต้องการระบบโดยละเอียด

---

**อัปเดตล่าสุด:** 2026-02-13  
**ทดสอบกับ:** Aspose.Page for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}