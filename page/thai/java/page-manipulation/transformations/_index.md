---
title: คู่มือการเปลี่ยนแปลงขั้นสูงด้วย Aspose.Page
linktitle: การเปลี่ยนแปลงในการจัดการเพจ Java
second_title: Aspose.Page Java API
description: เรียนรู้วิธีดำเนินการแปลงหน้าขั้นสูงใน Java โดยใช้ Aspose.Page สำหรับ Java ปรับปรุงแอปพลิเคชัน Java ของคุณด้วยความสามารถในการจัดการอันทรงพลัง
type: docs
weight: 11
url: /th/java/page-manipulation/transformations/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมเกี่ยวกับการใช้คุณสมบัติอันทรงพลังของ Aspose.Page สำหรับ Java เพื่อทำการแปลงในการจัดการ Java Page Aspose.Page เป็นไลบรารี Java อเนกประสงค์ที่ช่วยให้นักพัฒนาสามารถทำงานกับงานการจัดการเพจต่างๆ ได้อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกคำแนะนำทีละขั้นตอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Page สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Page สำหรับเอกสาร Java](https://reference.aspose.com/page/java/).
- การตั้งค่า Java Integrated Development Environment (IDE) บนเครื่องของคุณ
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ Aspose.Page สำหรับ Java:
```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## ตัวอย่างที่ 1: ไม่มีการเปลี่ยนแปลง
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
//สร้างสี่เหลี่ยม
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// ตั้งค่าสีในสถานะกราฟิกที่ระดับบน
document.setPaint(Color.ORANGE);
// เติมสี่เหลี่ยมแรกโดยไม่มีการแปลงใดๆ
document.fill(shape);
// ปิดหน้าปัจจุบัน
document.closePage();
// บันทึกเอกสาร
document.save();
```
## ตัวอย่างที่ 2: การแปล
```java
// บันทึกสถานะกราฟิกเพื่อย้อนกลับหลังการแปลง
document.writeGraphicsSave();
// แทนที่สถานะกราฟิกปัจจุบัน 250 ไปทางขวา
document.translate(250, 0);
// ตั้งค่าสีในสถานะกราฟิกปัจจุบัน
document.setPaint(Color.BLUE);
// เติมสี่เหลี่ยมที่สองด้วยการแปลงการแปล
document.fill(shape);
// คืนค่าสถานะกราฟิกเป็นระดับก่อนหน้า (บน)
document.writeGraphicsRestore();
```
## ตัวอย่างที่ 3: การปรับขนาด
```java
// บันทึกสถานะกราฟิกเพื่อย้อนกลับหลังการแปลง
document.writeGraphicsSave();
// ปรับขนาดสถานะกราฟิกปัจจุบันบน 0.5 ในแกน X และ 0.75f ในแกน Y
document.scale(0.5f, 0.75f);
// ตั้งค่าสีในสถานะกราฟิกปัจจุบัน
document.setPaint(Color.RED);
// เติมสี่เหลี่ยมที่สามด้วยการแปลงขนาด
document.fill(shape);
// คืนค่าสถานะกราฟิกเป็นระดับก่อนหน้า (บน)
document.writeGraphicsRestore();
```
ดำเนินการต่อรูปแบบด้วยตัวอย่างสำหรับการหมุน การตัด และการแปลงที่ซับซ้อนตามตัวอย่างโค้ด Java ที่ให้มา
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจการเปลี่ยนแปลงต่างๆ ในการจัดการ Java Page โดยใช้ Aspose.Page สำหรับ Java โดยการปฏิบัติตามตัวอย่างเหล่านี้ คุณสามารถปรับปรุงแอปพลิเคชัน Java ของคุณด้วยความสามารถในการจัดการเพจขั้นสูง
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java สำหรับรูปแบบเอกสารอื่นได้หรือไม่
Aspose.Page มุ่งเน้นไปที่การจัดการหน้าสำหรับรูปแบบ PostScript และ XPS เป็นหลัก
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เยี่ยมชม[Aspose.Page สำหรับเอกสาร Java](https://reference.aspose.com/page/java/) เพื่อข้อมูลที่ครบถ้วน
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 ได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะขอการสนับสนุนจากชุมชนหรือถามคำถามเกี่ยวกับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เยี่ยมชม[Aspose.Page สำหรับฟอรัม Java](https://forum.aspose.com/c/page/39) สำหรับการอภิปรายในชุมชน