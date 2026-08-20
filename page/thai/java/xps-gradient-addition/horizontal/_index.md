---
date: 2026-03-13
description: เรียนรู้วิธีเพิ่มไล่สีลงในเอกสาร XPS ด้วย Java โดยใช้ Aspose.Page และวิธีปรับแต่งจุดไล่สีเพื่อสร้างเอฟเฟกต์แนวนอนที่น่าตื่นตาตื่นใจ
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: วิธีเพิ่มการไล่สี – การไล่สีแนวนอนใน Java XPS
url: /th/java/xps-gradient-addition/horizontal/
weight: 11
---

 => "**ทดสอบกับ:** Aspose.Page for Java 24.11"

**Author:** Aspose => "**ผู้เขียน:** Aspose"

Then closing shortcodes.

Make sure to keep blank lines as original.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม Gradient – Horizontal Gradient ใน Java XPS

## คำแนะนำ
ยินดีต้อนรับสู่คู่มือแบบขั้นตอนต่อขั้นตอนเกี่ยวกับ **วิธีเพิ่ม gradient** ในเอกสาร XPS ด้วย Java ในบทเรียนนี้คุณจะได้เรียนรู้วิธีเพิ่ม horizontal gradient, ทำไมมันถึงสำคัญต่อการทำให้ภาพดูสวยงาม, และวิธี **ปรับแต่ง gradient stops** เพื่อควบคุมสีอย่างแม่นยำ Aspose.Page for Java ทำให้การทำงานกับเอกสาร XPS (XML Paper Specification) ง่ายขึ้น, ให้คุณมุ่งเน้นที่การออกแบบแทนการจัดการไฟล์ระดับต่ำ

## คำตอบเร็ว
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java  
- **เวอร์ชัน Java ใดทำงานได้?** Runtime Java 8+ ใดก็ได้  
- **ต้องการไลเซนส์หรือไม่?** ทดลองใช้ฟรีสำหรับการพัฒนา; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถเปลี่ยนทิศทางของ gradient ได้หรือไม่?** ได้ – เพียงปรับจุดเริ่มต้น/สิ้นสุดของ linear brush  
- **สามารถเพิ่มหลาย gradient ได้หรือไม่?** แน่นอน – ทำซ้ำขั้นตอนการสร้าง path ด้วย brush ที่ต่างกัน  

## Horizontal Gradient คืออะไรใน XPS?
Horizontal gradient คือการเปลี่ยนสีอย่างราบรื่นจากซ้ายไปขวาบนรูปทรงหนึ่ง ใน XPS มันถูกแทนด้วย linear gradient brush ที่ทำการอินเตอร์โพเลตระหว่าง **gradient stops** ที่กำหนดไว้ ผลลัพธ์นี้มักใช้สำหรับแบนเนอร์, ปุ่ม, และการเติมพื้นหลัง

## ทำไมต้องใช้ Aspose.Page for Java?
- **รองรับ XPS อย่างเต็มรูปแบบ** – สร้าง, แก้ไข, และเรนเดอร์โดยไม่ต้องใช้เครื่องมือของบุคคลที่สาม  
- **API ที่ง่าย** – วัตถุระดับสูงเช่น `XpsDocument`, `XpsPath`, และ `XpsGradientBrush` ซ่อนความซับซ้อนของ XML  
- **ประสิทธิภาพ** – ปรับให้เหมาะกับเอกสารขนาดใหญ่และการประมวลผลแบบแบตช์  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

1. **สภาพแวดล้อมการพัฒนา Java** – ติดตั้ง JDK ล่าสุดจาก [java.com](https://www.java.com).  
2. **ไลบรารี Aspose.Page for Java** – ดาวน์โหลดไฟล์ JAR จาก [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็น การนำเข้าต่าง ๆ นี้ทำให้คุณเข้าถึงการสร้างเอกสาร, การจัดการ gradient, และเรขาคณิตพื้นฐาน

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
สร้างอินสแตนซ์ `XpsDocument` ใหม่และระบุโฟลเดอร์ที่คุณต้องการบันทึกผลลัพธ์

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 2: สร้าง Horizontal Gradient
กำหนดรายการของ **gradient stops** ที่ควบคุมสีและตำแหน่งของแต่ละจุดเปลี่ยนสี ตัวอย่างด้านล่างสร้าง gradient ที่มีสีสันเหมือนสายรุ้ง

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
- **สี** – ใช้ `doc.createColor(alpha, red, green, blue)` เพื่อตั้งค่า ARGB ใด ๆ  
- **ตำแหน่ง** – อาร์กิวเมนต์ที่สอง (`float` ระหว่าง `0` ถึง `1`) กำหนดว่าจุดหยุดปรากฏที่ไหนบนเส้น gradient ปรับค่าต่าง ๆ เพื่อย้ายสีไปทางซ้ายหรือขวา  

## ขั้นตอนที่ 3: เพิ่ม Path ด้วย Gradient
สร้าง path รูปสี่เหลี่ยม, ใช้การแปลง (transform) หากจำเป็น, แล้วเติมด้วย linear gradient brush brush นี้ใช้สองจุด (`(10,0)` ถึง `(228,0)`) เพื่อสร้างเอฟเฟกต์แนวนอน เนื่องจากค่า Y‑coordinate เหมือนกัน brush นี้ทำหน้าที่เป็น **horizontal gradient brush**

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**เคล็ดลับ:** การใช้รายการ `stops` เดียวกันสำหรับหลาย path สามารถเพิ่มประสิทธิภาพได้, แต่จำไว้ว่าให้เรียก `clear()` ก่อนเพิ่ม stops ใหม่

## ขั้นตอนที่ 4: บันทึกเอกสาร
บันทึกไฟล์ XPS ลงดิสก์ คุณสามารถเปิดไฟล์ด้วยโปรแกรมดู XPS ใดก็ได้เพื่อดู horizontal gradient ที่ทำงาน

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## วิธีใช้หลาย Gradient
หากคุณต้องการ **ใช้หลาย gradient** ภายในเอกสาร XPS เดียวกัน เพียงทำซ้ำขั้นตอน “Create Horizontal Gradient” และ “Add Path with Gradient” สำหรับแต่ละรูปทรงใหม่ ใช้รายการ `XpsGradientStop` ใหม่ (หรือเคลียร์รายการที่มี) และกำหนด `LinearGradientBrush` ใหม่พร้อมจุดเริ่มต้น/สิ้นสุดของมัน วิธีนี้ช่วยให้คุณสามารถซ้อน gradient, สร้างพื้นหลังซับซ้อน, หรือไฮไลท์ UI element ต่าง ๆ ในหน้าเดียวได้

## ทำไมเรื่องนี้สำคัญ – ประโยชน์ของ Horizontal Gradient Brush
- **ความลึกของภาพ:** Horizontal gradient brush เพิ่มความรู้สึกสามมิติอย่างละเอียดโดยไม่ต้องใช้ภาพเพิ่มเติม  
- **ประหยัดขนาดไฟล์:** Gradient ถูกเก็บเป็นคำนิยามเวกเตอร์ ทำให้ไฟล์ XPS มีขนาดเบา  
- **การขยายขนาด:** เนื่องจาก gradient เป็นเวกเตอร์ จึงขยายได้อย่างราบรื่นบนหน้าจอความละเอียดสูง  

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| Gradient ปรากฏเป็นสีเดียว | ไม่ได้เพิ่ม gradient stops หรือ brush ไม่ได้ตั้งค่า | ตรวจสอบให้แน่ใจว่า `path.setFill(...)` ใช้ `LinearGradientBrush` และได้เพิ่ม stops ผ่าน `getGradientStops().addAll(stops)` |
| สีดูจืด | ค่า alpha ไม่ถูกต้อง (พารามิเตอร์แรก) | ใช้ค่า `255` สำหรับสีที่ทึบเต็มที่ หากไม่ต้องการความโปร่งใส |
| ขนาด Path ผิด | ค่าตารางแปลง (transform matrix) ผิด | ปรับค่าพารามิเตอร์ของเมทริกซ์ (`scaleX, skewY, skewX, scaleY, translateX, translateY`) |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้หลาย gradient ในเอกสาร XPS เดียวได้หรือไม่?**  
A: ได้, คุณสามารถเพิ่มหลาย path, แต่ละ path มี gradient brush ของตนเอง เพื่อสร้างการออกแบบแบบหลายชั้นที่ซับซ้อน

**Q: Aspose.Page รองรับเวอร์ชัน Java ล่าสุดหรือไม่?**  
A: Aspose.Page for Java มีการอัปเดตอย่างสม่ำเสมอและทำงานกับ Java 8 และรุ่นใหม่กว่า

**Q: มีประเภท gradient อื่น ๆ ที่ Aspose.Page รองรับหรือไม่?**  
A: นอกจาก linear gradients, Aspose.Page ยังรองรับ radial gradients สำหรับการเปลี่ยนสีแบบวงกลม

**Q: ฉันสามารถปรับแต่งสีและตำแหน่งของ gradient stops ได้หรือไม่?**  
A: แน่นอน! คุณมีการควบคุมเต็มที่ต่อสี ARGB ของแต่ละ stop และตำแหน่งสัมพัทธ์ของมัน (ช่วง 0‑1)

**Q: มีฟอรั่มชุมชนสำหรับ Aspose.Page ที่ฉันสามารถขอความช่วยเหลือได้หรือไม่?**  
A: มี, คุณสามารถเยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและรับความช่วยเหลือ

---

**อัปเดตล่าสุด:** 2026-03-13  
**ทดสอบกับ:** Aspose.Page for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}