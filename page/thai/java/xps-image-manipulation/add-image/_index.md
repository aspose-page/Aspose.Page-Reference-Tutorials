---
date: 2025-12-28
description: เรียนรู้วิธีเพิ่มรูปภาพลงในเอกสาร XPS ด้วย Java โดยใช้ Aspose.Page คู่มือแบบขั้นตอนนี้จะแสดงให้คุณเห็นวิธีเพิ่มรูปภาพอย่างง่ายดายและปรับปรุงการประมวลผลเอกสารของคุณ
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: วิธีเพิ่มรูปภาพในเอกสาร XPS ของ Java – คู่มือแบบง่ายด้วย Aspose.Page
url: /th/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มรูปภาพในเอกสาร Java XPS ด้วย Aspose.Page

การเพิ่มรูปภาพลงในไฟล์ XPS เป็นความต้องการทั่วไปสำหรับนักพัฒนา Java ที่ต้องการเสริมความสมบูรณ์ให้กับรายงาน ใบแจ้งหนี้ หรือเอกสารภาพใด ๆ ในบทเรียนนี้คุณจะได้ค้นพบ **วิธีเพิ่มรูปภาพ** ลงในเอกสาร XPS ด้วยไลบรารี Aspose.Page for Java ที่ทรงพลัง เราจะเดินผ่านแต่ละขั้นตอน อธิบายว่าทำไมบรรทัดแต่ละบรรทัดถึงสำคัญ และให้เคล็ดลับเพื่อหลีกเลี่ยงข้อผิดพลาดทั่วไป

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.Page for Java  
- **ฉันสามารถเพิ่มหลายรูปภาพได้หรือไม่?** ใช่ – ทำซ้ำขั้นตอนการเพิ่มรูปภาพสำหรับแต่ละรูป  
- **รูปแบบภาพที่รองรับ?** TIFF, JPEG, PNG, GIF (และรูปแบบอื่นที่ .NET รองรับ)  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **เวลาในการทำงานโดยทั่วไป?** ประมาณ 10‑15 นาทีสำหรับการแทรกรูปภาพพื้นฐาน

## บทนำ
การเพิ่มรูปภาพลงในเอกสาร XPS เป็นความต้องการทั่วไปในหลายแอปพลิเคชัน Java ตั้งแต่การสร้างรายงานจนถึงการประมวลผลเอกสาร Aspose.Page for Java ทำให้ภารกิจนี้ง่ายขึ้น ด้วยเมธอดที่มีประสิทธิภาพในการผสานรูปภาพเข้ากับไฟล์ XPS ของคุณ ในบทเรียนนี้เราจะสาธิตวิธีเพิ่มรูปภาพลงในเอกสาร XPS ด้วย Aspose.Page for Java

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มบทเรียน โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
1. **Aspose.Page for Java Library** – ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page for Java จาก [website](https://releases.aspose.com/page/java/)  
2. **Java Development Environment** – ตรวจสอบว่าคุณมีสภาพแวดล้อมการพัฒนา Java ตั้งค่าไว้บนเครื่องของคุณแล้ว  

ตอนนี้เรามาไปยังขั้นตอนต่อไปกัน

## นำเข้าแพ็กเกจ
ในโครงการ Java ของคุณ ให้นำเข้าแพ็กเกจ Aspose.Page for Java ที่จำเป็นเพื่อเข้าถึงคลาสและเมธอดที่ต้องการ

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดพาธไปยังไดเรกทอรีเอกสารของคุณ ซึ่งเป็นที่เก็บไฟล์ XPS และไฟล์รูปภาพ

```java
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างเอกสาร XPS ใหม่
สร้างเอกสาร XPS ใหม่โดยใช้โค้ดตัวอย่างต่อไปนี้

```java
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 3: เพิ่มรูปภาพในเอกสาร XPS
เพื่อเพิ่มรูปภาพ ให้สร้างพาธในเอกสาร XPS และตั้งค่า image brush ด้วยไฟล์รูปภาพและพิกัดที่ระบุ

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## ขั้นตอนที่ 4: บันทึกเอกสาร XPS ที่ได้ผลลัพธ์
บันทึกเอกสาร XPS ที่แก้ไขแล้วไปยังไดเรกทอรีที่คุณระบุ

```java
doc.save(dataDir + "AddImage_out.xps");
```

ทำซ้ำขั้นตอนเหล่านี้เพื่อเพิ่มรูปภาพเพิ่มเติมหรือปรับแต่งรูปภาพที่มีอยู่ตามความต้องการของโครงการของคุณ

## สรุป
ขอแสดงความยินดี! คุณได้เรียนรู้ **วิธีเพิ่มรูปภาพ** ลงในเอกสาร XPS ด้วย Aspose.Page for Java อย่างสำเร็จ ทักษะนี้มีคุณค่าอย่างยิ่งสำหรับการเพิ่มความสวยงามให้กับแอปพลิเคชันและเอกสาร Java ของคุณ

### คำถามที่พบบ่อย
### ฉันสามารถเพิ่มหลายรูปภาพในเอกสาร XPS เดียวกันโดยใช้ Aspose.Page for Java ได้หรือไม่?
ใช่ คุณสามารถเพิ่มหลายรูปภาพโดยทำซ้ำขั้นตอนที่อธิบายไว้ในบทเรียนนี้สำหรับแต่ละรูป

### รูปแบบภาพใดบ้างที่ Aspose.Page for Java รองรับ?
Aspose.Page for Java รองรับรูปแบบภาพต่าง ๆ รวมถึง TIFF, JPEG, PNG, และ GIF

### มีเวอร์ชันทดลองของ Aspose.Page for Java หรือไม่?
ใช่ คุณสามารถรับเวอร์ชันทดลองฟรีของ Aspose.Page for Java จาก [this link](https://releases.aspose.com/)

### ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
คุณสามารถขอรับไลเซนส์ชั่วคราวได้จาก [this link](https://purchase.aspose.com/temporary-license/)

### ฉันจะหาแหล่งสนับสนุนเพิ่มเติมหรือหารือเกี่ยวกับปัญหา Aspose.Page for Java ได้ที่ไหน?
เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อขอความช่วยเหลือ แบ่งปันประสบการณ์ และเชื่อมต่อกับชุมชน Aspose.Page

## เคล็ดลับเพิ่มเติม & ข้อผิดพลาดทั่วไป
- **Path Geometry Accuracy** – ตรวจสอบให้แน่ใจว่า 문자열พาธแบบ SVG ตรงกับขนาดของรูปภาพของคุณ; หากไม่ตรงรูปภาพอาจถูกยืดหรือถูกตัด  
- **Image Brush Scaling** – เมธอด `createImageBrush` รับสี่เหลี่ยมต้นฉบับและปลายทาง; การปรับค่าต่าง ๆ จะช่วยควบคุมตำแหน่งและการสเกลได้อย่างแม่นยำ  
- **License Activation** – หากคุณรันโค้ดโดยไม่มีไลเซนส์ที่ถูกต้อง Aspose จะใส่ลายน้ำลงในไฟล์ XPS ที่สร้างขึ้น  

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}