---
title: เพิ่มการไล่ระดับสีแนวนอนใน Java PostScript
linktitle: เพิ่มการไล่ระดับสีแนวนอนใน Java PostScript
second_title: Aspose.Page Java API
description: เรียนรู้วิธีเพิ่มการไล่ระดับสีแนวนอนใน Java PostScript ด้วย Aspose.Page สำหรับ Java สร้างเอกสารที่สวยงามสะดุดตาได้อย่างง่ายดาย
weight: 11
url: /th/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มการไล่ระดับสีแนวนอนใน Java PostScript

## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการเพิ่มการไล่ระดับสีแนวนอนใน Java PostScript โดยใช้ Aspose.Page สำหรับ Java Aspose.Page เป็นไลบรารี Java อันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับ PostScript และรูปแบบเอกสารอื่นๆ ได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างเอกสาร PostScript ที่มีการไล่ระดับสีแนวนอนโดยใช้ตัวอย่างทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
- Aspose.Page สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[เอกสารประกอบ Java ของ Aspose.Page](https://reference.aspose.com/page/java/).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ แพ็คเกจเหล่านี้มีความสำคัญอย่างยิ่งต่อการทำงานกับ Aspose.Page
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## ขั้นตอนที่ 1: สร้างสี่เหลี่ยมผืนผ้า
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
//สร้างสี่เหลี่ยม
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## ขั้นตอนที่ 2: สร้างสีไล่ระดับสีเชิงเส้นแนวนอน
```java
// สร้างสีไล่ระดับสีเชิงเส้นแนวนอน ส่วนประกอบมาตราส่วนในการแปลงจะต้องเท่ากับความกว้างและความสูงของสี่เหลี่ยมผืนผ้า
// ส่วนประกอบการแปลเป็นการชดเชยของสี่เหลี่ยม
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// เซ็ตสี
document.setPaint(paint);
```
## ขั้นตอนที่ 3: เติมสี่เหลี่ยม
```java
// เติมสี่เหลี่ยม
document.fill(rectangle);
```
## ขั้นตอนที่ 4: เติมข้อความด้วยการไล่ระดับสี
```java
// เติมข้อความด้วยการไล่ระดับสี
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## ขั้นตอนที่ 5: ลากเส้นข้อความด้วยการไล่ระดับสี
```java
// ขีดข้อความด้วยการไล่ระดับสี
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## บทสรุป
ยินดีด้วย! คุณได้เพิ่มการไล่ระดับสีแนวนอนใน Java PostScript โดยใช้ Aspose.Page สำหรับ Java สำเร็จแล้ว บทช่วยสอนนี้ให้คำแนะนำโดยละเอียดทีละขั้นตอนเพื่อช่วยคุณสร้างเอกสาร PostScript ที่ดึงดูดสายตา
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java ในโครงการเชิงพาณิชย์ได้หรือไม่
ได้ Aspose.Page สำหรับ Java สามารถใช้ในโครงการเชิงพาณิชย์ได้ สำหรับรายละเอียดใบอนุญาต โปรดไปที่[มอบหมายจัดซื้อ](https://purchase.aspose.com/buy).
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถเข้าถึง Aspose.Page สำหรับ Java รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารและการสนับสนุนเพิ่มเติมได้ที่ไหน
 เยี่ยมชม[เอกสารประกอบ Java ของ Aspose.Page](https://reference.aspose.com/page/java/) เพื่อทรัพยากรที่ครอบคลุม สำหรับการสนับสนุนชุมชน ตรวจสอบ[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39).
### ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[มอบหมายจัดซื้อ](https://purchase.aspose.com/temporary-license/).
### ข้อกำหนดของระบบสำหรับ Aspose.Page สำหรับ Java คืออะไร
 อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/page/java/) สำหรับความต้องการของระบบโดยละเอียด
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
