---
title: ตั้งค่า Opacity Mask ใน Java XPS
linktitle: ตั้งค่า Opacity Mask ใน Java XPS
second_title: Aspose.Page Java API
description: ค้นพบพลังของการตั้งค่ามาสก์ทึบใน Java XPS ด้วย Aspose.Page ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อประสบการณ์การใช้งานเอกสารที่ได้รับการปรับปรุงด้วยภาพ
weight: 11
url: /th/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่า Opacity Mask ใน Java XPS

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมของเราเกี่ยวกับการตั้งค่ามาสก์ทึบใน Java XPS โดยใช้ Aspose.Page ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการสร้างเอกสาร XPS การเพิ่มแคนวาส และการใช้มาสก์ความทึบกับสี่เหลี่ยมผืนผ้าโดยใช้ฟีเจอร์อันทรงพลังของ Aspose.Page สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Page สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
-  ใบอนุญาตที่ถูกต้องสำหรับ Aspose.Page หากคุณไม่มี คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
- สภาพแวดล้อมการพัฒนาที่ตั้งค่าให้รันแอปพลิเคชัน Java
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Page ไว้อย่างเหมาะสม ด้านล่างนี้เป็นตัวอย่างข้อมูลที่จะแนะนำคุณ:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
ตอนนี้ เรามาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: สร้างเอกสาร XPS ใหม่
```java
// สร้างเอกสาร XPS ใหม่
XpsDocument doc = new XpsDocument();
```
## ขั้นตอนที่ 2: เพิ่ม Canvas
```java
// ผ้าใบใหม่
XpsCanvas canvas = doc.addCanvas();
```
## ขั้นตอนที่ 3: เพิ่มสี่เหลี่ยมผืนผ้าด้วย Opacity Mask
```java
// สี่เหลี่ยมผืนผ้าตรงกลางด้านซ้ายโดยมีความทึบซึ่งปกปิดโดย ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## ขั้นตอนที่ 4: ตั้งค่า Opacity Mask ด้วย ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## ขั้นตอนที่ 5: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
```java
// บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
doc.save(dataDir + "OpacityMask_out.xps"); 
```
ทำตามขั้นตอนเหล่านี้อย่างระมัดระวังเพื่อรวมมาสก์ความทึบลงในเอกสาร Java XPS ของคุณโดยใช้ Aspose.Page
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีตั้งค่ามาสก์ความทึบใน Java XPS ด้วย Aspose.Page เรียบร้อยแล้ว ฟีเจอร์นี้ช่วยเพิ่มเลเยอร์ของภาพที่สมบูรณ์ให้กับเอกสารของคุณ ทำให้เอกสารมีความน่าสนใจและมีชีวิตชีวามากขึ้น
## คำถามที่พบบ่อย
### Aspose.Page เข้ากันได้กับสภาพแวดล้อมการพัฒนา Java ทั้งหมดหรือไม่
ใช่ Aspose.Page ได้รับการออกแบบมาให้ทำงานได้อย่างราบรื่นกับสภาพแวดล้อมการพัฒนา Java ต่างๆ
### ฉันสามารถใช้ Aspose.Page โดยไม่มีใบอนุญาตได้หรือไม่
แม้ว่าคุณจะสามารถใช้ Aspose.Page ได้โดยไม่ต้องมีใบอนุญาต แต่ขอแนะนำให้ขอรับใบอนุญาตสำหรับคุณสมบัติและการสนับสนุนเต็มรูปแบบ
### มีข้อจำกัดใดๆ ในเวอร์ชันทดลองหรือไม่?
เวอร์ชันทดลองอาจมีข้อจำกัดด้านฟีเจอร์บางประการ ขอแนะนำให้ตรวจสอบเอกสารเพื่อดูรายละเอียด
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Page ได้อย่างไร
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนจากชุมชนหรือซื้อใบอนุญาตเพื่อความช่วยเหลือระดับพรีเมียม
### มีการรับประกันคืนเงินสำหรับ Aspose.Page หรือไม่
 อ้างถึง[หน้าซื้อ](https://purchase.aspose.com/buy) สำหรับข้อมูลเกี่ยวกับนโยบายการคืนเงิน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
