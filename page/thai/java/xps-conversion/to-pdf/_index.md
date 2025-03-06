---
title: แปลง XPS เป็น PDF ใน Java
linktitle: แปลง XPS เป็น PDF ใน Java
second_title: Aspose.Page Java API
description: ปลดล็อกการแปลง XPS เป็น PDF ใน Java อย่างราบรื่นด้วย Aspose.Page ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการประมวลผลเอกสารที่มีประสิทธิภาพและแม่นยำ
weight: 12
url: /th/java/xps-conversion/to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XPS เป็น PDF ใน Java

## การแนะนำ
ในขอบเขตของการพัฒนา Java ความจำเป็นในการแปลงไฟล์ XPS เป็นรูปแบบ PDF เป็นข้อกำหนดทั่วไป การบรรลุเป้าหมายนี้ได้อย่างราบรื่นและมีประสิทธิภาพสามารถเป็นตัวเปลี่ยนเกมในโครงการต่างๆ โชคดีที่ด้วยพลังของ Aspose.Page สำหรับ Java งานนี้ไม่เพียงแต่สามารถทำได้ แต่ยังตรงไปตรงมาอีกด้วย
ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการแปลง XPS เป็น PDF โดยใช้ Aspose.Page สำหรับ Java เราจะแจกแจงแต่ละขั้นตอนโดยให้คำอธิบายโดยละเอียดและข้อมูลเชิงลึกเพื่อให้แน่ใจว่าการใช้งานจะราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่กระบวนการแปลง ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ
-  Aspose.Page สำหรับ Java: ดาวน์โหลดและตั้งค่า Aspose.Page สำหรับไลบรารี Java คุณสามารถค้นหาข้อมูลที่จำเป็นและลิงค์ดาวน์โหลดได้ใน[เอกสารประกอบ](https://reference.aspose.com/page/java/).
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Page สำหรับ Java ขั้นตอนนี้มีความสำคัญอย่างยิ่งในการเข้าถึงฟังก์ชันที่จำเป็นสำหรับการแปลง XPS เป็น PDF
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
ตอนนี้ เรามาแจกแจงกระบวนการแปลง XPS เป็น PDF ออกเป็นคำแนะนำทีละขั้นตอน:
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ XPS ของคุณ
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: เริ่มต้นสตรีมเอาท์พุต PDF
สร้าง FileOutputStream สำหรับเอาต์พุต PDF
```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```
## ขั้นตอนที่ 3: โหลดเอกสาร XPS
โหลดเอกสาร XPS โดยใช้ Aspose.Page สำหรับ Java
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## ขั้นตอนที่ 4: เริ่มต้นตัวเลือกการบันทึก PDF
สร้างตัวเลือกสำหรับการแปลง PDF โดยระบุพารามิเตอร์ เช่น คุณภาพของภาพ การบีบอัด และหมายเลขหน้า
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## ขั้นตอนที่ 5: สร้างอุปกรณ์แสดงผล PDF
ตั้งค่าอุปกรณ์เรนเดอร์สำหรับรูปแบบ PDF โดยใช้ Aspose.Page สำหรับ Java
```java
PdfDevice device = new PdfDevice(pdfStream);
```
## ขั้นตอนที่ 6: บันทึกเอกสาร
สุดท้าย ให้บันทึกเอกสาร XPS เป็น PDF โดยใช้ตัวเลือกและอุปกรณ์แสดงผลที่ระบุ
```java
document.save(device, options);
```
ทำซ้ำขั้นตอนเหล่านี้ โดยปรับเส้นทางและตัวเลือกของไฟล์ตามกรณีการใช้งานเฉพาะของคุณ
## บทสรุป
โดยสรุป การแปลง XPS เป็น PDF ใน Java เป็นเรื่องง่ายด้วย Aspose.Page ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับโปรเจ็กต์ Java ของคุณได้อย่างราบรื่น ช่วยเพิ่มความสามารถในการประมวลผลเอกสารของคุณ

## คำถามที่พบบ่อย
### ฉันสามารถแปลงไฟล์ XPS ด้วยหลายหน้าโดยใช้ Aspose.Page สำหรับ Java ได้หรือไม่
ได้ คุณสามารถระบุหมายเลขหน้าที่ต้องการได้ในตัวเลือก ดังแสดงในขั้นตอนที่ 4
### ฉันจะรับการสนับสนุนเพิ่มเติมหรือหารือเกี่ยวกับคำถามที่เกี่ยวข้องกับ Aspose.Page ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถสำรวจคุณสมบัติต่างๆ ได้ด้วย[ทดลองฟรี](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 เยี่ยม[ลิงค์นี้](https://purchase.aspose.com/temporary-license/) สำหรับรายละเอียดใบอนุญาตชั่วคราว
### ฉันจะซื้อสิทธิ์การใช้งาน Aspose.Page สำหรับ Java ได้ที่ไหน
 คุณสามารถซื้อใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
