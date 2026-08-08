---
date: 2026-04-30
description: เรียนรู้วิธีสร้างเอกสาร XPS ด้วย Java และเพิ่มมาสก์ความโปร่งใสโดยใช้
  Aspose.Page Java คู่มือแบบขั้นตอนพร้อมตัวอย่างโค้ด
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: ตั้งค่า มาสก์ความทึบแสงใน Java XPS
second_title: Aspose.Page Java API
title: สร้างเอกสาร XPS ด้วย Java – ตั้งค่า Opacity Mask ด้วย Aspose.Page
url: /th/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่า Opacity Mask ใน Java XPS ด้วย Aspose.Page Java

## บทนำ
ในบทแนะนำนี้คุณจะ **create XPS document Java** ไฟล์และเรียนรู้วิธีการใช้ opacity mask ที่ทำให้กราฟิกของคุณดูเรียบหรูและกึ่ง‑โปร่งใส เราจะเดินผ่านกระบวนการทั้งหมด—ตั้งแต่การเริ่มต้นเอกสาร XPS, การเพิ่ม canvas, การวาดสี่เหลี่ยม, จนถึงการแนบ opacity mask ที่มาจากภาพ—โดยใช้ Aspose.Page Java API ที่ใช้งานง่าย เมื่อเสร็จคุณจะสามารถสร้างไฟล์ XPS ระดับมืออาชีพโดยอัตโนมัติและนำ mask ไปใช้ซ้ำกับรูปทรงใดก็ได้ที่ต้องการ

## คำตอบอย่างรวดเร็ว
- **Opacity mask ทำหน้าที่อะไร?** มันกำหนดระดับความโปร่งใสที่แตกต่างกันสำหรับรูปทรงหนึ่ง ๆ ทำให้เนื้อหาที่อยู่ด้านล่างสามารถมองเห็นได้.  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java (aspose page java).  
- **ต้องการลิขสิทธิ์หรือไม่?** ลิขสิทธิ์ชั่วคราวใช้ได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง.  
- **ต้องใช้โค้ดกี่บรรทัด?** ประมาณ 20 บรรทัดของ Java พร้อมกับคำสั่งตั้งค่าเล็กน้อย.  
- **สามารถใช้ mask ซ้ำกับหลายรูปทรงได้หรือไม่?** ใช่, คุณสามารถกำหนด `ImageBrush` เดียวกันให้กับหลาย path.

## Opacity Mask คืออะไรใน XPS?
Opacity mask คือภาพบิตแมพหรือเวกเตอร์ที่ควบคุมค่าอัลฟา (ความโปร่งใส) ของแต่ละพิกเซลในรูปทรง เมื่อใช้กับสี่เหลี่ยมส่วนต่าง ๆ ของสี่เหลี่ยมจะกลายเป็นทึบเต็ม, กึ่งโปร่งใส, หรือโปร่งใสเต็ม ทำให้เกิดเอฟเฟกต์ภาพที่ซับซ้อนโดยไม่ต้องใช้เลเยอร์การวาดเพิ่มเติม

## ทำไมต้องใช้ Aspose.Page Java เพื่อ **create XPS document java**?
- **Pure Java API** – ไม่มีการพึ่งพา native, ดังนั้นโค้ดเดียวกันทำงานได้บน Windows, Linux หรือ macOS.  
- **Full XPS spec compliance** – Mask แสดงผลตรงตามมาตรฐาน XPS.  
- **Object‑oriented design** – คล้าย .NET ทำให้เรียนรู้ได้ง่ายหากคุณเคยใช้ Aspose ในภาษาอื่น.  
- **High performance** – ปรับให้ทำงานได้อย่างมีประสิทธิภาพกับเอกสารขนาดใหญ่และการประมวลผลแบบแบตช์.

## กรณีการใช้งานทั่วไป
- **Watermarking** – ใส่โลโก้กึ่ง‑โปร่งใสทั่วทั้งหน้า.  
- **Dynamic theming** – เปลี่ยนสไตล์การแสดงผลของ UI ในรายงานที่สร้างขึ้น.  
- **Print‑ready previews** – แสดงว่าการออกแบบจะเป็นอย่างไรเมื่อมีความโปร่งใสต่าง ๆ ก่อนส่งไปพิมพ์.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/page/java/)**.  
- ลิขสิทธิ์ที่ถูกต้องสำหรับ Aspose.Page หากคุณไม่มี สามารถรับลิขสิทธิ์ชั่วคราว **[ที่นี่](https://purchase.aspose.com/temporary-license/)**.  
- สภาพแวดล้อมการพัฒนาที่สามารถคอมไพล์และรันแอปพลิเคชัน Java ได้ (เช่น IntelliJ IDEA, Eclipse หรือ VS Code).

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็นจากไลบรารี Aspose.Page เพื่อให้ API พร้อมใช้งานในโปรเจกต์ของคุณ.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: สร้าง XPS Document ใหม่
แรกสุด, สร้างอินสแตนซ์ของ XPS Document ใหม่ที่จะเก็บกราฟิกทั้งหมดของเรา.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### ขั้นตอนที่ 2: เพิ่ม Canvas
Canvas ทำหน้าที่เป็นพื้นผิวการวาดภายในหน้า XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### ขั้นตอนที่ 3: เพิ่มสี่เหลี่ยมและใช้สีเติมแบบ Solid
ที่นี่เราสร้างเส้นทางสี่เหลี่ยมและเติมสีแดงแบบ solid สี่เหลี่ยมนี้จะได้รับ opacity mask ในภายหลัง.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### ขั้นตอนที่ 4: เพิ่ม Opacity Mask ด้วย ImageBrush
เราจะโหลดภาพ TIFF, กำหนดสี่เหลี่ยมต้นทางและปลายทาง, และตั้งค่า brush เป็นโหมด tile เพื่อให้ mask ทำซ้ำหากจำเป็น.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### ขั้นตอนที่ 5: บันทึก XPS Document ที่ได้
สุดท้าย, บันทึกเอกสารลงดิสก์ ไฟล์ผลลัพธ์จะมีสี่เหลี่ยมพร้อมกับ opacity mask ที่ได้ใส่ไว้.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

ทำตามขั้นตอนเหล่านี้อย่างระมัดระวังเพื่อรวมฟังก์ชัน **add opacity mask** เข้าไปใน Java XPS document ของคุณโดยใช้ Aspose.Page.

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **Image not found** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและไฟล์ `R08SY_NN.tif` มีอยู่.  
- **Mask appears solid** – ตรวจสอบว่าภาพต้นทางมีค่าอัลฟาที่แตกต่างกัน; ภาพที่ทึบเต็มจะไม่แสดงความโปร่งใส.  
- **Tile mode not respected** – สี่เหลี่ยมปลายทางต้องมีขนาดเล็กกว่าสี่เหลี่ยมต้นทางเพื่อให้การทำซ้ำเป็นที่สังเกต.

## คำถามที่พบบ่อย

**Q: Aspose.Page รองรับสภาพแวดล้อมการพัฒนา Java ทั้งหมดหรือไม่?**  
A: ใช่, Aspose.Page ถูกออกแบบให้ทำงานร่วมกับ IDE และเครื่องมือ build ของ Java ได้อย่างราบรื่น.

**Q: สามารถใช้ Aspose.Page โดยไม่ต้องมีลิขสิทธิ์ได้หรือไม่?**  
A: แม้ว่าคุณจะประเมินไลบรารีด้วยลิขสิทธิ์ชั่วคราวได้, แต่ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง.

**Q: มีข้อจำกัดใดในเวอร์ชันทดลองหรือไม่?**  
A: เวอร์ชันทดลองอาจมีการจำกัดขนาดหรือคุณสมบัติบางอย่าง; โปรดตรวจสอบเอกสารอย่างเป็นทางการสำหรับรายละเอียด.

**Q: จะขอรับการสนับสนุนสำหรับ Aspose.Page อย่างไร?**  
A: เยี่ยมชม **[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39)** เพื่อขอความช่วยเหลือจากชุมชนหรือซื้อไลเซนส์เพื่อรับการช่วยเหลือระดับพรีเมียม.

**Q: มีการรับประกันคืนเงินสำหรับ Aspose.Page หรือไม่?**  
A: ดู **[หน้าซื้อ](https://purchase.aspose.com/buy)** เพื่อข้อมูลเกี่ยวกับนโยบายการคืนเงิน.

---

**อัปเดตล่าสุด:** 2026-04-30  
**ทดสอบด้วย:** Aspose.Page Java 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}