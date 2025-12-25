---
date: 2025-12-25
description: เรียนรู้วิธีเพิ่มไล่สีแนวตั้งใน Java XPS ด้วย Aspose.Page. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อเพิ่มความสวยงามให้กับเอกสารของคุณ.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: วิธีเพิ่มไล่สีแนวตั้งใน Java XPS
url: /th/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มการไล่สีแนวตั้งใน Java XPS

## บทนำ
ในบทเรียนนี้คุณจะได้ค้นพบ **วิธีเพิ่มการไล่สีแนวตั้ง** ให้กับเอกสาร XPS เมื่อทำงานกับ Java การใช้การไล่สีแนวตั้งสามารถปรับปรุงผลกระทบด้านภาพของรายงาน ใบแจ้งหนี้ หรือเนื้อหาที่พิมพ์ได้อย่างมาก เราจะเดินผ่านแต่ละขั้นตอน ตั้งแต่การตั้งค่าโครงการจนถึงการบันทึกไฟล์ XPS สุดท้าย โดยใช้ไลบรารี Aspose.Page for Java ที่มีประสิทธิภาพ

## คำตอบสั้น
- **การไล่สีแนวตั้งทำอะไร?** มันสร้างการเปลี่ยนสีอย่างราบรื่นจากบนลงล่างของรูปทรง.  
- **ต้องใช้ไลบรารีใด?** Aspose.Page for Java (ดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการ).  
- **ต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **รองรับ Java 8+ หรือไม่?** ใช่, API รองรับ Java 8 และเวอร์ชันต่อไป.  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ปกติใช้เวลาน้อยกว่า 10 นาทีหลังจากตั้งค่าสภาพแวดล้อมเรียบร้อย.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- สภาพแวดล้อมการพัฒนา Java ที่ทำงานได้ (JDK 8 หรือใหม่กว่า).  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/java/).  
- ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการเขียนโปรแกรม Java.  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นสำหรับโครงการ Java ของคุณ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Page for Java ถูกเพิ่มเข้าไปใน classpath ของโครงการ.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## ขั้นตอนที่ 1: เริ่มต้นเอกสาร
เริ่มต้นด้วยการสร้างเอกสาร XPS ใหม่ วัตถุนี้จะเก็บองค์ประกอบการวาดทั้งหมดที่คุณจะเพิ่มในภายหลัง.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 2: สร้าง Path พร้อมการไล่สีแนวตั้ง
ต่อไป กำหนดเส้นทางสี่เหลี่ยมและใช้การไล่สีเชิงเส้นแนวตั้ง จุดหยุดของการไล่สีกำหนดสีและตำแหน่งของมันตามแกนแนวตั้ง.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## ขั้นตอนที่ 3: บันทึกเอกสาร
สุดท้าย เขียนไฟล์ XPS ไปยังดิสก์ ไฟล์ที่ได้จะมีสี่เหลี่ยมที่เติมด้วยการไล่สีแนวตั้งที่คุณกำหนด.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

ยินดีด้วย! คุณได้เรียนรู้ **วิธีเพิ่มการไล่สีแนวตั้ง** ให้กับเอกสาร Java XPS ด้วย Aspose.Page อย่างสำเร็จ.

## ทำไมต้องใช้การไล่สีแนวตั้ง?
- **เพิ่มความสวยงาม:** การไล่สีเพิ่มความลึกและลุคโมเดิร์นให้กับรูปทรงคงที่.  
- **ความสอดคล้องของแบรนด์:** ทำให้สีขององค์กรสอดคล้องอย่างราบรื่นในทุกหน้า.  
- **ปรับแต่งง่าย:** เปลี่ยนสีหรือจุดหยุดได้โดยไม่ต้องออกแบบกราฟิกใหม่.

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **การไล่สีไม่แสดง:** ตรวจสอบว่าจุดเริ่มต้นและจุดสิ้นสุดของ `LinearGradientBrush` ถูกตั้งค่าอย่างถูกต้องสำหรับการวางแนวตั้ง.  
- **ไฟล์ไม่ถูกบันทึก:** ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่สามารถเขียนได้และคุณมีสิทธิ์เขียนไฟล์.  
- **ไม่พบไลบรารี:** ตรวจสอบอีกครั้งว่า JAR ของ Aspose.Page ถูกใส่ในเส้นทางการสร้างของโครงการ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Page for Java ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ใช่, Aspose.Page for Java มีให้ใช้เชิงพาณิชย์ คุณสามารถซื้อได้ที่ [here](https://purchase.aspose.com/buy).

**Q: มีเวอร์ชันทดลองฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
A: มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีได้ที่ [here](https://releases.aspose.com/).

**Q: จะหาเอกสารประกอบสำหรับ Aspose.Page for Java ได้จากที่ไหน?**  
A: เอกสารประกอบมีให้ที่ [here](https://reference.aspose.com/page/java/).

**Q: จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: รับไลเซนส์ชั่วคราวได้ที่ [here](https://purchase.aspose.com/temporary-license/).

**Q: ต้องการความช่วยเหลือหรือมีคำถาม?**  
A: เยี่ยมชมฟอรั่มชุมชน Aspose.Page ที่ [forum](https://forum.aspose.com/c/page/39).

---

**อัปเดตล่าสุด:** 2025-12-25  
**ทดสอบด้วย:** Aspose.Page for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}