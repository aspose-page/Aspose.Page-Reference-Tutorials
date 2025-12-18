---
date: 2025-12-18
description: เรียนรู้วิธีเพิ่มกริดและเพิ่มสี่เหลี่ยมโปร่งใสในเอกสาร XPS ของ Java ด้วย
  Aspose.Page คู่มือขั้นตอนต่อขั้นตอนเพื่อบันทึกเอกสาร XPS อย่างมีประสิทธิภาพ
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: วิธีเพิ่มกริดโดยใช้ Visual Brush ใน Java
url: /th/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม Grid ด้วย Visual Brush ใน Java

## Introduction
หากคุณกำลังมองหา **how to add grid** ในเอกสาร XPS ที่สร้างด้วย Java คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนการเพิ่ม grid ด้วย Visual Brush การวางชั้นสี่เหลี่ยมโปร่งแสง และสุดท้าย **save XPS document** ด้วย Aspose.Page Java API เมื่อเสร็จคุณจะได้ภาพที่ดูเป็นมืออาชีพและสามารถนำไปใช้ซ้ำในรายงาน ใบแจ้งหนี้ หรือแอปพลิเคชันที่ต้องจัดการเอกสารจำนวนมาก

## Quick Answers
- **What does a Visual Brush do?** มันทาสีพื้นที่ที่กำหนดด้วยเนื้อหา visual ที่สามารถนำกลับมาใช้ใหม่ได้ เหมาะวดลายที่ต้องทำซ้ำเช่น grid.  
- **Can I change the grid color?** ได้ – ปรับการตั้งค่า solid‑color brush ของ brush.  
- **How do I add a transparent rectangle on top of the grid?** ใช้ `setOpacity` กับ path ที่เติมสีทึบ.  
- **What method saves the file?** `doc.save(...)` เขียนไฟล์ XPS ลงดิสก์.  
- **Do I need a license?** จำเป็นต้องมีใบอนุญาตชั่วคราวหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์

## Visual Brush Grid คืออะไร?
Visual Brush ช่วยให้คุณกำหนด visual ขนาดเล็ก (รูปแบบ grid) แล้วทำการ tile ไปทั่วพื้นที่ที่ใหญ่กว่า วิธีนี้ใช้หน่วยความจำน้อยกว่าการวาดแต่ละเส้นแยกกันและให้ผลลัพธ์ที่ pixel‑perfect ในการทำซ้ำ

## ทำไมต้องใช้ Aspose.Page สำหรับงานนี้?
- **Cross‑platform** – ทำงานบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java.  
- **High‑fidelity rendering** – ควบคุมสี, ความโปร่งแสง, และการ tile อย่างแม่นยำ.  
- **No external dependencies** – ทุกอย่างจัดการผ่านไลบรารี Aspose.Page

## ข้อกำหนดเบื้องต้น
- ความรู้พื้นฐานการเขียนโปรแกรม Java.  
- ไลบรารี Aspose.Page ติดตั้งแล้ว – คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- JDK 8 หรือรุ่นใหม่กว่า ตั้งค่าไว้บนเครื่องพัฒนาของคุณ.

## นำเข้าแพ็คเกจ
ก่อนอื่นให้นำเข้าคลาสที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหา type ที่เราจะใช้จากที่ไหน:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
สร้างอินสแตนซ์ `XpsDocument` ใหม่และระบุตำแหน่งโฟลเดอร์ที่คุณต้องการบันทึกไฟล์ผลลัพธ์.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### ขั้นตอนที่ 2: สร้าง Magenta Grid Visual Brush
เรากำหนดรูปทรงสีแมเจนต้าเล็ก ๆ ที่จะทำการ tile ไปทั่วพื้นที่ grid.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### ขั้นตอนที่ 3: กำหนด Geometry สำหรับ Grid Brush
ตั้งค่าพื้นที่สี่เหลี่ยมที่จะรับ visual ที่ทำการ tile.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### ขั้นตอนที่ 4: สร้าง Canvas ใหม่สำหรับเอกสาร
เพิ่ม canvas ลงในเอกสารและกำหนดตำแหน่งที่ grid จะปรากฏ.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### ขั้นตอนที่ 5: เพิ่ม Grid ลงใน Canvas
ใช้ visual brush กับ geometry เพื่อเปิดการทำ tile.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### ขั้นตอนที่ 6: เพิ่ม Transparent Red Rectangle (ฟีเจอร์รอง)
ที่นี่เราจะแสดง **add transparent rectangle** บน grid เพื่อเน้น.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### ขั้นตอนที่ 7: บันทึก XPS Document ที่ได้
สุดท้ายเขียนเอกสารลงดิสก์—นี่คือขั้นตอน **save XPS document**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

ทำตามขั้นตอนเหล่านี้ คุณจะได้ grid ที่ดูเป็นมืออาชีพพร้อมกับ overlay โปร่งแสงทั้งหมดที่สร้างขึ้นโดยอัตโนมัติ

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **Incorrect tile size:** ตรวจสอบว่า `Rectangle2D` ที่ใช้กับ brush มีขนาดตรงกับขนาดการทำซ้ำที่ต้องการ; มิฉะนั้นลวดลายอาจบิดเบี้ยว.  
- **Opacity not applied:** อย่าลืมเรียก `setOpacity` กับ path ที่ต้องการให้โปร่งแสง; คำสั่งนี้จะไม่ส่งผลต่อ brush เอง.  
- **File not saved:** ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และแอปพลิเคชันของคุณมีสิทธิ์เขียน.

## คำถามที่พบบ่อย

**Q: Aspose.Page เหมาะสำหรับการสร้างเอกสารระดับมืออาชีพหรือไม่?**  
A: ใช่, Aspose.Page เป็นไลบรารีที่แข็งแกร่งออกแบบมาสำหรับการสร้าง XPS และ PDF คุณภาพสูงใน Java.

**Q: ฉันสามารถปรับสีของ grid ด้วย Visual Brush ได้หรือไม่?**  
A: ได้เลย! เปลี่ยนพารามิเตอร์ของ `createColor` ในการเรียก `setFill` ของ brush ให้เป็นค่า RGBA ที่คุณต้องการ.

**Q: ฉันจะหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Page ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับความช่วยเหลือจากชุมชนและคำตอบจากทีมอย่างเป็นทางการ.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Page หรือไม่?**  
A: มี, คุณสามารถเข้าถึง [free trial](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติทั้งหมดก่อนตัดสินใจซื้อ.

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับการทดสอบได้อย่างไร?**  
A: รับ [temporary license](https://purchase.aspose.com/temporary-license/) ที่ใช้ได้สำหรับการพัฒนาและประเมินผล.

---

**อัปเดตล่าสุด:** 2025-12-18  
**ทดสอบด้วย:** Aspose.Page for Java 23.12 (latest)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}