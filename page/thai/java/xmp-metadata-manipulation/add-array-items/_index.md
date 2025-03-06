---
title: เพิ่มรายการอาร์เรย์ในข้อมูลเมตา XMP โดยใช้ Java
linktitle: เพิ่มรายการอาร์เรย์ในข้อมูลเมตา XMP โดยใช้ Java
second_title: Aspose.Page Java API
description: ปรับปรุงไฟล์ EPS ด้วย Aspose.Page สำหรับ Java เรียนรู้การเพิ่มรายการอาร์เรย์ลงในข้อมูลเมตา XMP ได้อย่างง่ายดาย ทำตามคำแนะนำทีละขั้นตอนของเราทันที!
weight: 10
url: /th/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรายการอาร์เรย์ในข้อมูลเมตา XMP โดยใช้ Java

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับการใช้ Aspose.Page สำหรับ Java เพื่อเพิ่มรายการอาร์เรย์ในข้อมูลเมตา XMP Aspose.Page เป็นไลบรารี Java ที่ทรงพลังที่ให้คุณจัดการและทำงานกับรูปแบบเอกสารต่าง ๆ รวมถึงไฟล์ EPS ในบทช่วยสอนนี้ เราจะเน้นไปที่งานเฉพาะในการเพิ่มรายการอาร์เรย์ในข้อมูลเมตา XMP โดยใช้ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้ง Aspose.Page สำหรับไลบรารี Java แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ไฟล์ EPS ที่ถูกต้องซึ่งมีข้อมูลเมตา XMP หรือความคิดเห็นข้อมูลเมตา PS ที่มีอยู่
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณต้องนำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Page รวมบรรทัดต่อไปนี้ไว้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
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
ในขั้นตอนนี้ เราจะดึงข้อมูลเมตา XMP ที่มีอยู่จากไฟล์ EPS หากไฟล์ EPS ไม่มีข้อมูลเมตา XMP Aspose.Page จะสร้างข้อมูลใหม่และเติมค่าจากความคิดเห็นข้อมูลเมตา PS
## ขั้นตอนที่ 2: เพิ่มรายการอาร์เรย์ "dc: title"
```java
// เพิ่มรายการอาร์เรย์ "dc:title" อีกหนึ่งรายการ
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
ตอนนี้ เราได้เพิ่มรายการอาร์เรย์ใหม่ให้กับคุณสมบัติ "dc:title" ในข้อมูลเมตา XMP แทนที่ "NewTitle" ด้วยชื่อที่ต้องการ
## ขั้นตอนที่ 3: เพิ่มรายการอาร์เรย์ "dc:creator"
```java
// เพิ่มรายการอาร์เรย์ "dc:creator" อีกหนึ่งรายการ
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
ในทำนองเดียวกัน เราเพิ่มรายการอาร์เรย์ใหม่ให้กับคุณสมบัติ "dc:creator" ในข้อมูลเมตา XMP แทนที่ "NewCreator" ด้วยข้อมูลผู้สร้างที่ต้องการ
## ขั้นตอนที่ 4: เริ่มต้นสตรีมไฟล์ EPS เอาท์พุต
```java
// เริ่มต้นสตรีมไฟล์ EPS เอาต์พุต
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
เตรียมเอาต์พุตไฟล์ EPS สตรีมซึ่งเอกสารที่แก้ไขซึ่งมีข้อมูลเมตา XMP ที่อัปเดตจะถูกบันทึก
## ขั้นตอนที่ 5: บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง
```java
//บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่เปลี่ยนแปลง
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
บันทึกเอกสารด้วยข้อมูลเมตา XMP ที่อัปเดตไปยังไฟล์ EPS เอาท์พุต
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มรายการอาร์เรย์ในข้อมูลเมตา XMP โดยใช้ Aspose.Page สำหรับ Java เรียบร้อยแล้ว ไลบรารีอันทรงพลังนี้ช่วยลดความยุ่งยากในการจัดการไฟล์ EPS และมีฟังก์ชันการทำงานที่กว้างขวางสำหรับการประมวลผลเอกสาร
## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Page สำหรับ Java กับรูปแบบเอกสารอื่นได้หรือไม่
ใช่ Aspose.Page รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง EPS, PDF และ XPS
### มีการทดลองใช้ฟรีสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารสำหรับ Aspose.Page สำหรับ Java ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/page/java/).
### ฉันจะซื้อ Aspose.Page สำหรับ Java ได้อย่างไร
 ท่านสามารถซื้อสินค้าได้[ที่นี่](https://purchase.aspose.com/buy).
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.Page สำหรับ Java หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
