---
date: 2025-12-08
description: เรียนรู้วิธีสร้างตัวอย่างการไล่สีแบบรัศมีใน Java PostScript ด้วย Aspose.Page
  คู่มือขั้นตอนโดยละเอียดพร้อมโค้ดเต็มและการแก้ไขปัญหา
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'ตัวอย่างการไล่สีแบบรัศมี: Java PostScript กับ Aspose.Page'
url: /th/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวอย่างการไล่สีแบบรัศมี: Java PostScript กับ Aspose.Page

## Introduction
ในบทแนะนำนี้คุณจะสร้าง **radial gradient example** สำหรับเอกสาร PostScript โดยใช้ Aspose.Page for Java เราจะเดินผ่านทุกขั้นตอน—from ตั้งค่าโครงการจนถึงการเรนเดอร์วงกลมที่เติมด้วยไล่สีแบบรัศมีที่เรียบลื่น—เพื่อให้คุณสามารถเพิ่มกราฟิกที่ดึงดูดสายตาในแอปพลิเคชัน Java ของคุณได้ทันที.

## Quick Answers
- **What does this tutorial create?** ไฟล์ PostScript (`.ps`) ที่มีวงกลมที่เติมด้วย radial gradient.  
- **Which library is required?** Aspose.Page for Java (เวอร์ชันล่าสุด).  
- **How long does implementation take?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างที่ทำงานได้.  
- **Do I need a license?** จำเป็นต้องมีลิขสิทธิ์แบบชั่วคราวหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์; เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา.  
- **Can I reuse the code for PDF or SVG?** ใช่—Aspose.Page รองรับหลายรูปแบบเอาต์พุตโดยเปลี่ยนแปลงเพียงเล็กน้อย.

## What Is a Radial Gradient?
Radial gradient คือการเปลี่ยนสีจากจุดศูนย์กลางออกไปด้านนอก สร้างการผสมสีแบบรอบวงที่เรียบลื่น เหมาะสำหรับไฮไลท์, พื้นหลังปุ่ม, หรือภาพใด ๆ ที่ต้องการเอฟเฟกต์ “แสงเรืองแสง” ธรรมชาติ.

## Why Use Aspose.Page for Radial Gradients?
- **Device‑independent rendering** – ทำงานเช่นเดียวกันบน PostScript, PDF, SVG, และอื่น ๆ  
- **Full Java integration** – ไม่มีโค้ดเนทีฟ, เพียง API ของ Java ธรรมดา  
- **High‑quality output** – รองรับการแอนติเอเลียสและการควบคุม color‑space  

## Prerequisites
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความคุ้นเคยพื้นฐานกับการเขียนโปรแกรม Java  
- JDK 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ  
- ไลบรารี Aspose.Page for Java (ดาวน์โหลดจาก [Aspose.Page Java documentation](https://reference.aspose.com/page/java/))  

## Import Packages
แรกเริ่ม, นำเข้าคลาสที่เราต้องการ ซึ่งรวมถึงประเภทกราฟิก AWT มาตรฐานและ API ของ Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Document Directory
กำหนดโฟลเดอร์ที่ไฟล์ PostScript ที่สร้างจะถูกบันทึก แทนที่ placeholder ด้วยพาธจริงบนระบบของคุณ.

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream
เปิด `FileOutputStream` ที่ชี้ไปยังไฟล์ `.ps` เป้าหมาย สตรีมนี้จะรับข้อมูลไบนารีที่สร้างโดย Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Step 3: Create Save Options
สร้างอินสแตนซ์ `PsSaveOptions` คุณสามารถปรับขนาดหน้า, การบีบอัด ฯลฯ แต่ค่าตั้งต้นก็เพียงพอสำหรับตัวอย่างนี้.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Step 4: Create PS Document
สร้างอ็อบเจกต์ `PsDocument` โดยส่งสตรีมเอาต์พุตและตัวเลือกการบันทึก ธง `false` บอก Aspose.Page ไม่ให้เปิดหน้าโดยอัตโนมัติ (เราจะทำเอง).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Create a Circle
เราจะวาดวงกลมโดยใช้ `Ellipse2D.Float` พารามิเตอร์คือ `(x, y, width, height)` การตั้งค่า width = height จะสร้างวงกลมที่สมบูรณ์.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Step 6: Define Gradient Colors
เตรียมอาเรย์สองชุด: หนึ่งสำหรับสีที่จะแสดงใน gradient และอีกหนึ่งสำหรับตำแหน่งเศษส่วนที่สอดคล้อง (0 = ศูนย์กลาง, 1 = ขอบ).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Step 7: Create AffineTransform
`AffineTransform` ปรับสเกลและย้ายตำแหน่ง gradient ให้พอดีกับวงกลมของเรา เมทริกซ์ `(scaleX, 0, 0, scaleY, translateX, translateY)` ทำหน้าที่นี้.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Step 8: Create Radial Gradient Paint
ตอนนี้เราจะสร้างอ็อบเจกต์ `RadialGradientPaint` ซึ่งรับจุดศูนย์กลาง, รัศมี, จุดโฟกัส, เศษส่วนสี, อาเรย์สี, วิธีวน, color space, และการแปลงที่เรากำหนดไว้.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Step 9: Set Paint and Fill Circle
ใช้ gradient paint กับเอกสารและเติมวงกลมที่กำหนดไว้ก่อนหน้านี้ นี่คือหัวใจของ **radial gradient example** ของเรา.

```java
document.setPaint(paint);
document.fill(circle);
```

## Step 10: Close Page and Save Document
ปิดหน้าสุดท้าย, เขียนเนื้อหาไปยังดิสก์, และปิดสตรีม ไฟล์ PostScript ของคุณพร้อมสำหรับการดูด้วยโปรแกรมดู PS ใด ๆ.

```java
document.closePage();
document.save();
```

ยินดีด้วย! คุณได้สร้าง **radial gradient example** ใน Java PostScript ด้วย Aspose.Page อย่างสำเร็จ.

## Common Issues and Solutions
| ปัญหา | วิธีแก้ |
|---------|----------|
| **FileNotFoundException** when opening the output stream | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และคุณมีสิทธิ์เขียน. |
| Gradient looks flat or missing | ตรวจสอบว่าอาเรย์ `fractions` มีความยาวเท่ากับอาเรย์ `colors` และ `AffineTransform` ปรับสเกลอย่างถูกต้อง. |
| Colors appear inverted | สลับลำดับของสีในอาเรย์ `colors` หรือปรับพิกัดของจุด `focus`. |

## Frequently Asked Questions

**Q: ฉันสามารถหาเอกสารสำหรับ Aspose.Page for Java ได้จากที่ไหน?**  
A: การอ้างอิง API เต็มรูปแบบมีให้ที่ [here](https://reference.aspose.com/page/java/).

**Q: ฉันจะดาวน์โหลด Aspose.Page for Java ได้อย่างไร?**  
A: ดาวน์โหลด JAR เวอร์ชันล่าสุดจาก [releases page](https://releases.aspose.com/page/java/).

**Q: มีเวอร์ชันทดลองฟรีหรือไม่?**  
A: มี—ดาวน์โหลดเวอร์ชันทดลองได้ [here](https://releases.aspose.com/).

**Q: ฉันสามารถขอรับลิขสิทธิ์ชั่วคราวสำหรับการทดสอบได้หรือไม่?**  
A: แน่นอน, ขอได้จาก [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: ฉันจะหาแหล่งสนับสนุนจากชุมชนได้จากที่ไหน?**  
A: เข้าร่วมการสนทนาที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Conclusion
ในคู่มือนี้เราได้สร้าง **radial gradient example** ที่สมบูรณ์สำหรับเอกสาร PostScript โดยใช้ Aspose.Page for Java ด้วยการทำตามขั้นตอนคุณจะมีรูปแบบที่นำกลับมาใช้ใหม่ได้สำหรับการสร้างไล่สีที่ซับซ้อน ซึ่งคุณสามารถปรับใช้กับ PDF, SVG หรือรูปแบบที่รองรับอื่น ๆ ทดลองใช้สี, รัศมี, และรูปทรงที่แตกต่างเพื่อเพิ่มความหลากหลายให้กับโครงการกราฟิก Java ของคุณ.

---

**อัปเดตล่าสุด:** 2025-12-08  
**ทดสอบด้วย:** Aspose.Page for Java 24.11 (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}