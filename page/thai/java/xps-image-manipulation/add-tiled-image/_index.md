---
date: 2026-05-30
description: เรียนรู้วิธีสร้างเอกสาร XPS ใน Java ด้วย Aspose.Page และเพิ่มภาพแบบต่อกันอย่างง่ายดายด้วยคู่มือขั้นตอนต่อขั้นตอนนี้.
  วิธีสร้างไฟล์ XPS อย่างรวดเร็ว.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: เพิ่มภาพแบบต่อกันใน Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: วิธีสร้างเอกสาร XPS ด้วยภาพแบบต่อกันใน Java
url: /th/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างเอกสาร XPS ด้วยภาพแบบต่อกันใน Java

## บทนำ
การสร้างเอกสาร XPS ด้วยโปรแกรมเป็นทักษะสำคัญสำหรับนักพัฒนา Java ที่ต้องการผลลัพธ์ที่สามารถพิมพ์ได้และอิสระต่ออุปกรณ์ **How to create XPS** ไฟล์อย่างมีประสิทธิภาพได้รับการตอบโดย Aspose.Page for Java ซึ่งทำให้รายละเอียดระดับต่ำของ XML Paper Specification ถูกซ่อนและให้คุณมุ่งเน้นที่การออกแบบภาพ ในคู่มือนี้คุณจะได้เห็นวิธีสร้างเอกสาร XPS, เพิ่มภาพแบบต่อกันเป็นพื้นหลังหรือแพทเทิร์น, และบันทึกผลลัพธ์—ทั้งหมดด้วยโค้ดที่กระชับและพร้อมใช้งานในผลิตภัณฑ์

## คำตอบสั้น
- **Aspose.Page ทำอะไร?** It provides a high‑level API to generate and manipulate XPS documents in Java.  
- **ฉันสามารถทำภาพต่อกันได้หรือไม่?** Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.  
- **ฉันต้องการใบอนุญาตหรือไม่?** A temporary or commercial license is required for production use.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Any JDK 8+ is compatible.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** Roughly 10–15 minutes for a basic tiled‑image scenario.

## “สร้างเอกสาร XPS” คืออะไร?
`XpsDocument` คืออ็อบเจ็กต์ระดับบนของ Aspose.Page ที่แสดงไฟล์ XPS เดียวในหน่วยความจำ มันบรรจุหน้า, แหล่งข้อมูล, และเมตาดาต้า, ทำให้คุณสามารถสร้างเอกสารได้โดยโปรแกรม การสร้างเอกสาร XPS หมายถึงการสร้างอินสแตนซ์ของคลาสนี้, เพิ่มองค์ประกอบภาพ, และในที่สุดเรียก `save` เพื่อเขียนไฟล์แบบ fixed‑layout ไปยังดิสก์ วิธีนี้ขจัดการจัดการ XML ด้วยตนเองและรับประกันความสอดคล้องกับ XML Paper Specification.

## ทำไมต้องเพิ่มภาพต่อกัน?
การต่อภาพทำให้กราฟิกซ้ำทั่วพื้นที่ที่กำหนด, ซึ่งเหมาะสำหรับพื้นหลัง, ลายน้ำ, หรือการเติมแบบแพทเทิร์น การใช้ `XpsTileMode.Tile` ทำให้ภาพซ้ำโดยอัตโนมัติโดยไม่ต้องทำสำเนาด้วยตนเอง, ช่วยประหยัดเวลาในการพัฒนาและรับประกันการเรนเดอร์ที่สม่ำเสมอบนอุปกรณ์ใดก็ได้ ภาพต่อกันยังช่วยให้ขนาดไฟล์เล็กลงเนื่องจากทรัพยากรบิตแมพเดียวกันถูกใช้ซ้ำแทนการฝังหลายครั้ง.

## ข้อกำหนดเบื้องต้น
Before diving in, make sure you have:

1. **Java Development Kit (JDK)** – ติดตั้ง JDK 8 หรือใหม่กว่า.  
2. **Aspose.Page for Java** – ดาวน์โหลดจาก [website](https://releases.aspose.com/page/java/).  
3. **A writable directory** – ที่ซึ่งไฟล์ XPS ที่สร้างจะถูกบันทึก.

## นำเข้าแพ็กเกจ
In your Java project, import the necessary classes:

`XpsDocument` คืออ็อบเจ็กต์หลักที่แสดงไฟล์ XPS.  
`XpsImageBrush` ใช้ภาพเป็นแหล่งในการทาสีรูปร่าง.  
`XpsTileMode` กำหนดวิธีการต่อภาพ.  
`Rectangle2D` อธิบายพื้นที่สี่เหลี่ยมสำหรับการกำหนดตำแหน่ง.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
Add the Aspose.Page JAR files to your project’s classpath and verify the import statements compile without errors.

### ขั้นตอนที่ 2: สร้างเอกสาร XPS
`XpsDocument` คือคอนเทนเนอร์หลักที่เก็บหน้า, เส้นทาง, และทรัพยากร สร้างอินสแตนซ์ด้วยขนาดหน้าที่ต้องการ, จากนั้นคุณสามารถเริ่มเพิ่มองค์ประกอบกราฟิกได้.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### ขั้นตอนที่ 3: กำหนดเส้นทางของภาพต่อกัน
Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory referenced by `dataDir`. The image will be used as a brush pattern.

### ขั้นตอนที่ 4: เพิ่มภาพต่อกัน
Create a rectangular path and fill it with an `XpsImageBrush`. By setting the tile mode to `Tile`, the image repeats across the rectangle. Adjust the source and destination rectangles to control tile size and positioning.

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
Persist the XPS file to disk. The output file will contain the tiled image you just defined and can be opened with any XPS viewer.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

ทำซ้ำขั้นตอนเหล่านี้เมื่อใดก็ตามที่คุณต้องการ **add tiled image** ไปยังหน้าอื่นหรือรูปทรงอื่นในเอกสาร XPS เดียวกัน.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| ภาพไม่แสดง | Verify the file path (`dataDir + "R08LN_NN.jpg"`) is correct and the image is accessible. |
| แพทเทิร์นต่อภาพดูบิดเบี้ยว | Adjust the source and destination `Rectangle2D` values to control the tile size. |
| ความทึบแสงไม่มีผล | Ensure the brush’s opacity is set **after** the tile mode configuration. |

## คำถามที่พบบ่อย

**Q:** Aspose.Page รองรับเวอร์ชัน Java ทั้งหมดหรือไม่?  
**A:** Aspose.Page รองรับ Java 8 ถึง Java 21; คุณสามารถดูเมทริกซ์ความเข้ากันได้ทั้งหมดได้ที่ [here](https://reference.aspose.com/page/java/).

**Q:** ฉันสามารถใช้ Aspose.Page สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?  
**A:** ใช่, จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์ ตัวเลือกการซื้อสามารถดูได้ที่ [here](https://purchase.aspose.com/buy).

**Q:** มีรุ่นทดลองฟรีหรือไม่?  
**A:** สามารถดาวน์โหลดรุ่นทดลองฟรีที่ทำงานเต็มรูปแบบได้จากหน้า releases ของ Aspose [here](https://releases.aspose.com/).

**Q:** ฉันจะหาแหล่งสนับสนุนจากชุมชนได้จากที่ไหน?  
**A:** เข้าร่วมฟอรั่มชุมชน Aspose.Page ที่ [forum](https://forum.aspose.com/c/page/39) เพื่อถามคำถามและแบ่งปันตัวอย่าง.

**Q:** ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับการประเมินได้อย่างไร?  
**A:** ใบอนุญาตชั่วคราวจะจัดให้ตามคำขอผ่านพอร์ทัลของ Aspose [here](https://purchase.aspose.com/temporary-license/).

## สรุป
ตอนนี้คุณมีเวิร์กโฟลว์ที่ครบถ้วนและพร้อมใช้งานในผลิตภัณฑ์สำหรับ **how to create XPS** เอกสารด้วยภาพต่อกันโดยใช้ Aspose.Page for Java โดยการใช้ `XpsImageBrush` และ `XpsTileMode.Tile` คุณสามารถสร้างกราฟิกที่หลากหลายและสามารถทำซ้ำได้โดยไม่ทำให้ไฟล์ใหญ่ขึ้น ทดลองปรับขนาดการต่อ, ระดับความทึบ, และรูปทรงต่าง ๆ เพื่อสร้างเลย์เอาต์เอกสารที่ซับซ้อน ขั้นตอนต่อไปคือสำรวจการเพิ่มรูปเวกเตอร์หรือข้อความทับเพื่อเพิ่มความสมบูรณ์ให้กับไฟล์ XPS ของคุณ.

---

**อัปเดตล่าสุด:** 2026-05-30  
**ทดสอบด้วย:** Aspose.Page for Java 24.12 (latest)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเพิ่มภาพในเอกสาร XPS ของ Java – คู่มืออย่างง่ายด้วย Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - การเพิ่มหน้าใน XPS คู่มือ](/page/java/xps-page-manipulation/add-page/)
- [แปลง XPS เป็น PDF ใน Java ด้วย Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}