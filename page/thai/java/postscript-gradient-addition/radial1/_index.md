---
date: 2026-09-09
description: เรียนรู้วิธีสร้าง radial gradient ใน Java PostScript ด้วย Aspose.Page.
  คู่มือ step‑by‑step นี้จะแสดงวิธีเพิ่ม color stops gradient, ตั้ง radii, และสร้างไฟล์
  PS อย่างรวดเร็ว.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: เชี่ยวชาญ radial gradients ใน Java
og_description: เรียนรู้วิธีสร้าง radial gradient ใน Java PostScript ด้วย Aspose.Page.
  คู่มือนี้อธิบายวิธีเพิ่ม color stops gradient, ตั้ง radii, และสร้างไฟล์ PS ในไม่กี่นาที.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: วิธีสร้าง radial gradient ใน Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: วิธีสร้าง radial gradient ใน Java PostScript
url: /th/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างการไล่สีแบบรัศมีใน Java PostScript ด้วย Aspose.Page

## บทนำ
หากคุณต้องการ **สร้างการไล่สีแบบรัศมี** ภายในไฟล์ PostScript, คุณมาถูกที่แล้ว. ในบทแนะนำนี้เราจะพาคุณผ่านทุกขั้นตอนที่จำเป็นเพื่อสร้างเอกสาร PostScript ที่มีการไล่สีแบบรัศมีที่ราบรื่น, โดยใช้ **Aspose.Page for Java**. เมื่อเสร็จคุณจะเข้าใจ API, ดูตัวอย่างที่สามารถรันได้เต็มรูปแบบ, และรู้วิธีปรับสี, ตำแหน่ง, และรัศมีสำหรับสถานการณ์การออกแบบใด ๆ

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดสร้างการไล่สีแบบรัศมีใน PostScript?** Aspose.Page for Java.  
- **การทำงานใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน.  
- **ฉันต้องการไลเซนส์เพื่อรันโค้ดหรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **รองรับเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า.  
- **ฉันสามารถเปลี่ยนรูปแบบของการไล่สีได้หรือไม่?** ได้ – ปรับรัศมีและจุดศูนย์กลางในคอนสตรัคเตอร์ของ `RadialGradientPaint`.

## วิธีสร้างการไล่สีแบบรัศมีใน Java

โหลดโปรเจกต์ Java ของคุณ, นำเข้าคลาสที่จำเป็น, และทำตามคำแนะนำขั้นตอนต่อไปนี้. คำตอบหลักคือคุณสร้างอินสแตนซ์ของ `RadialGradientPaint` ด้วยสีหยุดของคุณแล้วนำไปใช้กับสี่เหลี่ยมที่วาดบน `PsDocument`. วิธีการสองอ็อบเจ็กต์นี้จัดการคำสั่ง PostScript ระดับล่างทั้งหมดให้คุณ.

## การไล่สีแบบรัศมีคืออะไร?
`RadialGradientPaint` เป็นคลาสของ Java AWT ที่กำหนดการเปลี่ยนสีแบบวงกลมจากจุดศูนย์กลางออกไปด้านนอก. มันสร้างการผสมสีที่ราบรื่นจากหลายสีหยุด, ทำให้เหมาะสำหรับสปอตไลท์, พื้นหลังอ่อนโยน, หรือเอฟเฟกต์ใด ๆ ที่สีกระจายจากจุดโฟกัส.

## ทำไมต้องใช้ Aspose.Page สำหรับการไล่สีแบบรัศมี?
Aspose.Page ให้การควบคุมโปรแกรมเต็มรูปแบบต่อผลลัพธ์ PostScript พร้อมจัดการงานหนักของไวยากรณ์ PS ระดับล่าง. มันรองรับ **รูปแบบเข้าและออกกว่า 50+**, สามารถเรนเดอร์เอกสารหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, และทำงานบนระบบปฏิบัติการใด ๆ ที่รองรับ Java 8+. ความสามารถที่วัดได้นี้ทำให้เป็นตัวเลือกที่เชื่อถือได้สำหรับการสร้างกราฟิกระดับองค์กร.

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK) 8+** – ตรวจสอบด้วยคำสั่ง `java -version`.  
- **Aspose.Page for Java** – ดาวน์โหลด JAR ล่าสุดจาก [หน้าดาวน์โหลด Aspose.Page อย่างเป็นทางการ](https://releases.aspose.com/page/java/).  
- **IDE ที่คุณเลือก** – Eclipse, IntelliJ IDEA, หรือ VS Code พร้อมส่วนขยาย Java.  
- **โฟลเดอร์ที่สามารถเขียนได้** – ที่ไฟล์ `.ps` ที่สร้างจะถูกบันทึก.

## นำเข้าชุดแพ็กเกจ
แรก, นำเข้าคลาสที่เราต้องการ. แพ็กเกจ `java.awt` ให้วัตถุการวาดสีไล่, ส่วน `com.aspose.eps` มีคลาสจัดการเอกสาร PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: สร้างสี่เหลี่ยมและเปิดเอกสาร PS
`PsDocument` เป็นคลาสของ Aspose.Page ที่แทนเอกสาร PostScript และให้เมธอดสำหรับวาดรูปทรง, ข้อความ, และภาพ. เราเริ่มด้วยการสร้าง output stream, กำหนดขนาดหน้า (A4 เป็นค่าเริ่มต้น), และกำหนดสี่เหลี่ยมที่จะเป็นที่วางการไล่สี.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **เคล็ดลับ:** ปรับพิกัดของสี่เหลี่ยม (`200, 100, 200, 200`) เพื่อวางการไล่สีที่ตำแหน่งใดก็ได้บนหน้า.

### ขั้นตอนที่ 2: กำหนดสีและส่วนแบ่ง
การไล่สีแบบรัศมีสร้างจาก *สีหยุด* (สี) และ *ส่วนแบ่ง* (ตำแหน่งสัมพัทธ์ของสีหยุด). ที่นี่เราสร้างอาเรย์ของสีหกสีและส่วนแบ่งที่สอดคล้องกัน.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **ทำไมเรื่องนี้สำคัญ:** โดยการปรับ `fractions` คุณควบคุมความเร็วของการเปลี่ยนสี, ทำให้ได้เอฟเฟกต์ที่ละเอียดอ่อนหรือโดดเด่น.

### ขั้นตอนที่ 3: สร้าง radial gradient paint
`RadialGradientPaint` เป็นคลาสหลักที่อธิบายการไล่สีแบบรัศมี, รวมถึงจุดศูนย์กลาง, รัศมี, จุดโฟกัส, ส่วนแบ่ง, สี, วิธีการวนซ้ำ, และสีสเปซ. ตอนนี้เราจะสร้างอ็อบเจ็กต์ `RadialGradientPaint` โดยใช้อาเรย์ที่กำหนดข้างต้น.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **หมายเหตุ:** `transform` สามารถเป็น `null` หากคุณไม่ต้องการการสเกลหรือการหมุนเพิ่มเติม. อย่าลังเลที่จะทดลองกับ `AffineTransform` สำหรับการไล่สีที่เอียง.

### ขั้นตอนที่ 4: ตั้งค่า paint และเติมสี่เหลี่ยม
เมื่อ paint พร้อม, เราบอก `PsDocument` ให้ใช้มันและจากนั้นเติมสี่เหลี่ยมที่เรากำหนดไว้ก่อนหน้า.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

ในขั้นตอนนี้หน้า PostScript มีสี่เหลี่ยมที่ถูกเติมด้วยการไล่สีแบบรัศมีอย่างราบรื่นตามที่เราตั้งค่า.

### ขั้นตอนที่ 5: ปิดและบันทึกเอกสาร
สุดท้าย, ปิดหน้าปัจจุบันและเขียนไฟล์ลงดิสก์.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

เปิด `RadialGradient1_outPS.ps` ในโปรแกรมดู PostScript ใดก็ได้ (เช่น Ghostscript) แล้วคุณจะเห็นการไล่สีที่แสดงผลตามที่กำหนด.

## ปัญหาที่พบบ่อยและวิธีแก้

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| การไล่สีปรากฏเป็นสีเดียว | อาเรย์ `fractions` ไม่เริ่มที่ `0.0f` หรือจบที่ `1.0f` | ตรวจสอบให้แน่ใจว่าส่วนแบ่งแรกเป็น `0.0f` และส่วนแบ่งสุดท้ายเป็น `1.0f`. |
| สีดูจางหรือซีด | ใช้ `ColorSpaceType` ผิด | เปลี่ยนเป็น `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` เพื่อให้ผลลัพธ์สีสดใสขึ้น. |
| ไม่มีไฟล์ผลลัพธ์ถูกสร้าง | พาธของ `FileOutputStream` ไม่ถูกต้องหรือไม่สามารถเขียนได้ | ตรวจสอบว่า `dataDir` มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Page for Java ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ใช่. จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง. คุณสามารถซื้อได้จาก [หน้าไลเซนส์ของ Aspose](https://purchase.aspose.com/buy).

**Q: ฉันสามารถหาเอกสารอ้างอิง API อย่างเป็นทางการได้ที่ไหน?**  
A: เอกสารเต็มรูปแบบสามารถดูได้ที่ [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: มีรุ่นทดลองฟรีสำหรับการทดสอบหรือไม่?**  
A: มีแน่นอน. ดาวน์โหลดรุ่นทดลองจาก [หน้ารีลีสของ Aspose.Page](https://releases.aspose.com/).

**Q: ฉันจะขอไลเซนส์ชั่วคราวสำหรับการประเมินได้อย่างไร?**  
A: สามารถขอไลเซนส์ชั่วคราวได้จาก [หน้าเรียกขอไลเซนส์ชั่วคราว](https://purchase.aspose.com/temporary-license/).

**Q: ฉันสามารถรับการสนับสนุนจากชุมชนได้ที่ไหน?**  
A: เข้าร่วมฟอรั่มชุมชน Aspose.Page ที่ [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## สรุป
ตอนนี้คุณรู้แล้วว่า **วิธีสร้างการไล่สีแบบรัศมี** ในเอกสาร Java PostScript ด้วย Aspose.Page. โดยการปรับขนาดสี่เหลี่ยม, สีหยุด, และรัศมีของการไล่สี คุณสามารถสร้างเอฟเฟกต์ภาพได้ไม่จำกัด – ตั้งแต่การเติมพื้นหลังอ่อนโยนจนถึงกราฟิกสปอตไลท์ที่โดดเด่น. อย่าลังเลที่จะทดลองค่าต่าง ๆ ของ `AffineTransform` เพื่อหมุนหรือเอียงการไล่สี, และผสานเทคนิคนี้กับข้อความและภาพเพื่อผลลัพธ์ PDF หรือ EPS ที่สมบูรณ์ยิ่งขึ้น.

---

**อัปเดตล่าสุด:** 2026-09-09  
**ทดสอบด้วย:** Aspose.Page for Java รุ่นล่าสุด (ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [เติมรูปทรงด้วยการไล่สี: ตัวอย่าง Java PostScript Radial](/page/java/postscript-gradient-addition/radial2/)
- [สร้างการไล่สี PostScript ใน Java – เพิ่มการไล่สีแนวตั้ง](/page/java/postscript-gradient-addition/vertical/)
- [บทแนะนำการทำให้โปร่งใสใน Aspose.Page – เพิ่มความโปร่งใสใน Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}