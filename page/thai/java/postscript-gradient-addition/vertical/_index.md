---
date: 2026-02-13
description: เรียนรู้วิธีสร้างไล่สี PostScript ใน Java ด้วย Aspose.Page คู่มือแบบขั้นตอนนี้จะแสดงให้คุณเห็นวิธีเพิ่มไล่สีแนวตั้งในเอกสาร
  PostScript ของคุณได้อย่างง่ายดาย
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: สร้างไล่ระดับสี PostScript ใน Java – เพิ่มไล่ระดับสีแนวตั้ง
url: /th/java/postscript-gradient-addition/vertical/
weight: 14
---

"

But keep the English terms like PostScript, Java.

Proceed.

I'll write Thai sentences.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Gradient PostScript ใน Java – เพิ่ม Gradient แนวตั้ง

## Introduction
ในบทแนะนำที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธี **สร้าง Gradient PostScript ใน Java** ด้วย Aspose.Page for Java การเพิ่ม Gradient แนวตั้งสามารถทำให้เอกสารของคุณดูมีชีวิตชีวาและเป็นมืออาชีพมากขึ้น และด้วยเพียงไม่กี่บรรทัดของโค้ด คุณก็สามารถสร้างเอฟเฟกต์ภาพที่น่าตื่นตาตื่นใจ เราจะพาคุณผ่านแต่ละขั้นตอน อธิบายว่าทำไมแต่ละส่วนจึงสำคัญ และให้เคล็ดลับปฏิบัติเพื่อหลีกเลี่ยงข้อผิดพลาดทั่วไป เมื่ออ่านจบคู่มือคุณจะสามารถสร้างไฟล์ PostScript ที่มีการเปลี่ยนสีแนวตั้งที่ราบรื่นและดึงดูดสายตาได้

## Quick Answers
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java  
- **สามารถปรับสีได้หรือไม่?** ได้, สามารถใช้ `java.awt.Color` ใดก็ได้  
- **รองรับการหมุนหรือไม่?** ได้, คุณสามารถหมุน Gradient ด้วย `AffineTransform`  
- **รูปแบบผลลัพธ์ที่สร้างคืออะไร?** ไฟล์ PostScript มาตรฐาน (.ps)  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานจริงหรือไม่?** ต้องมี, จำเป็นต้องใช้ลิขสิทธิ์เชิงพาณิชย์  

## Why add a vertical gradient to a PostScript document?
Gradient แนวตั้งช่วยให้หน้าของคุณมีความลึกโดยไม่เพิ่มขนาดไฟล์ เหมาะสำหรับ:

* ส่วนหัวหรือส่วนท้ายของรายงานที่ต้องการพื้นหลังสีอ่อนเป็นจุดเด่น  
* การเน้นส่วนต่าง ๆ ในคู่มือเทคนิคหรือเอกสารวิชาการ  
* การให้ลุคทันสมัยกับแผนภูมิ, แผนภาพ หรือโบรชัวร์ส่งเสริมการขาย  

เนื่องจาก Gradient ถูกกำหนดในรูปแบบเวกเตอร์ ผลลัพธ์จึงคมชัดที่ความละเอียดใด ๆ ก็ตาม

## Prerequisites
ก่อนเริ่มทำตามบทแนะนำนี้ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งานแล้ว:
- Java Development Kit (JDK) ที่ติดตั้งบนเครื่องของคุณ  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/java/)  

## Import Packages
ในโปรเจกต์ Java ของคุณ ให้ import แพ็กเกจที่จำเป็นเพื่อเริ่มต้น:
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

ตอนนี้เราจะเดินผ่านกระบวนการเพิ่ม Gradient แนวตั้งทีละขั้นตอน

## How to create PostScript gradient in Java
ต่อไปนี้เป็นคู่มือขั้นตอนต่อขั้นตอนที่แสดงอย่างชัดเจนว่า **สร้าง Gradient PostScript ใน Java** อย่างไรโดยใช้ Aspose.Page API

### Step 1: Set up Your Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: Create Save Options with A4 Size
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New PS Document
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create a Rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: Set Up Colors and Fractions for the Gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: Create the Gradient Transform
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: Create Vertical Linear Gradient Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: Set Paint and Fill the Rectangle
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: Close Current Page and Save the Document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

ยินดีด้วย! คุณได้เพิ่ม Gradient แนวตั้งลงในเอกสาร PostScript ของ Java สำเร็จโดยใช้ Aspose.Page for Java

## Common Issues and Solutions
- **Gradient ปรากฏเป็นสีเดียว:** ตรวจสอบให้แน่ใจว่าการสเกลของ `AffineTransform` ตรงกับขนาดของสี่เหลี่ยม  
- **สีดูจาง:** ยืนยันว่าคุณใช้ `ColorSpaceType` ที่ถูกต้อง (SRGB) และอาเรย์ fractions เรียงจาก 0.0 ถึง 1.0  
- **ไฟล์ไม่ถูกสร้าง:** ตรวจสอบว่าไดเรกทอรีผลลัพธ์ (`dataDir`) มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน  

## Frequently Asked Questions
### สามารถใช้ Aspose.Page for Java ร่วมกับไลบรารี Java อื่นได้หรือไม่?
ได้, Aspose.Page for Java ถูกออกแบบให้ทำงานร่วมกับไลบรารี Java อื่นได้อย่างราบรื่น

### มีรุ่นทดลองใช้งานฟรีสำหรับ Aspose.Page for Java หรือไม่?
มี, คุณสามารถรับรุ่นทดลองฟรีได้จาก [ที่นี่](https://releases.aspose.com/)

### จะหาเอกสารเพิ่มเติมได้จากที่ไหน?
เอกสารโดยละเอียดพร้อมให้ดาวน์โหลดได้ที่ [นี่](https://reference.aspose.com/page/java/)

### จะซื้อ Aspose.Page for Java ได้อย่างไร?
คุณสามารถสั่งซื้อ Aspose.Page for Java ได้จาก [ที่นี่](https://purchase.aspose.com/buy)

### มีฟอรั่มสำหรับการสนทนาเกี่ยวกับ Aspose.Page หรือไม่?
มี, คุณสามารถเข้าร่วมฟอรั่มชุมชนได้ที่ [นี่](https://forum.aspose.com/c/page/39)

## Additional Frequently Asked Questions

**Q: สามารถสร้าง Gradient ทิศทางอื่น (แนวนอน, แนวทแยง) ได้หรือไม่?**  
A: แน่นอน. ปรับจุดเริ่มต้นและจุดสิ้นสุดใน `LinearGradientPaint` และแก้ไขมุมการหมุนใน `AffineTransform`

**Q: สามารถใช้กับการส่งออกเป็น PDF ได้หรือไม่?**  
A: โลจิก Gradient เดียวกันสามารถนำไปใช้เมื่อบันทึกเป็น PDF โดยใช้ `PdfSaveOptions` แทน `PsSaveOptions`

**Q: จะเปลี่ยนขนาด Gradient อย่างไดนามิกได้อย่างไร?**  
A: คำนวณขนาดของสี่เหลี่ยมในขณะรันไทม์และส่งค่าที่ได้ไปยังคอนสตรัคเตอร์ของ `Rectangle2D` และ `AffineTransform`

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}