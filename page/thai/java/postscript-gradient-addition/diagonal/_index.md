---
date: 2026-02-13
description: เพิ่มประสิทธิภาพเอกสาร Java PostScript ของคุณด้วยการไล่สีแนวทแยงโดยใช้
  Aspose.Page Java. เรียนรู้วิธีเพิ่มเอฟเฟกต์ไล่สีด้วย LinearGradientPaint ใน Java
  และสร้างการเปลี่ยนสีที่สดใสได้อย่างง่ายดาย.
linktitle: 'How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page
  Java'
second_title: Aspose.Page Java API
title: 'วิธีเพิ่มไล่ระดับสี: ไล่ระดับสีแนวทแยงใน Java PostScript ด้วย Aspose.Page
  Java'
url: /th/java/postscript-gradient-addition/diagonal/
weight: 10
---

 markdown formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไดอะแกรมไล่ระดับสีแนวทแยงใน Java PostScript ด้วย Aspose.Page Java

## บทนำ
หากคุณต้องการเพิ่มความสวยงามให้กับไฟล์ PostScript ด้วยการไล่สีแนวทแยงที่ราบรื่น, **Aspose.Page Java** ทำให้ทำได้อย่างง่ายดายอย่างน่าแปลกใจ ในบทแนะนำนี้เราจะอธิบาย **วิธีเพิ่มไล่ระดับสี** อย่างเป็นขั้นตอนโดยใช้คลาส `LinearGradientPaint` จาก Java 2D เมื่อเสร็จคุณจะได้โค้ดสั้นที่พร้อมรันซึ่งสร้างเอกสาร PostScript พร้อมไล่สีแนวทแยงที่สดใส.

## วิธีเพิ่มไล่ระดับสีใน Java PostScript
การเพิ่มไล่ระดับสีอาจฟังดูเหมือนเป็นงานด้านกราฟิกเท่านั้น, แต่ด้วย Aspose.Page คุณจะได้การควบคุมเต็มรูปแบบต่อคำสั่ง PostScript ภายในขณะใช้ Java อย่างเดียว ส่วนนี้จะอธิบายว่าทำไมวิธีนี้ถึงได้ผลและคุณจะได้อะไรบ้างเมื่อเทียบกับการเขียน PostScript ด้วยตนเอง.

## คำตอบด่วน
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java.  
- **คลาสใดสร้างไล่ระดับสี?** `LinearGradientPaint`.  
- **สามารถเปลี่ยนสีได้หรือไม่?** ได้ – แก้ไขอาร์เรย์ `Color[]`.  
- **ต้องใช้ลิขสิทธิ์สำหรับการผลิตหรือไม่?** ต้องมีลิขสิทธิ์เชิงพาณิชย์; มีรุ่นทดลองฟรี.  
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** ประมาณ 10 นาทีสำหรับไล่ระดับสีพื้นฐาน.

## Aspose.Page Java คืออะไร?
Aspose.Page Java เป็น API ที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถสร้าง, แก้ไข, และแปลงไฟล์ PostScript และ PDF ได้โดยไม่ต้องใช้ซอฟต์แวร์ภายนอก มันเปิดเผยความสามารถกราฟิกทั้งหมดของภาษา PostScript ผ่านอินเทอร์เฟซ Java แบบวัตถุ‑เชิงวัตถุที่เรียบง่าย.

## ทำไมต้องใช้ไล่ระดับสีแนวทแยง?
ไล่ระดับสีแนวทแยงช่วยเพิ่มความลึกและความน่าสนใจให้กับแผนภูมิ, แบนเนอร์, หรือองค์ประกอบกราฟิกใด ๆ ที่ต้องการลุคทันสมัย เนื่องจากไล่ระดับสีวิ่งจากมุมหนึ่งไปยังอีกมุมหนึ่ง ทำให้เหมาะสำหรับพื้นหลัง, สกินปุ่ม, และรูปทรงตกแต่ง.

## ข้อกำหนดเบื้องต้น
- Java Development Kit (JDK) 8 หรือสูงกว่า.  
- IDE เช่น Eclipse, IntelliJ IDEA หรือ VS Code.  
- **Aspose.Page for Java** library – ดาวน์โหลดเวอร์ชันล่าสุดจาก [official download page](https://releases.aspose.com/page/java/).

## นำเข้าแพ็กเกจ
ก่อนอื่นให้ทำการนำเข้าแพ็กเกจ Java 2D และคลาสของ Aspose ที่จำเป็น การนำเข้าดังกล่าวจะให้คุณเข้าถึงการกำหนดสี, รูปร่างเรขาคณิต, การทาสีไล่ระดับ, และ API ของเอกสาร PostScript.

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

## ขั้นตอนที่ 1: สร้าง Output Stream สำหรับเอกสาร PostScript
เราจะเริ่มโดยกำหนดโฟลเดอร์ที่ไฟล์จะถูกบันทึกและเปิด `FileOutputStream` สตรีมนี้จะรับข้อมูล PostScript ที่สร้างขึ้น.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## ขั้นตอนที่ 2: สร้าง Save Options ขนาด A4
`PsSaveOptions` ให้คุณระบุขนาดหน้า, ความละเอียด, และการตั้งค่าอื่น ๆ ของผลลัพธ์ ที่นี่เราใช้ขนาด A4 เริ่มต้น.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## ขั้นตอนที่ 3: สร้าง PS Document ใหม่
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

## ขั้นตอนที่ 5: สร้าง Gradient Transform
`AffineTransform` ช่วยให้เราหมุน, ขยาย, และแปลไล่ระดับสีเพื่อให้วิ่งแนวทแยงผ่านสี่เหลี่ยม คณิตศาสตร์ด้านล่างคำนวณความยาวด้านตรงข้ามของสามเหลี่ยมมุมฉากและปรับอัตราส่วนการขยายตามนั้น.

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

## ขั้นตอนที่ 6: สร้าง Diagonal Linear Gradient Paint
นี่คือหัวใจของ **วิธีเพิ่มไล่ระดับสี** – เราสร้าง `LinearGradientPaint` ที่ครอบคลุมจากมุมบน‑ซ้ายของสี่เหลี่ยมไปยังมุมล่าง‑ขวา โดยใช้การแปลงที่กำหนดไว้ก่อนหน้า `MultipleGradientPaint.CycleMethod.NO_CYCLE` ทำให้ไล่ระดับสีไม่ทำซ้ำ.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## ขั้นตอนที่ 7: ตั้งค่า Paint และเติมสี่เหลี่ยม
ใช้ gradient paint กับเอกสารและเติมรูปสี่เหลี่ยม ขั้นตอนนี้จะเรนเดอร์การเปลี่ยนสีแนวทแยงบนหน้า PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## ขั้นตอนที่ 8: ปิดหน้าปัจจุบันและบันทึกเอกสาร
สุดท้าย ปิดหน้า, ทำการ flush สตรีม, และบันทึกไฟล์ ไฟล์ `DiagonalGradient_outPS.ps` ที่ได้สามารถเปิดด้วยโปรแกรมดู PostScript ใดก็ได้.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## ปัญหาทั่วไป & เคล็ดลับ
- **ไล่ระดับสีดูแบน** – ตรวจสอบมุมการหมุนอีกครั้ง; การหมุน 45° จะสร้างแนวทแยงที่แท้จริง.  
- **สีดูซีด** – ตรวจสอบว่าคุณใช้ `MultipleGradientPaint.ColorSpaceType.SRGB` เพื่อการเรนเดอร์สีที่แม่นยำ.  
- **เกิดข้อผิดพลาดไฟล์ไม่พบ** – ยืนยันว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ไลบรารีนี้สำหรับการดำเนินการกราฟิกอื่น ๆ ใน Java ได้หรือไม่?**  
A: ใช่, Aspose.Page for Java มีชุดเต็มของ primitive การวาด, การเรนเดอร์ข้อความ, และความสามารถในการจัดการภาพ.

**Q: มีรุ่นทดลองฟรีสำหรับ Aspose.Page Java หรือไม่?**  
A: แน่นอน คุณสามารถดาวน์โหลดรุ่นทดลองเต็มรูปแบบได้จาก [Aspose free trial page](https://releases.aspose.com/).

**Q: ฉันจะหาเอกสารสำหรับ Aspose.Page Java ได้จากที่ไหน?**  
A: เอกสารอ้างอิง API อย่างเป็นทางการมีให้ที่ [here](https://reference.aspose.com/page/java/).

**Q: ฉันจะซื้อไลเซนส์สำหรับ Aspose.Page Java ได้อย่างไร?**  
A: สามารถซื้อไลเซนส์ได้โดยตรงจาก [Aspose purchase portal](https://purchase.aspose.com/buy).

**Q: ต้องการความช่วยเหลือหรือมีคำถาม?**  
A: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) ที่ดำเนินการโดยชุมชนเพื่อรับความช่วยเหลือจากวิศวกรของ Aspose และนักพัฒนาคนอื่น ๆ.

---

**อัปเดตล่าสุด:** 2026-02-13  
**ทดสอบกับ:** Aspose.Page for Java 24.12 (ล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}