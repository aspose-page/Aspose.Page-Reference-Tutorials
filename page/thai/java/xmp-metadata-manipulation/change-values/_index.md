---
date: 2025-12-21
description: เรียนรู้วิธีที่ Aspose.Page แก้ไข XMP ในเอกสาร EPS ด้วย Java ปรับปรุงเมตาดาต้าอย่างรวดเร็วด้วย
  Aspose.Page สำหรับ Java.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page แก้ไข xmp – เปลี่ยนค่าภายใน XMP ด้วย Java
url: /th/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเปลี่ยนค่าใน XMP ด้วย Java

## บทนำ
หากคุณต้องการ **aspose.page modify xmp** ข้อมูลภายในไฟล์ EPS คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนที่จำเป็นในการอ่าน, ปรับปรุง, และบันทึกค่า XMP (Extensible Metadata Platform) ด้วยไลบรารี Aspose.Page สำหรับ Java เมื่อเสร็จสิ้น คุณจะสามารถปรับแต่งเมตาดาต้าเอกสาร—เช่นผู้สร้าง, ชื่อเรื่อง, และวันที่แก้ไข—ให้ตรงกับความต้องการของโครงการของคุณได้

## คำตอบอย่างรวดเร็ว
- **“aspose.page modify xmp” ทำอะไร?** มันช่วยให้คุณอ่านและเขียนเมตาดาต้า XMP ในไฟล์ EPS ผ่าน Aspose.Page Java API  
- **ต้องใช้เวอร์ชันไลบรารีใด?** เวอร์ชัน Aspose.Page for Java ใดก็ได้ที่เป็นรุ่นล่าสุด (API มีความเสถียรข้ามเวอร์ชัน)  
- **ต้องมีลิขสิทธิ์เพื่อรันตัวอย่างหรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการประเมิน; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถเปลี่ยนหลายฟิลด์ XMP พร้อมกันได้หรือไม่?** ได้—เรียก `put` สำหรับแต่ละฟิลด์ก่อนบันทึกเอกสาร  
- **ต้องจัดการเขตเวลาไหม?** การตั้งค่าเขตเวลาเริ่มต้น (เช่น UTC) จะทำให้ค่าที่เป็นวันที่สอดคล้องกัน

## XMP คืออะไรและทำไมต้องแก้ไข
XMP (Extensible Metadata Platform) เป็นวิธีมาตรฐานในการฝังเมตาดาต้าระดับสูงโดยตรงในไฟล์เช่น EPS, PDF, และรูปภาพ การอัปเดต XMP ช่วยให้คุณควบคุมวิธีที่เอกสารถูกจัดทำดัชนี, แสดงผล, และค้นหา—ซึ่งสำคัญต่อการสร้างแบรนด์, การปฏิบัติตามกฎระเบียบ, และการอัตโนมัติกระบวนการทำงาน

## ทำไมต้องใช้ Aspose.Page สำหรับ Java
- **API ครบวงจร** – ไม่ต้องพึ่งเครื่องมือภายนอก; ทุกอย่างทำงานภายในกระบวนการเดียว  
- **ข้ามแพลตฟอร์ม** – ทำงานบน OS ใดก็ได้ที่รองรับ Java  
- **ไม่มีการพึ่งพาเนทีฟ** – การทำงานแบบ Pure Java ทำให้การปรับใช้ง่ายขึ้น  
- **รองรับอย่างแข็งแรง** – จัดการกับบล็อก XMP ที่มีอยู่และสร้างบล็อกใหม่จากคอมเมนต์ PS หากไม่มี

## ข้อกำหนดเบืต้น
ก่อนที่เราจะเริ่มบทแนะนำนี้ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
1. **สภาพแวดล้อมการพัฒนา Java** – JDK (เวอร์ชัน 8 หรือใหม่กว่า) พร้อม IDE หรือเครื่องมือสร้างโปรเจกต์ที่คุณเลือก  
2. **Aspose.Page for Java Library** – ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page for Java คุณสามารถหาแพคเกจที่จำเป็นได้จาก [ที่นี่](https://releases.aspose.com/page/java/)

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โปรเจกต์ Java ของคุณ แพ็กเกจเหล่านี้สำคัญต่อการโต้ตอบและจัดการเอกสาร EPS

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

## ขั้นตอนที่ 1: ดึงเมตาดาต้า XMP
ดึงเมตาดาต้า XMP จากเอกสาร EPS หากไฟล์ EPS ไม่มีเมตาดาต้า XMP จะสร้างใหม่โดยใช้ค่าจากคอมเมนต์เมตาดาต้า PS เช่น %%Creator, %%CreateDate, และ %%Title

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## ขั้นตอนที่ 2: เปลี่ยนค่า “ModifyDate”
ปรับค่า “ModifyDate” ในเมตาดาต้า XMP ให้ตรงกับวันที่ที่ต้องการ

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## ขั้นตอนที่ 3: เปลี่ยนค่า “Creator”
อัปเดตค่า “Creator” ในเมตาดาต้า XMP เพื่อระบุผู้สร้างเอกสาร

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## ขั้นตอนที่ 4: เปลี่ยนค่า “Title”
ปรับค่า “Title” ในเมตาดาต้า XMP เพื่อกำหนดชื่อเรื่องที่เหมาะสมสำหรับเอกสาร

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## ขั้นตอนที่ 5: บันทึกเอกสารพร้อมเมตาดาต้า XMP ที่เปลี่ยนแปลงแล้ว
บันทึกเอกสารพร้อมเมตาดาต้า XMP ที่อัปเดตเป็นไฟล์ EPS ใหม่

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## ปัญหาที่พบบ่อยและวิธีแก้
- **ไม่มีบล็อก XMP** – API จะสร้างบล็อกโดยอัตโนมัติจากคอมเมนต์ PS, แต่คุณก็สามารถสร้าง `XmpMetadata` ด้วยตนเองได้หากต้องการ  
- **ความไม่ตรงกันของเขตเวลา** – ควรตั้งค่า `TimeZone.setDefault` ก่อนสร้างอ็อบเจ็กต์ `Date` เพื่อหลีกเลี่ยงการเบี่ยงเบนที่ไม่คาดคิด  
- **ข้อผิดพลาดการเข้าถึงไฟล์** – ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์เข้าและออกถูกต้องและแอปพลิเคชันของคุณมีสิทธิ์อ่าน/เขียน

## คำถามที่พบบ่อย

**ถาม: จะจัดการเรื่องเขตเวลาอย่างไรเมื่อแก้ไขค่า XMP?**  
ตอบ: ใช้ `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` เพื่อให้การตั้งค่าเขตเวลาสอดคล้องกัน

**ถาม: สามารถเปลี่ยนหลายค่า XMP ในการดำเนินการเดียวได้หรือไม่?**  
ตอบ: ได้, โดยใช้เมธอด `put` สำหรับแต่ละค่าที่ต้องการ คุณสามารถแก้ไขหลายค่า XMP พร้อมกันได้

**ถาม: จะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Page for Java ได้จากที่ไหน?**  
ตอบ: สำรวจเอกสารฉบับเต็มได้ [ที่นี่](https://reference.aspose.com/page/java/)

**ถาม: มีรุ่นทดลองฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
ตอบ: มี, คุณสามารถเข้าถึงรุ่นทดลองได้ [ที่นี่](https://releases.aspose.com/)

**ถาม: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
ตอบ: ขอรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

**ถาม: การแก้ไข XMP มีผลต่อเนื้อหาภาพของ EPS หรือไม่?**  
ตอบ: ไม่. การเปลี่ยนแปลง XMP เป็นเพียงเมตาดาต้าเท่านั้นและไม่กระทบต่อองค์ประกอบกราฟิกของไฟล์ EPS

**ถาม: สามารถอ่านค่าที่อัปเดตกลับมาโปรแกรมได้เพื่อยืนยันการเปลี่ยนแปลงหรือไม่?**  
ตอบ: แน่นอน—เพียงเรียก `xmp.get("dc:creator")` (หรือคีย์ที่เกี่ยวข้อง) หลังจากบันทึกและก่อนปิดเอกสาร

## สรุป
ขอแสดงความยินดี! คุณได้สำเร็จในการทำ **aspose.page modify xmp** ค่าในเอกสาร EPS ด้วย Aspose.Page for Java บทแนะนำนี้ได้ให้ความรู้แก่คุณในการแก้ไขเมตาดาต้า เพื่อให้เอกสารของคุณสอดคล้องกับความต้องการเฉพาะของคุณอย่างราบรื่น

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
