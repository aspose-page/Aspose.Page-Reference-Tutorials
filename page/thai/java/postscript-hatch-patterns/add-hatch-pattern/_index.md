---
title: เพิ่มรูปแบบฟักใน Java PostScript
linktitle: เพิ่มรูปแบบฟักใน Java PostScript
second_title: Aspose.Page Java API
description: เรียนรู้วิธีเพิ่มรูปแบบแฮทช์ที่น่าดึงดูดให้กับเอกสาร Java PostScript โดยใช้ Aspose.Page ยกระดับเนื้อหาภาพของคุณได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/java/postscript-hatch-patterns/add-hatch-pattern/
---
## การแนะนำ
ในโลกของการเขียนโปรแกรม Java การปรับปรุงองค์ประกอบภาพเป็นข้อกำหนดทั่วไปสำหรับนักพัฒนา การปรับปรุงภาพที่น่าสนใจประการหนึ่งคือการเพิ่มรูปแบบฟักลงในเอกสาร PostScript บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มรูปแบบแฮทช์โดยใช้ Aspose.Page สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าต่อไปนี้:
- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนา Java พร้อมแล้ว
-  Aspose.Page สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.Page สำหรับไลบรารี Java คุณสามารถค้นหาไฟล์ที่จำเป็นได้[ที่นี่](https://releases.aspose.com/page/java/).
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ ใช้ข้อมูลโค้ดต่อไปนี้:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## ขั้นตอนที่ 1: ตั้งค่าพารามิเตอร์เริ่มต้น
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## ขั้นตอนที่ 2: บันทึกสถานะกราฟิกและแปล
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## ขั้นตอนที่ 3: สร้างสี่เหลี่ยมจัตุรัสสำหรับแต่ละรูปแบบ
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## ขั้นตอนที่ 4: ตั้งค่าปากกาสำหรับโครงร่าง Square Pattern
```java
BasicStroke stroke = new BasicStroke(2);
```
## ขั้นตอนที่ 5: วนซ้ำผ่านรูปแบบฟัก
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (ดำเนินการต่อด้วยรหัสที่ให้ไว้)
}
```
## ขั้นตอนที่ 6: กู้คืนสถานะกราฟิก
```java
document.writeGraphicsRestore();
```
## ขั้นตอนที่ 7: กรอกข้อความด้วยรูปแบบฟัก
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## ขั้นตอนที่ 8: ร่างข้อความด้วยรูปแบบฟัก
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## ขั้นตอนที่ 9: ปิดและบันทึกเอกสาร
```java
document.closePage();
document.save();
```
ทำตามขั้นตอนเหล่านี้ แล้วคุณจะเพิ่มรูปแบบแฮทช์ลงในเอกสาร Java PostScript ของคุณได้สำเร็จโดยใช้ Aspose.Page
## บทสรุป
การรวมองค์ประกอบภาพ เช่น รูปแบบแฮทช์สามารถเพิ่มความน่าสนใจให้กับแอปพลิเคชัน Java ของคุณได้อย่างมาก Aspose.Page สำหรับ Java ทำให้กระบวนการนี้ราบรื่น ช่วยให้คุณสร้างเอกสาร PostScript ที่สวยงามสะดุดตาได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับเฟรมเวิร์ก Java อื่นได้หรือไม่
ใช่ Aspose.Page สำหรับ Java ได้รับการออกแบบมาเพื่อผสานรวมกับเฟรมเวิร์ก Java ต่างๆ ได้อย่างราบรื่น
### มีเวอร์ชันทดลองใช้งานสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาบทช่วยสอนและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 สำรวจ[Aspose.Page สำหรับฟอรัม Java](https://forum.aspose.com/c/page/39) สำหรับบทช่วยสอนและการสนับสนุนจากชุมชน
### มีทรัพยากรเอกสารที่ครอบคลุมสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/page/java/).