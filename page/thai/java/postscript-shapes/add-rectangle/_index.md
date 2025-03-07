---
title: ปรับแต่ง Java PostScript - การเพิ่มสี่เหลี่ยมด้วย Aspose.Page
linktitle: เพิ่มสี่เหลี่ยมผืนผ้าใน Java PostScript
second_title: Aspose.Page Java API
description: สำรวจคำแนะนำทีละขั้นตอนในการเพิ่มสี่เหลี่ยมสีสันสดใสให้กับเอกสาร Java PostScript โดยใช้ Aspose.Page สำหรับ Java ปรับปรุงการปรับแต่งเอกสารของคุณได้อย่างง่ายดาย!
weight: 11
url: /th/java/postscript-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ปรับแต่ง Java PostScript - การเพิ่มสี่เหลี่ยมด้วย Aspose.Page

## การแนะนำ
คุณต้องการปรับปรุงเอกสาร Java PostScript ของคุณด้วยสี่เหลี่ยมที่มีชีวิตชีวาหรือไม่? ไม่ต้องมองอีกต่อไป! ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีใช้ Aspose.Page สำหรับ Java เพื่อเพิ่มสี่เหลี่ยมให้กับเอกสาร PostScript ของคุณ Aspose.Page เป็นไลบรารีอันทรงพลังที่นำเสนอฟีเจอร์ที่มีประสิทธิภาพสำหรับการทำงานกับไฟล์ PostScript ทำให้เป็นตัวเลือกในอุดมคติสำหรับนักพัฒนาที่ต้องการจัดการและปรับแต่งเอกสารของตน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Page สำหรับไลบรารี Java แล้ว ถ้าไม่เช่นนั้น ให้ดาวน์โหลดจาก[Aspose.Page สำหรับเอกสาร Java](https://reference.aspose.com/page/java/).
- สภาพแวดล้อมการพัฒนา Java ที่ตั้งค่าไว้ในเครื่องของคุณ
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้เริ่มด้วยการอิมพอร์ตแพ็คเกจที่จำเป็น:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## บทช่วยสอน: การเพิ่มสี่เหลี่ยมใน Java PostScript
## ขั้นตอนที่ 1: ตั้งค่าสีสำหรับการเติมสี่เหลี่ยมผืนผ้า
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
// สร้างเอกสาร PS ใหม่โดยเปิดหน้าไว้
PsDocument document = new PsDocument(outPsStream, options, false);
// ตั้งค่าสีสำหรับเติมสี่เหลี่ยม
document.setPaint(Color.ORANGE);        
// เติมสี่เหลี่ยมแรก
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## ขั้นตอนที่ 2: ตั้งค่าสีสำหรับการลากเส้นสี่เหลี่ยม
```java
// ตั้งค่าสีสำหรับการลากเส้นสี่เหลี่ยม
document.setPaint(Color.RED);
// ตั้งจังหวะ
document.setStroke(new BasicStroke(3));
// ลากเส้น (ร่าง) สี่เหลี่ยมที่สอง
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## ขั้นตอนที่ 3: ปิดหน้าปัจจุบันและบันทึกเอกสาร
```java
// ปิดหน้าปัจจุบัน
document.closePage();
// บันทึกเอกสาร
document.save();
```
ยินดีด้วย! คุณได้เพิ่มสี่เหลี่ยมสีสันสดใสให้กับเอกสาร Java PostScript ของคุณสำเร็จแล้วโดยใช้ Aspose.Page
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการปรับปรุงเอกสาร Java PostScript ของคุณด้วยสี่เหลี่ยมโดยใช้ Aspose.Page สำหรับ Java ไลบรารีอันทรงพลังนี้เปิดโลกแห่งความเป็นไปได้สำหรับนักพัฒนาที่ต้องการปรับแต่งและจัดการเอกสารของตนได้อย่างง่ายดาย
สนุกกับการทดลองใช้รูปทรงและสีต่างๆ เพื่อทำให้เอกสารของคุณดูน่าดึงดูด!
## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Page รองรับ Java เป็นหลัก แต่มีไลบรารีที่คล้ายกันในภาษาอื่น
### มี Aspose.Page สำหรับ Java เวอร์ชันทดลองใช้หรือไม่
 ใช่ คุณสามารถสำรวจคุณสมบัติของ Aspose.Page สำหรับ Java ได้ด้วย[รุ่นทดลองใช้ฟรี](https://releases.aspose.com/).
### ฉันจะรับความช่วยเหลือและการสนทนาเพิ่มเติมได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อมีส่วนร่วมกับชุมชนและรับความช่วยเหลือ
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อ Aspose.Page สำหรับ Java เวอร์ชันลิขสิทธิ์ได้ที่ไหน
 ซื้อเวอร์ชันลิขสิทธิ์[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
