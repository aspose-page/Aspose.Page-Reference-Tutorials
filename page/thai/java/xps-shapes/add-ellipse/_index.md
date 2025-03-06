---
title: เพิ่ม Radial Gradient Ellipse ด้วย Aspose.Page
linktitle: เพิ่มวงรีใน Java XPS
second_title: Aspose.Page Java API
description: สำรวจคำแนะนำทีละขั้นตอนเกี่ยวกับการเพิ่มวงรีลายเส้นแบบไล่ระดับสีใน Java XPS โดยใช้ Aspose.Page สำหรับ Java ปรับปรุงการสร้างเอกสารของคุณได้อย่างง่ายดาย
weight: 10
url: /th/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่ม Radial Gradient Ellipse ด้วย Aspose.Page

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการเพิ่มวงรีใน Java XPS โดยใช้ Aspose.Page สำหรับ Java Aspose.Page เป็นไลบรารี Java อันทรงพลังที่ช่วยให้นักพัฒนาทำงานกับเอกสาร XPS ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างวงรีที่มีการลากเส้นแบบไล่ระดับสีในแนวรัศมี และบันทึกเป็นเอกสาร XPS
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
-  ดาวน์โหลด Aspose.Page สำหรับไลบรารี Java แล้ว คุณสามารถรับมันได้[ที่นี่](https://releases.aspose.com/page/java/).
- โปรแกรมแก้ไขโค้ดที่คุณเลือก (Eclipse, IntelliJ ฯลฯ) สำหรับการเขียนและรันโค้ด Java
## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าคุณมีแพ็คเกจที่จำเป็นที่นำเข้าในโปรเจ็กต์ Java ของคุณเพื่อใช้ Aspose.Page เพิ่มคำสั่งนำเข้าต่อไปนี้ที่ด้านบนของไฟล์ Java ของคุณ:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณที่จะบันทึกเอกสาร XPS:
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: สร้างเอกสาร XPS
เตรียมใช้งานเอกสาร XPS ใหม่โดยใช้รหัสต่อไปนี้:
```java
XpsDocument doc = new XpsDocument();
```
## ขั้นตอนที่ 3: กำหนดจุดหยุดการไล่ระดับสีแบบรัศมี
สร้างรายการจุดหยุดการไล่ระดับสีสำหรับวงรีที่มีการลากเส้นไล่ระดับสีตามรัศมี:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## ขั้นตอนที่ 4: สร้างเรขาคณิตเส้นทาง
กำหนดวงรีที่มีการลากเส้นไล่ระดับแนวรัศมีโดยใช้เรขาคณิตของเส้นทาง:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## ขั้นตอนที่ 5: เพิ่ม Canvas และ Path
เพิ่มผืนผ้าใบใหม่ให้กับเอกสารและต่อท้ายเส้นทางด้วยรูปทรงเรขาคณิตที่กำหนด:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## ขั้นตอนที่ 6: ตั้งค่าโรคหลอดเลือดสมองและการไล่ระดับสี
กำหนดเส้นโครงร่างของเส้นทางด้วยแปรงไล่ระดับสีแบบรัศมี:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## ขั้นตอนที่ 7: ตั้งค่าความหนาของเส้นขีด
ระบุความหนาของเส้นขีดของเส้นทาง:
```java
path.setStrokeThickness(12f);
```
## ขั้นตอนที่ 8: บันทึกเอกสาร
บันทึกเอกสาร XPS ที่เป็นผลลัพธ์:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
ยินดีด้วย! คุณได้เพิ่มวงรีที่มีการไล่ระดับสีแบบรัศมีใน Java XPS โดยใช้ Aspose.Page สำหรับ Java สำเร็จแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจขั้นตอนในการสร้างเอกสาร XPS พร้อมด้วยวงรีลายเส้นไล่ระดับแนวรัศมีที่ดึงดูดสายตา Aspose.Page สำหรับ Java ช่วยให้การจัดการเอกสาร XPS ง่ายขึ้น ทำให้นักพัฒนามีชุดเครื่องมืออันทรงพลัง
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับไลบรารี Java อื่นได้หรือไม่
ได้ Aspose.Page สำหรับ Java สามารถรวมเข้ากับไลบรารี Java อื่นๆ ได้อย่างราบรื่น
### Aspose.Page เหมาะสำหรับการประมวลผลเอกสารขนาดใหญ่หรือไม่
อย่างแน่นอน! Aspose.Page ได้รับการออกแบบมาเพื่อจัดการการประมวลผลเอกสารขนาดใหญ่อย่างมีประสิทธิภาพ
### ฉันจะหาบทช่วยสอนและตัวอย่างเพิ่มเติมสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เยี่ยมชม[Aspose.Page สำหรับเอกสาร Java](https://reference.aspose.com/page/java/)สำหรับบทช่วยสอนและตัวอย่างที่ครอบคลุม
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### มีฟอรัมชุมชนสำหรับการสนทนา Aspose.Page หรือไม่
 ใช่เข้าร่วม[ฟอรั่มชุมชน Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อมีส่วนร่วมกับนักพัฒนารายอื่นและรับความช่วยเหลือ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
