---
title: รับข้อมูลเมตาจาก XMP โดยใช้ Java
linktitle: รับข้อมูลเมตาจาก XMP โดยใช้ Java
second_title: Aspose.Page Java API
description: ปลดล็อกพลังของ Aspose.Page สำหรับ Java เพื่อแยกข้อมูลเมตา XMP ได้อย่างง่ายดาย ยกระดับการวิเคราะห์เอกสารด้วยคำแนะนำทีละขั้นตอนของเรา!
type: docs
weight: 18
url: /th/java/xmp-metadata-manipulation/get-metadata/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับการใช้ Aspose.Page สำหรับ Java เพื่อแยกข้อมูลเมตาจากไฟล์ XMP XMP (Extensible Metadata Platform) มอบวิธีการมาตรฐานในการจัดเก็บข้อมูลเมตาในไฟล์ บทช่วยสอนนี้มุ่งเน้นไปที่การดึงข้อมูลที่จำเป็นจาก XMP โดยใช้ Java โดยนำเสนอข้อมูลเชิงลึกเกี่ยวกับรายละเอียดเอกสาร
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนเครื่องของคุณแล้ว
-  Aspose.Page สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page ซึ่งคุณสามารถหาได้[ที่นี่](https://releases.aspose.com/page/java/).
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็น:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## ขั้นตอนที่ 1: เริ่มต้นอินพุตไฟล์ EPS สตรีม
เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณและเริ่มต้นสตรีมไฟล์ EPS อินพุต
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## ขั้นตอนที่ 2: รับข้อมูลเมตา XMP
ดึงข้อมูลเมตา XMP จากไฟล์ EPS หากไฟล์ไม่มีข้อมูลเมตา XMP ไฟล์ใหม่จะถูกสร้างขึ้นพร้อมค่าจากความคิดเห็นข้อมูลเมตา PS
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## ขั้นตอนที่ 3: แยกข้อมูล CreatorTool
ตรวจสอบและพิมพ์ค่า "CreatorTool" จากข้อมูลเมตา XMP
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## ขั้นตอนที่ 4: แยกข้อมูล CreateDate
ตรวจสอบและพิมพ์ค่า "CreateDate" จากข้อมูลเมตา XMP
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## ขั้นตอนที่ 5: ดึงความกว้างของภาพขนาดย่อ
หากมีภาพขนาดย่อ ให้แยกและพิมพ์ความกว้างของภาพขนาดย่อภาพแรก
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## ขั้นตอนที่ 6: แยกข้อมูลรูปแบบ
ตรวจสอบและพิมพ์ค่า "รูปแบบ" จากข้อมูลเมตา XMP
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## ขั้นตอนที่ 7: รับ DocumentID
ตรวจสอบและพิมพ์ค่า "DocumentID" จากข้อมูลเมตา XMP
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีแยกข้อมูลเมตา XMP โดยใช้ Aspose.Page สำหรับ Java เรียบร้อยแล้ว คู่มือนี้ให้ภาพรวมที่ครอบคลุมของกระบวนการ เพื่อให้มั่นใจว่าคุณสามารถดึงข้อมูลสำคัญจากเอกสารของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
 ใช่ Aspose.Page รองรับหลายภาษา รวมถึง Java, .NET และอื่นๆ อีกมากมาย ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/page/java/) เพื่อดูรายละเอียด
### Aspose.Page สำหรับ Java ทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อสนับสนุนชุมชน
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### มีแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Page สำหรับ Java หรือไม่
 สำรวจให้ครบถ้วน[เอกสารประกอบ](https://reference.aspose.com/page/java/) และดาวน์โหลดห้องสมุด[ที่นี่](https://releases.aspose.com/page/java/).