---
title: เพิ่มการไล่ระดับสีในแนวทแยงใน Java PostScript
linktitle: เพิ่มการไล่ระดับสีในแนวทแยงใน Java PostScript
second_title: Aspose.Page Java API
description: ปรับปรุงเอกสาร Java PostScript ของคุณด้วยการไล่ระดับสีในแนวทแยงโดยใช้ Aspose.Page สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อเพิ่มการเปลี่ยนสีที่สดใสได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/java/postscript-gradient-addition/diagonal/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการเพิ่มการไล่ระดับสีในแนวทแยงใน Java PostScript โดยใช้ Aspose.Page สำหรับ Java ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการ โดยแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน ในฐานะนักเขียน SEO ที่เชี่ยวชาญ ฉันจะตรวจสอบให้แน่ใจว่าเนื้อหาไม่เพียงแต่ให้ข้อมูลเท่านั้น แต่ยังปรับให้เหมาะกับเครื่องมือค้นหาด้วย ทำให้นักพัฒนาและผู้ที่สนใจติดตามได้ง่าย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Eclipse หรือ IntelliJ
-  Aspose.Page สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้น:
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
## ขั้นตอนที่ 1: สร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```
## ขั้นตอนที่ 2: สร้างตัวเลือกการบันทึกด้วยขนาด A4
```java
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
```
## ขั้นตอนที่ 3: สร้างเอกสาร PS ใหม่
```java
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ขั้นตอนที่ 4: สร้างสี่เหลี่ยมผืนผ้า
```java
//สร้างสี่เหลี่ยม
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## ขั้นตอนที่ 5: สร้างการเปลี่ยนแปลงแบบไล่ระดับสี
```java
//สร้างการแปลงแบบไล่ระดับสี ส่วนประกอบมาตราส่วนจะต้องเท่ากับความกว้างและความสูงของสี่เหลี่ยมผืนผ้า
// ส่วนประกอบการแปลเป็นการชดเชยของสี่เหลี่ยม
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// หมุนการไล่ระดับสี จากนั้นปรับขนาดและแปลเพื่อการเปลี่ยนสีที่มองเห็นได้
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```
## ขั้นตอนที่ 6: สร้างสีไล่ระดับสีเชิงเส้นในแนวทแยง
```java
// สร้างสีไล่ระดับสีเชิงเส้นในแนวทแยง
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```
## ขั้นตอนที่ 7: ตั้งค่าสีและเติมสี่เหลี่ยม
```java
// ตั้งค่าสีและเติมสี่เหลี่ยม
document.setPaint(paint);
document.fill(rectangle);
```
## ขั้นตอนที่ 8: ปิดหน้าปัจจุบันและบันทึกเอกสาร
```java
// ปิดหน้าปัจจุบันและบันทึกเอกสาร
document.closePage();
document.save();
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะเพิ่มการไล่ระดับสีในแนวทแยงใน Java PostScript ได้สำเร็จโดยใช้ Aspose.Page สำหรับ Java
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีปรับปรุงเอกสาร Java PostScript ด้วยการไล่ระดับสีในแนวทแยงโดยใช้ Aspose.Page สำหรับ Java ทดลองใช้พารามิเตอร์ต่างๆ เพื่อให้ได้เอฟเฟ็กต์ภาพที่ไม่เหมือนใคร
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ไลบรารีนี้สำหรับการทำงานกราฟิกอื่นๆ ใน Java ได้หรือไม่
ตอบ: ใช่ Aspose.Page สำหรับ Java มีคุณสมบัติมากมายสำหรับการทำงานกับ PostScript และองค์ประกอบกราฟิกอื่นๆ
### ถาม: Aspose.Page สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 ตอบ: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/page/java/).
### ถาม: ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถซื้อใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).
### ถาม: ต้องการความช่วยเหลือหรือมีคำถาม?
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39).