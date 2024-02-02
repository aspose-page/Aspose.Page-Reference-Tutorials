---
title: แปลง XPS เป็น JPEG ใน Java
linktitle: แปลง XPS เป็น JPEG ใน Java
second_title: Aspose.Page Java API
description: เรียนรู้วิธีแปลง XPS เป็น JPEG ใน Java โดยใช้ Aspose.Page คู่มือที่ครอบคลุมพร้อมคำแนะนำทีละขั้นตอนเพื่อการบูรณาการที่ราบรื่น
type: docs
weight: 11
url: /th/java/xps-conversion/to-jpeg/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีแปลงไฟล์ XPS (XML Paper Specification) เป็นรูปภาพ JPEG โดยใช้ Aspose.Page สำหรับ Java Aspose.Page เป็นไลบรารี Java อันทรงพลังที่ช่วยให้นักพัฒนาทำงานกับ XPS และรูปแบบเอกสารอื่นๆ ได้อย่างราบรื่น คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณเข้าใจกระบวนการและนำไปใช้ในแอปพลิเคชัน Java ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนเครื่องของคุณ
-  Aspose.Page สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.Page สำหรับไลบรารี Java คุณสามารถค้นหาห้องสมุด[ที่นี่](https://releases.aspose.com/page/java/).
- ตัวอย่างเอกสาร XPS: มีเอกสาร XPS ตัวอย่างที่คุณต้องการแปลงเป็น JPEG
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นลงในคลาส Java ของคุณ:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## ขั้นตอนที่ 1: เริ่มต้นเส้นทางและเอกสาร XPS
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// เตรียมใช้งานสตรีมอินพุต XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## ขั้นตอนที่ 2: ตั้งค่า JpegSaveOptions
```java
// เริ่มต้นวัตถุตัวเลือกด้วยพารามิเตอร์ที่จำเป็น
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## ขั้นตอนที่ 3: สร้างอุปกรณ์แสดงผล
```java
// สร้างอุปกรณ์เรนเดอร์สำหรับรูปแบบ PDF
ImageDevice device = new ImageDevice();
```
## ขั้นตอนที่ 4: บันทึก XPS เป็น JPEG
```java
document.save(device, options);
```
## ขั้นตอนที่ 5: วนซ้ำและบันทึกหน้า JPEG
```java
//วนซ้ำผ่านพาร์ติชันเอกสาร (เอกสารคงที่ตามเงื่อนไข XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // วนซ้ำผ่านหน้าพาร์ติชัน
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // เริ่มต้นสตรีมเอาท์พุตรูปภาพ
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // เขียนภาพ
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //ปิดสตรีม
        imageStream.close();
    }
}
```
ชุดขั้นตอนนี้จะแปลงเอกสาร XPS ของคุณเป็นภาพ JPEG ได้อย่างมีประสิทธิภาพ โดยแต่ละขั้นตอนจะบันทึกแยกกัน
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีแปลง XPS เป็น JPEG ใน Java โดยใช้ Aspose.Page เรียบร้อยแล้ว กระบวนการนี้มีค่ามากสำหรับนักพัฒนาที่ทำงานเกี่ยวกับการแปลงเอกสารในแอปพลิเคชัน Java
## คำถามที่พบบ่อย

### ถาม: Aspose.Page เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่
 ตอบ: ใช่ Aspose.Page เป็นผลิตภัณฑ์เชิงพาณิชย์ที่มีตัวเลือกสิทธิ์การใช้งานให้เลือก ตรวจสอบ[ที่นี่](https://purchase.aspose.com/buy) เพื่อดูรายละเอียด
### ถาม: ฉันสามารถลองใช้ Aspose.Page ก่อนซื้อได้หรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะหาเอกสารประกอบของ Aspose.Page ได้ที่ไหน
 ตอบ: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/page/java/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.Page ได้อย่างไร
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนตามชุมชน
### ถาม: ฉันจำเป็นต้องมีใบอนุญาตชั่วคราวในการทดสอบหรือไม่
 ตอบ: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).