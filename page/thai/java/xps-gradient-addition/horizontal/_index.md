---
title: เพิ่มการไล่ระดับสีแนวนอนใน Java XPS
linktitle: เพิ่มการไล่ระดับสีแนวนอนใน Java XPS
second_title: Aspose.Page Java API
description: เรียนรู้วิธีเพิ่มการไล่ระดับสีแนวนอนที่น่าทึ่งให้กับเอกสาร XPS ใน Java โดยใช้ Aspose.Page ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 11
url: /th/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มการไล่ระดับสีแนวนอนใน Java XPS

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการเพิ่มการไล่ระดับสีแนวนอนใน Java XPS โดยใช้ Aspose.Page สำหรับ Java Aspose.Page สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาทำงานกับเอกสาร XPS (XML Paper Specification) ได้อย่างราบรื่น
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างแอปพลิเคชัน Java เพื่อเพิ่มการไล่ระดับสีแนวนอนให้กับเอกสาร XPS ทำตามขั้นตอนด้านล่างเพื่อให้บรรลุเป้าหมายนี้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ ถ้าไม่เช่นนั้น ให้ดาวน์โหลดและติดตั้ง Java เวอร์ชันล่าสุดจาก[ชวา.คอม](https://www.java.com).
2.  Aspose.Page สำหรับไลบรารี Java: คุณต้องมี Aspose.Page สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[Aspose.Page สำหรับเอกสาร Java](https://reference.aspose.com/page/java/).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นสำหรับแอปพลิเคชัน Java ของคุณ รวม Aspose.Page สำหรับไลบรารี Java ในโปรเจ็กต์ของคุณ คุณสามารถทำได้โดยเพิ่มบรรทัดโค้ดต่อไปนี้:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## ขั้นตอนที่ 1: เริ่มต้นเอกสาร
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
//เริ่มต้นเอกสาร
XpsDocument doc = new XpsDocument();
```
## ขั้นตอนที่ 2: สร้างการไล่ระดับสีแนวนอน
```java
// การไล่ระดับสีแนวนอน
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## ขั้นตอนที่ 3: เพิ่มเส้นทางด้วยการไล่ระดับสี
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## ขั้นตอนที่ 4: บันทึกเอกสาร
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
ทำซ้ำขั้นตอนเหล่านี้ตามความจำเป็น โดยปรับพารามิเตอร์ตามความต้องการเฉพาะของคุณ
## บทสรุป
ยินดีด้วย! คุณได้เพิ่มการไล่ระดับสีแนวนอนลงในเอกสาร XPS โดยใช้ Aspose.Page สำหรับ Java สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำที่ครอบคลุมสำหรับนักพัฒนาที่ต้องการปรับปรุงแอปพลิเคชัน Java ด้วยเอฟเฟกต์การไล่ระดับสี
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้การไล่ระดับสีหลายแบบในเอกสาร XPS เดียวได้หรือไม่
ได้ คุณสามารถเพิ่มหลายเส้นทางด้วยการไล่ระดับสีที่แตกต่างกันเพื่อสร้างการออกแบบที่ซับซ้อน
### ถาม: Aspose.Page เข้ากันได้กับ Java เวอร์ชันล่าสุดหรือไม่
Aspose.Page สำหรับ Java ได้รับการอัปเดตเป็นประจำเพื่อให้แน่ใจว่าสามารถใช้งานร่วมกับ Java รุ่นล่าสุดได้
### ถาม: มีการไล่ระดับสีประเภทอื่นๆ ใน Aspose.Page หรือไม่
ใช่ นอกจากการไล่ระดับสีเชิงเส้นแล้ว Aspose.Page ยังรองรับการไล่ระดับสีแบบรัศมีเพื่อเอฟเฟกต์ที่หลากหลายมากขึ้น
### ถาม: ฉันสามารถปรับแต่งสีและตำแหน่งของจุดไล่ระดับสีได้หรือไม่
อย่างแน่นอน! คุณสามารถควบคุมสีและตำแหน่งของแต่ละจุดไล่ระดับสีได้อย่างเต็มที่
### ถาม: มีฟอรัมชุมชนสำหรับ Aspose.Page ที่ฉันสามารถขอความช่วยเหลือได้หรือไม่
 ใช่คุณสามารถเยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและรับความช่วยเหลือ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
