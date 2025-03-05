---
title: เพิ่มการไล่ระดับสีแนวตั้งใน Java XPS
linktitle: เพิ่มการไล่ระดับสีแนวตั้งใน Java XPS
second_title: Aspose.Page Java API
description: เรียนรู้วิธีเพิ่มการไล่ระดับสีแนวตั้งให้กับเอกสาร Java XPS ด้วย Aspose.Page เพิ่มความดึงดูดสายตาได้อย่างง่ายดาย คำแนะนำทีละขั้นตอนภายใน
type: docs
weight: 12
url: /th/java/xps-gradient-addition/vertical/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการเพิ่มการไล่ระดับสีแนวตั้งใน Java XPS โดยใช้ Aspose.Page สำหรับ Java การเพิ่มการไล่ระดับสีให้กับเอกสาร XPS ของคุณสามารถเพิ่มความน่าดึงดูดทางสายตาให้กับเนื้อหาของคุณ ทำให้มีความน่าดึงดูดและสวยงามมากขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- สภาพแวดล้อมการพัฒนา Java ที่ใช้งานได้
-  Aspose.Page สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/java/).
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นสำหรับโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้รวม Aspose.Page สำหรับไลบรารี Java ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
        
// นำเข้า Aspose.Page สำหรับ Java
```
## ขั้นตอนที่ 1: เริ่มต้นเอกสาร
เริ่มต้นด้วยการเริ่มต้นเอกสาร XPS นี่เป็นการวางรากฐานสำหรับการเพิ่มองค์ประกอบ เช่น เส้นทางและการไล่ระดับสีให้กับเอกสารของคุณ
```java
// เริ่มต้นเอกสาร
XpsDocument doc = new XpsDocument();
```
## ขั้นตอนที่ 2: สร้างเส้นทางด้วยการไล่ระดับสีในแนวตั้ง
ตอนนี้ เรามาสร้างเส้นทางที่มีการไล่ระดับสีในแนวตั้งกันดีกว่า สิ่งนี้เกี่ยวข้องกับการกำหนดเรขาคณิตของเส้นทางและการระบุจุดหยุดการไล่ระดับสี
```java
// สร้างเส้นทางด้วยเรขาคณิต
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// กำหนดจุดหยุดการไล่ระดับสีในแนวตั้ง
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//ใช้การไล่ระดับสีแนวตั้งกับเส้นทาง
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## ขั้นตอนที่ 3: บันทึกเอกสาร
สุดท้าย ให้บันทึกเอกสาร XPS โดยเพิ่มการไล่ระดับสีแนวตั้งลงในไดเร็กทอรีที่คุณต้องการ
```java
// บันทึกเอกสาร
doc.save(dataDir + "VerticalGradient.xps");
```
ยินดีด้วย! คุณได้เพิ่มการไล่ระดับสีแนวตั้งลงในเอกสาร Java XPS ของคุณสำเร็จแล้วโดยใช้ Aspose.Page
## บทสรุป
การปรับปรุงเอกสาร XPS ของคุณด้วยการไล่ระดับสีสามารถปรับปรุงรูปลักษณ์ที่สวยงามได้อย่างมาก Aspose.Page สำหรับ Java ทำให้กระบวนการนี้ง่ายขึ้น ช่วยให้คุณสร้างเอกสารที่น่าทึ่งได้อย่างง่ายดาย

### คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java ในโครงการเชิงพาณิชย์ได้หรือไม่
 ใช่ Aspose.Page สำหรับ Java พร้อมให้ใช้งานเชิงพาณิชย์แล้ว คุณสามารถซื้อได้[ที่นี่](https://purchase.aspose.com/buy).
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/page/java/).
### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 ได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ต้องการความช่วยเหลือหรือมีคำถาม?
 เยี่ยมชมชุมชน Aspose.Page[ฟอรั่ม](https://forum.aspose.com/c/page/39).