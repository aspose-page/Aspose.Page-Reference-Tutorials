---
title: เพิ่ม Grid โดยใช้ Visual Brush ใน Java
linktitle: เพิ่ม Grid โดยใช้ Visual Brush ใน Java
second_title: Aspose.Page Java API
description: ปรับปรุงภาพเอกสาร Java ด้วย Aspose.Page! เรียนรู้การเพิ่มกริดโดยใช้ Visual Brush ทีละขั้นตอน ยกระดับความน่าดึงดูดใจให้กับแอปพลิเคชันของคุณได้อย่างง่ายดาย
weight: 10
url: /th/java/visual-elements/add-grid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่ม Grid โดยใช้ Visual Brush ใน Java

## การแนะนำ
คุณต้องการปรับปรุงแอปพลิเคชัน Java ของคุณด้วยกริดที่ดึงดูดสายตาโดยใช้ Aspose.Page หรือไม่? ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มตารางโดยใช้ Visual Brush ใน Java ด้วย Aspose.Page Visual Brush ช่วยให้คุณสามารถวาดพื้นที่ด้วยเนื้อหาภาพ สร้างเอฟเฟกต์เส้นตารางที่น่าทึ่งในเอกสารของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้งไลบรารี Aspose.Page แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Page สำหรับเอกสาร Java](https://reference.aspose.com/page/java/).
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าคุณมีแพ็คเกจที่จำเป็นที่นำเข้าในโปรเจ็กต์ Java ของคุณ:
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
มาแบ่งกระบวนการออกเป็นหลายขั้นตอนเพื่อให้คุณปฏิบัติตามได้ง่ายขึ้น
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```
## ขั้นตอนที่ 2: สร้าง Visual Brush Magenta Grid
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```
## ขั้นตอนที่ 3: กำหนดเรขาคณิตสำหรับ Magenta Grid Visual Brush
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```
## ขั้นตอนที่ 4: สร้าง Canvas ใหม่
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```
## ขั้นตอนที่ 5: เพิ่มตารางลงใน Canvas
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```
## ขั้นตอนที่ 6: เพิ่มสี่เหลี่ยมผืนผ้าโปร่งใสสีแดง
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```
## ขั้นตอนที่ 7: บันทึกเอกสาร XPS ที่เป็นผลลัพธ์
```java
doc.save(dataDir + "AddGrid_out.xps");
```
ทำตามขั้นตอนเหล่านี้ แล้วคุณจะเพิ่มตารางที่ดึงดูดสายตาได้สำเร็จโดยใช้ Visual Brush ในแอปพลิเคชัน Java ของคุณด้วย Aspose.Page
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีใช้ประโยชน์จาก Aspose.Page สำหรับ Java เพื่อเพิ่มกริดโดยใช้ Visual Brush ปรับปรุงภาพเอกสารของคุณอย่างง่ายดายด้วยคุณสมบัติอันทรงพลังนี้
## คำถามที่พบบ่อย
### Aspose.Page เหมาะสำหรับการสร้างเอกสารระดับมืออาชีพหรือไม่?
ใช่ Aspose.Page เป็นไลบรารีที่มีประสิทธิภาพซึ่งออกแบบมาสำหรับการสร้างเอกสารระดับมืออาชีพใน Java
### ฉันสามารถปรับแต่งสีตารางโดยใช้ Visual Brush ได้หรือไม่
อย่างแน่นอน! Visual Brush ช่วยให้คุณสามารถวาดภาพด้วยสีต่างๆ ได้ โดยให้ความยืดหยุ่นในการปรับแต่ง
### ฉันจะรับการสนับสนุนเพิ่มเติมสำหรับ Aspose.Page ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page หรือไม่
 ใช่ คุณสามารถเข้าถึง[ทดลองฟรี](https://releases.aspose.com/) เพื่อสำรวจฟีเจอร์ของ Aspose.Page
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร
 ได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการทดสอบ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
