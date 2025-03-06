---
title: การไล่ระดับสีแบบรัศมี Java PostScript ด้วย Aspose.Page
linktitle: การไล่ระดับสีแบบรัศมี Java PostScript ด้วย Aspose.Page
second_title: Aspose.Page Java API
description: สำรวจคำแนะนำทีละขั้นตอนเพื่อเพิ่ม Radial Gradient ใน Java PostScript โดยใช้ Aspose.Page สำหรับกราฟิกที่น่าทึ่งในแอปพลิเคชัน Java ของคุณ
weight: 13
url: /th/java/postscript-gradient-addition/radial2/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การไล่ระดับสีแบบรัศมี Java PostScript ด้วย Aspose.Page

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการเพิ่ม Radial Gradient 2 ใน Java PostScript โดยใช้ Aspose.Page สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้างเอกสาร PostScript ที่มีการไล่ระดับสีแบบรัศมีที่สวยงาม เพิ่มประสิทธิภาพแอปพลิเคชัน Java ของคุณด้วยกราฟิกที่ดึงดูดสายตา
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้การทำงานของการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
-  Aspose.Page สำหรับไลบรารี Java ซึ่งคุณสามารถดาวน์โหลดได้จาก[เอกสารประกอบ Java ของ Aspose.Page](https://reference.aspose.com/page/java/).
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Page:
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
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: สร้างกระแสเอาต์พุต
สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## ขั้นตอนที่ 3: สร้างตัวเลือกการบันทึก
สร้างตัวเลือกการบันทึกด้วยขนาด A4:
```java
PsSaveOptions options = new PsSaveOptions();
```
## ขั้นตอนที่ 4: สร้างเอกสาร PS
สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ขั้นตอนที่ 5: สร้างแวดวง
กำหนดวงกลมโดยใช้คลาส Ellipse2D.Float:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## ขั้นตอนที่ 6: กำหนดสีไล่ระดับสี
สร้างอาร์เรย์ของสีและเศษส่วนสำหรับการไล่ระดับสีในแนวรัศมี:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## ขั้นตอนที่ 7: สร้าง AffineTransform
สร้าง AffineTransform สำหรับการไล่ระดับสีแบบรัศมี:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## ขั้นตอนที่ 8: สร้างสีไล่ระดับสีแบบเรเดียล
สร้าง RadialGradientPaint ด้วยพารามิเตอร์ที่ระบุ:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## ขั้นตอนที่ 9: ตั้งค่าสีและเติมวงกลม
ตั้งค่าสีและเติมวงกลมด้วยการไล่ระดับสีแบบรัศมี:
```java
document.setPaint(paint);
document.fill(circle);
```
## ขั้นตอนที่ 10: ปิดหน้าและบันทึกเอกสาร
ปิดหน้าปัจจุบันและบันทึกเอกสาร:
```java
document.closePage();
document.save();
```
ยินดีด้วย! คุณได้เพิ่ม Radial Gradient 2 ใน Java PostScript โดยใช้ Aspose.Page สำหรับ Java สำเร็จแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีปรับปรุงแอปพลิเคชัน Java ของคุณด้วยการไล่ระดับสีแบบรัศมีในเอกสาร PostScript Aspose.Page สำหรับ Java มีชุดเครื่องมืออันทรงพลังเพื่อสร้างกราฟิกที่น่าทึ่ง ช่วยให้คุณยกระดับโปรเจ็กต์ Java ของคุณขึ้นไปอีกระดับ
## คำถามที่พบบ่อย
### ถาม: ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 ตอบ: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/page/java/).
### ถาม: ฉันจะดาวน์โหลด Aspose.Page สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถดาวน์โหลดได้จาก[หน้าเผยแพร่](https://releases.aspose.com/page/java/).
### ถาม: มีการทดลองใช้ฟรีหรือไม่?
 ตอบ: ได้ คุณสามารถเข้าถึงรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันสามารถรับสิทธิ์การใช้งานชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้หรือไม่
 ตอบ: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะขอการสนับสนุนจากชุมชนและมีส่วนร่วมในการสนทนาได้ที่ไหน
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
