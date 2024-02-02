---
title: แปลง XPS เป็น PNG ใน Java
linktitle: แปลง XPS เป็น PNG ใน Java
second_title: Aspose.Page Java API
description: แปลง XPS เป็น PNG ใน Java ได้อย่างง่ายดายโดยใช้ Aspose.Page ปรับปรุงงานเอกสารด้วยโซลูชันที่เชื่อถือได้และเป็นมิตรต่อนักพัฒนา
type: docs
weight: 13
url: /th/java/xps-conversion/to-png/
---
## การแนะนำ
ในโลกแบบไดนามิกของการพัฒนาซอฟต์แวร์ ความจำเป็นในการแปลงเอกสาร XPS (XML Paper Specification) เป็นอิมเมจ PNG (Portable Network Graphics) เกิดขึ้นบ่อยครั้ง เพื่อให้งานนี้สำเร็จลุล่วงได้อย่างราบรื่นใน Java Aspose.Page จึงมอบโซลูชันอันทรงพลัง ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการแปลง XPS เป็น PNG โดยใช้ Aspose.Page สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Page สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/page/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ที่เข้ากันได้กับ Java เช่น IntelliJ IDEA หรือ Eclipse
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Page เพิ่มคำสั่งนำเข้าต่อไปนี้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: โหลดเอกสาร XPS
```java
// โหลดเอกสาร XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## ขั้นตอนที่ 3: เริ่มต้นตัวเลือก
```java
// เริ่มต้นวัตถุตัวเลือกด้วยพารามิเตอร์ที่จำเป็น
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## ขั้นตอนที่ 4: สร้างอุปกรณ์แสดงผล
```java
// สร้างอุปกรณ์เรนเดอร์สำหรับรูปแบบ PDF
ImageDevice device = new ImageDevice();
```
## ขั้นตอนที่ 5: บันทึกและทำซ้ำ
```java
// บันทึกเอกสาร XPS เป็น PNG โดยใช้ตัวเลือกและอุปกรณ์
document.save(device, options);
//วนซ้ำผ่านพาร์ติชันเอกสาร (เอกสารคงที่ตามเงื่อนไข XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // วนซ้ำผ่านหน้าพาร์ติชัน
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // เริ่มต้นสตรีมเอาท์พุตรูปภาพ
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // เขียนภาพ
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // ปิดสตรีม
        imageStream.close();
    }
}
```
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถแปลงเอกสาร XPS เป็นภาพ PNG ได้อย่างง่ายดายโดยใช้ Aspose.Page สำหรับ Java
## บทสรุป
โดยสรุป Aspose.Page สำหรับ Java ทำให้กระบวนการแปลง XPS เป็น PNG ง่ายขึ้น ทำให้นักพัฒนามีเครื่องมือที่เชื่อถือได้และมีประสิทธิภาพ รวมไลบรารีนี้เข้ากับโปรเจ็กต์ Java ของคุณเพื่อปรับปรุงงานการจัดการเอกสาร
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java ในโครงการเชิงพาณิชย์ได้หรือไม่
 ใช่ Aspose.Page เป็นผลิตภัณฑ์เชิงพาณิชย์ คุณสามารถค้นหาข้อมูลใบอนุญาตได้[ที่นี่](https://purchase.aspose.com/buy).
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถทดลองใช้งานฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 มีเอกสารประกอบครบถ้วน[ที่นี่](https://reference.aspose.com/page/java/).
### ฉันจะขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### มีฟอรัมชุมชนสำหรับการสนทนา Aspose.Page หรือไม่
 ใช่ เยี่ยมชมฟอรั่มชุมชน[ที่นี่](https://forum.aspose.com/c/page/39).