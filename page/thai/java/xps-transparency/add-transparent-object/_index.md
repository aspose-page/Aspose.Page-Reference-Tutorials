---
date: 2026-01-02
description: เรียนรู้วิธีเพิ่มความโปร่งใสให้กับเอกสาร Java XPS ด้วย Aspose.Page ปฏิบัติตามคู่มือขั้นตอนโดยละเอียดของเราเพื่อเพิ่มวัตถุที่โปร่งใสพร้อมเอฟเฟกต์ภาพที่น่าทึ่ง
linktitle: Add Transparent Object in Java XPS
second_title: Aspose.Page Java API
title: วิธีเพิ่มความโปร่งใสให้กับเอกสาร XPS ของ Java
url: /th/java/xps-transparency/add-transparent-object/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มความโปร่งใสให้กับเอกสาร Java XPS

## บทนำ
หากคุณกำลังมองหา **วิธีเพิ่มความโปร่งใส** ให้กับเอกสาร Java XPS ของคุณและต้องการให้ดูทันสมัยและมีลักษณะเป็นชั้น ๆ Aspose.Page for Java ทำให้กระบวนการง่ายขึ้น ในบทเรียนนี้เราจะอธิบายทุกอย่างที่คุณต้องการ ตั้งแต่การตั้งค่าสภาพแวดล้อม การสร้างเส้นทางโปร่งใส การจัดการความทึบแสง และสุดท้ายการบันทึกผลลัพธ์ เมื่อเสร็จคุณจะสามารถเพิ่มความโปร่งใสให้กับวัตถุ XPS ใด ๆ ได้อย่างมั่นใจ

## คำตอบด่วน
- **ต้องการไลบรารีอะไร?** Aspose.Page for Java  
- **ฉันสามารถควบคุมความทึบแสงโดยโปรแกรมได้หรือไม่?** Yes, via the `setOpacity` method on a brush.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** A commercial license is required for non‑evaluation use.  
- **รองรับเวอร์ชัน Java ใด?** Java 8 and later.  
- **ผลลัพธ์เข้ากันได้กับโปรแกรมดู XPS มาตรฐานหรือไม่?** Absolutely—standard viewers render the transparency correctly.

## ความโปร่งใสใน XPS คืออะไร?
ความโปร่งใสทำให้คุณสามารถเรนเดอร์วัตถุด้วยความทึบแสงที่แตกต่างกัน ทำให้ส่วนพื้นหลังมองเห็นผ่านได้ เอฟเฟกต์นี้มีประโยชน์สำหรับลายน้ำ กราฟิกซ้อนทับ หรือการออกแบบใด ๆ ที่การจัดชั้นภาพช่วยเพิ่มความอ่านง่าย

## ทำไมต้องใช้ Aspose.Page สำหรับการเพิ่มความโปร่งใส?
- **การควบคุมเต็มรูปแบบ** over geometry, brushes, and transforms.  
- **ไม่มีการพึ่งพาภายนอก**—everything is handled inside the API.  
- **รองรับหลายแพลตฟอร์ม** support, so the same code works on Windows, Linux, and macOS.  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มลงลึก โปรดตรวจสอบว่าคุณมี:

- สภาพแวดล้อมการพัฒนา Java (JDK 8+).  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการ [here](https://releases.aspose.com/page/java/).

## นำเข้าแพ็กเกจ
ในโครงการ Java ของคุณ ให้นำเข้าแพ็กเกจ Aspose.Page ที่จำเป็นเพื่อเริ่มต้นการเพิ่มวัตถุโปร่งใส รวมบรรทัดต่อไปนี้ไว้ที่ส่วนต้นของไฟล์ Java ของคุณ:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.Color;
```

ตอนนี้ เราจะทำการแยกโค้ดตัวอย่างออกเป็นหลายขั้นตอน.

## ขั้นตอนที่ 1: เริ่มต้นเอกสาร
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize document
XpsDocument doc = new XpsDocument();
```
เริ่มต้นโดยการตั้งค่าเอกสารของคุณและระบุไดเรกทอรีที่ไฟล์ XPS ของคุณจะถูกบันทึก

## ขั้นตอนที่ 2: สร้างวัตถุโปร่งใส
```java
// Just to demonstrate transparency
doc.addPath(doc.createPathGeometry("M120,0 H400 v1000 H120")).setFill(doc.createSolidColorBrush(Color.GRAY));
doc.addPath(doc.createPathGeometry("M300,120 h600 V420 h-600")).setFill(doc.createSolidColorBrush(Color.GRAY));
```
ที่นี่ เราจะสร้างเส้นทางสีเทาสองเส้นที่จะทำหน้าที่เป็นพื้นหลังสำหรับรูปร่างโปร่งใสที่เราจะเพิ่มในภายหลัง

## ขั้นตอนที่ 3: เพิ่มเส้นทางที่เติมสี
```java
// Create path with closed rectangle geometry
XpsPath path1 = doc.createPath(doc.createPathGeometry("M20,20 h200 v200 h-200 z"));
// Set blue solid brush to fill path1
path1.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add it to the current page
XpsPath path2 = doc.add(path1);
```
ในขั้นตอนนี้ เราจะสร้างสี่เหลี่ยมสีฟ้าแบบทึบและวางไว้บนหน้า สี่เหลี่ยมนี้จะถูกทับด้วยรูปร่างโปร่งใสในภายหลังเพื่อแสดงผล

## ขั้นตอนที่ 4: จัดการความโปร่งใส
```java
// path1 and path2 are the same as long as path1 hasn't been placed inside any other element
path2.setFill(doc.createSolidColorBrush(Color.GREEN));
// Now add path2 once again. Now path2 has a parent, so path3 won't be the same as path2.
XpsPath path3 = doc.add(path2);
path3.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 0, 300));
path3.setFill(doc.createSolidColorBrush(Color.RED));
```
ที่นี่ เราเปลี่ยนสีเติมของเส้นทางที่ทำสำเนาและใช้การแปลงการย้ายตำแหน่ง (translation transform) ซึ่งจะแสดงให้เห็นว่าความโปร่งใสทำงานอย่างไรเมื่อวัตถุแชร์องค์ประกอบพาเรนต์เดียวกัน

## ขั้นตอนที่ 5: ทำสำเนาและแก้ไขเส้นทาง
```java
// Create new path4 with path2's geometry
XpsPath path4 = doc.addPath(path2.getData());
path4.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 300, 0));
path4.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add path4 once again.
XpsPath path5 = doc.add(path4);
path5.setRenderTransform(path5.getRenderTransform().deepClone());
path5.getRenderTransform().translate(0, 300);
path5.getFill().setOpacity(0.8f);
```
เราคลอนเส้นทางที่มีอยู่แล้ว ย้ายตำแหน่ง และปรับความทึบแสงเป็น 0.8 (ทึบ 80 %) ขั้นตอนนี้แสดงให้เห็นว่าคุณสามารถใช้เรขาคณิตซ้ำได้พร้อมปรับความโปร่งใสสำหรับแต่ละอินสแตนซ์

## ขั้นตอนที่ 6: บันทึกเอกสาร
```java
// Save the modified document
doc.save(dataDir + "WorkingWithTransparency_out.xps");
```
สุดท้าย เราบันทึกไฟล์ XPS เปิดไฟล์ที่ได้ในโปรแกรมดู XPS ใด ๆ เพื่อดูความโปร่งใสแบบหลายชั้นทำงาน

## ปัญหาทั่วไป & เคล็ดลับ
- **ความทึบแสงไม่แสดง?** ตรวจสอบว่าคุณใช้ brush ที่รองรับความทึบแสง (เช่น `createSolidColorBrush`).  
- **การแปลงไม่ทำงาน?** ตรวจสอบว่าคุณเรียก `setRenderTransform` **ก่อน** เพิ่มเส้นทางลงในเอกสาร.  
- **เคล็ดลับด้านประสิทธิภาพ:** ใช้วัตถุ geometry ซ้ำเมื่อสร้างรูปทรงที่คล้ายกันหลาย ๆ รูปเพื่อ ลดการใช้หน่วยความจำ.

## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ความโปร่งใสกับรูปทรงอื่น ๆ นอกจากสี่เหลี่ยมได้หรือไม่?
ตอบ: ใช่ คุณสามารถใช้ความโปร่งใสกับรูปทรงต่าง ๆ ได้โดยใช้เรขาคณิตที่ให้มา.

### ถาม: ฉันจะควบคุมระดับความโปร่งใสของวัตถุได้อย่างไร?
ตอบ: ปรับคุณสมบัติ opacity ของการเติมสีเพื่อควบคุมระดับความโปร่งใส.

### ถาม: Aspose.Page เหมาะสำหรับการสร้างเอกสารระดับมืออาชีพหรือไม่?
ตอบ: แน่นอน! Aspose.Page มีฟีเจอร์ที่แข็งแกร่งสำหรับการจัดการเอกสารระดับมืออาชีพ.

### ถาม: ฉันสามารถรวม Aspose.Page กับไลบรารี Java อื่นได้หรือไม่?
ตอบ: ใช่ Aspose.Page สามารถรวมเข้ากับไลบรารี Java อื่นได้อย่างราบรื่นเพื่อเพิ่มฟังก์ชันการทำงาน.

### ถาม: ฉันจะหา ตัวอย่างเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Page ได้จากที่ไหน?
ตอบ: เยี่ยมชม [Aspose.Page Java Forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชนและสำรวจเอกสารเพิ่มเติม [here](https://reference.aspose.com/page/java/).

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}