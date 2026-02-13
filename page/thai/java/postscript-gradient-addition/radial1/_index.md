---
date: 2026-02-13
description: เรียนรู้วิธีสร้างไล่ระดับสี PostScript ด้วยไล่ระดับสีแบบรัศมีและจุดสีโดยใช้
  Aspose.Page สำหรับ Java คู่มือขั้นตอนต่อขั้นตอนนี้จะแสดงวิธีเพิ่มไล่ระดับสีจุดสีในเอกสารของคุณ.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: สร้างไล่ระดับสี PostScript – ไล่ระดับสีแบบรัศมีใน Java
url: /th/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม Gradient แบบรัศมีใน Java PostScript ด้วย Aspose.Page

## บทนำ
หากคุณเคยต้อง **สร้าง PostScript gradient** ที่มีการเปลี่ยนสีเรียบและดึงดูดสายตา การเรียนรู้วิธีเพิ่ม radial gradient คือจุดเริ่มต้นที่สมบูรณ์แบบ ในบทแนะนำนี้เราจะพาคุณผ่านทุกขั้นตอนที่จำเป็นเพื่อสร้างไฟล์ PostScript ที่มี radial gradient สวยงามโดยใช้ไลบรารี **Aspose.Page for Java** เมื่อเสร็จสิ้นคุณจะเข้าใจ API, เห็นตัวอย่างที่สามารถรันได้เต็มรูปแบบ, และรู้วิธีปรับสี, ตำแหน่ง, และรัศมีให้เหมาะกับการออกแบบใด ๆ

## คำตอบด่วน
- **ไลบรารีที่สร้าง radial gradient ใน PostScript คืออะไร?** Aspose.Page for Java.  
- **การทำงานใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน.  
- **ต้องมีลิขสิทธิ์เพื่อรันโค้ดหรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **รองรับเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า.  
- **ฉันสามารถเปลี่ยนรูปแบบของ gradient ได้หรือไม่?** ได้ – ปรับรัศมีและจุดศูนย์กลางในคอนสตรัคเตอร์ `RadialGradientPaint`.

## วิธีสร้าง PostScript Gradient ด้วยการเติมแบบรัศมี
ด้านล่างนี้คุณจะพบขั้นตอนสั้น ๆ ที่แสดงอย่างชัดเจนว่า **สร้างเนื้อหา PostScript gradient** อย่างไรโดยใช้การเติมแบบรัศมี แต่ละขั้นตอนมีคำอธิบายสั้น ๆ ตามด้วยบล็อกโค้ดต้นฉบับ (ไม่เปลี่ยนแปลง)

## Radial Gradient คืออะไร?
Radial gradient จะทาสีที่กระจายออกจากจุดศูนย์กลางอย่างค่อยเป็นค่อยไปจนถึงขอบ สีจะผสมกันอย่างนุ่มนวลตามรูปวงกลมหรือรูปรี ซึ่งเหมาะสำหรับไฮไลท์, สปอตไลท์, หรือการเติมพื้นหลังที่นุ่มนวล

## ทำไมต้องใช้ Aspose.Page สำหรับ Radial Gradient?
- **ควบคุมผลลัพธ์ PostScript อย่างเต็มที่** – ไม่ต้องเขียนคำสั่ง PS ระดับต่ำด้วยตนเอง.  
- **ข้ามแพลตฟอร์ม** – ทำงานบน OS ใดก็ได้ที่รัน Java.  
- **การจัดการสีที่หลากหลาย** – รองรับหลาย color stop, color space ที่ต่างกัน, และวิธีการวนรอบ.  
- **พร้อมสำหรับการบูรณาการ** – สามารถรวมกับฟีเจอร์อื่นของ Aspose.Page เช่น ข้อความ, รูปภาพ, และรูปทรงเวกเตอร์.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

- **Java Development Kit (JDK) 8+** – ตรวจสอบด้วย `java -version`.  
- **Aspose.Page for Java** – ดาวน์โหลด JAR ล่าสุดจาก [หน้าดาวน์โหลด Aspose.Page อย่างเป็นทางการ](https://releases.aspose.com/page/java/).  
- **IDE ที่คุณเลือก** – Eclipse, IntelliJ IDEA หรือ VS Code พร้อมส่วนขยาย Java.  
- **โฟลเดอร์ที่สามารถเขียนได้** – ที่จะบันทึกไฟล์ `.ps` ที่สร้างขึ้น.

## การนำเข้าแพ็กเกจ
ก่อนอื่นให้ทำการนำเข้าคลาสที่จำเป็น `java.awt` จะให้วัตถุ gradient paint, ส่วน `com.aspose.eps` มีคลาสจัดการเอกสาร PostScript.

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

## คู่มือขั้นตอน

### ขั้นตอนที่ 1: สร้างสี่เหลี่ยมและเปิดเอกสาร PS
เราจะเริ่มด้วยการสร้าง output stream, ตั้งค่าขนาดหน้า (ค่าเริ่มต้น A4) และกำหนดสี่เหลี่ยมที่จะเป็นพื้นที่ของ gradient.

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

> **เคล็ดลับ:** ปรับพิกัดของสี่เหลี่ยม (`200, 100, 200, 200`) เพื่อวาง gradient ที่ตำแหน่งใดก็ได้บนหน้า.

### ขั้นตอนที่ 2: กำหนดสีและอัตราส่วน
Radial gradient ถูกสร้างจาก *color stops* (สี) และ *fractions* (ตำแหน่งสัมพัทธ์ของ stop เหล่านั้น) ที่นี่เราจะสร้างอาเรย์ของหกสีและอัตราส่วนที่สอดคล้องกัน.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **ทำไมเรื่องนี้สำคัญ:** การปรับ `fractions` จะควบคุมความเร็วของการเปลี่ยนสี ทำให้ได้เอฟเฟกต์ที่ละเอียดอ่อนหรือดรามาติก.

### การเพิ่ม Color Stops Gradient ให้กับการเติมแบบรัศมีของคุณ
เมื่อคุณต้องการ **add color stops gradient**, อาเรย์ `colors` และ `fractions` คือกุญแจสำคัญ คุณสามารถจัดลำดับใหม่, เพิ่ม, หรือเอาออกตามที่การออกแบบของคุณต้องการ.

### ขั้นตอนที่ 3: สร้าง Radial Gradient Paint
ตอนนี้เราจะสร้างอ็อบเจ็กต์ `RadialGradientPaint` คอนสตรัคเตอร์รับจุดศูนย์กลางของ gradient, รัศมี, จุดโฟกัส, fractions, colors, วิธีวนรอบ, color space, และการแปลงเพิ่มเติม (optional).

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

> **หมายเหตุ:** `transform` สามารถเป็น `null` หากไม่ต้องการการสเกลหรือการหมุนเพิ่มเติม คุณสามารถทดลองใช้ `AffineTransform` เพื่อสร้าง gradient ที่เอียงได้.

### ขั้นตอนที่ 4: ตั้งค่า Paint และเติมสี่เหลี่ยม
เมื่อ paint พร้อมแล้ว เราบอก `PsDocument` ให้ใช้มันและเติมสี่เหลี่ยมที่กำหนดไว้ก่อนหน้านี้.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

ในขั้นตอนนี้หน้า PostScript จะมีสี่เหลี่ยมที่เติมด้วย radial gradient อย่างราบรื่นตามที่เราตั้งค่าไว้.

### ขั้นตอนที่ 5: ปิดและบันทึกเอกสาร
สุดท้าย ปิดหน้าและเขียนไฟล์ลงดิสก์.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

เปิด `RadialGradient1_outPS.ps` ด้วยโปรแกรมดู PostScript ใดก็ได้ (เช่น Ghostscript) คุณจะเห็น gradient แสดงผลตามที่กำหนดอย่างแม่นยำ.

## ปัญหาทั่วไปและวิธีแก้
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| Gradient ปรากฏเป็นสีเดียว | อาร์เรย์ `fractions` ไม่เริ่มที่ `0.0f` หรือสิ้นสุดที่ `1.0f` | ตรวจสอบให้แน่ใจว่า fraction แรกเป็น `0.0f` และตัวสุดท้ายเป็น `1.0f`. |
| สีดูซีด | ใช้ `ColorSpaceType` ผิด | เปลี่ยนเป็น `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` เพื่อให้ผลลัพธ์สีสดใสขึ้น. |
| ไม่มีไฟล์ผลลัพธ์สร้างขึ้น | เส้นทาง `FileOutputStream` ไม่ถูกต้องหรือไม่สามารถเขียนได้ | ตรวจสอบว่า `dataDir` มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน. |

## คำถามที่พบบ่อย

**ถาม:** ฉันสามารถใช้ Aspose.Page for Java ในโครงการเชิงพาณิชย์ได้หรือไม่?  
**ตอบ:** ใช่. ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง. คุณสามารถซื้อได้จาก [หน้าใบอนุญาต Aspose](https://purchase.aspose.com/buy).

**ถาม:** ฉันสามารถหาเอกสารอ้างอิง API อย่างเป็นทางการได้ที่ไหน?  
**ตอบ:** เอกสารเต็มอยู่ที่ [นี่](https://reference.aspose.com/page/java/).

**ถาม:** มีเวอร์ชันทดลองฟรีสำหรับการทดสอบหรือไม่?  
**ตอบ:** แน่นอน. ดาวน์โหลดเวอร์ชันทดลองจาก [หน้า releases ของ Aspose.Page](https://releases.aspose.com/).

**ถาม:** ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับการประเมินได้อย่างไร?  
**ตอบ:** สามารถขอได้ที่ [นี่](https://purchase.aspose.com/temporary-license/).

**ถาม:** ฉันจะหาแหล่งสนับสนุนจากชุมชนได้ที่ไหน?  
**ตอบ:** เข้าร่วมฟอรั่มชุมชน Aspose.Page ที่ [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## สรุป
คุณได้เรียนรู้ **วิธีเพิ่ม radial gradient** ให้กับเอกสาร Java PostScript ด้วย Aspose.Page แล้ว โดยการปรับขนาดสี่เหลี่ยม, color stops, และรัศมีของ gradient คุณสามารถสร้างเอฟเฟกต์ภาพที่หลากหลาย ตั้งแต่การเติมพื้นหลังที่อ่อนโยนจนถึงกราฟิกสปอตไลท์ที่โดดเด่น อย่าลังเลทดลองค่า `AffineTransform` ต่าง ๆ เพื่อหมุนหรือเอียง gradient และผสานเทคนิคนี้กับข้อความและรูปภาพเพื่อให้ได้ผลลัพธ์ PDF หรือ EPS ที่สมบูรณ์ยิ่งขึ้น

---

**อัปเดตล่าสุด:** 2026-02-13  
**ทดสอบกับ:** Aspose.Page for Java รุ่นล่าสุด (ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}