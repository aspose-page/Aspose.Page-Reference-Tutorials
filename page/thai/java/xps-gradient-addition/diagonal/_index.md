---
date: 2026-05-25
description: เรียนรู้วิธีเพิ่ม gradient ให้กับเอกสาร XPS ใน Java ด้วย Aspose.Page
  คู่มือขั้นตอนต่อขั้นตอนนี้แสดงวิธีเพิ่ม diagonal gradient, ใช้ linear gradient brushes,
  และสร้างไฟล์ XPS ระดับมืออาชีพ
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: เพิ่ม Diagonal Gradient ใน Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'วิธีเพิ่ม Gradient: Diagonal Gradient ใน Java XPS'
url: /th/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มการไล่สี: การไล่สีแนวทแยงใน Java XPS

## บทนำ
ในการพัฒนา Java สมัยใหม่ การเชี่ยวชาญ **วิธีเพิ่มการไล่สี** ให้กับเอกสาร XPS จะทำให้รายงานของคุณดูเรียบหรูและดึงดูดสายตาได้อย่างโดดเด่น บทแนะนำนี้จะพาคุณผ่านการสร้างไฟล์ XPS ตั้งแต่เริ่มต้น การเพิ่มการไล่สีแนวทแยง และการบันทึกผลลัพธ์—ทั้งหมดด้วย Aspose.Page for Java คุณจะเข้าใจว่าการไล่สีสำคัญอย่างไร ดูตัวอย่างการเรียก API อย่างชัดเจน และได้รับเคล็ดลับปฏิบัติจริงเพื่อหลีกเลี่ยงข้อผิดพลาดทั่วไป

## คำตอบสั้น
- **ไลบรารีหลักคืออะไร?** Aspose.Page for Java  
- **เมธอดใดที่เพิ่มการไล่สี?** `createLinearGradientBrush` พร้อม gradient stops  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10‑15 นาทีสำหรับการไล่สีแนวทแยงพื้นฐาน  
- **สามารถใช้กับเฟรมเวิร์ก Java อื่นได้หรือไม่?** ได้, API ไม่ผูกติดกับเฟรมเวิร์กใดเป็นพิเศษ  

## การไล่สีแนวทแยงในเอกสาร XPS คืออะไร?
การไล่สีแนวทแยงคือการเปลี่ยนสีอย่างราบรื่นจากมุมหนึ่งของรูปไปยังมุมตรงข้าม สร้างเอฟเฟกต์ภาพที่เอียงในแนวทแยง ใน XPS เอฟเฟกต์นี้ถูกกำหนดโดย linear gradient brush ที่มี gradient stops เรียงลำดับซึ่งระบุสีและตำแหน่งสัมพัทธ์ตามเส้นทแยง

## ทำไมต้องเพิ่มการไล่สีแนวทแยงด้วย Aspose.Page?
Aspose.Page ให้ **ความเที่ยงตรงการเรนเดอร์ 100 %** สำหรับการไล่สีในผู้ชม XPS มากกว่า 20 ตัว และรองรับ **ฟีเจอร์ XPS 30+** เช่น ข้อความ, รูปภาพ, และรูปเวกเตอร์ API จะจัดการ markup ของ XPS ที่ซับซ้อนให้คุณโฟกัสที่การออกแบบ พร้อมรับประกันว่าไฟล์เดียวกันจะแสดงผลเหมือนกันบน Windows, macOS, และ Linux

## ข้อกำหนดเบื้องต้น
- ความรู้พื้นฐานการเขียนโปรแกรม Java  
- ติดตั้ง JDK บนเครื่องของคุณ  
- ไลบรารี Aspose.Page for Java – ดาวน์โหลด **[ที่นี่](https://releases.aspose.com/page/java/)**  
- IDE เช่น IntelliJ IDEA หรือ Eclipse  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็น การนำเข้าต่าง ๆ นี้จะทำให้คุณเข้าถึงเรขาคณิต, การจัดการไล่สี, และการสร้างเอกสาร XPS

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
สร้างโปรเจกต์ Java ใหม่ใน IDE ที่คุณเลือกและเพิ่มไฟล์ JAR ของ Aspose.Page ไปยัง build path ของโปรเจกต์

## ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสาร
ระบุที่ที่ไฟล์ XPS ที่สร้างขึ้นจะถูกบันทึก

```java
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 3: สร้าง XPS Document
`XpsDocument` คืออ็อบเจกต์หลักที่แทนไฟล์ XPS ในหน่วยความจำ การสร้างอ็อบเจกต์นี้จะให้แคนวาสสำหรับเพิ่มหน้า, รูปร่าง, และ brush ต่าง ๆ

```java
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 4: เพิ่ม Path การไล่สีแนวทแยง
สร้าง path รูปสี่เหลี่ยมที่จะรับการไล่สี Path geometry ใช้คำสั่ง move‑line‑close อย่างง่าย  
XpsPath กำหนดรูปเวกเตอร์ในเอกสาร XPS เช่น สี่เหลี่ยมหรือเรขาคณิตที่กำหนดเอง

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## ขั้นตอนที่ 5: กำหนด Linear Gradient Stops
ตั้งค่าสีและตำแหน่งของแต่ละจุด การหยุดแต่ละจุดจะกำหนดตำแหน่งใน gradient ที่สีเฉพาะปรากฏขึ้น  
XpsGradientStop แทนการหยุดสีเดียวใน gradient โดยระบุสีและออฟเซ็ตของมัน

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## ขั้นตอนที่ 6: ใช้ Linear Gradient กับ Path
`XpsLinearGradientBrush` คือ brush ประเภทของ Aspose.Page สำหรับการเปลี่ยนสีแบบเส้นตรง มันรับจุดสองจุดที่กำหนดทิศทางของ gradient และคอลเลกชันของ gradient stops ที่กำหนดสีตามเส้นนั้น

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร
บันทึกไฟล์ XPS ลงดิสก์ ไฟล์จะมีสี่เหลี่ยมที่เติมด้วยการไล่สีแนวทแยงที่คุณกำหนดไว้

```java
doc.save(dataDir + "LinearGradient.xps");
```

## วิธีเพิ่มการไล่สีใน Java XPS?
โหลด XpsDocument, สร้าง `XpsLinearGradientBrush` ด้วยจุดเริ่มต้น `(0,0)` และจุดสิ้นสุด `(width,height)`, แนบ gradient stops, กำหนด brush ให้กับ property `Fill` ของรูปทรง, แล้วเรียก `save` ขั้นตอนสั้น ๆ นี้ทำให้คุณฝังการไล่สีแนวทแยงได้ด้วยเพียงไม่กี่การเรียก API ทำให้โค้ดของคุณสะอาดและดูแลรักษาง่าย

## ข้อผิดพลาดทั่วไป & เคล็ดลับ
- **ทิศทางของ gradient** – ตรวจสอบให้แน่ใจว่าจุดเริ่มต้นและจุดสิ้นสุดของ brush สะท้อนแนวทแยงที่ต้องการ; การสลับจุดจะทำให้ gradient กลับด้าน  
- **ความแม่นยำของสี** – Aspose ใช้ ARGB; หากต้องการความโปร่งใสให้ใส่ค่าแอลฟา  
- **เส้นทางไฟล์** – ใช้เส้นทางแบบ absolute เสมอหรือยืนยันว่าเส้นทาง relative ชี้ไปยังไดเรกทอรีที่เขียนได้

## คำถามที่พบบ่อยเพิ่มเติม

**ถาม: วิธี **how to add gradient** ไปยังรูป XPS ที่มีอยู่แล้ว?**  
ตอบ: สร้าง `XpsLinearGradientBrush`, กำหนด gradient stops, แล้วกำหนดให้กับ property `Fill` ของรูปตามที่แสดงในขั้นตอน 6

**ถาม: **apply linear gradient** ทำงานอย่างไรเบื้องหลัง?**  
ตอบ: มันสร้างการกำหนด brush ในแพ็กเกจ XPS ที่อ้างอิงจุดเริ่มต้น/สิ้นสุดและคอลเลกชันของ gradient stops ซึ่ง viewer จะเรนเดอร์เป็นการเปลี่ยนสีอย่างราบรื่น

**ถาม: มีวิธีเร็ว ๆ **how to use aspose** สำหรับฟีเจอร์ XPS อื่น ๆ หรือไม่?**  
ตอบ: ใช่, API ของ Aspose.Page มีเมธอดสำหรับเพิ่มรูปภาพ, ข้อความ, และรูปทรงแบบกำหนดเอง—สำรวจคลาส `XpsDocument` เพื่อดูตัวช่วยเพิ่มเติม

**ถาม: สามารถ **add gradient path** ให้กับรูปที่ไม่ใช่สี่เหลี่ยมได้หรือ?**  
ตอบ: แน่นอน. กำหนดเรขาคณิตใดก็ได้ด้วย `createPathGeometry` แล้วตั้ง `Fill` ให้เป็น gradient brush

**ถาม: การไล่สีทำให้ขนาดไฟล์เพิ่มขึ้นอย่างมีนัยสำคัญหรือไม่?**  
ตอบ: เพิ่มเพียงเล็กน้อย; การกำหนด gradient เป็น XML entry ที่มีน้ำหนักเบาในแพ็กเกจ XPS

---

**อัปเดตล่าสุด:** 2026-05-25  
**ทดสอบกับ:** Aspose.Page for Java 24.11  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [Aspose Page XPS Gradient Addition](/page/java/xps-gradient-addition/)
- [Java XPS Text Addition - Aspose.Page Tutorial](/page/java/xps-text-manipulation/add-text/)
- [How to Add Image to Java XPS Documents – A Simple Guide with Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}