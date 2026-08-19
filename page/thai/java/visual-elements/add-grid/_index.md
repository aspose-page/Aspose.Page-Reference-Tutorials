---
date: 2026-03-05
description: เรียนรู้วิธีเพิ่มกริดโดยใช้ Visual Brush ใน Java กับ Aspose.Page. ปฏิบัติตามคู่มือแบบขั้นตอนต่อขั้นตอนเพื่อเพิ่มภาพเอกสารอย่างง่ายดาย.
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: วิธีเพิ่มกริดโดยใช้ Visual Brush ใน Java
url: /th/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม Grid ด้วย Visual Brush ใน Java

## บทนำ
หากคุณกำลังมองหา **วิธีเพิ่ม grid** ลงในเอกสารที่สร้างด้วย Java, ฟีเจอร์ Visual Brush ของ Aspose.Page ทำให้ทำได้อย่างง่ายดาย ในบทแนะนำนี้เราจะเดินผ่านแต่ละขั้นตอน, อธิบายว่าทำไม Visual Brush จึงเหมาะกับรูปแบบกริด, และแสดงตัวอย่างที่สมบูรณ์พร้อมรันได้

## คำตอบสั้น
- **Visual Brush คืออะไร?** องค์ประกอบภาพที่สามารถทำซ้ำหรือยืดเพื่อเติมพื้นที่ได้.  
- **ทำไมต้องใช้กริด?** กริดช่วยจัดโครงสร้างเลย์เอาต์, สร้างลวดลายพื้นหลัง, หรือเน้นส่วนต่าง ๆ ในเอกสาร XPS.  
- **ข้อกำหนดเบื้องต้น?** Java JDK, Aspose.Page for Java, และความเข้าใจพื้นฐานเกี่ยวกับกราฟิกใน Java.  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10‑15 นาทีหลังจากตั้งค่าห้องสมุดแล้ว.  
- **ฉันสามารถปรับสีได้หรือไม่?** ได้ – คุณควบคุมสีเติม, ความโปร่งแสง, และขนาดไทล์โดยตรงในโค้ด.

## ทำไมต้องใช้ Visual Brush เพื่อเพิ่มกริด?
Visual Brush ให้คุณกำหนดภาพขนาดเล็ก ("ไทล์") ครั้งเดียวแล้วทำซ้ำบนรูปทรงใดก็ได้ วิธีนี้ประหยัดหน่วยความจำและทำให้โค้ดของคุณสะอาดตา, โดยเฉพาะเมื่อคุณต้องใช้รูปแบบเดียวกันกับหลายแคนวาส

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- ห้องสมุด Aspose.Page ถูกติดตั้งแล้ว. คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Java Development Kit (JDK) ถูกติดตั้งบนเครื่องของคุณ.

## นำเข้าแพ็กเกจ
ตรวจสอบว่าคุณได้นำเข้าแพ็กเกจที่จำเป็นในโปรเจกต์ Java ของคุณแล้ว:
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

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
แรกเริ่ม, สร้างอินสแตนซ์ `XpsDocument` และระบุตำแหน่งโฟลเดอร์ที่ผลลัพธ์จะถูกบันทึก.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### ขั้นตอนที่ 2: สร้าง Magenta Grid Visual Brush
เราสร้างไทล์สีแมเจนตาขนาดเล็กที่จะทำซ้ำ. รูปทรงพาธกำหนดรูปร่างของไทล์.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### ขั้นตอนที่ 3: กำหนด Geometry สำหรับ Magenta Grid Visual Brush
ที่นี่เรากำหนดพื้นที่ที่จะรับแปรงแบบไทล์.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### ขั้นตอนที่ 4: สร้าง Canvas ใหม่
Canvas ใหม่ถูกเพิ่มลงในเอกสาร, และเรานำการแปลงการแปลที่ทำให้กริดปรากฏในตำแหน่งที่ต้องการ.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### ขั้นตอนที่ 5: เพิ่มกริดลงใน Canvas
ตอนนี้เราผูก visual brush กับ geometry และตั้งค่าโหมดการทำซ้ำ.
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### ขั้นตอนที่ 6: เพิ่มสี่เหลี่ยมสีแดงโปร่งแสง
เพื่อสาธิตการจัดชั้น, เราใส่สี่เหลี่ยมสีแดงกึ่งโปร่งแสงทับบนกริด.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### ขั้นตอนที่ 7: บันทึกเอกสาร XPS ที่ได้
สุดท้าย, เขียนไฟล์ XPS ไปยังดิสก์.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

ทำตามขั้นตอนเหล่านี้, และคุณจะสามารถเพิ่มกริดที่ดูสวยงามโดยใช้ Visual Brush ในแอปพลิเคชัน Java ของคุณด้วย Aspose.Page.

## กรณีการใช้งานทั่วไป
- **พื้นหลังรายงาน:** เพิ่มลวดลายกริดแบบละเอียดในรายงานการเงินหรือวิศวกรรมเพื่อความอ่านง่ายยิ่งขึ้น.  
- **เทมเพลตการออกแบบ:** สร้างเทมเพลตหน้าที่ใช้ซ้ำได้โดยที่กริดเดียวกันทำซ้ำหลายหน้า.  
- **เน้นส่วนต่าง ๆ:** วางกริดสีทับเพื่อดึงความสนใจไปยังพื้นที่เอกสารเฉพาะ.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **กริดแสดงผลบิดเบือน** | ตรวจสอบว่า `TileMode` ถูกตั้งเป็น `XpsTileMode.Tile` และสี่เหลี่ยมต้นฉบับและปลายทางมีขนาดเท่ากัน. |
| **สีดูผิดพลาด** | ตรวจสอบว่าคุณใช้ค่า RGBA ที่ถูกต้องเมื่อสร้าง solid color brush (`createColor(alpha, red, green, blue)`). |
| **เอกสารไม่ถูกบันทึก** | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และสามารถเขียนได้และคุณมีสิทธิ์ระบบไฟล์ที่เหมาะสม. |

## สรุป
ยินดีด้วย! คุณได้เรียนรู้ **วิธีเพิ่ม grid** ด้วย Visual Brush ของ Aspose.Page ใน Java เทคนิคนี้ให้การควบคุมระดับละเอียดในการเรนเดอร์ลวดลายพร้อมรักษาโค้ดให้สะอาดและดูแลได้ง่าย

## คำถามที่พบบ่อย
### Aspose.Page เหมาะกับการสร้างเอกสารระดับมืออาชีพหรือไม่?
ใช่, Aspose.Page เป็นไลบรารีที่แข็งแกร่งออกแบบมาสำหรับการสร้างเอกสารระดับมืออาชีพใน Java.

### ฉันสามารถปรับสีกริดโดยใช้ Visual Brush ได้หรือไม่?
แน่นอน! Visual Brush อนุญาตให้คุณทาสีด้วยสีต่าง ๆ ให้ความยืดหยุ่นในการปรับแต่ง.

### ฉันจะหาแหล่งสนับสนุนเพิ่มเติมสำหรับ Aspose.Page ได้จากที่ไหน?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support and discussions.

### มีการทดลองใช้ฟรีสำหรับ Aspose.Page หรือไม่?
Yes, you can access the [free trial](https://releases.aspose.com/) to explore Aspose.Page's features.

### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page อย่างไร?
Acquire a [temporary license](https://purchase.aspose.com/temporary-license/) for testing purposes.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose  

---