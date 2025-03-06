---
title: เพิ่มข้อมูลเมตาใน XMP โดยใช้ Java
linktitle: เพิ่มข้อมูลเมตาใน XMP โดยใช้ Java
second_title: Aspose.Page Java API
description: สำรวจการบูรณาการอย่างราบรื่นของ Aspose.Page สำหรับ Java และเรียนรู้วิธีเพิ่มข้อมูลเมตา XMP ให้กับไฟล์ EPS ของคุณได้อย่างง่ายดาย ยกระดับเกมการจัดการเอกสารของคุณวันนี้!
weight: 11
url: /th/java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มข้อมูลเมตาใน XMP โดยใช้ Java

## การแนะนำ
คุณต้องการปรับปรุงข้อมูลเมตาของเอกสารของคุณด้วยการเพิ่มข้อมูล XMP โดยใช้ Java หรือไม่? ไม่ต้องมองอีกต่อไป! คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดขั้นตอนการเพิ่มข้อมูลเมตาลงในไฟล์ EPS โดยใช้ Aspose.Page สำหรับไลบรารี Java Aspose.Page เป็นเครื่องมืออันทรงพลังที่ทำให้งานจัดการเอกสารในแอปพลิเคชัน Java ง่ายขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Page สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/page/java/).
- ไฟล์ EPS ที่คุณต้องการแก้ไข
## แพ็คเกจนำเข้า
ประการแรก นำเข้าแพ็คเกจที่จำเป็นไปยังโปรแกรม Java ของคุณ:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## ขั้นตอนที่ 1: รับข้อมูลเมตา XMP
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// เริ่มต้นสตรีมไฟล์ EPS อินพุต
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// รับข้อมูลเมตา XMP หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP ไฟล์ใหม่จะถูกสร้างขึ้นโดยใช้ค่าจากความคิดเห็นข้อมูลเมตา PS (%%Creator, %%CreateDate, %%Title ฯลฯ)
XmpMetadata xmp = document.getXmpMetadata();
```
ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Document Directory" ด้วยเส้นทางจริงที่ใช้จัดเก็บเอกสารของคุณ

## ขั้นตอนที่ 2: รับค่า CreatorTool
```java
// รับค่า "CreatorTool"
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## ขั้นตอนที่ 3: ดึงค่า CreateDate
```java
// รับค่า "CreateDate"
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## ขั้นตอนที่ 4: รับค่าชื่อ
```java
// รับค่า "ชื่อ"
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## ขั้นตอนที่ 5: ดึงค่ารูปแบบ
```java
//รับค่า "รูปแบบ"
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## ขั้นตอนที่ 6: รับมูลค่าผู้สร้าง
```java
// รับคุณค่า "ผู้สร้าง"
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## ขั้นตอนที่ 7: ดึงค่า MetadataDate
```java
// รับค่า "MetadataDate"
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## ขั้นตอนที่ 8: บันทึกเอกสารด้วยเมตาดาต้า XMP ใหม่
```java
// เริ่มต้นสตรีมไฟล์ EPS เอาต์พุต
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// บันทึกเอกสารด้วยข้อมูลเมตา XMP ใหม่
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
สุดท้ายนี้อย่าลืมปิดอินพุต EPS stream:
```java
// ปิดสตรีม EPS อินพุต
psStream.close();
```
ตอนนี้ คุณได้เพิ่มข้อมูลเมตาลงในไฟล์ EPS ของคุณโดยใช้ Aspose.Page สำหรับ Java สำเร็จแล้ว!
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการเพิ่มข้อมูลเมตา XMP ลงในไฟล์ EPS โดยใช้ Aspose.Page สำหรับไลบรารี Java เครื่องมืออันทรงพลังนี้ช่วยให้คุณสามารถจัดการเอกสารได้อย่างราบรื่น ช่วยเพิ่มประสบการณ์การจัดการเอกสารโดยรวมของคุณ
## คำถามที่พบบ่อย
### ถาม: Aspose.Page สำหรับ Java ใช้งานได้ฟรีหรือไม่
 ตอบ: Aspose.Page สำหรับ Java เป็นผลิตภัณฑ์เชิงพาณิชย์ คุณสามารถสำรวจคุณลักษณะต่างๆ ได้ผ่านการทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 ตอบ: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/page/java/).
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 ตอบ: คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: Aspose.Page สำหรับ Java รองรับไฟล์รูปแบบใดบ้าง
ตอบ: Aspose.Page สำหรับ Java รองรับรูปแบบต่างๆ รวมถึง EPS, PDF และ XPS
### ถาม: ฉันสามารถซื้อ Aspose.Page สำหรับ Java ได้หรือไม่
 ตอบ: ได้ คุณสามารถซื้อ Aspose.Page สำหรับ Java ได้[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
