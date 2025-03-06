---
title: เปลี่ยนค่าใน XMP โดยใช้ Java
linktitle: เปลี่ยนค่าใน XMP โดยใช้ Java
second_title: Aspose.Page Java API
description: ปรับปรุงเอกสาร EPS ด้วย Aspose.Page สำหรับ Java ปรับเปลี่ยนข้อมูลเมตา XMP ได้อย่างง่ายดายเพื่อเนื้อหาที่ได้รับการปรับแต่งและเป็นมืออาชีพ #การพัฒนาจาวา
weight: 17
url: /th/java/xmp-metadata-manipulation/change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เปลี่ยนค่าใน XMP โดยใช้ Java

## การแนะนำ
ในขอบเขตของการประมวลผลและการจัดการเอกสาร Aspose.Page สำหรับ Java โดดเด่นในฐานะเครื่องมืออันทรงพลัง บทช่วยสอนนี้จะเจาะลึกกระบวนการเปลี่ยนค่า XMP (Extensible Metadata Platform) ในเอกสาร EPS (Encapsulated PostScript) โดยใช้ Java กับไลบรารี Aspose.Page ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณจะได้เรียนรู้วิธีแก้ไขข้อมูลเมตาอย่างง่ายดาย เพื่อให้มั่นใจว่าเอกสารของคุณได้รับการปรับแต่งให้ตรงกับความต้องการเฉพาะของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนา Java ที่ใช้งานได้บนเครื่องของคุณ
2.  Aspose.Page สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.Page สำหรับไลบรารี Java คุณสามารถค้นหาแพ็คเกจที่จำเป็นได้[ที่นี่](https://releases.aspose.com/page/java/).
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ แพ็คเกจเหล่านี้มีความสำคัญสำหรับการโต้ตอบและจัดการเอกสาร EPS
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
ดึงข้อมูลเมตา XMP จากเอกสาร EPS หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP ไฟล์ใหม่จะถูกสร้างขึ้นโดยมีค่าจากความคิดเห็นข้อมูลเมตา PS เช่น %%Creator, %%CreateDate และ %%Title
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// เริ่มต้นสตรีมไฟล์ EPS อินพุต
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// รับข้อมูลเมตา XMP หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP ไฟล์ใหม่จะถูกสร้างขึ้นโดยมีค่าจากความคิดเห็นข้อมูลเมตา PS
XmpMetadata xmp = document.getXmpMetadata();
```
## ขั้นตอนที่ 2: เปลี่ยนค่า "ModifyDate"
แก้ไขค่า "ModifyDate" ในข้อมูลเมตา XMP เพื่อให้สะท้อนถึงวันที่ที่ต้องการ
```java
// เปลี่ยนค่า "ModifyDate"
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## ขั้นตอนที่ 3: เปลี่ยนค่า "ผู้สร้าง"
อัปเดตค่า "ผู้สร้าง" ในข้อมูลเมตา XMP เพื่อระบุผู้สร้างเอกสาร
```java
// เปลี่ยนค่า "ผู้สร้าง"
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## ขั้นตอนที่ 4: เปลี่ยนค่า "ชื่อ"
แก้ไขค่า "ชื่อเรื่อง" ในข้อมูลเมตา XMP เพื่อตั้งชื่อที่เหมาะสมสำหรับเอกสาร
```java
//เปลี่ยนค่า "ชื่อ"
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## ขั้นตอนที่ 5: บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง
บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่อัปเดตเป็นไฟล์ EPS ใหม่
```java
// เริ่มต้นสตรีมไฟล์ EPS เอาต์พุต
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## บทสรุป
ยินดีด้วย! คุณได้สำรวจกระบวนการเปลี่ยนค่า XMP ในเอกสาร EPS โดยใช้ Aspose.Page สำหรับ Java สำเร็จแล้ว บทช่วยสอนนี้ช่วยให้คุณมีความรู้ในการแก้ไขข้อมูลเมตา เพื่อให้มั่นใจว่าเอกสารของคุณสอดคล้องกับข้อกำหนดเฉพาะของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ถาม: ฉันจะจัดการกับการพิจารณาเขตเวลาเมื่อแก้ไขค่า XMP ได้อย่างไร
 ใช้ประโยชน์`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` เพื่อให้มั่นใจถึงความสอดคล้องในการตั้งค่าเขตเวลา
### ถาม: ฉันสามารถเปลี่ยนค่า XMP หลายค่าในการดำเนินการครั้งเดียวได้หรือไม่
 ใช่ โดยใช้`put` สำหรับแต่ละค่าที่ต้องการ คุณสามารถแก้ไขค่า XMP หลายค่าพร้อมกันได้
### ถาม: ฉันจะหาเอกสารเพิ่มเติมสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 สำรวจเอกสารที่ครอบคลุม[ที่นี่](https://reference.aspose.com/page/java/).
### ถาม: Aspose.Page สำหรับ Java มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 ได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
