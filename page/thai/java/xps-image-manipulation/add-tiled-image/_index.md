---
title: เพิ่มรูปภาพแบบเรียงต่อกันใน Java XPS
linktitle: เพิ่มรูปภาพแบบเรียงต่อกันใน Java XPS
second_title: Aspose.Page Java API
description: สำรวจการจัดการเอกสาร Java XPS ได้อย่างราบรื่นด้วย Aspose.Page เรียนรู้วิธีการเพิ่มรูปภาพเรียงต่อกันอย่างง่ายดายโดยใช้คำแนะนำทีละขั้นตอนนี้
weight: 11
url: /th/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรูปภาพแบบเรียงต่อกันใน Java XPS

## การแนะนำ
ในโลกแบบไดนามิกของการพัฒนา Java ความต้องการการจัดการและการสร้างเอกสารที่มีประสิทธิภาพมีเพิ่มมากขึ้น Aspose.Page สำหรับ Java กลายเป็นเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร XPS ได้อย่างราบรื่น บทช่วยสอนนี้มุ่งเน้นไปที่งานเฉพาะ – การเพิ่มรูปภาพแบบเรียงต่อกันลงในเอกสาร Java XPS
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Page สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Page สำหรับ Java จาก[เว็บไซต์](https://releases.aspose.com/page/java/).
3. ไดเร็กทอรีเอกสารของคุณ: เลือกหรือสร้างไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร XPS ของคุณ
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Page:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
ตอนนี้ เรามาแจกแจงขั้นตอนการเพิ่มรูปภาพแบบเรียงต่อกันลงในเอกสาร Java XPS ให้เป็นขั้นตอนที่ชัดเจนและจัดการได้
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการตั้งค่าโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่า Aspose.Page สำหรับ Java ได้รับการผสานรวมอย่างเหมาะสม
## ขั้นตอนที่ 2: สร้างเอกสาร XPS
เตรียมใช้งานเอกสาร XPS ใหม่โดยใช้รหัสต่อไปนี้:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างเอกสาร XPS ใหม่
XpsDocument doc = new XpsDocument();
```
## ขั้นตอนที่ 3: กำหนดเส้นทางรูปภาพแบบเรียงต่อกัน
ระบุเส้นทางไปยังรูปภาพเรียงต่อกันที่คุณต้องการเพิ่มลงในเอกสาร XPS
## ขั้นตอนที่ 4: เพิ่มรูปภาพที่เรียงต่อกัน
ใช้ข้อมูลโค้ดด้านล่างเพื่อเพิ่มรูปภาพแบบเรียงต่อกันลงในเอกสาร XPS:
```java
// ภาพไทล์
// ImageBrush เต็มไปด้วยสี่เหลี่ยมที่ด้านบนขวาด้านล่าง
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## ขั้นตอนที่ 5: บันทึกเอกสาร
สุดท้าย ให้บันทึกเอกสาร XPS ที่เป็นผลลัพธ์โดยใช้โค้ดด้านล่าง:
```java
// บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
ทำซ้ำขั้นตอนเหล่านี้เพื่อรวมภาพที่เรียงต่อกันเข้ากับเอกสาร Java XPS ของคุณได้อย่างง่ายดายโดยใช้ Aspose.Page
## บทสรุป
Aspose.Page สำหรับ Java ปรับปรุงกระบวนการทำงานกับเอกสาร XPS ให้มีประสิทธิภาพยิ่งขึ้น โดยนำเสนอโซลูชันที่มีประสิทธิภาพสำหรับการจัดการเอกสารแก่นักพัฒนา ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถเพิ่มรูปภาพแบบเรียงต่อกันลงในเอกสาร Java XPS ของคุณได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### Aspose.Page เข้ากันได้กับ Java เวอร์ชันทั้งหมดหรือไม่
 Aspose.Page ได้รับการออกแบบมาเพื่อทำงานกับ Java เวอร์ชันต่างๆ ตรวจสอบความเข้ากันได้โดยการตรวจสอบเอกสารประกอบ[ที่นี่](https://reference.aspose.com/page/java/).
### ฉันสามารถใช้ Aspose.Page สำหรับโครงการเชิงพาณิชย์ได้หรือไม่
ใช่ Aspose.Page เสนอใบอนุญาตเชิงพาณิชย์ ซื้อพวกเขา[ที่นี่](https://purchase.aspose.com/buy).
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ สำรวจฟีเจอร์ Aspose.Page ด้วยการทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาการสนับสนุนและการสนทนาจากชุมชนได้ที่ไหน
 มีส่วนร่วมกับชุมชน Aspose.Page บน[ฟอรั่ม](https://forum.aspose.com/c/page/39).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร
 รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
