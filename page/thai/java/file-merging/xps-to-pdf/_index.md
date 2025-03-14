---
title: แปลง XPS เป็น PDF ใน Java
linktitle: แปลง XPS เป็น PDF ใน Java
second_title: Aspose.Page Java API
description: เรียนรู้วิธีแปลง XPS เป็น PDF ใน Java ได้อย่างง่ายดายด้วย Aspose.Page ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการแปลงเอกสารอย่างมีประสิทธิภาพ
weight: 11
url: /th/java/file-merging/xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XPS เป็น PDF ใน Java

## การแนะนำ
ในขอบเขตของการพัฒนา Java การแปลง XPS เป็น PDF เป็นงานทั่วไป และการมีเครื่องมือที่เชื่อถือได้เพื่อให้บรรลุเป้าหมายนี้ได้อย่างราบรื่นถือเป็นสิ่งสำคัญยิ่ง Aspose.Page สำหรับ Java เป็นไลบรารีตัวอย่างที่มีฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับการจัดการเอกสาร XPS บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแปลง XPS เป็น PDF โดยใช้ Aspose.Page เพื่อให้มั่นใจถึงความเรียบง่ายและมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่กระบวนการแปลง ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ล่าสุดบนระบบของคุณ
2.  Aspose.Page สำหรับไลบรารี Java: ดาวน์โหลดและรวม Aspose.Page สำหรับไลบรารี Java ในโปรเจ็กต์ของคุณ คุณสามารถค้นหาห้องสมุดและเอกสารประกอบของห้องสมุดได้[ที่นี่](https://reference.aspose.com/page/java/).
## แพ็คเกจนำเข้า
เมื่อคุณตั้งค่าโปรเจ็กต์แล้ว ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Page นี่เป็นตัวอย่างเพื่อแนะนำคุณ:
```java

import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร
```java
String dataDir = "Your Document Directory";
```
ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังเอกสาร XPS ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นสตรีมเอาท์พุต PDF
```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```
สร้างออบเจ็กต์ FileOutputStream สำหรับไฟล์ PDF โดยระบุเส้นทางเอาต์พุตที่ต้องการ
## ขั้นตอนที่ 3: โหลดเอกสาร XPS
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
โหลดเอกสาร XPS โดยใช้คลาส XpsDocument
## ขั้นตอนที่ 4: เริ่มต้นตัวเลือกการบันทึก PDF
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
กำหนดค่าตัวเลือกการบันทึก PDF ตามความต้องการของคุณ เช่น การตั้งค่าการบีบอัดรูปภาพและข้อความ
## ขั้นตอนที่ 5: สร้างอุปกรณ์แสดงผลสำหรับรูปแบบ PDF
```java
PdfDevice device = new PdfDevice(pdfStream);
```
เตรียมใช้งานวัตถุ PdfDevice เพื่อแสดงผลเอกสาร XPS เป็น PDF
## ขั้นตอนที่ 6: บันทึกเอกสาร
```java
document.save(device, options);
```
สุดท้าย ให้บันทึกเอกสาร XPS เป็น PDF โดยใช้วิธีการบันทึก
ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถแปลง XPS เป็น PDF ใน Java ได้อย่างราบรื่นโดยใช้ Aspose.Page ซึ่งเป็นโซลูชันที่เชื่อถือได้และมีประสิทธิภาพสำหรับความต้องการในการแปลงเอกสารของคุณ
## บทสรุป
โดยสรุป Aspose.Page สำหรับ Java ช่วยให้กระบวนการแปลง XPS เป็น PDF ง่ายขึ้น ช่วยให้นักพัฒนา Java สามารถรวมฟังก์ชันนี้เข้ากับแอปพลิเคชันของตนได้อย่างราบรื่น คำแนะนำทีละขั้นตอนช่วยให้มั่นใจได้ถึงประสบการณ์ที่ราบรื่น ทำให้ทั้งผู้เริ่มต้นและนักพัฒนาที่มีประสบการณ์สามารถเข้าถึงได้
## คำถามที่พบบ่อย
### ถาม: Aspose.Page เข้ากันได้กับ Java เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Page ได้รับการออกแบบมาให้เข้ากันได้กับ Java เวอร์ชันต่างๆ
### ถาม: ฉันสามารถปรับแต่งการตั้งค่าการบีบอัดสำหรับ PDF ที่แปลงแล้วได้หรือไม่
ตอบ: แน่นอนว่า Aspose.Page มีตัวเลือกในการปรับแต่งการตั้งค่าการบีบอัดรูปภาพและข้อความ
### ถาม: ฉันจะรับการสนับสนุนเพิ่มเติมหรือการสนทนาในชุมชนได้จากที่ไหน
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการอภิปรายและการสนับสนุนของชุมชน
### ถาม: Aspose.Page มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร
 ตอบ: คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
