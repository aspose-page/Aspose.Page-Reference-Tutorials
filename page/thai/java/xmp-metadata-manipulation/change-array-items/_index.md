---
title: เปลี่ยนรายการอาร์เรย์ใน XMP โดยใช้ Java
linktitle: เปลี่ยนรายการอาร์เรย์ใน XMP โดยใช้ Java
second_title: Aspose.Page Java API
description: เรียนรู้วิธีเปลี่ยนรายการอาร์เรย์ใน XMP โดยใช้ Aspose.Page สำหรับ Java แก้ไขข้อมูลเมตาได้อย่างง่ายดายด้วยคำแนะนำทีละขั้นตอนของเรา ปรับปรุงเอกสาร EPS ของคุณทันที!
weight: 15
url: /th/java/xmp-metadata-manipulation/change-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เปลี่ยนรายการอาร์เรย์ใน XMP โดยใช้ Java

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมเกี่ยวกับการเปลี่ยนรายการอาร์เรย์ใน XMP โดยใช้ Aspose.Page สำหรับ Java! Aspose.Page เป็นไลบรารี Java ที่ทรงพลังที่ช่วยให้คุณทำงานกับเมตาดาต้า XMP ในไฟล์ EPS ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแก้ไขรายการอาร์เรย์ภายในข้อมูลเมตา XMP ซึ่งช่วยคุณปรับปรุงและปรับแต่งเอกสาร EPS ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  ไลบรารี Aspose.Page สำหรับ Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/java/).
## แพ็คเกจนำเข้า
ในการเริ่มต้น เรามานำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณกัน ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Page รวมอยู่ในโปรเจ็กต์ของคุณ
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## ขั้นตอนที่ 1: รับข้อมูลเมตา XMP
ขั้นแรก ให้ดึงข้อมูลเมตา XMP จากไฟล์ EPS ของคุณ หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP ไฟล์ใหม่จะถูกสร้างขึ้นโดยมีค่าจากความคิดเห็นข้อมูลเมตา PS เช่น %%Creator, %%CreateDate, %%Title เป็นต้น
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// เริ่มต้นสตรีมไฟล์ EPS อินพุต
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// รับข้อมูลเมตา XMP หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP ไฟล์ใหม่จะเต็มไปด้วยค่าจากความคิดเห็นข้อมูลเมตา PS
XmpMetadata xmp = document.getXmpMetadata();
```
## ขั้นตอนที่ 2: ตั้งค่ารายการอาร์เรย์ "dc: title"
ตอนนี้ เรามาตั้งค่ารายการอาร์เรย์ "dc:title" ที่ดัชนี 0 ด้วยค่าใหม่
```java
// ตั้งค่ารายการอาร์เรย์ "dc:title" ตามดัชนี 0
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## ขั้นตอนที่ 3: ตั้งค่ารายการอาร์เรย์ "dc:creator"
ในทำนองเดียวกัน ให้ตั้งค่ารายการอาร์เรย์ "dc:creator" ที่ดัชนี 0 ด้วยค่าผู้สร้างใหม่
```java
// ตั้งค่ารายการอาร์เรย์ "dc:creator" ตามดัชนี 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## ขั้นตอนที่ 4: เริ่มต้นสตรีมไฟล์ EPS เอาท์พุต
เตรียมสตรีมไฟล์ EPS เอาท์พุตซึ่งเอกสารที่แก้ไขจะถูกบันทึก
```java
// เริ่มต้นสตรีมไฟล์ EPS เอาต์พุต
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## ขั้นตอนที่ 5: บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง
บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่อัปเดต
```java
//บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเปลี่ยนรายการอาร์เรย์ใน XMP โดยใช้ Aspose.Page สำหรับ Java เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอน เพื่อให้มั่นใจว่าคุณสามารถปรับปรุงเอกสาร EPS ของคุณได้อย่างง่ายดายด้วยเมตาดาต้าที่ปรับแต่งเอง

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Page ได้รับการออกแบบมาสำหรับ Java เป็นหลัก แต่ Aspose มีไลบรารีที่คล้ายกันสำหรับภาษาอื่น
### ฉันจะหาเอกสารประกอบโดยละเอียดสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/page/java/).
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อ Aspose.Page สำหรับ Java เวอร์ชันเต็มได้ที่ไหน
 คุณสามารถซื้อเวอร์ชันเต็มได้[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
