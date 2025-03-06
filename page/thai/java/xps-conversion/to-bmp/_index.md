---
title: แปลง XPS เป็น BMP ใน Java
linktitle: แปลง XPS เป็น BMP ใน Java
second_title: Aspose.Page Java API
description: เรียนรู้วิธีแปลง XPS เป็น BMP ใน Java ด้วย Aspose.Page ปฏิบัติตามคำแนะนำง่ายๆ ของเราเพื่อการแปลงเอกสารที่มีประสิทธิภาพและมีคุณภาพสูง
weight: 10
url: /th/java/xps-conversion/to-bmp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XPS เป็น BMP ใน Java

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการแปลงไฟล์ XPS (XML Paper Specification) เป็นรูปแบบ BMP (บิตแมป) ใน Java โดยใช้ Aspose.Page Aspose.Page สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีคุณลักษณะที่ครอบคลุมสำหรับการทำงานกับเอกสาร XPS ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลงไฟล์ XPS เป็นอิมเมจ BMP ได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่กระบวนการแปลง ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
-  Aspose.Page สำหรับไลบรารี Java: ดาวน์โหลดและรวม Aspose.Page สำหรับไลบรารี Java ในโปรเจ็กต์ของคุณ คุณสามารถค้นหาห้องสมุด[ที่นี่](https://releases.aspose.com/page/java/).
- ไฟล์ XPS ตัวอย่าง: เตรียมเอกสาร XPS ตัวอย่างที่คุณต้องการแปลงเป็น BMP
## แพ็คเกจนำเข้า
รวมแพ็คเกจ Aspose.Page ที่จำเป็นในโค้ด Java ของคุณ:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
เรามาแบ่งกระบวนการแปลงออกเป็นขั้นตอนที่ง่ายต่อการปฏิบัติตาม:
## ขั้นตอนที่ 1: โหลดเอกสาร XPS
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// โหลดเอกสาร XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## ขั้นตอนที่ 2: เริ่มต้นตัวเลือก
```java
// เริ่มต้นวัตถุตัวเลือกด้วยพารามิเตอร์ที่จำเป็น
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[]{1, 2, 6});
```
## ขั้นตอนที่ 3: สร้างอุปกรณ์แสดงผล
```java
// สร้างอุปกรณ์เรนเดอร์สำหรับรูปแบบ BMP
ImageDevice device = new ImageDevice();
```
## ขั้นตอนที่ 4: บันทึกเอกสาร
```java
// บันทึกเอกสาร XPS ลงใน BMP โดยใช้ตัวเลือกและอุปกรณ์
document.save(device, options);
```
## ขั้นตอนที่ 5: วนซ้ำและบันทึกรูปภาพ
```java
// วนซ้ำผ่านพาร์ติชันเอกสาร
for (int i = 0; i < device.getResult().length; i++) {
    // วนซ้ำผ่านหน้าพาร์ติชัน
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // เริ่มต้นสตรีมเอาท์พุตรูปภาพ
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // เขียนภาพ
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
ทำซ้ำขั้นตอนเหล่านี้เพื่อปรับแต่งหรือแก้ไขเพิ่มเติมที่คุณอาจต้องการในกระบวนการแปลง
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีแปลงไฟล์ XPS เป็น BMP ใน Java โดยใช้ Aspose.Page เรียบร้อยแล้ว ความยืดหยุ่นและความสะดวกในการใช้งานของ Aspose.Page ทำให้ Aspose.Page เป็นเครื่องมืออันทรงคุณค่าในการจัดการงานการแปลงเอกสาร
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งความละเอียดของภาพ BMP ได้หรือไม่
 ตอบ: ได้ คุณสามารถปรับความละเอียดได้โดยการแก้ไข`options.setResolution()`พารามิเตอร์ในโค้ด
### ถาม: Aspose.Page เข้ากันได้กับ Java เวอร์ชันต่างๆ หรือไม่
ตอบ: ใช่ Aspose.Page รองรับ Java เวอร์ชันต่างๆ มากมาย ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งเวอร์ชันที่เข้ากันได้
### ถาม: ฉันจะแปลงไฟล์ XPS จากช่วงหน้าที่ต้องการได้อย่างไร
 ตอบ: ใช้`options.setPageNumbers()` วิธีการระบุหมายเลขหน้าที่คุณต้องการแปลง
### ถาม: Aspose.Page รองรับรูปแบบเอาต์พุตอื่นๆ หรือไม่
ตอบ: ใช่ Aspose.Page รองรับรูปแบบเอาต์พุตที่หลากหลาย โปรดดูเอกสารประกอบสำหรับรายการที่ครอบคลุม
### ถาม: ฉันจะขอความช่วยเหลือหรือการสนับสนุนเพิ่มเติมได้จากที่ไหน
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปรายของชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
