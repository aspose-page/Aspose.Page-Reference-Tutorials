---
title: เพิ่มการไล่ระดับสีแนวตั้งใน Java PostScript
linktitle: เพิ่มการไล่ระดับสีแนวตั้งใน Java PostScript
second_title: Aspose.Page Java API
description: สำรวจคำแนะนำทีละขั้นตอนในการเพิ่มการไล่ระดับสีแนวตั้งใน Java PostScript ด้วย Aspose.Page สำหรับ Java ปรับปรุงเอกสารของคุณอย่างง่ายดายด้วยภาพที่มีชีวิตชีวา
type: docs
weight: 14
url: /th/java/postscript-gradient-addition/vertical/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการเพิ่มการไล่ระดับสีแนวตั้งใน Java PostScript โดยใช้ Aspose.Page สำหรับ Java หากคุณต้องการปรับปรุงเอกสารของคุณด้วยการไล่ระดับสีที่สะดุดตา บทช่วยสอนนี้เหมาะสำหรับคุณ Aspose.Page สำหรับ Java มีเครื่องมืออันทรงพลังในการจัดการเอกสาร PostScript ได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
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
ตอนนี้ เรามาแจกแจงขั้นตอนการเพิ่มการไล่ระดับสีแนวตั้งใน Java PostScript ออกเป็นหลายขั้นตอน
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: สร้างสตรีมเอาต์พุตสำหรับเอกสาร PostScript
```java
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## ขั้นตอนที่ 3: สร้างตัวเลือกการบันทึกด้วยขนาด A4
```java
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
```
## ขั้นตอนที่ 4: สร้างเอกสาร PS ใหม่
```java
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ขั้นตอนที่ 5: สร้างสี่เหลี่ยมผืนผ้า
```java
//สร้างสี่เหลี่ยม
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## ขั้นตอนที่ 6: ตั้งค่าสีและเศษส่วนสำหรับการไล่ระดับสี
```java
// สร้างอาร์เรย์ของสีและเศษส่วนสำหรับการไล่ระดับสี
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## ขั้นตอนที่ 7: สร้างการเปลี่ยนแปลงแบบไล่ระดับสี
```java
// สร้างการแปลงแบบไล่ระดับสี ส่วนประกอบมาตราส่วนในการแปลงจะต้องเท่ากับความกว้างและความสูงของสี่เหลี่ยมผืนผ้า
// ส่วนประกอบการแปลเป็นการชดเชยของสี่เหลี่ยม
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// หมุนการไล่ระดับสี 90 องศารอบจุดกำเนิด
transform.rotate(90 * (Math.PI / 180));
```
## ขั้นตอนที่ 8: สร้างสีไล่ระดับสีเชิงเส้นแนวตั้ง
```java
// สร้างสีไล่ระดับสีเชิงเส้นแนวตั้ง
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## ขั้นตอนที่ 9: ตั้งค่าสีและเติมสี่เหลี่ยม
```java
// เซ็ตสี
document.setPaint(paint);
// เติมสี่เหลี่ยม
document.fill(rectangle);
```
## ขั้นตอนที่ 10: ปิดหน้าปัจจุบันและบันทึกเอกสาร
```java
// ปิดหน้าปัจจุบัน
document.closePage();
// บันทึกเอกสาร
document.save();
```
ยินดีด้วย! คุณได้เพิ่มการไล่ระดับสีแนวตั้งลงในเอกสาร Java PostScript ของคุณสำเร็จแล้วโดยใช้ Aspose.Page สำหรับ Java
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการปรับปรุงเอกสารของคุณด้วยการไล่ระดับสีแนวตั้งที่มีชีวิตชีวาโดยใช้ Aspose.Page สำหรับ Java ตอนนี้คุณสามารถยกระดับการปรับแต่งเอกสารของคุณไปอีกระดับด้วยการผสมผสานภาพที่น่าทึ่ง
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับไลบรารี Java อื่นได้หรือไม่
ใช่ Aspose.Page สำหรับ Java ได้รับการออกแบบมาให้ทำงานร่วมกับไลบรารี Java อื่นๆ ได้อย่างราบรื่น
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารเพิ่มเติมได้ที่ไหน?
 มีเอกสารรายละเอียดให้[ที่นี่](https://reference.aspose.com/page/java/).
### ฉันจะซื้อ Aspose.Page สำหรับ Java ได้อย่างไร
 คุณสามารถซื้อ Aspose.Page สำหรับ Java ได้[ที่นี่](https://purchase.aspose.com/buy).
### มีฟอรัมสำหรับการสนทนา Aspose.Page หรือไม่
 ใช่ คุณสามารถเข้าร่วมฟอรัมชุมชนได้[ที่นี่](https://forum.aspose.com/c/page/39).