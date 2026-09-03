---
date: 2026-05-25
description: เรียนรู้วิธีแก้ไข xmp ในเอกสาร EPS ด้วย Java และ Aspose.Page. อัปเดต
  metadata อย่างรวดเร็วและเชื่อถือได้.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: เปลี่ยนค่าใน XMP ด้วย Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: วิธีแก้ไข xmp ด้วย Aspose.Page – เปลี่ยนค่าใน XMP ด้วย Java
url: /th/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เปลี่ยนค่าใน XMP ด้วย Java

## บทนำ
หากคุณกำลังมองหา **วิธีแก้ไข xmp** ภายในไฟล์ EPS ด้วย Java คุณมาถูกที่แล้ว บทเรียนนี้จะพาคุณผ่านทุกขั้นตอน—การอ่านบล็อก XMP ที่มีอยู่, การอัปเดตฟิลด์ต่าง ๆ เช่น creator, title, และ modify date, และสุดท้ายการบันทึกการเปลี่ยนแปลงกลับไปยังเอกสาร EPS เมื่อเสร็จคุณจะมีโค้ดสั้นที่นำกลับมาใช้ใหม่ได้ซึ่งสามารถใส่ลงในกระบวนการทำงานอัตโนมัติใด ๆ เพื่อให้ไฟล์ของคุณมีเมตาดาต้าที่ถูกต้องสำหรับการสร้างแบรนด์, การปฏิบัติตามกฎระเบียบ, หรือการทำดัชนีโดยเครื่องมือค้นหา

## คำตอบอย่างรวดเร็ว
- **aspose.page modify xmp** ทำอะไร? มันทำให้คุณสามารถอ่านและเขียนเมตาดาต้า XMP ในไฟล์ EPS ผ่าน Aspose.Page Java API.  
- **เวอร์ชันของไลบรารีที่ต้องการคืออะไร?** ใด ๆ ที่เป็น Aspose.Page for Java รุ่นล่าสุด (API มีความเสถียรข้ามเวอร์ชัน).  
- **ฉันต้องการไลเซนส์เพื่อรันตัวอย่างหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.  
- **ฉันสามารถเปลี่ยนหลายฟิลด์ XMP พร้อมกันได้หรือไม่?** ใช่—เรียก `put` สำหรับแต่ละฟิลด์ก่อนบันทึกเอกสาร.  
- **จำเป็นต้องจัดการเขตเวลาไหม?** การตั้งค่าเขตเวลาเริ่มต้น (เช่น UTC) จะทำให้ค่าที่บันทึกมีความสอดคล้องกัน.

## XMP คืออะไรและทำไมต้องแก้ไขมัน?
XMP (Extensible Metadata Platform) เป็นรูปแบบมาตรฐานที่ใช้ XML สำหรับฝังเมตาดาต้าที่มีความละเอียดสูงโดยตรงภายในไฟล์ เช่น EPS, PDF, และรูปภาพ การอัปเดต XMP ทำให้คุณควบคุมวิธีที่เอกสารถูกจัดทำดัชนี, แสดงผล, และค้นหา—เป็นสิ่งสำคัญสำหรับความสอดคล้องของแบรนด์, การปฏิบัติตามกฎระเบียบ, และสายงานเนื้อหาอัตโนมัติ

## ทำไมต้องใช้ Aspose.Page สำหรับ Java?
Aspose.Page ให้ **API แบบ pure‑Java ที่ครบวงจร** ที่ขจัดความจำเป็นในการใช้เครื่องมือภายนอกหรือไลบรารีเนทีฟ รองรับ **รูปแบบเข้าและออกกว่า 50+** และสามารถประมวลผลไฟล์ EPS ขนาดถึง **500 MB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ ส่งมอบการจัดการเมตาดาต้าอย่างรวดเร็วและใช้หน่วยความจำน้อยบนระบบปฏิบัติการใด ๆ ที่รัน Java

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทเรียนนี้ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
1. **สภาพแวดล้อมการพัฒนา Java** – JDK (เวอร์ชัน 8 หรือใหม่กว่า) และ IDE หรือเครื่องมือสร้างตามที่คุณเลือก.  
2. **ไลบรารี Aspose.Page for Java** – ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page for Java คุณสามารถค้นหาแพคเกจที่จำเป็นได้ [ที่นี่](https://releases.aspose.com/page/java/).

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ แพ็กเกจเหล่านี้สำคัญต่อการโต้ตอบและจัดการเอกสาร EPS

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

## วิธีแก้ไข XMP ใน EPS ด้วย Java?
`Document` เป็นคลาสของ Aspose.Page ที่แทนไฟล์ EPS และให้การเข้าถึงเนื้อหาและเมตาดาต้าของมัน `XmpMetadata` แทนบล็อก XMP ที่แนบกับเอกสารและอนุญาตให้อ่านและเขียนฟิลด์เมตาดาต้า `put` จะเพิ่มหรืออัปเดตรายการเมตาดาต้าในอ็อบเจ็กต์ XmpMetadata `save` จะเขียนเอกสารที่แก้ไขแล้วรวมถึงเมตาดาต้า XMP ที่อัปเดตกลับไปยังไฟล์

โหลดไฟล์ EPS ด้วย `new Document("input.eps")` ดึงอ็อบเจ็กต์ `XmpMetadata` ของมัน, อัปเดตคีย์ที่ต้องการโดยใช้ `put`, และสุดท้ายเรียก `save` เพื่อบันทึกการเปลี่ยนแปลงไปยังไฟล์ใหม่ กระบวนการสั้นนี้จัดการบล็อก XMP ที่หายไปโดยอัตโนมัติ, สร้างบล็อกจากคอมเมนต์ PostScript เมื่อจำเป็น, และรับประกันวันที่ที่สอดคล้องกับเขตเวลา

## ขั้นตอนที่ 1: รับเมตาดาต้า XMP
คลาส `XmpMetadata` แทนบล็อก XMP ที่แนบกับเอกสาร EPS เมื่อคุณเรียก `document.getXmpMetadata()` API จะคืนบล็อกที่มีอยู่หรือสร้างบล็อกใหม่จากคอมเมนต์ PS เช่น `%%Creator`, `%%CreateDate`, และ `%%Title`

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## ขั้นตอนที่ 2: เปลี่ยนค่า "ModifyDate"
อัปเดตรายการ `"ModifyDate"` ให้สะท้อนเวลาการแก้ไขใหม่ ใช้ `java.util.Date` ร่วมกับ `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` เพื่อรับประกันว่าค่าที่เก็บเป็นแบบไม่ขึ้นกับเขตเวลา

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## ขั้นตอนที่ 3: เปลี่ยนค่า "Creator"
คีย์ `"Creator"` เก็บชื่อแอปพลิเคชันหรือบุคคลที่สร้างไฟล์ EPS เรียก `xmp.put("dc:creator", "Your Company Name")` เพื่อแทนที่ค่าที่มีอยู่ด้วยตัวระบุที่กำหนดเอง

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## ขั้นตอนที่ 4: เปลี่ยนค่า "Title"
ฟิลด์ `"Title"` ถูกแสดงโดยระบบจัดการสินทรัพย์หลายระบบ การตั้งค่าผ่าน `xmp.put("dc:title", "New Document Title")` จะทำให้เอกสารปรากฏอย่างถูกต้องในแคตาล็อกและผลการค้นหา

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## ขั้นตอนที่ 5: บันทึกเอกสารพร้อมเมตาดาต้า XMP ที่เปลี่ยนแปลง
หลังจากทำการแก้ไขทั้งหมดแล้ว เรียก `document.save("output.eps")` ไลบรารีจะเขียนบล็อก XMP ที่อัปเดตกลับเข้าไปในสตรีม EPS ขณะเดียวกันคงเนื้อหากราฟิกเดิมไว้โดยไม่เปลี่ยนแปลง

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
- **บล็อก XMP หาย** – API จะสร้างบล็อกโดยอัตโนมัติจากคอมเมนต์ PS, แต่คุณก็สามารถสร้าง `XmpMetadata` ด้วยตนเองได้หากต้องการ.  
- **ความไม่ตรงกันของเขตเวลา** – ตั้งค่า `TimeZone.setDefault` ก่อนสร้างอ็อบเจ็กต์ `Date` เพื่อหลีกเลี่ยงการเบี่ยงเบนที่ไม่คาดคิด.  
- **ข้อผิดพลาดการเข้าถึงไฟล์** – ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์เข้าและออกถูกต้องและแอปพลิเคชันของคุณมีสิทธิ์อ่าน/เขียน.

## คำถามที่พบบ่อย

**Q: ฉันจะจัดการเรื่องเขตเวลาอย่างไรเมื่อแก้ไขค่าของ XMP?**  
A: ใช้ `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` เพื่อให้การตั้งค่าเขตเวลามีความสอดคล้องกัน.

**Q: ฉันสามารถเปลี่ยนหลายค่า XMP ในการดำเนินการเดียวได้หรือไม่?**  
A: ใช่, โดยใช้เมธอด `put` สำหรับแต่ละค่าที่ต้องการ คุณสามารถแก้ไขหลายค่า XMP พร้อมกันได้.

**Q: ฉันจะหาเอกสารเพิ่มเติมสำหรับ Aspose.Page for Java ได้จากที่ไหน?**  
A: สำรวจเอกสารฉบับเต็ม [ที่นี่](https://reference.aspose.com/page/java/).

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
A: มี, คุณสามารถเข้าถึงการทดลองใช้ฟรี [ที่นี่](https://releases.aspose.com/).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: รับไลเซนส์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

**Q: การแก้ไข XMP มีผลต่อเนื้อหาภาพของ EPS หรือไม่?**  
A: ไม่มี. การเปลี่ยนแปลง XMP เป็นเพียงเมตาดาต้าเท่านั้นและไม่กระทบต่อองค์ประกอบกราฟิกของไฟล์ EPS.

**Q: ฉันสามารถอ่านค่าที่อัปเดตกลับมาโปรแกรมเมติกเพื่อยืนยันการเปลี่ยนแปลงได้หรือไม่?**  
A: แน่นอน—เพียงเรียก `xmp.get("dc:creator")` (หรือคีย์ที่เกี่ยวข้อง) หลังจากบันทึกและก่อนปิดเอกสาร.

## สรุป
ขอแสดงความยินดี! คุณได้เชี่ยวชาญ **วิธีแก้ไข xmp** ในเอกสาร EPS ด้วย Aspose.Page for Java แล้ว ด้วยการฝังเมตาดาต้า creator, title, และ modify‑date ที่แม่นยำ คุณทำให้สินทรัพย์ของคุณสามารถค้นหา, ปฏิบัติตามกฎระเบียบ, และสอดคล้องกับมาตรฐานแบรนด์ได้อย่างเต็มที่ อย่าลังเลที่จะผสานรูปแบบนี้เข้าไปในกระบวนการประมวลผลแบบแบตช์, ขั้นตอน CI/CD, หรือเวิร์กโฟลว์การสร้างเอกสารอัตโนมัติใด ๆ

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [Aspose Page Java Tutorial – เพิ่มเมตาดาต้า XMP ให้ไฟล์ EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [How to Read XMP Metadata using Java – Aspose.Page Guide](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - Change Array Items in XMP using Java](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}