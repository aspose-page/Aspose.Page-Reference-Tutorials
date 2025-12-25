---
date: 2025-12-25
description: เรียนรู้วิธีเพิ่มไล่สีลงในเอกสาร XPS ด้วย Java โดยใช้ Aspose.Page และวิธีปรับแต่งจุดไล่สีเพื่อสร้างเอฟเฟกต์แนวนอนที่น่าทึ่ง
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: วิธีเพิ่มไล่สี – ไล่สีแนวนอนใน Java XPS
url: /th/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม Gradient – Horizontal Gradient ใน Java XPS

## บทนำ
ยินดีต้อนรับสู่คู่มือขั้นตอน‑ต่อ​ขั้นตอนเกี่ยวกับ **วิธีเพิ่ม gradient** ให้กับเอกสาร XPS ด้วย Java ในบทเรียนนี้คุณจะได้เรียนรู้วิธีเพิ่ม horizontal gradient, ทำไมมันถึงสำคัญต่อการทำให้ภาพดูสวยงาม, และวิธี **ปรับแต่ง gradient stops** เพื่อควบคุมสีอย่างแม่นยำ Aspose.Page for Java ทำให้การทำงานกับเอกสาร XPS (XML Paper Specification) ง่ายขึ้น, ให้คุณมุ่งเน้นที่การออกแบบแทนการจัดการไฟล์ระดับต่ำ

## คำตอบสั้น
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java  
- **เวอร์ชัน Java ที่ใช้ได้?** ใด ๆ ที่เป็น Java 8+ runtime  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้ trial ฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถเปลี่ยนทิศทางของ gradient ได้หรือไม่?** ได้ – เพียงปรับจุดเริ่มต้น/สิ้นสุดของ linear brush  
- **สามารถเพิ่มหลาย gradient ได้หรือไม่?** แน่นอน – ทำซ้ำขั้นตอนการสร้าง path พร้อม brush ที่ต่างกัน  

## Horizontal Gradient คืออะไรใน XPS?
Horizontal gradient คือการเปลี่ยนสีอย่างราบรื่นจากซ้ายไปขวาบนรูปทรงหนึ่ง ใน XPS มันถูกแทนด้วย linear gradient brush ที่ทำการอินเตอร์โพเลตระหว่าง **gradient stops** ที่กำหนดไว้ ผลลัพธ์นี้มักใช้สำหรับแบนเนอร์, ปุ่ม, และการเติมพื้นหลัง

## ทำไมต้องใช้ Aspose.Page for Java?
- **รองรับ XPS อย่างเต็มรูปแบบ** – สร้าง, แก้ไข, และเรนเดอร์โดยไม่ต้องพึ่งเครื่องมือของบุคคลที่สาม  
- **API ที่เรียบง่าย** – อ็อบเจ็กต์ระดับสูงเช่น `XpsDocument`, `XpsPath`, และ `XpsGradientBrush` ซ่อนความซับซ้อนของ XML ไว้ให้  
- **ประสิทธิภาพ** – ปรับให้ทำงานได้ดีกับเอกสารขนาดใหญ่และการประมวลผลเป็นชุด  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน, โปรดตรวจสอบว่าคุณมี:

1. **สภาพแวดล้อมการพัฒนา Java** – ติดตั้ง JDK ล่าสุดจาก [java.com](https://www.java.com)  
2. **ไลบรารี Aspose.Page for Java** – ดาวน์โหลดไฟล์ JAR จาก [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็น การนำเข้าต่าง ๆ นี้ทำให้คุณเข้าถึงการสร้างเอกสาร, การจัดการ gradient, และเรขาคณิตพื้นฐานได้

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## ขั้นตอนที่ 1: เริ่มต้น XPS Document
สร้างอินสแตนซ์ `XpsDocument` ใหม่และระบุตำแหน่งโฟลเดอร์ที่ต้องการบันทึกผลลัพธ์

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 2: สร้าง Horizontal Gradient
กำหนดรายการ **gradient stops** ที่ควบคุมสีและตำแหน่งของแต่ละจุดเปลี่ยนสี ตัวอย่างด้านล่างสร้าง gradient สไตล์สายรุ้งที่สดใส

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### วิธีปรับแต่ง gradient stops
- **สี** – ใช้ `doc.createColor(alpha, red, green, blue)` เพื่อกำหนดค่า ARGB ใด ๆ  
- **ตำแหน่ง** – อาร์กิวเมนต์ที่สอง (`float` ระหว่าง `0` ถึง `1`) กำหนดว่าจุดหยุดปรากฏที่ตำแหน่งใดบนเส้น gradient ปรับค่าต่าง ๆ เพื่อย้ายสีไปทางซ้ายหรือขวา  

## ขั้นตอนที่ 3: เพิ่ม Path ด้วย Gradient
สร้าง path รูปสี่เหลี่ยม, ใช้การแปลง (transform) หากจำเป็น, แล้วเติมด้วย linear gradient brush brush นี้ใช้สองจุด (`(10,0)` ถึง `(228,0)`) เพื่อให้ได้เอฟเฟกต์แนวนอน

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**เคล็ดลับ:** การใช้รายการ `stops` เดียวกันสำหรับหลาย path สามารถเพิ่มประสิทธิภาพได้, แต่ต้องจำไว้ว่าให้เรียก `clear()` ก่อนเพิ่ม stops ใหม่

## ขั้นตอนที่ 4: บันทึกเอกสาร
บันทึกไฟล์ XPS ลงดิสก์ ตอนนี้คุณสามารถเปิดไฟล์ด้วยโปรแกรมดู XPS ใดก็ได้เพื่อดู horizontal gradient ที่ทำงาน

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| Gradient ปรากฏเป็นสีเดียว | ไม่ได้เพิ่ม gradient stops หรือ brush ไม่ได้ตั้งค่า | ตรวจสอบให้แน่ใจว่า `path.setFill(...)` ใช้ `LinearGradientBrush` และว่าได้เพิ่ม stops ผ่าน `getGradientStops().addAll(stops)` |
| สีดูจืด | ค่า alpha (พารามิเตอร์แรก) ไม่ถูกต้อง | ใช้ค่า `255` สำหรับสีที่ทึบเต็มที่ เว้นแต่ต้องการความโปร่งใส |
| ขนาดของ path ผิด | ค่ามาตรฐานของเมทริกซ์แปลง (transform) ผิด | ปรับพารามิเตอร์ของเมทริกซ์ (`scaleX, skewY, skewX, scaleY, translateX, translateY`) ให้เหมาะสม |

## คำถามที่พบบ่อย

**ถาม: สามารถใช้หลาย gradient ในเอกสาร XPS เดียวได้หรือไม่?**  
ตอบ: ได้, คุณสามารถเพิ่มหลาย path, แต่ละ path มี brush gradient ของตนเอง เพื่อสร้างการออกแบบแบบหลายชั้นที่ซับซ้อน

**ถาม: Aspose.Page รองรับเวอร์ชัน Java ล่าสุดหรือไม่?**  
ตอบ: Aspose.Page for Java มีการอัปเดตอย่างสม่ำเสมอและทำงานได้กับ Java 8 และเวอร์ชันใหม่กว่า

**ถาม: มีประเภท gradient อื่น ๆ ที่ Aspose.Page รองรับหรือไม่?**  
ตอบ: นอกจาก linear gradient แล้ว Aspose.Page ยังรองรับ radial gradient สำหรับการเปลี่ยนสีเป็นวงกลม

**ถาม: สามารถปรับสีและตำแหน่งของ gradient stops ได้หรือไม่?**  
ตอบ: แน่นอน! คุณสามารถควบคุมสี ARGB ของแต่ละ stop และตำแหน่งสัมพัทธ์ของมัน (ช่วง 0‑1) ได้เต็มที่

**ถาม: มีฟอรั่มชุมชนสำหรับ Aspose.Page ที่ฉันสามารถขอความช่วยเหลือได้หรือไม่?**  
ตอบ: มี, คุณสามารถเยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและรับการช่วยเหลือ

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}