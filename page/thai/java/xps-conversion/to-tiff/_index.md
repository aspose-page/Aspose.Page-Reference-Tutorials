---
title: แปลง XSP เป็น TIFF ใน Java
linktitle: แปลง XSP เป็น TIFF ใน Java
second_title: Aspose.Page Java API
description: แปลง XPS เป็น TIFF ได้อย่างง่ายดายด้วย Aspose.Page สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น ดาวน์โหลดเดี๋ยวนี้!
weight: 14
url: /th/java/xps-conversion/to-tiff/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XSP เป็น TIFF ใน Java

ในยุคดิจิทัลปัจจุบัน การแปลงเอกสารมีบทบาทสำคัญในการใช้งานต่างๆ หากคุณเป็นนักพัฒนา Java ที่กำลังมองหาโซลูชันที่มีประสิทธิภาพในการแปลงเอกสาร XPS (XML Paper Specification) เป็น TIFF (รูปแบบไฟล์ภาพที่ติดแท็ก) Aspose.Page สำหรับ Java จะเป็นไลบรารี่ที่เหมาะกับคุณ ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการ เพื่อให้แน่ใจว่าคุณจะได้รับประสบการณ์ที่ราบรื่นพร้อมคำอธิบายโดยละเอียดและข้อมูลโค้ด
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่กระบวนการแปลง ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
-  Aspose.Page สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
-  ใบอนุญาตที่ถูกต้องสำหรับ Aspose.Page สำหรับ Java คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/) หรือซื้อใบอนุญาตแบบเต็ม[ที่นี่](https://purchase.aspose.com/buy).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Page สำหรับ Java ให้กับโปรเจ็กต์ของคุณ
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีไฟล์ XPS อินพุตอยู่
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: โหลดเอกสาร XPS
โหลดเอกสาร XPS โดยใช้ไลบรารี Aspose.Page
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## ขั้นตอนที่ 3: เริ่มต้น TiffSaveOptions
เริ่มต้นออบเจ็กต์ TiffSaveOptions ด้วยพารามิเตอร์ที่จำเป็น เช่น โหมดการปรับให้เรียบ ความละเอียด และหมายเลขหน้าเฉพาะ
```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## ขั้นตอนที่ 4: สร้างอุปกรณ์แสดงผล
สร้างอุปกรณ์เรนเดอร์สำหรับรูปแบบ TIFF โดยใช้คลาส ImageDevice
```java
ImageDevice device = new ImageDevice();
```
## ขั้นตอนที่ 5: บันทึกเอกสารเป็น TIFF
บันทึกเอกสาร XPS เป็นรูปแบบ TIFF โดยใช้ตัวเลือกที่ระบุและอุปกรณ์แสดงผล
```java
document.save(device, options);
```
## ขั้นตอนที่ 6: วนซ้ำและบันทึกรูปภาพ TIFF
วนซ้ำพาร์ติชันและหน้าเอกสาร เริ่มต้นสตรีมเอาต์พุตรูปภาพ และบันทึกรูปภาพ TIFF
```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
 ยินดีด้วย! คุณได้แปลง XPS เป็น TIFF ใน Java สำเร็จแล้วโดยใช้ Aspose.Page รู้สึกอิสระที่จะสำรวจคุณสมบัติและฟังก์ชั่นเพิ่มเติมของห้องสมุดใน[เอกสารประกอบ](https://reference.aspose.com/page/java/).
## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนสำคัญในการแปลง XPS เป็น TIFF ใน Java โดยใช้ Aspose.Page การแปลงเอกสารอยู่ใกล้แค่ปลายนิ้วของคุณ ช่วยให้คุณสามารถปรับปรุงแอปพลิเคชันของคุณด้วยการรองรับรูปแบบไฟล์ที่หลากหลาย
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java โดยไม่มีใบอนุญาตได้หรือไม่
 แม้ว่าคุณจะได้รับใบอนุญาตชั่วคราวสำหรับการประเมิน แต่จำเป็นต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งานจริง รับใบอนุญาตของคุณ[ที่นี่](https://purchase.aspose.com/buy).
### มีข้อ จำกัด เกี่ยวกับขนาดของไฟล์ XPS สำหรับการแปลงหรือไม่?
Aspose.Page สำหรับ Java จัดการเอกสารขนาดต่างๆ แต่ขอแนะนำให้ทดสอบกับไฟล์ขนาดใหญ่กว่าในสภาพแวดล้อมเฉพาะของคุณ
### ฉันจะรับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.Page สำหรับ Java ได้อย่างไร
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถสำรวจห้องสมุดด้วยการทดลองใช้ฟรี ดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/).
### ความละเอียดที่แนะนำสำหรับภาพ TIFF ในการแปลงนี้คือเท่าใด
ตัวอย่างที่ให้มาใช้ความละเอียด 300 DPI แต่คุณสามารถปรับได้ตามความต้องการเฉพาะของคุณ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
