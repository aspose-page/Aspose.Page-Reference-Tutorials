---
title: เพิ่มสี่เหลี่ยมผืนผ้าใน Java XPS
linktitle: เพิ่มสี่เหลี่ยมผืนผ้าใน Java XPS
second_title: Aspose.Page Java API
description: เรียนรู้วิธีเพิ่มสี่เหลี่ยมใน Java XPS โดยใช้ Aspose.Page ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการเอกสารที่ราบรื่น #JavaXPS #AsposePage
weight: 11
url: /th/java/xps-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มสี่เหลี่ยมผืนผ้าใน Java XPS

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมเกี่ยวกับการเพิ่มสี่เหลี่ยมใน Java XPS โดยใช้ Aspose.Page! ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นด้วย Java XPS บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการพร้อมคำแนะนำทีละขั้นตอน เพื่อให้แน่ใจว่าคุณจะเข้าใจหัวข้อนี้อย่างลึกซึ้ง
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
-  ติดตั้งไลบรารี Aspose.Page แล้ว ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[เอกสารประกอบ Java ของ Aspose.Page](https://reference.aspose.com/page/java/).
- สภาพแวดล้อมการพัฒนา Java ที่ใช้งานได้
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Page ถูกเพิ่มใน classpath ของคุณอย่างถูกต้อง นี่คือตัวอย่างพื้นฐาน:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
ตอนนี้ เรามาแยกตัวอย่างออกเป็นหลายขั้นตอนเพื่อเพิ่มสี่เหลี่ยมผืนผ้าใน Java XPS
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ
## ขั้นตอนที่ 2: สร้างเอกสาร XPS ใหม่
```java
// สร้างเอกสาร XPS ใหม่
XpsDocument doc = new XpsDocument();
```
นี่เป็นการเริ่มต้นเอกสาร XPS ใหม่
## ขั้นตอนที่ 3: เพิ่มสี่เหลี่ยมผืนผ้าลายเส้นสีทึบ CMYK
```java
// สี่เหลี่ยมผืนผ้าขีดสีทึบ CMYK (สีน้ำเงิน) ที่ด้านซ้ายล่าง
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
ขั้นตอนนี้จะเพิ่มสี่เหลี่ยมลายเส้นที่มีสีทึบ CMYK
## ขั้นตอนที่ 4: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
```java
// บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
doc.save(dataDir + "AddRectangle_out.xps");
```
สุดท้าย ให้บันทึกเอกสาร XPS ที่แก้ไขแล้วด้วยสี่เหลี่ยมที่เพิ่มเข้าไป
ทำซ้ำขั้นตอนเหล่านี้ โดยปรับพารามิเตอร์ตามต้องการ เพื่อปรับแต่งสี่เหลี่ยมของคุณเพิ่มเติม
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มสี่เหลี่ยมใน Java XPS โดยใช้ Aspose.Page เรียบร้อยแล้ว บทช่วยสอนนี้เป็นรากฐานที่มั่นคงสำหรับความพยายามในการจัดการเอกสาร XPS ของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มสี่เหลี่ยมหลายอันในเอกสาร XPS เดียวได้หรือไม่
ได้ คุณสามารถเพิ่มสี่เหลี่ยมได้มากเท่าที่ต้องการโดยทำซ้ำขั้นตอนที่อธิบายไว้ในบทช่วยสอน
### ฉันจะเปลี่ยนสีของสี่เหลี่ยมได้อย่างไร?
 แก้ไขค่าสีใน`createColor` วิธีเพื่อให้ได้สีที่ต้องการ
### Aspose.Page เหมาะสำหรับการจัดการการจัดการเอกสาร XPS ที่ซับซ้อนหรือไม่
อย่างแน่นอน! Aspose.Page มีชุดคุณลักษณะที่มีประสิทธิภาพสำหรับการจัดการงานเอกสาร XPS ต่างๆ
### ฉันจะหาตัวอย่างและการสนับสนุนเพิ่มเติมได้ที่ไหน
 สำรวจ[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39)เพื่อดูตัวอย่างเพิ่มเติมและขอความช่วยเหลือจากชุมชน
### ฉันสามารถลองใช้ Aspose.Page ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถสำรวจได้[ทดลองฟรี](https://releases.aspose.com/) เพื่อสัมผัสความสามารถของ Aspose.Page
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
