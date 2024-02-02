---
title: เพิ่มคุณสมบัติอย่างง่ายใน XMP โดยใช้ Java
linktitle: เพิ่มคุณสมบัติอย่างง่ายใน XMP โดยใช้ Java
second_title: Aspose.Page Java API
description: ปลดล็อก Aspose.Page เพื่อดูศักยภาพของ Java ด้วยคำแนะนำในการเพิ่มคุณสมบัติให้กับข้อมูลเมตา XMP ในไฟล์ EPS ยกระดับการประมวลผลเอกสารอย่างง่ายดาย!
type: docs
weight: 14
url: /th/java/xmp-metadata-manipulation/add-simple-properties/
---
## การแนะนำ
ในภูมิทัศน์ของการประมวลผลเอกสารที่มีการพัฒนาอยู่ตลอดเวลา การจัดการเมตาดาต้าอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญ Aspose.Page สำหรับ Java ช่วยให้นักพัฒนาจัดการข้อมูล Extensible Metadata Platform (XMP) ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะสำรวจกระบวนการเพิ่มคุณสมบัติอย่างง่ายให้กับ XMP โดยใช้ Java โดยให้คำแนะนำทีละขั้นตอนที่ครอบคลุมแก่คุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Page สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
- ไฟล์ EPS ตัวอย่างที่มีข้อมูลเมตา หากคุณยังไม่มี คุณสามารถใช้ไฟล์ "xmp3.eps" ที่ให้มาได้เลย
## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าคุณนำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นโปรเจ็กต์ของคุณ:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## ขั้นตอนที่ 1: รับข้อมูลเมตา XMP
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// เริ่มต้นสตรีมไฟล์ EPS อินพุต
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// รับข้อมูลเมตา XMP หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP เราจะได้ไฟล์ใหม่ที่เต็มไปด้วยค่าจากความคิดเห็นข้อมูลเมตา PS (%%Creator, %%CreateDate, %%Title ฯลฯ)
XmpMetadata xmp = document.getXmpMetadata();
```
## ขั้นตอนที่ 2: เพิ่มคุณสมบัติวันที่
```java
// เพิ่มคุณสมบัติวันที่ค่า "xmp:Date1"
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## ขั้นตอนที่ 3: เพิ่มคุณสมบัติจำนวนเต็ม
```java
// เพิ่มค่าคุณสมบัติจำนวนเต็ม "xmp:Intg1"
xmp.put("xmp:Intg1", new XmpValue(111));
```
## ขั้นตอนที่ 4: เพิ่มคุณสมบัติสองเท่า
```java
// เพิ่มค่าคุณสมบัติคู่ "xmp:Double1"
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## ขั้นตอนที่ 5: เพิ่มคุณสมบัติสตริง
```java
// เพิ่มคุณสมบัติสตริงค่า "xmp:String1"
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## ขั้นตอนที่ 6: บันทึกเอกสาร
```java
// เริ่มต้นสตรีมไฟล์ EPS เอาต์พุต
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## ขั้นตอนที่ 7: ปิดสตรีม
```java
// ปิดสตรีม EPS อินพุต
psStream.close();
```
## บทสรุป
Aspose.Page สำหรับ Java ช่วยให้กระบวนการจัดการข้อมูลเมตา XMP ในไฟล์ EPS ง่ายขึ้น ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถเพิ่มคุณสมบัติง่ายๆ เพื่อปรับปรุงข้อมูลเมตาของเอกสารของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Page รองรับ Java เป็นหลัก แต่มีเวอร์ชันสำหรับภาษาอื่น เช่น .NET
### Aspose.Page สำหรับ Java ทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถสำรวจคุณสมบัติของ Aspose.Page ได้โดยการทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารประกอบโดยละเอียดสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/page/java/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 สามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อ Aspose.Page สำหรับ Java ได้ที่ไหน
 ท่านสามารถซื้อสินค้าได้[ที่นี่](https://purchase.aspose.com/buy).