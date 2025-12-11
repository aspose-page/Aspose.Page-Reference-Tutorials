---
date: 2025-12-09
description: เรียนรู้วิธีสร้างไล่สี PostScript ใน Java ด้วย Aspose.Page คู่มือแบบทีละขั้นตอนนี้จะแสดงวิธีเพิ่มไล่สีแนวตั้งในเอกสาร
  PostScript ของคุณได้อย่างง่ายดาย
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: สร้างไล่ระดับสี PostScript ใน Java – เพิ่มไล่ระดับสีแนวตั้ง
url: /th/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง PostScript Gradient ใน Java – เพิ่ม Gradient แนวตั้ง

## บทนำ
ในบทแนะนำที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธี **สร้าง PostScript gradient ใน Java** ด้วย Aspose.Page for Java การเพิ่ม gradient แนวตั้งสามารถทำให้เอกสารของคุณดูมีชีวิตชีวาและเป็นมืออาชีพมากขึ้น และด้วยเพียงไม่กี่บรรทัดของโค้ดคุณก็สามารถสร้างเอฟเฟกต์ภาพที่น่าทึ่งได้ เราจะพาคุณผ่านแต่ละขั้นตอน อธิบายว่าทำไมแต่ละส่วนจึงสำคัญ และให้เคล็ดลับปฏิบัติเพื่อหลีกเลี่ยงข้อผิดพลาดทั่วไป  
ในคู่มือนี้เราจะ **สร้าง postscript gradient java** ทีละขั้นตอน

## คำตอบอย่างรวดเร็ว
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java  
- **สามารถปรับสีได้หรือไม่?** ได้, สามารถใช้ `java.awt.Color` ใดก็ได้  
- **รองรับการหมุนหรือไม่?** ได้, คุณสามารถหมุน gradient ด้วย `AffineTransform`  
- **รูปแบบผลลัพธ์ที่สร้างคืออะไร?** ไฟล์ PostScript มาตรฐาน (.ps)  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานจริงหรือไม่?** ต้อง, จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์  

## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มทำตามบทแนะนำ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/java/)

## การนำเข้าแพ็กเกจ
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

ตอนนี้เราจะทำการแยกกระบวนการเพิ่ม gradient แนวตั้งใน PostScript ของ Java ออกเป็นหลายขั้นตอน

## วิธีสร้าง PostScript gradient Java
ด้านล่างเป็นคู่มือขั้นตอน‑โดย‑ขั้นตอนที่แสดงอย่างชัดเจนว่า **สร้าง PostScript gradient ใน Java** อย่างไรโดยใช้ Aspose.Page API

### ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสารของคุณ
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้าง Output Stream สำหรับเอกสาร PostScript
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### ขั้นตอนที่ 3: สร้าง Save Options ด้วยขนาด A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### ขั้นตอนที่ 4: สร้างเอกสาร PS ใหม่
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### ขั้นตอนที่ 5: สร้างสี่เหลี่ยม
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### ขั้นตอนที่ 6: ตั้งค่าสีและอัตราส่วนสำหรับ Gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### ขั้นตอนที่ 7: สร้าง Gradient Transform
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### ขั้นตอนที่ 8: สร้าง Vertical Linear Gradient Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### ขั้นตอนที่ 9: ตั้งค่า Paint และเติมสี่เหลี่ยม
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### ขั้นตอนที่ 10: ปิดหน้าเดิมและบันทึกเอกสาร
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

ขอแสดงความยินดี! คุณได้เพิ่ม gradient แนวตั้งให้กับเอกสาร PostScript ของ Java สำเร็จโดยใช้ Aspose.Page for Java

## ทำไมต้องใช้ gradient แนวตั้งใน PostScript?
Gradient แนวตั้งช่วยให้หน้าของคุณมีความลึกและความน่าสนใจโดยไม่เพิ่มขนาดไฟล์อย่างมีนัยสำคัญ มันมีประโยชน์เป็นพิเศษสำหรับ:
- ส่วนหัวและส่วนท้ายของรายงาน  
- พื้นหลังของแผนภูมิหรือไดอะแกรม  
- การเน้นส่วนต่าง ๆ ในเอกสารเทคนิค  

## ปัญหาที่พบบ่อยและวิธีแก้
- **Gradient ดูแบน:** ตรวจสอบให้แน่ใจว่าการสเกลของ `AffineTransform` ตรงกับขนาดสี่เหลี่ยม  
- **สีดูซีด:** ยืนยันว่าคุณใช้ `ColorSpaceType` ที่ถูกต้อง (SRGB) และอาร์เรย์ fractions เรียงจาก 0.0 ถึง 1.0  
- **ไฟล์ไม่ถูกสร้าง:** ตรวจสอบว่าโฟลเดอร์ output (`dataDir`) มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน  

## คำถามที่พบบ่อย
### สามารถใช้ Aspose.Page for Java ร่วมกับไลบรารี Java อื่นได้หรือไม่?
ได้, Aspose.Page for Java ถูกออกแบบให้ทำงานร่วมกับไลบรารี Java อื่นอย่างราบรื่น

### มีรุ่นทดลองฟรีสำหรับ Aspose.Page for Java หรือไม่?
ได้, คุณสามารถรับรุ่นทดลองฟรีได้จาก [ที่นี่](https://releases.aspose.com/)

### จะหาเอกสารเพิ่มเติมได้จากที่ไหน?
เอกสารโดยละเอียดพร้อมให้บริการที่ [นี่](https://reference.aspose.com/page/java/)

### จะซื้อ Aspose.Page for Java ได้อย่างไร?
คุณสามารถซื้อ Aspose.Page for Java ได้จาก [ที่นี่](https://purchase.aspose.com/buy)

### มีฟอรั่มสำหรับการสนทนาเกี่ยวกับ Aspose.Page หรือไม่?
ได้, คุณสามารถเข้าร่วมฟอรั่มชุมชนได้ที่ [นี่](https://forum.aspose.com/c/page/39)

## คำถามที่พบบ่อยเพิ่มเติม

**ถาม: ฉันสามารถสร้าง gradient ในทิศทางอื่น (แนวนอน, แนวทแยง) ได้หรือไม่?**  
ตอบ: แน่นอน. ปรับจุดเริ่มต้นและจุดสิ้นสุดใน `LinearGradientPaint` และแก้ไขมุมการหมุนใน `AffineTransform`

**ถาม: โค้ดนี้ทำงานกับการส่งออกเป็น PDF ได้หรือไม่?**  
ตอบ: ตรรกะ gradient เดียวกันสามารถนำไปใช้เมื่อบันทึกเป็น PDF โดยใช้ `PdfSaveOptions` แทน `PsSaveOptions`

**ถาม: จะเปลี่ยนขนาด gradient อย่างไดนามิกได้อย่างไร?**  
ตอบ: คำนวณขนาดสี่เหลี่ยมในเวลารันและส่งค่าที่ได้ไปยังคอนสตรัคเตอร์ของ `Rectangle2D` และ `AffineTransform`

---

**อัปเดตล่าสุด:** 2025-12-09  
**ทดสอบด้วย:** Aspose.Page for Java 24.11 (ล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}