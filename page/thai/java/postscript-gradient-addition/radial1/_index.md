---
title: การเรียนรู้การไล่ระดับสีแบบเรเดียลใน Java PostScript ด้วย Aspose.Page
linktitle: การเรียนรู้การไล่ระดับสีแบบรัศมีใน Java
second_title: Aspose.Page Java API
description: เรียนรู้วิธีเพิ่มการไล่ระดับสีแบบรัศมีที่น่าทึ่งใน Java PostScript โดยใช้ Aspose.Page สำหรับ Java ยกระดับเอกสาร PostScript ของคุณด้วยคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 12
url: /th/java/postscript-gradient-addition/radial1/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีเพิ่มการไล่ระดับสีแบบรัศมีใน Java PostScript โดยใช้ Aspose.Page ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างเอกสาร PostScript ที่มีการไล่ระดับสีแบบรัศมีที่สวยงาม Aspose.Page สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณทำงานกับไฟล์ PostScript ได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ
-  Aspose.Page สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page จาก[ที่นี่](https://releases.aspose.com/page/java/).
- Integrated Development Environment (IDE): เลือก Java IDE ที่คุณต้องการ เช่น Eclipse หรือ IntelliJ
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นกับโปรเจ็กต์ Java PostScript ของคุณ:
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
## ขั้นตอนที่ 1: สร้างสี่เหลี่ยมผืนผ้า
เริ่มต้นด้วยการสร้างสี่เหลี่ยมในเอกสาร PostScript ของเรา:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
//สร้างสี่เหลี่ยม
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```
## ขั้นตอนที่ 2: กำหนดสีและเศษส่วน
กำหนดอาร์เรย์ของสีและเศษส่วนสำหรับการไล่ระดับสีในแนวรัศมี:
```java
// สร้างอาร์เรย์ของสีและเศษส่วนสำหรับการไล่ระดับสี
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```
## ขั้นตอนที่ 3: สร้างสีไล่ระดับสีแบบเรเดียล
สร้างสีไล่ระดับรัศมีสำหรับสี่เหลี่ยมผืนผ้า:
```java
// สร้างสีไล่ระดับแนวรัศมี
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(300, 200), 100, new Point2D.Float(300, 200),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## ขั้นตอนที่ 4: ตั้งค่าสีและเติมสี่เหลี่ยม
ตั้งค่าสีและเติมสี่เหลี่ยมด้วยการไล่ระดับสีแบบรัศมี:
```java
// เซ็ตสี
document.setPaint(paint);
// เติมสี่เหลี่ยม
document.fill(rectangle);
```
## ขั้นตอนที่ 5: ปิดและบันทึก
สุดท้าย ปิดหน้าปัจจุบันและบันทึกเอกสาร:
```java
// ปิดหน้าปัจจุบัน
document.closePage();
// บันทึกเอกสาร
document.save();
```
การดำเนินการนี้ทำให้กระบวนการเพิ่มการไล่ระดับสีแบบรัศมีไปยังเอกสาร Java PostScript ของคุณเสร็จสมบูรณ์โดยใช้ Aspose.Page
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีปรับปรุงเอกสาร PostScript ด้วยการไล่ระดับสีแบบรัศมีโดยใช้ Aspose.Page สำหรับ Java เรียบร้อยแล้ว ทดลองใช้สีและการกำหนดค่าต่างๆ เพื่อสร้างเอฟเฟกต์ภาพที่น่าทึ่ง
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java ในโครงการเชิงพาณิชย์ได้หรือไม่
 ได้ คุณสามารถใช้ Aspose.Page สำหรับ Java ในโครงการเชิงพาณิชย์ได้ สำหรับรายละเอียดใบอนุญาต โปรดไปที่[ที่นี่](https://purchase.aspose.com/buy).
### ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/page/java/).
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับใบอนุญาตชั่วคราวได้อย่างไร
 ได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ต้องการการสนับสนุนจากชุมชนหรือไม่?
 เข้าร่วมชุมชน Aspose.Page[ฟอรั่ม](https://forum.aspose.com/c/page/39).