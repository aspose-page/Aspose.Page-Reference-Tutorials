---
date: 2026-04-24
description: เรียนรู้วิธีสร้างเอกสาร XPS ด้วย Java พร้อมวงรีไล่ระดับสีแบบรัศมี คู่มือขั้นตอนนี้แสดงวิธีตั้งความหนาของเส้นและกำหนดรูปทรงเส้นทางโดยใช้
  Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: เพิ่มวงรีใน Java XPS
second_title: Aspose.Page Java API
title: สร้างเอกสาร XPS ด้วย Java – เพิ่มวงรีไล่สีแบบรัศมี
url: /th/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มวงรีไล่สีรัศมีด้วย Aspose.Page

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **create XPS document Java** ด้วยวงรีที่มีเส้นขอบไล่สีรัศมีสวยงามโดยใช้ Aspose.Page for Java. Aspose.Page เป็นไลบรารีที่แข็งแรงซึ่งทำให้รายละเอียดระดับต่ำของ XPS เป็นนามธรรม ช่วยให้คุณมุ่งเน้นที่การออกแบบแทนที่จะเป็นความซับซ้อนของรูปแบบไฟล์. เมื่อจบคู่มือนี้ คุณจะมีไฟล์ XPS ที่พร้อมใช้งานซึ่งสามารถฝังลงในรายงาน ใบแจ้งหนี้ หรือกระบวนการสร้างเอกสารใด ๆ

## คำตอบเร็ว
- **โค้ดนี้สร้างอะไรขึ้นมา?** ไฟล์ XPS หนึ่งหน้า ที่มีวงรีที่มีเส้นขอบไล่สีรัศมีหลายสี.  
- **API หลักที่ใช้คืออะไร?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **ฉันต้องใช้ไลเซนส์เพื่อรันตัวอย่างหรือไม่?** ไลเซนส์ชั่วคราวทำงานได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **คุณสมบัติสำคัญที่เราตั้งค่าคืออะไร?** Brush ของเส้นขอบ (radial gradient), วิธีการกระจาย, จุดหยุดไล่สี, และความหนาของเส้นขอบ.  
- **ฉันสามารถเปลี่ยนขนาดของวงรีได้หรือไม่?** ได้ – แก้ไขสตริงของ path geometry หรือพิกัดของ gradient brush.

## “create XPS document Java” คืออะไร?
การสร้างเอกสาร XPS ด้วย Java หมายถึงการสร้างไฟล์ XML Paper Specification (XPS) อย่างโปรแกรมเมติกโดยตรงจากโค้ด Java. Aspose.Page ให้โมเดลออบเจ็กต์ระดับสูง (`XpsDocument`, `XpsCanvas`, ฯลฯ) ที่ทำให้การทำงานกับ XML markup ง่ายเหมือนการทำงานกับออบเจ็กต์ Java ปกติ.

## ทำไมต้องใช้วงรีไล่สีรัศมี?
ไล่สีรัศมีให้ความรู้สึกสามมิติ เหมาะสำหรับการเน้นภาพ โลโก้ หรือองค์ประกอบตกแต่งในรายงาน. เมื่อเทียบกับเส้นขอบสีทึบ, ไล่สีเพิ่มความลึกโดยไม่เพิ่มขนาดไฟล์อย่างมีนัยสำคัญ, และรูปแบบ XPS รักษาคุณภาพเวกเตอร์สำหรับการขยายขนาดใด ๆ.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อม:
- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ.
- ไลบรารี Aspose.Page for Java ดาวน์โหลดแล้ว คุณสามารถรับได้ [ที่นี่](https://releases.aspose.com/page/java/).
- โปรแกรมแก้ไขโค้ดตามที่คุณเลือก (Eclipse, IntelliJ ฯลฯ) สำหรับเขียนและรันโค้ด Java.

## นำเข้าแพ็กเกจ
ตรวจสอบว่าคุณได้นำเข้าแพ็กเกจที่จำเป็นในโปรเจค Java ของคุณเพื่อใช้ Aspose.Page. เพิ่มคำสั่ง import ต่อไปนี้ที่ส่วนบนของไฟล์ Java ของคุณ:

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

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดเส้นทางไปยังไดเรกทอรีเอกสารของคุณที่ไฟล์ XPS จะถูกบันทึก:

```java
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง XPS Document
สร้างเอกสาร XPS ใหม่โดยใช้โค้ดต่อไปนี้:

```java
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 3: กำหนดจุดหยุดไล่สีรัศมี
สร้างรายการของจุดหยุดไล่สีสำหรับวงรีที่มีเส้นขอบไล่สีรัศมี:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## ขั้นตอนที่ 4: สร้าง Path Geometry
กำหนดวงรีที่มีเส้นขอบไล่สีรัศมีโดยใช้ path geometry:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## ขั้นตอนที่ 5: เพิ่ม Canvas และ Path
เพิ่ม canvas ใหม่ไปยังเอกสารและต่อ path ด้วย geometry ที่กำหนด:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## ขั้นตอนที่ 6: ตั้งค่า Stroke และ Gradient
กำหนดค่า stroke ของ path ด้วย brush ไล่สีรัศมี:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## ขั้นตอนที่ 7: ตั้งค่า Stroke Thickness
ระบุ **set stroke thickness** ของ path:

```java
path.setStrokeThickness(12f);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร
บันทึกไฟล์ XPS ที่ได้:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Congratulations! You have successfully added a radial gradient stroked ellipse while **create XPS document Java** with Aspose.Page.

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **วงรีแสดงผลแบน** | ใช้ `XpsSpreadMethod.Pad` แทน `Reflect` | เปลี่ยนวิธีการกระจายเป็น `XpsSpreadMethod.Reflect` ตามที่แสดงในขั้นตอนที่ 6. |
| **ไม่มีไฟล์ผลลัพธ์** | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่ | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่หรือใช้เส้นทางแบบเต็ม. |
| **สีไล่สีดูผิดพลาด** | ลำดับของจุดหยุดไล่สีไม่ถูกต้อง | ตรวจสอบค่า `offset` (0 → 1) เพิ่มขึ้นอย่างต่อเนื่อง. |
| **ข้อผิดพลาดการคอมไพล์** | ไม่มีไฟล์ JAR ของ Aspose.Page ใน classpath | เพิ่ม `aspose-page-xx.jar` ไปยัง dependencies ของโปรเจคของคุณ. |

## คำถามที่พบบ่อย

**Q:** ฉันสามารถใช้ Aspose.Page for Java กับไลบรารี Java อื่นได้หรือไม่?  
**A:** ใช่, Aspose.Page for Java สามารถรวมกับไลบรารี Java อื่นได้อย่างราบรื่น.

**Q:** Aspose.Page เหมาะกับการประมวลผลเอกสารขนาดใหญ่หรือไม่?  
**A:** แน่นอน! Aspose.Page ถูกออกแบบมาเพื่อจัดการการประมวลผลเอกสารขนาดใหญ่อย่างมีประสิทธิภาพ.

**Q:** ฉันสามารถหา tutorial และตัวอย่างเพิ่มเติมสำหรับ Aspose.Page for Java ได้ที่ไหน?  
**A:** เยี่ยมชม [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) เพื่อรับ tutorial และตัวอย่างที่ครอบคลุม.

**Q:** ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?  
**A:** คุณสามารถรับไลเซนส์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

**Q:** มีฟอรั่มชุมชนสำหรับการสนทนาเกี่ยวกับ Aspose.Page หรือไม่?  
**A:** มี, เข้าร่วม [Aspose.Page community forum](https://forum.aspose.com/c/page/39) เพื่อพูดคุยกับนักพัฒนาคนอื่นและขอความช่วยเหลือ.

---

**อัปเดตล่าสุด:** 2026-04-24  
**ทดสอบด้วย:** Aspose.Page for Java 24.11 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}