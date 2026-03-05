---
date: 2025-12-28
description: เรียนรู้วิธีสร้างเอกสาร XPS ใน Java ด้วย Aspose.Page และเพิ่มภาพแบบต่อกระเบื้องอย่างง่ายดายด้วยคู่มือขั้นตอนต่อขั้นตอนนี้.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: วิธีสร้างเอกสาร XPS ด้วยภาพแบบต่อกระเบื้องใน Java
url: /th/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร XPS และเพิ่มภาพแบบต่อกันใน Java

## บทนำ
ในการพัฒนา Java สมัยใหม่ ความสามารถในการ **สร้างไฟล์เอกสาร XPS** ด้วยโปรแกรมเป็นทักษะที่มีคุณค่า โดยเฉพาะเมื่อคุณต้องการเพิ่มกราฟิกเช่นภาพแบบต่อกัน Aspose.Page for Java ทำให้กระบวนการนี้ง่ายขึ้น ช่วยให้คุณมุ่งเน้นที่การออกแบบภาพแทนการจัดการไฟล์ระดับล่าง ในบทเรียนนี้คุณจะได้เรียนรู้วิธีสร้างเอกสาร XPS, **เพิ่มภาพแบบต่อกัน**, และบันทึกผลลัพธ์ พร้อมตัวอย่างโค้ดที่ชัดเจนเป็นขั้นตอน

## คำตอบสั้น
- **Aspose.Page ทำอะไร?** ให้ API ระดับสูงสำหรับสร้างและจัดการเอกสาร XPS ใน Java  
- **ฉันสามารถทำภาพต่อกันได้หรือไม่?** ได้ – ใช้ `XpsImageBrush` กับ `XpsTileMode.Tile`  
- **ต้องมีลิขสิทธิ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ชั่วคราวหรือเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  
- **รองรับเวอร์ชัน Java ใด?** รองรับ JDK 8 ขึ้นไปทั้งหมด  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10–15 นาทีสำหรับสถานการณ์พื้นฐานของภาพต่อกัน

## “สร้างเอกสาร XPS” คืออะไร?
ไฟล์ XPS (XML Paper Specification) เป็นรูปแบบเอกสารแบบจัดวางคงที่ที่คล้ายกับ PDF การสร้างเอกสาร XPS ด้วยโปรแกรมทำให้คุณสามารถสร้างไฟล์ที่พิมพ์ได้และอิสระต่ออุปกรณ์โดยตรงจากโค้ด Java

## ทำไมต้องเพิ่มภาพแบบต่อกัน?
การต่อภาพทำให้กราฟิกซ้ำทั่วพื้นที่ที่กำหนด ซึ่งเหมาะสำหรับพื้นหลัง, ลายน้ำ, หรือการเติมลวดลาย ด้วย `XpsTileMode.Tile` ของ Aspose.Page คุณสามารถทำได้ด้วยไม่กี่บรรทัดของโค้ด

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมี:

1. **Java Development Kit (JDK)** – ติดตั้ง JDK 8 หรือใหม่กว่า  
2. **Aspose.Page for Java** – ดาวน์โหลดจาก [เว็บไซต์](https://releases.aspose.com/page/java/)  
3. **ไดเรกทอรีที่สามารถเขียนได้** – ที่จะบันทึกไฟล์ XPS ที่สร้างขึ้น

## นำเข้าแพ็กเกจ
ในโครงการ Java ของคุณ ให้นำเข้าคลาสที่จำเป็น:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เพิ่มไฟล์ JAR ของ Aspose.Page ไปยัง classpath ของโครงการและตรวจสอบให้แน่ใจว่าคำสั่ง import คอมไพล์โดยไม่มีข้อผิดพลาด

### ขั้นตอนที่ 2: สร้างเอกสาร XPS
สร้างอ็อบเจ็กต์ `XpsDocument` ใหม่ ซึ่งเป็นคอนเทนเนอร์หลักที่เก็บหน้าต่าง ๆ, เส้นทาง, และทรัพยากรทั้งหมด

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### ขั้นตอนที่ 3: กำหนดเส้นทางของภาพที่ต้องการต่อกัน
วางภาพที่คุณต้องการต่อกัน (เช่น `R08LN_NN.jpg`) ไว้ในไดเรกทอรีที่อ้างอิงโดย `dataDir` ภาพนี้จะถูกใช้เป็นรูปแบบของ brush

### ขั้นตอนที่ 4: เพิ่มภาพแบบต่อกัน
สร้างเส้นทางสี่เหลี่ยมและเติมด้วย `XpsImageBrush` โดยตั้งค่า tile mode เป็น `Tile` เพื่อให้ภาพซ้ำทั่วสี่เหลี่ยม

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### ขั้นตอนที่ 5: บันทึกเอกสาร
บันทึกไฟล์ XPS ลงดิสก์ ไฟล์ผลลัพธ์จะมีภาพแบบต่อกันที่คุณกำหนดไว้

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

ทำซ้ำขั้นตอนเหล่านี้เมื่อใดก็ตามที่คุณต้องการ **เพิ่มภาพแบบต่อกัน** ไปยังหน้าอื่นหรือรูปทรงอื่นภายในเอกสาร XPS เดียวกัน

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| ภาพไม่แสดง | ตรวจสอบว่าเส้นทางไฟล์ (`dataDir + "R08LN_NN.jpg"`) ถูกต้องและภาพสามารถเข้าถึงได้ |
| ลวดลายต่อกันบิดเบี้ยว | ปรับค่า `Rectangle2D` ของแหล่งและปลายทางเพื่อควบคุมขนาดของลวดลาย |
| ความโปร่งใสไม่มีผล | ตรวจสอบให้แน่ใจว่าการตั้งค่าความโปร่งใสของ brush ทำ **หลัง** การกำหนดค่า tile mode |

## คำถามที่พบบ่อย

### Aspose.Page รองรับทุกเวอร์ชันของ Java หรือไม่?
Aspose.Page ถูกออกแบบให้ทำงานกับหลายเวอร์ชันของ Java ตรวจสอบความเข้ากันได้ได้จากเอกสาร [ที่นี่](https://reference.aspose.com/page/java/)

### สามารถใช้ Aspose.Page ในโครงการเชิงพาณิชย์ได้หรือไม่?
ได้, Aspose.Page มีลิขสิทธิ์เชิงพาณิชย์ สามารถซื้อได้ [ที่นี่](https://purchase.aspose.com/buy)

### มีรุ่นทดลองฟรีหรือไม่?
มี, ทดลองใช้คุณสมบัติของ Aspose.Page ได้ฟรี [ที่นี่](https://releases.aspose.com/)

### จะหาแหล่งสนับสนุนและการสนทนาชุมชนได้จากที่ไหน?
เข้าร่วมชุมชน Aspose.Page ได้ที่ [ฟอรั่ม](https://forum.aspose.com/c/page/39)

### จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page ได้อย่างไร?
ขอรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

---

**อัปเดตล่าสุด:** 2025-12-28  
**ทดสอบกับ:** Aspose.Page for Java 24.12 (ล่าสุด)  
**ผู้เขียน:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
