---
title: ครอบตัดไฟล์ EPS ใน Java - คำแนะนำทีละขั้นตอนด้วย Aspose.Page
linktitle: ครอบตัดไฟล์ EPS ใน Java
second_title: Aspose.Page Java API
description: สำรวจคำแนะนำทีละขั้นตอนเกี่ยวกับการครอบตัดไฟล์ EPS ใน Java โดยใช้ Aspose.Page เพิ่มทักษะการจัดการเอกสารของคุณได้อย่างง่ายดาย
weight: 10
url: /th/java/manipulation-eps/crop/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ครอบตัดไฟล์ EPS ใน Java - คำแนะนำทีละขั้นตอนด้วย Aspose.Page

## การแนะนำ
คุณกำลังมองหาการจัดการไฟล์ EPS ในแอปพลิเคชัน Java ของคุณและสงสัยว่าจะครอบตัดไฟล์เหล่านั้นอย่างมีประสิทธิภาพได้อย่างไรใช่หรือไม่ ไม่ต้องมองอีกต่อไป! ในคู่มือที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดขั้นตอนของการครอบตัดไฟล์ EPS โดยใช้ Aspose.Page สำหรับไลบรารี Java อันทรงพลัง
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
-  Aspose.Page สำหรับไลบรารี Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Page สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
- Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
- ไดเร็กทอรีเอกสารของคุณ: สร้างไดเร็กทอรีเฉพาะเพื่อจัดเก็บไฟล์ EPS อินพุตและเอาต์พุตของคุณ
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ ข้อมูลโค้ดด้านล่างสาธิตวิธีการนำเข้าแพ็คเกจที่จำเป็น:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```
ตอนนี้ เรามาแจกแจงแต่ละขั้นตอนของโค้ดด้านบนเพื่อความเข้าใจที่ชัดเจนยิ่งขึ้น
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารและสตรีมอินพุต
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินพุตสตรีมสำหรับไฟล์ EPS
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
ในขั้นตอนนี้ เราจะกำหนดเส้นทางไดเร็กทอรีซึ่งมีไฟล์ EPS ของคุณอยู่ และสร้างอินพุตสตรีมสำหรับไฟล์ EPS เป้าหมาย
## ขั้นตอนที่ 2: เตรียมใช้งานวัตถุ PsDocument
```java
// เริ่มต้นวัตถุ PsDocument ด้วยสตรีมอินพุต
PsDocument doc = new PsDocument(inputEpsStream);
```
ที่นี่ เราเริ่มต้นวัตถุ PsDocument โดยใช้สตรีมอินพุตที่สร้างขึ้นในขั้นตอนก่อนหน้า
## ขั้นตอนที่ 3: แยกกล่องขอบเขตเริ่มต้น
```java
// รับกรอบขอบเริ่มต้นของภาพ EPS
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
รับกล่องขอบเขตเริ่มต้นของอิมเมจ EPS ซึ่งช่วยในการกำหนดพารามิเตอร์การครอบตัด
## ขั้นตอนที่ 4: สร้างกระแสเอาต์พุต
```java
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
สร้างสตรีมเอาต์พุตเพื่อบันทึกอิมเมจ EPS ที่ครอบตัด
## ขั้นตอนที่ 5: กำหนด Bounding Box และครอบตัดใหม่
```java
// สร้างกรอบขอบเขตใหม่
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// ครอบตัดรูปภาพ EPS และบันทึกลงในเอาต์พุตสตรีม
doc.cropEps(outputEpsStream, newBoundingBox);
```
กำหนดกรอบขอบเขตใหม่ด้วยพิกัดและขนาดเฉพาะ จากนั้นดำเนินการครอบตัดรูปภาพ EPS ตามนั้น
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีครอบตัดไฟล์ EPS ใน Java โดยใช้ Aspose.Page เรียบร้อยแล้ว รวมความรู้นี้เข้ากับโครงการของคุณเพื่อเพิ่มความสามารถในการจัดการเอกสารของคุณ
## คำถามที่พบบ่อย
### ถาม: Aspose.Page เข้ากันได้กับ Java 8 หรือไม่
ตอบ: ใช่ Aspose.Page เข้ากันได้กับ Java 8 และเวอร์ชันที่สูงกว่า
### ถาม: ฉันสามารถใช้ Aspose.Page เพื่อวัตถุประสงค์ทางการค้าได้หรือไม่
 ตอบ: ใช่คุณทำได้ สำหรับรายละเอียดใบอนุญาต โปรดไปที่[ที่นี่](https://purchase.aspose.com/buy).
### ถาม: ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนได้จากที่ไหน
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการอภิปรายและการสนับสนุน
### ถาม: มีการทดลองใช้ฟรีหรือไม่?
 ตอบ: ได้ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะได้รับใบอนุญาตชั่วคราวได้อย่างไร
 ตอบ: รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
