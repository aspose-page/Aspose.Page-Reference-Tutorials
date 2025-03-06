---
title: ปรับขนาดไฟล์ EPS ใน Java ด้วย Aspose.Page
linktitle: ปรับขนาดไฟล์ EPS ใน Java
second_title: Aspose.Page Java API
description: เรียนรู้วิธีปรับขนาดไฟล์ EPS ใน Java ได้อย่างง่ายดายด้วย Aspose.Page สำหรับ Java ปฏิบัติตามคำแนะนำที่ครอบคลุมของเราสำหรับคำแนะนำทีละขั้นตอน
weight: 11
url: /th/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปรับขนาดไฟล์ EPS ใน Java ด้วย Aspose.Page

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการปรับขนาดไฟล์ EPS ใน Java โดยใช้ไลบรารี Aspose.Page อันทรงพลัง หากคุณจำเป็นต้องปรับขนาดภาพ EPS ของคุณโดยทางโปรแกรม แสดงว่าคุณมาถูกที่แล้ว ในบทช่วยสอนนี้ เราจะสำรวจตัวเลือกการปรับขนาดต่างๆ รวมถึงจุด นิ้ว มิลลิเมตร และเปอร์เซ็นต์ เพื่อให้คุณมีความยืดหยุ่นตามที่คุณต้องการสำหรับความต้องการเฉพาะของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
-  Aspose.Page สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณมีการนำเข้าที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Page นี่คือตัวอย่าง:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
ตอนนี้ เราจะแบ่งบทช่วยสอนออกเป็นหลายขั้นตอนสำหรับตัวเลือกการปรับขนาดแต่ละรายการ:
## ปรับขนาด EPS โดยใช้คะแนน
### ขั้นตอนที่ 1: ตั้งค่าสตรีมอินพุต
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### ขั้นตอนที่ 2: เตรียมใช้งานวัตถุ PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### ขั้นตอนที่ 3: แยกขนาดปัจจุบันของอิมเมจ EPS
```java
Dimension oldSize = doc.extractEpsSize();
```
### ขั้นตอนที่ 4: สร้างสตรีมเอาต์พุต
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### ขั้นตอนที่ 5: ปรับขนาดและบันทึกเป็นจุด
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## ปรับขนาด EPS โดยใช้นิ้ว
ทำตามขั้นตอนที่คล้ายกันกับตัวอย่างที่ 1 โดยแทนที่ "Points" ด้วย "Inches" และปรับขนาดใหม่ตามนั้น
## ปรับขนาด EPS โดยใช้หน่วยมิลลิเมตร
ทำตามขั้นตอนที่คล้ายกันกับตัวอย่างที่ 1 โดยแทนที่ "จุด" ด้วย "มิลลิเมตร" และปรับขนาดใหม่ตามนั้น
## ปรับขนาด EPS โดยใช้เปอร์เซ็นต์
ทำตามขั้นตอนที่คล้ายกันกับตัวอย่างที่ 1 โดยแทนที่ "คะแนน" ด้วย "เปอร์เซ็นต์" และปรับขนาดใหม่ให้เหมาะสม
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีปรับขนาดไฟล์ EPS ใน Java โดยใช้ Aspose.Page เรียบร้อยแล้ว คู่มือนี้มีตัวเลือกที่หลากหลาย เพื่อให้มั่นใจว่าคุณสามารถปรับแต่งกระบวนการปรับขนาดให้ตรงกับความต้องการเฉพาะของคุณได้

## คำถามที่พบบ่อย
### ฉันสามารถใช้ไลบรารีนี้กับรูปแบบรูปภาพอื่นได้หรือไม่
ไม่ Aspose.Page ได้รับการออกแบบมาโดยเฉพาะสำหรับการจัดการไฟล์ PostScript และ EPS
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
ใช่ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับความช่วยเหลือและการสนทนาเพิ่มเติมได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อสนับสนุนชุมชน
### ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### มีโครงการตัวอย่างใดบ้าง?
 ใช่ ตรวจสอบเอกสาร[ที่นี่](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
