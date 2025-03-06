---
title: เพิ่มรูปแบบการปูกระเบื้องพื้นผิวใน Java PostScript
linktitle: เพิ่มรูปแบบการปูกระเบื้องพื้นผิวใน Java PostScript
second_title: Aspose.Page Java API
description: เพิ่มรูปแบบการเรียงต่อพื้นผิวให้กับเอกสาร PostScript ได้อย่างง่ายดายด้วย Aspose.Page สำหรับ Java สำรวจคู่มือการบูรณาการอย่างราบรื่นของเราเพื่อความเป็นไปได้ที่สร้างสรรค์
weight: 10
url: /th/java/postscript-texture-patterns/add-texture-tiling-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรูปแบบการปูกระเบื้องพื้นผิวใน Java PostScript

## การแนะนำ
ในขอบเขตของการพัฒนา Java การสร้างรูปแบบและพื้นผิวที่ซับซ้อนในเอกสาร PostScript ถือเป็นข้อกำหนดทั่วไป Aspose.Page สำหรับ Java พิสูจน์แล้วว่าเป็นเครื่องมืออันทรงคุณค่าในการบรรลุงานนี้ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มรูปแบบการเรียงต่อพื้นผิวในเอกสาร Java PostScript โดยใช้ Aspose.Page
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- ความคุ้นเคยกับโครงสร้างเอกสาร PostScript
-  ติดตั้ง Aspose.Page สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นสำหรับโปรเจ็กต์ Java ของคุณ:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## ขั้นตอนที่ 1: สร้างเอกสาร PostScript
เริ่มต้นด้วยการสร้างเอกสาร PostScript ใหม่ ระบุเอาต์พุตสตรีมและบันทึกตัวเลือก ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าเส้นทางที่จำเป็นแล้ว
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ขั้นตอนที่ 2: ตั้งค่าสภาพแวดล้อมกราฟิก
ตั้งค่าสภาพแวดล้อมกราฟิกโดยการแปลจุดเริ่มต้นและสร้าง BufferedImage จากไฟล์ภาพพื้นผิว
```java
document.writeGraphicsSave();
document.translate(200, 100);
// สร้างวัตถุ BufferedImage จากไฟล์รูปภาพ
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```
## ขั้นตอนที่ 3: สร้างแปรงพื้นผิว
กำหนดแปรงพื้นผิวจากรูปภาพ โดยระบุพื้นที่ที่จะครอบคลุมโดยพื้นผิว
```java
// สร้างพื้นที่ภาพให้มีความกว้างเป็นสองเท่า
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// สร้างแปรงพื้นผิวจากภาพ
TexturePaint paint = new TexturePaint(image, imageArea);
```
## ขั้นตอนที่ 4: วาดและเติมรูปร่าง
สร้างสี่เหลี่ยมและเติมด้วยแปรงพื้นผิวที่กำหนดไว้ นอกจากนี้ วาดและร่างรูปร่างเพื่อให้ดูดึงดูดสายตา
```java
// สร้างสี่เหลี่ยม
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// ตั้งค่าแปรงพื้นผิวนี้เป็นสีปัจจุบัน
document.setPaint(paint);
// เติมสี่เหลี่ยม
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```
## ขั้นตอนที่ 5: เพิ่มข้อความด้วยรูปแบบพื้นผิว
เพิ่มข้อความลงในเอกสารและเติม/ลากเส้นด้วยรูปแบบพื้นผิว ปรับแต่งแบบอักษร ตำแหน่ง และพารามิเตอร์อื่นๆ ตามต้องการ
```java
// เติมข้อความด้วยลวดลายพื้นผิว
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// ร่างข้อความด้วยลวดลายพื้นผิว
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## ขั้นตอนที่ 6: บันทึกและปิด
สรุปกระบวนการโดยการปิดหน้าปัจจุบัน บันทึกเอกสาร และรับประกันการดำเนินการที่ราบรื่น
```java
// ปิดหน้าปัจจุบัน
document.closePage();
// บันทึกเอกสาร
document.save();
```
## บทสรุป
ยินดีด้วย! คุณได้เพิ่มรูปแบบการเรียงต่อพื้นผิวลงในเอกสาร Java PostScript โดยใช้ Aspose.Page สำหรับ Java สำเร็จแล้ว รู้สึกอิสระที่จะสำรวจตัวเลือกการปรับแต่งเพิ่มเติมและปลดปล่อยศักยภาพสูงสุดของไลบรารีอันทรงพลังนี้

## คำถามที่พบบ่อย
### Aspose.Page สำหรับ Java เหมาะสำหรับผู้เริ่มต้นหรือไม่
อย่างแน่นอน! Aspose.Page สำหรับ Java มีเอกสารประกอบที่ครอบคลุม ทำให้นักพัฒนาทุกระดับสามารถเข้าถึงได้
### ฉันสามารถรวม Aspose.Page สำหรับ Java เข้ากับโปรเจ็กต์ Java ที่มีอยู่ของฉันได้หรือไม่
 ใช่ คุณสามารถรวม Aspose.Page สำหรับ Java เข้ากับโปรเจ็กต์ของคุณได้อย่างง่ายดายโดยทำตามเอกสารที่ให้มา[ที่นี่](https://reference.aspose.com/page/java/).
### ฉันจะรับการสนับสนุนหรือหารือเกี่ยวกับคำถามที่เกี่ยวข้องกับ Aspose.Page ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อมีส่วนร่วมกับชุมชนและขอความช่วยเหลือ
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 เยี่ยม[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) เพื่อขอรับใบอนุญาตชั่วคราว
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
