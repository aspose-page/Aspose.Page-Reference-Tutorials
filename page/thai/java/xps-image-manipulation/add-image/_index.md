---
title: การเพิ่มอิมเมจ Java XPS - คำแนะนำง่ายๆ ด้วย Aspose.Page
linktitle: เพิ่มรูปภาพใน Java XPS
second_title: Aspose.Page Java API
description: เรียนรู้วิธีเพิ่มรูปภาพลงในเอกสาร XPS ใน Java ได้อย่างง่ายดายโดยใช้ Aspose.Page ยกระดับการประมวลผลเอกสารของคุณด้วยคำแนะนำทีละขั้นตอนนี้
weight: 10
url: /th/java/xps-image-manipulation/add-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเพิ่มอิมเมจ Java XPS - คำแนะนำง่ายๆ ด้วย Aspose.Page

ในโลกของการพัฒนา Java ความสามารถในการทำงานกับเอกสาร XPS ถือเป็นสิ่งสำคัญสำหรับแอปพลิเคชันต่างๆ Aspose.Page สำหรับ Java มีชุดเครื่องมืออันทรงพลังในการจัดการเอกสาร XPS และงานที่สำคัญอย่างหนึ่งคือการเพิ่มรูปภาพ ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มรูปภาพลงในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ Java
## การแนะนำ
การเพิ่มรูปภาพลงในเอกสาร XPS เป็นข้อกำหนดทั่วไปในแอปพลิเคชัน Java จำนวนมาก ตั้งแต่การสร้างรายงานไปจนถึงการประมวลผลเอกสาร Aspose.Page สำหรับ Java ช่วยให้งานนี้ง่ายขึ้น โดยนำเสนอวิธีการที่มีประสิทธิภาพในการรวมรูปภาพเข้ากับไฟล์ XPS ของคุณได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะสาธิตวิธีเพิ่มรูปภาพลงในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Page สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.Page สำหรับไลบรารี Java จาก[เว็บไซต์](https://releases.aspose.com/page/java/).
2. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนเครื่องของคุณ
ตอนนี้เรามาดูขั้นตอนต่อไปกันดีกว่า
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจ Aspose.Page สำหรับ Java ที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการที่จำเป็น
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณที่จะจัดเก็บเอกสาร XPS และไฟล์รูปภาพ
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: สร้างเอกสาร XPS ใหม่
เริ่มต้นเอกสาร XPS ใหม่โดยใช้ข้อมูลโค้ดต่อไปนี้:
```java
XpsDocument doc = new XpsDocument();
```
## ขั้นตอนที่ 3: เพิ่มรูปภาพลงในเอกสาร XPS
หากต้องการเพิ่มรูปภาพ ให้สร้างเส้นทางในเอกสาร XPS และตั้งค่าแปรงรูปภาพโดยใช้ไฟล์รูปภาพและพิกัดที่ให้มา
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```
## ขั้นตอนที่ 4: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
บันทึกเอกสาร XPS ที่แก้ไขไปยังไดเร็กทอรีที่ระบุของคุณ
```java
doc.save(dataDir + "AddImage_out.xps");
```
ทำซ้ำขั้นตอนเหล่านี้เพื่อเพิ่มรูปภาพหรือปรับแต่งรูปภาพที่มีอยู่ตามความต้องการของโปรเจ็กต์ของคุณ
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มรูปภาพลงในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ Java เรียบร้อยแล้ว ทักษะนี้มีคุณค่าอย่างยิ่งในการปรับปรุงรูปลักษณ์ของแอปพลิเคชันและเอกสาร Java ของคุณ
### คำถามที่พบบ่อย
### ฉันสามารถเพิ่มหลายภาพลงในเอกสาร XPS เดียวกันโดยใช้ Aspose.Page สำหรับ Java ได้หรือไม่
ได้ คุณสามารถเพิ่มภาพได้หลายภาพโดยทำซ้ำขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้สำหรับแต่ละภาพ
### Aspose.Page สำหรับ Java รองรับรูปแบบรูปภาพใดบ้าง
Aspose.Page สำหรับ Java รองรับรูปแบบรูปภาพที่หลากหลาย รวมถึง TIFF, JPEG, PNG และ GIF
### มี Aspose.Page สำหรับ Java เวอร์ชันทดลองใช้หรือไม่
 ใช่ คุณสามารถขอรับ Aspose.Page สำหรับ Java รุ่นทดลองใช้ฟรีได้จาก[ลิงค์นี้](https://releases.aspose.com/).
### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).
### ฉันจะรับการสนับสนุนเพิ่มเติมหรือหารือเกี่ยวกับปัญหาที่เกี่ยวข้องกับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อขอความช่วยเหลือ แบ่งปันประสบการณ์ และเชื่อมต่อกับชุมชน Aspose.Page
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
