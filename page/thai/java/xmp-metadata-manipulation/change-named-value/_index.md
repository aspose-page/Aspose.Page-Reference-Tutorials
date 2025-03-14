---
title: เปลี่ยนค่าชื่อใน XMP โดยใช้ Java
linktitle: เปลี่ยนค่าชื่อใน XMP โดยใช้ Java
second_title: Aspose.Page Java API
description: ค้นพบ Aspose.Page สำหรับ Java - เปลี่ยนแปลงข้อมูลเมตา XMP ในไฟล์ EPS ได้อย่างง่ายดายด้วยคำแนะนำทีละขั้นตอนเพื่อการประมวลผลเอกสารที่มีประสิทธิภาพยิ่งขึ้น
weight: 16
url: /th/java/xmp-metadata-manipulation/change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เปลี่ยนค่าชื่อใน XMP โดยใช้ Java

ในขอบเขตของการจัดการเอกสาร Aspose.Page สำหรับ Java มีความโดดเด่นในฐานะเครื่องมืออันทรงพลัง ช่วยให้นักพัฒนาสามารถทำงานกับเมตาดาต้า XMP ในไฟล์ EPS ได้อย่างราบรื่น คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการเปลี่ยนแปลงค่าที่มีชื่อใน XMP โดยใช้ Aspose.Page สำหรับ Java ก่อนที่เราจะเจาะลึกรายละเอียดเรามาเริ่มด้วยการแนะนำกันก่อน
## การแนะนำ
Aspose.Page สำหรับ Java เป็นไลบรารี Java ที่มีประสิทธิภาพซึ่งอำนวยความสะดวกในการจัดการและประมวลผลไฟล์ EPS เมื่อพูดถึงการจัดการข้อมูลเมตา XMP ภายในไฟล์เหล่านี้ Aspose.Page เสริมศักยภาพให้กับนักพัฒนาด้วยชุดคุณสมบัติที่ครอบคลุม ในบทช่วยสอนนี้ เราจะมุ่งเน้นไปที่การเปลี่ยนแปลงค่าที่มีชื่อใน XMP โดยเสนอคำแนะนำที่ชัดเจนและกระชับสำหรับนักพัฒนาที่ต้องการปรับปรุงความสามารถในการประมวลผลเอกสารของตน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนเครื่องของคุณ
2.  Aspose.Page สำหรับไลบรารี Java: ดาวน์โหลดและรวม Aspose.Page สำหรับไลบรารี Java เข้ากับโปรเจ็กต์ของคุณ คุณสามารถค้นหาห้องสมุดและเอกสารรายละเอียดได้[ที่นี่](https://reference.aspose.com/page/java/).
3. ไฟล์ EPS ตัวอย่าง: เตรียมไฟล์ EPS ตัวอย่างให้พร้อมสำหรับการทดลอง หากคุณไม่มี คุณสามารถใช้ไฟล์ตัวอย่างที่ให้มาชื่อ "xmp4.eps"
## แพ็คเกจนำเข้า
ในการเริ่มต้นกระบวนการ ให้นำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณ แพ็คเกจเหล่านี้จำเป็นสำหรับการโต้ตอบกับ Aspose.Page สำหรับ Java รวมบรรทัดต่อไปนี้ไว้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
ตอนนี้ เรามาแจกแจงขั้นตอนการเปลี่ยนแปลงค่าที่มีชื่อใน XMP โดยใช้ Aspose.Page สำหรับ Java ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: เริ่มต้นอินพุตไฟล์ EPS สตรีม
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
        
// เริ่มต้นสตรีมไฟล์ EPS อินพุต
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```
## ขั้นตอนที่ 2: เริ่มต้น PsDocument
```java
PsDocument document = new PsDocument(psStream);
```
## ขั้นตอนที่ 3: รับข้อมูลเมตา XMP
```java
// รับข้อมูลเมตา XMP หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP เราจะได้ไฟล์ใหม่ที่เต็มไปด้วยค่าจากความคิดเห็นข้อมูลเมตา PS (%%Creator, %%CreateDate, %%Title ฯลฯ)
XmpMetadata xmp = document.getXmpMetadata();
```
## ขั้นตอนที่ 4: ตั้งค่าใหม่ใน XMP
```java
// ตั้งค่าสตริงใหม่ "นิ้ว" สำหรับค่าชื่อ "stDim:unit" ของโครงสร้าง "xmpTPg:MaxPageSize"
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```
## ขั้นตอนที่ 5: เริ่มต้นสตรีมไฟล์ EPS เอาท์พุต
```java
// เริ่มต้นสตรีมไฟล์ EPS เอาต์พุต
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```
## ขั้นตอนที่ 6: บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง
```java
//บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## ขั้นตอนที่ 7: ปิดอินพุต EPS Stream
```java
// ปิดสตรีม EPS อินพุต
psStream.close();
```
คำแนะนำทีละขั้นตอนนี้ช่วยให้มั่นใจได้ถึงแนวทางที่เป็นระบบในการเปลี่ยนแปลงค่าที่กำหนดชื่อใน XMP โดยใช้ Aspose.Page สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น
## บทสรุป
โดยสรุป Aspose.Page สำหรับ Java ช่วยให้กระบวนการทำงานกับข้อมูลเมตา XMP ในไฟล์ EPS ง่ายขึ้น บทช่วยสอนนี้ช่วยให้คุณมีความรู้ในการเปลี่ยนแปลงค่าที่มีชื่อใน XMP ได้อย่างมีประสิทธิภาพ ซึ่งช่วยเพิ่มความสามารถในการประมวลผลเอกสารของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Page รองรับ Java เป็นหลัก แต่ Aspose มีไลบรารีที่คล้ายกันสำหรับภาษาการเขียนโปรแกรมต่างๆ
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถทดลองใช้ Aspose.Page สำหรับ Java ได้ฟรี[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนและการสนทนาเพิ่มเติมเกี่ยวกับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อ Aspose.Page สำหรับ Java ได้ที่ไหน
 หากต้องการซื้อ Aspose.Page สำหรับ Java โปรดไปที่[หน้าซื้อ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
