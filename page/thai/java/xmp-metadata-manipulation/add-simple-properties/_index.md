---
date: 2025-12-20
description: เรียนรู้วิธีสร้างเมตาดาต้า XMP ในไฟล์ EPS ด้วย Aspose.Page สำหรับ Java
  คู่มือแบบขั้นตอนต่อขั้นตอนเพื่อเพิ่มคุณสมบัติ XMP อย่างง่ายโดยโปรแกรม
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: วิธีสร้างไฟล์ EPS ที่มีเมตาดาต้า XMP ด้วย Java
url: /th/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มคุณสมบัติแบบง่ายใน XMP ด้วย Java

## บทนำ
ในกระบวนการทำงานกับเอกสารสมัยใหม่ การสามารถ **สร้างไฟล์ XMP metadata EPS** ด้วยโปรแกรมได้ทำให้คุณควบคุมวิธีการอธิบาย ค้นหา และเก็บถาวรกราฟิกของคุณได้อย่างเต็มที่ ด้วย Aspose.Page for Java คุณสามารถอ่าน แก้ไข และเขียนแพ็กเกจ XMP ภายในเอกสาร EPS ได้โดยไม่ต้องออกจากสภาพแวดล้อมของ Java ในบทแนะนำนี้ เราจะพาคุณผ่านขั้นตอนที่แน่นอนเพื่อเพิ่มคุณสมบัติ XMP อย่างง่ายลงในไฟล์ EPS เพื่อให้คุณสามารถเสริมกราฟิกของคุณด้วยเมตาดาต้าตามต้องการได้อย่างรวดเร็วและเชื่อถือได้

## คำตอบสั้น
- **“create xmp metadata eps” หมายถึงอะไร?** การเพิ่มแพ็กเกจ XMP (เมตาดาต้าแบบ XML) ลงในไฟล์ EPS  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java (ดาวน์โหลดได้จากเว็บไซต์ Aspose)  
- **ต้องใช้ไลเซนส์สำหรับการทดสอบหรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ต้องใช้โค้ดกี่บรรทัด?** น้อยกว่า 30 บรรทัดของ Java พร้อมกับคำสั่ง import บางบรรทัด  
- **สามารถเพิ่มประเภทข้อมูลอื่นได้หรือไม่?** ได้ – วันที่ จำนวนเต็ม จำนวนทศนิยม สตริง และแม้แต่แอเรย์ก็รองรับ

## create xmp metadata eps คืออะไร?
XMP (Extensible Metadata Platform) เป็นมาตรฐานสำหรับฝังเมตาดาต้าครบถ้วนภายในไฟล์ เมื่อคุณ **create XMP metadata EPS** คุณจะฝังแพ็กเกจ XML ลงในเอกสาร EPS (Encapsulated PostScript) ทำให้แอปพลิเคชันต่อไปสามารถอ่านผู้สร้าง วันที่สร้าง แท็กที่กำหนดเอง และข้อมูลอื่น ๆ ได้

## ทำไมต้องเพิ่ม XMP metadata ลงในไฟล์ EPS?
- **การค้นหา:** ทำให้ระบบ DAM สามารถทำดัชนีอัตโนมัติได้  
- **การปฏิบัติตาม:** เก็บข้อมูลกฎหมายหรือข้อมูลลิขสิทธิ์โดยตรงในไฟล์  
- **การอัตโนมัติ:** ให้ไพป์ไลน์ต่อไปทำการตัดสินใจบนพื้นฐานของข้อมูลที่ฝังไว้  
- **การพกพา:** เมตาดาต้าจะเดินทางพร้อมกับ EPS ทำให้ความสอดคล้องข้ามแพลตฟอร์มได้รับการรับประกัน

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลด **[ที่นี่](https://releases.aspose.com/page/java/)**  
- ตัวอย่างไฟล์ EPS ที่มีเมตาดาต้า หากไม่มี คุณสามารถใช้ไฟล์ **`xmp3.eps`** ที่ให้มาด้วยได้

## นำเข้าแพ็กเกจ
แรกสุด ให้นำเข้าคลาสที่จำเป็น การ import จะเหมือนกับตัวอย่างต้นฉบับโดยไม่มีการเปลี่ยนแปลง:

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

## ขั้นตอนที่ 1: โหลดเอกสาร EPS และดึง XMP metadata
เราเปิดไฟล์ EPS สร้างอินสแตนซ์ `PsDocument` และดึง (หรือสร้าง) แพ็กเกจ XMP:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## ขั้นตอนที่ 2: เพิ่มคุณสมบัติแบบวันที่
การเพิ่มวันที่ทำได้ง่ายโดยสร้างอ็อบเจกต์ `Date` แล้วใส่ลงในแผนที่ XMP:

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## ขั้นตอนที่ 3: เพิ่มคุณสมบัติแบบจำนวนเต็ม
คุณสามารถเก็บตัวระบุเชิงตัวเลขหรือหมายเลขเวอร์ชันโดยใช้ค่า integer:

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## ขั้นตอนที่ 4: เพิ่มคุณสมบัติแบบ Double
ตัวเลขแบบ floating‑point มีประโยชน์สำหรับการวัดหรือการให้คะแนน:

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## ขั้นตอนที่ 5: เพิ่มคุณสมบัติแบบสตริง
แท็กข้อความที่กำหนดเอง (เช่น รหัสโครงการ) จะถูกเก็บเป็นสตริง:

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## ขั้นตอนที่ 6: บันทึกไฟล์ EPS ที่อัปเดต
หลังจากเพิ่มคุณสมบัติต่าง ๆ แล้ว ให้เขียนเอกสารกลับไปยังดิสก์:

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## ขั้นตอนที่ 7: ทำความสะอาดทรัพยากร
ควรปิดสตรีมอินพุตเสมอเพื่อหลีกเลี่ยงการรั่วไหลของไฟล์แฮนด์เดิล:

```java
// Close input EPS stream
psStream.close();
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **Null XMP metadata** | ไฟล์ EPS ไม่มีแพ็กเกจ XMP และไลบรารีไม่สามารถสรุปคอมเมนต์ PS ได้ | ตรวจสอบให้ไฟล์ EPS ต้นทางมีคอมเมนต์ PS อย่างน้อยหนึ่งรายการ (เช่น `%%Creator`). ไลบรารีจะสร้างแพ็กเกจ XMP ขั้นพื้นฐานโดยอัตโนมัติ |
| **Time zone mismatch** | วันที่แสดงผลช้าหรือเร็วเมื่อเปิดในแอปพลิเคชันอื่น | ตั้งค่า `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` ก่อนสร้างอ็อบเจกต์ `Date` ตามที่แสดงในขั้นตอน 2 |
| **License exception** | รันไทม์โยน `LicenseException` | ใช้ไลเซนส์ Aspose.Page ที่ถูกต้องก่อนเรียก API หรือรันในโหมดทดลองเพื่อประเมิน |

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณจะรู้วิธี **create XMP metadata EPS** ด้วย Aspose.Page for Java การเพิ่มคุณสมบัติแบบง่ายเช่น วันที่ จำนวนเต็ม จำนวนทศนิยม และสตริงนั้นทำได้ไม่ยาก และไฟล์ EPS ที่ได้จะมีเมตาดาต้าที่สมบูรณ์และค้นหาได้ ซึ่งเป็นประโยชน์ต่อกระบวนการทำงานต่อไปทุกขั้นตอน

## คำถามที่พบบ่อย
### สามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?
Aspose.Page รองรับหลัก ๆ ที่ Java แต่ก็มีเวอร์ชันสำหรับภาษาอื่นเช่น .NET

### มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?
มี คุณสามารถสำรวจคุณสมบัติของ Aspose.Page ได้โดยรับการทดลองใช้ [ที่นี่](https://releases.aspose.com/)

### จะหาเอกสารประกอบละเอียดสำหรับ Aspose.Page for Java ได้จากที่ไหน?
เอกสารพร้อมใช้งาน [ที่นี่](https://reference.aspose.com/page/java/)

### จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
สามารถขอรับไลเซนส์ชั่วคราว [ที่นี่](https://purchase.aspose.com/temporary-license/)

### จะซื้อ Aspose.Page for Java ได้จากที่ไหน?
คุณสามารถสั่งซื้อผลิตภัณฑ์ [ที่นี่](https://purchase.aspose.com/buy)

---

**อัปเดตล่าสุด:** 2025-12-20  
**ทดสอบด้วย:** Aspose.Page for Java 24.11 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}