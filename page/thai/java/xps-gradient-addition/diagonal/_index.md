---
title: เพิ่มการไล่ระดับสีในแนวทแยงใน Java XPS
linktitle: เพิ่มการไล่ระดับสีในแนวทแยงใน Java XPS
second_title: Aspose.Page Java API
description: เรียนรู้วิธีเพิ่มการไล่ระดับสีในแนวทแยงอันน่าทึ่งให้กับเอกสาร XPS ของคุณใน Java โดยใช้ Aspose.Page ยกระดับการนำเสนอด้วยภาพของคุณได้อย่างง่ายดาย
weight: 10
url: /th/java/xps-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มการไล่ระดับสีในแนวทแยงใน Java XPS

## การแนะนำ
ในโลกของการพัฒนา Java ที่เปลี่ยนแปลงตลอดเวลา การปรับปรุงรูปลักษณ์ที่สวยงามของเอกสาร XPS ของคุณถือเป็นสิ่งสำคัญ วิธีหนึ่งที่มีประสิทธิภาพในการบรรลุเป้าหมายนี้คือการผสมผสานการไล่ระดับสีในแนวทแยงเข้าด้วยกัน บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการโดยใช้ Aspose.Page สำหรับ Java โดยให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ด
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Page สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
- โปรแกรมแก้ไขโค้ดเช่น IntelliJ IDEA หรือ Eclipse
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นสำหรับโปรเจ็กต์ Java ของคุณ ในโค้ดของคุณ คุณสามารถเพิ่มการนำเข้าต่อไปนี้:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ Java ใหม่ใน Integrated Development Environment (IDE) ที่คุณต้องการ และรวมไลบรารี Aspose.Page ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณที่จะบันทึกไฟล์ XPS:
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 3: สร้างเอกสาร XPS
เริ่มต้นวัตถุ XpsDocument ใหม่:
```java
XpsDocument doc = new XpsDocument();
```
## ขั้นตอนที่ 4: เพิ่มเส้นทางไล่ระดับสีในแนวทแยง
เพิ่มเส้นทางไปยังเอกสาร XPS ด้วยการไล่ระดับสีในแนวทแยง:
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```
## ขั้นตอนที่ 5: กำหนดจุดหยุดการไล่ระดับสีเชิงเส้น
ตั้งค่าการหยุดการไล่ระดับสีเชิงเส้นด้วยสีและตำแหน่งเฉพาะ:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... ทำซ้ำสำหรับสีและตำแหน่งอื่น
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```
## ขั้นตอนที่ 6: ใช้การไล่ระดับสีเชิงเส้นกับเส้นทาง
ใช้การไล่ระดับสีเชิงเส้นกับเส้นทางที่กำหนดไว้ก่อนหน้านี้:
```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## ขั้นตอนที่ 7: บันทึกเอกสาร
บันทึกเอกสาร XPS ด้วยการไล่ระดับสีในแนวทแยงเพิ่มเติม:
```java
doc.save(dataDir + "LinearGradient.xps");
```
## บทสรุป
ยินดีด้วย! คุณได้เพิ่มการไล่ระดับสีในแนวทแยงลงในเอกสาร XPS ของคุณสำเร็จแล้วโดยใช้ Aspose.Page สำหรับ Java คุณลักษณะที่ดึงดูดสายตานี้สามารถปรับปรุงการนำเสนอเอกสารโดยรวมของคุณได้
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.Page สำหรับ Java กับเฟรมเวิร์ก Java อื่นๆ ได้หรือไม่
Aspose.Page ได้รับการออกแบบมาเพื่อผสานรวมกับเฟรมเวิร์ก Java ต่างๆ ได้อย่างราบรื่น ทำให้เป็นตัวเลือกที่หลากหลายสำหรับโปรเจ็กต์ของคุณ
### ถาม: Aspose.Page มีข้อควรพิจารณาในการอนุญาตให้ใช้สิทธิ์หรือไม่
 ใช่ อย่าลืมตรวจสอบรายละเอียดใบอนุญาตใน[Aspose.หน้าการซื้อเพจ](https://purchase.aspose.com/buy).
### ถาม: ฉันสามารถลองใช้ Aspose.Page สำหรับ Java ก่อนซื้อได้หรือไม่
 อย่างแน่นอน! คุณสามารถสำรวจ[รุ่นทดลองใช้ฟรีที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนหรือเชื่อมต่อกับชุมชน Aspose ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อมีส่วนร่วมกับชุมชนและขอความช่วยเหลือ
### ถาม: มีข้อกำหนดเรื่องใบอนุญาตชั่วคราวหรือไม่?
 ใช่ คุณสามารถได้รับ[ใบอนุญาตชั่วคราวที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
