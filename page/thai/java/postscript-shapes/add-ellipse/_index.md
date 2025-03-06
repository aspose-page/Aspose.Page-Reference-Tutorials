---
title: เพิ่มวงรีใน Java PostScript
linktitle: เพิ่มวงรีใน Java PostScript
second_title: Aspose.Page Java API
description: เชี่ยวชาญการสร้างเอกสาร PostScript ที่น่าทึ่งใน Java ด้วย Aspose.Page เรียนรู้การเพิ่มจุดไข่ปลาทีละขั้นตอนเพื่อให้เนื้อหาดึงดูดสายตา
weight: 10
url: /th/java/postscript-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มวงรีใน Java PostScript

## การแนะนำ
ในโลกแบบไดนามิกของการพัฒนา Java การสร้างเอกสารที่ดึงดูดสายตาถือเป็นข้อกำหนดทั่วไป Aspose.Page สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาจัดการไฟล์ PostScript ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะสำรวจวิธีเพิ่มจุดไข่ปลาให้กับเอกสาร PostScript โดยใช้ Aspose.Page สำหรับ Java ทำตามเพื่อพัฒนาทักษะการสร้างเอกสารของคุณ!
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนา Java ที่ใช้งานได้ติดตั้งอยู่บนเครื่องของคุณ
2.  Aspose.Page สำหรับไลบรารี Java: ดาวน์โหลดและรวมไลบรารี Aspose.Page ในโปรเจ็กต์ Java ของคุณ คุณสามารถค้นหาห้องสมุด[ที่นี่](https://releases.aspose.com/page/java/).
## แพ็คเกจนำเข้า
ในโค้ด Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Page นี่คือตัวอย่าง:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## ขั้นตอนที่ 1: ตั้งค่าเอกสารของคุณ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ขั้นตอนที่ 2: เติมวงรีด้วยสี
```java
// กำหนดสีสำหรับเติมวงรี
document.setPaint(Color.ORANGE);
// เติมวงรีแรก
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```
## ขั้นตอนที่ 3: ร่างวงรีด้วยโรคหลอดเลือดสมอง
```java
// ตั้งค่าสีสำหรับวงรีลากเส้น
document.setPaint(Color.RED);
// ตั้งจังหวะ
document.setStroke(new BasicStroke(3));
// ลากเส้น (โครงร่าง) วงรีที่สอง
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```
## ขั้นตอนที่ 4: ปิดและบันทึกเอกสาร
```java
// ปิดหน้าปัจจุบัน
document.closePage();
// บันทึกเอกสาร
document.save();
```
ตอนนี้ คุณได้เพิ่มจุดไข่ปลาลงในเอกสาร PostScript ของคุณโดยใช้ Aspose.Page สำหรับ Java สำเร็จแล้ว! ทดลองใช้พิกัดและมิติต่างๆ เพื่อปรับแต่งภาพของคุณ
## บทสรุป
 Aspose.Page สำหรับ Java ช่วยให้กระบวนการสร้างและจัดการเอกสาร PostScript ง่ายขึ้น บทช่วยสอนนี้ช่วยให้คุณมีความรู้ในการเพิ่มวงรี ซึ่งเป็นรากฐานที่มั่นคงสำหรับการแสดงภาพที่ซับซ้อนมากขึ้น ดำดิ่งสู่[เอกสารประกอบ](https://reference.aspose.com/page/java/) สำหรับรายละเอียดและความสามารถเพิ่มเติม
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Page สำหรับ Java กับไลบรารี Java อื่นๆ ได้หรือไม่
ตอบ: ใช่ Aspose.Page สำหรับ Java ได้รับการออกแบบมาเพื่อผสานรวมกับไลบรารี Java อื่นๆ ได้อย่างราบรื่น
### ถาม: ฉันจะรับสิทธิ์ใช้งานชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 ตอบ: ขอรับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบ
### ถาม: Aspose.Page เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่
 ตอบ: แน่นอน! เยี่ยม[ที่นี่](https://purchase.aspose.com/buy) เพื่อสำรวจตัวเลือกใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์
### ถาม: ฉันจะขอความช่วยเหลือหรือหารือเกี่ยวกับคำถามที่เกี่ยวข้องกับ Aspose.Page ได้ที่ไหน
 ตอบ: เข้าร่วมชุมชนได้ที่[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อหารือและช่วยเหลือ
### ถาม: มีแหล่งข้อมูลฟรีสำหรับเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Page สำหรับ Java หรือไม่
 ตอบ: ใช้[ทดลองฟรี](https://releases.aspose.com/) และสำรวจตัวอย่างในเอกสารประกอบ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
