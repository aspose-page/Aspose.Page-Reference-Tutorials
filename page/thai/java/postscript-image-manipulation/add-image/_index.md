---
title: เพิ่มรูปภาพใน Java PostScript
linktitle: เพิ่มรูปภาพใน Java PostScript
second_title: Aspose.Page Java API
description: สำรวจการบูรณาการอย่างราบรื่นของ Aspose.Page Java ในบทช่วยสอนนี้เกี่ยวกับการเพิ่มรูปภาพลงในเอกสาร PostScript ยกระดับความสามารถในการจัดการเอกสารของคุณ
type: docs
weight: 10
url: /th/java/postscript-image-manipulation/add-image/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการเพิ่มรูปภาพลงในเอกสาร Java PostScript โดยใช้ Aspose.Page สำหรับไลบรารี Java Aspose.Page เป็นไลบรารีอันทรงพลังที่มีฟีเจอร์ต่างๆ สำหรับการทำงานกับไฟล์ PostScript ช่วยให้นักพัฒนาสามารถจัดการและปรับปรุงเอกสารของตนได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Page สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ ใช้ข้อมูลโค้ดต่อไปนี้เป็นข้อมูลอ้างอิง:
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## ขั้นตอนที่ 1: เขียนบันทึกกราฟิก
ขั้นตอนแรกเกี่ยวข้องกับการเขียนบันทึกกราฟิกลงในเอกสาร เพื่อให้แน่ใจว่าการเปลี่ยนแปลงหรือการแก้ไขใดๆ ที่ทำในภายหลังสามารถย้อนกลับได้หากจำเป็น
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## ขั้นตอนที่ 2: แปลและแปลง
จากนั้น แปลเอกสารและสร้างออบเจ็กต์ BufferedImage จากไฟล์รูปภาพ ใช้ชุดของการแปลง เช่น การปรับขนาดและการหมุนโดยใช้ AffineTransform
```java
document.translate(100, 100);
// สร้างวัตถุ BufferedImage จากไฟล์รูปภาพ
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// สร้างการแปลงภาพ
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## ขั้นตอนที่ 3: เพิ่มรูปภาพลงในเอกสาร
ตอนนี้ เพิ่มรูปภาพที่แปลงแล้วลงในเอกสาร
```java
document.drawImage(image, transform, null);
```
## ขั้นตอนที่ 4: เขียนการคืนค่ากราฟิก
หลังจากเพิ่มรูปภาพแล้ว ให้เขียนการคืนค่ากราฟิกเพื่อดำเนินการเปลี่ยนแปลงให้เสร็จสิ้น
```java
document.writeGraphicsRestore();
```
## ขั้นตอนที่ 5: ปิดหน้าปัจจุบันและบันทึก
ปิดหน้าปัจจุบันและบันทึกเอกสาร
```java
document.closePage();
document.save();
```
ทำซ้ำขั้นตอนเหล่านี้เพื่อเพิ่มรูปภาพหลายรูปหรือปรับแต่งการแปลงตามความต้องการของคุณ
## บทสรุป
 ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มรูปภาพลงในเอกสาร Java PostScript โดยใช้ Aspose.Page สำหรับ Java เรียบร้อยแล้ว สำรวจ[เอกสารประกอบ](https://reference.aspose.com/page/java/) สำหรับคุณสมบัติและฟังก์ชันขั้นสูงเพิ่มเติม
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Page รองรับ Java เป็นหลัก แต่ก็มีเวอร์ชันสำหรับภาษาการเขียนโปรแกรมอื่นๆ เช่นกัน
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาการสนับสนุนชุมชนและการสนทนาที่เกี่ยวข้องกับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อสนับสนุนชุมชน
### มีแหล่งข้อมูลเพิ่มเติมสำหรับการซื้อ Aspose.Page สำหรับ Java หรือไม่
 คุณสามารถซื้อห้องสมุดได้[ที่นี่](https://purchase.aspose.com/buy).