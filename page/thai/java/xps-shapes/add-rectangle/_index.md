---
date: 2026-04-24
description: เรียนรู้วิธีตั้งค่าสีสี่เหลี่ยมและเพิ่มสี่เหลี่ยมใน Java XPS ด้วย Aspose.Page
  คู่มือนี้ครอบคลุมการเพิ่มสี่เหลี่ยมใน Java และการเปลี่ยนเส้นขอบสี่เหลี่ยม
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: เพิ่มสี่เหลี่ยมใน Java XPS
second_title: Aspose.Page Java API
title: ตั้งค่าสีสี่เหลี่ยมและเพิ่มสี่เหลี่ยมใน Java XPS
url: /th/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าสีสี่เหลี่ยมและเพิ่มสี่เหลี่ยมใน Java XPS

## บทนำ
ในคู่มือนี้ คุณจะได้เรียนรู้วิธี **ตั้งค่าสีสี่เหลี่ยม** และ **เพิ่มสี่เหลี่ยม** ใน Java XPS ด้วยไลบรารี Aspose.Page ไม่ว่าคุณจะต้องการวาดรูปทรงง่าย ๆ สำหรับรายงานหรือสร้างกราฟิกเวกเตอร์ที่ซับซ้อน การเชี่ยวชาญการจัดรูปแบบสี่เหลี่ยมจะให้การควบคุมที่แม่นยำต่อเอกสาร XPS ของคุณ  

## คำตอบเร็ว
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for Java  
- **ฉันสามารถเปลี่ยนเส้นขอบของสี่เหลี่ยมได้หรือไม่?** ใช่, โดยใช้ `setStroke` และ `setStrokeThickness`  
- **รองรับโปรไฟล์สี CMYK หรือไม่?** แน่นอน – คุณสามารถโหลดโปรไฟล์ ICC ตามที่แสดง  
- **ต้องการใบอนุญาตสำหรับการใช้งานจริงหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานที่ไม่ใช่การประเมินผล  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับสี่เหลี่ยมพื้นฐาน  

## **set rectangle color** คืออะไร?
การตั้งค่าสีของสี่เหลี่ยมหมายถึงการกำหนดสีเติมหรือสีเส้นขอบที่รูปทรงจะถูกเรนเดอร์ในเอกสาร XPS ฉบับสุดท้าย ด้วย Aspose.Page คุณสามารถใช้ RGB, CMYK หรือแม้แต่โปรไฟล์สี ICC ที่กำหนดเองเพื่อให้ได้สีที่ตรงกันอย่างแม่นยำ  

## ทำไมต้องใช้ Aspose.Page เพื่อ **add rectangle java** และ **change rectangle stroke**?
- **Full‑featured API** – รองรับทั้งสีทึบและไล่สี.  
- **Cross‑platform** – ทำงานบน Java runtime ใดก็ได้โดยไม่มีการพึ่งพาเนทีฟ.  
- **Rich geometry support** – สร้างเส้นทางซับซ้อน, ใช้การแปลง, และจัดการความหนาของเส้นขอบได้อย่างง่ายดาย.  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานการเขียนโปรแกรม Java.  
- ไลบรารี Aspose.Page ติดตั้งแล้ว หากยังไม่ได้ติดตั้ง ให้ดาวน์โหลดจาก [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ (IDE, JDK ฯลฯ).  

## นำเข้าแพ็กเกจ
เพื่อเริ่มต้น ให้นำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Page ถูกเพิ่มเข้าไปใน classpath อย่างถูกต้อง นี่คือตัวอย่างพื้นฐาน:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

ต่อไป เราจะอธิบายตัวอย่างที่ให้ไว้เป็นหลายขั้นตอนเพื่อ **add a rectangle** และ **set its color** ใน Java XPS.

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` ด้วยเส้นทางเต็มที่คุณต้องการอ่าน/เขียนไฟล์ XPS.

## ขั้นตอนที่ 2: สร้างเอกสาร XPS ใหม่
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
บรรทัดนี้จะเริ่มต้นเอกสาร XPS ใหม่ที่ใช้เก็บรูปทรงของเรา.

## ขั้นตอนที่ 3: เพิ่มสี่เหลี่ยมที่มีเส้นขอบสี CMYK แบบทึบ
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
ขั้นตอนนี้จะเพิ่ม **stroked rectangle** ที่มีสี CMYK แบบทึบ เมธอด `setStroke` กำหนดสีเส้นขอบของสี่เหลี่ยม, ส่วน `setStrokeThickness` ควบคุมความหนาของเส้น – เหมาะสำหรับ **changing rectangle stroke**.

### เคล็ดลับพิเศษ:
หากคุณต้องการสี RGB ให้แทนที่การเรียก `createColor` ด้วย `doc.createColor(0, 0, 255)` เพื่อเติมสีฟ้าแบบทึบ.

## ขั้นตอนที่ 4: บันทึกเอกสาร XPS ที่ได้
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
สุดท้าย บันทึกเอกสาร XPS ลงดิสก์ ไฟล์ `AddRectangle_out.xps` ตอนนี้มีสี่เหลี่ยมที่คุณกำหนดสีและเส้นขอบแล้ว.

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|----------|
| **สี่เหลี่ยมไม่ปรากฏ** | รูปทรงพาธไม่ถูกต้องหรือความหนาของเส้นขอบตั้งเป็น 0 | ตรวจสอบสตริงพาธ (`"M 20,10 L 220,10 220,100 20,100 Z"`) และให้แน่ใจว่า `setStrokeThickness` มากกว่า 0. |
| **สีไม่ถูกต้อง** | ใช้โปรไฟล์ ICC ที่ไม่ตรงกับพื้นที่สีที่ต้องการ | ใช้ `doc.createColor(r, g, b)` สำหรับ RGB หรือตรวจสอบเส้นทางไฟล์ ICC อีกครั้ง |
| **ไฟล์ไม่ถูกบันทึก** | `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่หรือไม่มีสิทธิ์เขียน | สร้างโฟลเดอร์ล่วงหน้าหรือเลือกตำแหน่งที่สามารถเขียนได้ |

## คำถามที่พบบ่อย

**ถาม:** *ฉันสามารถเพิ่มหลายสี่เหลี่ยมในเอกสาร XPS เดียวได้หรือไม่?*  
ตอบ: ได้. เพียงทำซ้ำขั้นตอนการสร้างรูปทรงและการจัดสไตล์สำหรับแต่ละสี่เหลี่ยมที่ต้องการ.

**ถาม:** *ฉันจะเปลี่ยนสีเติมของสี่เหลี่ยมแทนสีเส้นขอบได้อย่างไร?*  
ตอบ: ใช้ `path.setFill(...)` กับแปรงสีทึบ, คล้ายกับการใช้ `setStroke`.

**ถาม:** *Aspose.Page เหมาะกับการจัดการเอกสาร XPS ที่ซับซ้อนหรือไม่?*  
ตอบ: แน่นอน. ไลบรารีรองรับคุณลักษณะขั้นสูงเช่นไล่สี, การแปลง, และฟอนต์ที่ฝังอยู่.

**ถาม:** *ฉันจะหา ตัวอย่างเพิ่มเติมและการสนับสนุนจากชุมชนได้จากที่ไหน?*  
ตอบ: สำรวจ [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อดูตัวอย่างโค้ดเพิ่มเติมและการช่วยเหลือจากเพื่อนร่วมงาน.

**ถาม:** *ฉันสามารถทดลองใช้ Aspose.Page ก่อนซื้อได้หรือไม่?*  
ตอบ: ได้, คุณสามารถสำรวจ [free trial](https://releases.aspose.com/) เพื่อประเมินความสามารถของ API.

---

**อัปเดตล่าสุด:** 2026-04-24  
**ทดสอบกับ:** Aspose.Page for Java 24.12  
**ผู้เขียน:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}