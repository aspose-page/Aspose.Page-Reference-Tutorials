---
date: 2026-09-19
description: เรียนรู้วิธีเพิ่มค่า XMP ที่ตั้งชื่อในไฟล์ EPS ด้วย Aspose.Page for Java
  – คู่มือแบบขั้นตอนต่อขั้นตอนพร้อมตัวอย่างโค้ด
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: เพิ่ม Named Value ใน XMP ด้วย Java
og_description: วิธีเพิ่มค่า XMP ที่ตั้งชื่อในไฟล์ EPS ด้วย Aspose.Page for Java.
  ปฏิบัติตามคู่มือสั้นนี้เพื่อแทรกเมตาดาต้าตามต้องการในไม่กี่นาที
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: วิธีเพิ่มค่า XMP ที่ตั้งชื่อในไฟล์ EPS ด้วย Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: วิธีเพิ่มค่า XMP ที่ตั้งชื่อในไฟล์ EPS ด้วย Java
url: /th/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มค่าแบบมีชื่อในเมตาดาต้า XMP ด้วย Java

## คำนำ
ในการพัฒนา Java สมัยใหม่ การเรียนรู้ **วิธีเพิ่ม XMP** เมตาดาต้าในไฟล์ EPS เป็นสิ่งสำคัญเพื่อรักษาที่มาของเอกสารและเพิ่มความสามารถในการค้นหา ด้วย **Aspose.Page for Java** คุณสามารถแทรกค่าแบบมีชื่อที่กำหนดเองลงในแพ็กเก็ต XMP ได้อย่างง่ายดาย คู่มือฉบับนี้จะพาคุณผ่านขั้นตอนที่แน่นอน—พร้อมตัวอย่างโค้ด—เพื่อให้คุณเริ่มเพิ่มเมตาดาต้า XMP ให้กับเอกสาร EPS ของคุณได้ทันที

## คำตอบสั้น
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for Java (Aspose)  
- **ประเภทไฟล์ที่เป้าหมายคืออะไร?** ไฟล์ EPS ที่มีเมตาดาต้า XMP  
- **กรณีการใช้งานหลัก?** เพิ่มค่าแบบมีชื่อที่กำหนดเอง (เช่น ขีดจำกัดขนาดหน้า) ไปยัง XMP  
- **ข้อกำหนดเบื้องต้น?** JDK 8+ และไลบรารี Aspose.Page for Java  
- **ระยะเวลาการดำเนินการโดยทั่วไป?** 5–10 นาทีหลังจากตั้งค่าลิบรารีแล้ว  

## asp คืออะไร?
Aspose เป็นชื่อย่อของ Aspose ชุดของ API ที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข แปลง และแสดงผลรูปแบบเอกสารหลากหลายโดยไม่ต้องพึ่งซอฟต์แวร์ภายนอก ส่วนประกอบ Aspose.Page for Java มุ่งเน้นการประมวลผล PostScript และ EPS โดยให้การเข้าถึงโปรแกรมต่อเนื้อหาหน้า กราฟิก และเมตาดาต้า เช่น XMP

## ทำไมต้องเพิ่มค่าแบบมีชื่อในเมตาดาต้า XMP?
ค่าแบบมีชื่อทำให้คุณสามารถเก็บคู่คีย์‑ค่าแบบ任意โดยตรงในแพ็กเก็ต XMP ทำให้เครื่องมือที่ตามมาสามารถอ่านได้ทันที สิ่งนี้ช่วยเพิ่มความเป็นมิตรต่อเครื่องมือค้นหา เปิดใช้งานการอัตโนมัติของเวิร์กโฟลว์ และตอบสนองความต้องการด้านการปฏิบัติตามกฎระเบียบโดยฝังข้อมูลกำกับโดยไม่ต้องเปลี่ยนแปลงเนื้อหาภาพ

## ทำไมเรื่องนี้ถึงสำคัญ
การเพิ่มค่าแบบมีชื่อลงใน XMP ทำให้คุณสามารถเก็บคู่คีย์‑ค่าแบบ任意ที่สามารถอ่านได้โดยไม่ต้องพาร์สไฟล์ EPS ทั้งหมด ความสามารถนี้มีคุณค่าอย่างยิ่งในสายงานการเผยแพร่อัตโนมัติ ระบบจัดการสินทรัพย์ดิจิทัล และเวิร์กโฟลว์ที่ขับเคลื่อนด้วยการปฏิบัติตามกฎระเบียบ ซึ่งเมตาดาต้ากำหนดการกระทำของขั้นตอนต่อไป

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงมือทำ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Java Development Kit (JDK):** JDK ล่าสุด (เวอร์ชัน 8 หรือสูงกว่า) ที่ติดตั้งบนเครื่องของคุณ  
- **Aspose.Page for Java Library:** ดาวน์โหลดจาก [Aspose.Page for Java download](https://releases.aspose.com/page/java/) อย่างเป็นทางการ แล้วเพิ่มไฟล์ JAR ไปยัง classpath ของโปรเจกต์ของคุณ  
- **ไฟล์ EPS** ที่มีเมตาดาต้า XMP อยู่แล้วหรือจะถูกสร้างโดยอัตโนมัติ  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจ Java ที่จำเป็น การนำเข้าดังกล่าวทำให้คุณเข้าถึงสตรีมไฟล์ โมเดลเอกสาร EPS และคลาสจัดการ XMP

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## วิธีเพิ่มค่าแบบมีชื่อใน XMP ของไฟล์ EPS ด้วย Java
เพื่อเพิ่มค่าแบบมีชื่อ ให้โหลดไฟล์ EPS ด้วย `FileInputStream` ดึงหรือสร้างอ็อบเจกต์ `XmpMetadata` ของมัน แล้วแทรก `NamedValue` ที่ต้องการลงในเนมสเปซที่เหมาะสม จากนั้นเขียนเอกสารที่แก้ไขกลับไปโดยใช้ `FileOutputStream` Aspose.Page จะจัดการการสร้างแพ็กเก็ต XMP อัตโนมัติหากไม่มีอยู่ ทำให้เมตาดาต้าใหม่ถูกฝังอย่างถูกต้อง

### ขั้นตอนที่ 1: เริ่มต้นสตรีมไฟล์ EPS เข้า
**FileInputStream** เป็นคลาส I/O ของ Java ที่อ่านไบต์ดิบจากไฟล์ โหลดไฟล์ EPS ต้นฉบับเข้า `FileInputStream` สตรีมนี้จะส่งเอกสารให้กับ API ของ Aspose

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **เคล็ดลับ:** ทำให้ตัวแปร `dataDir` สามารถกำหนดค่าได้ เพื่อให้โค้ดเดียวกันทำงานได้ในหลายสภาพแวดล้อม

### ขั้นตอนที่ 2: รับเมตาดาต้า XMP
**XmpMetadata** แสดงถึงแพ็กเก็ต XMP ที่เชื่อมโยงกับเอกสาร EPS ดึงแพ็กเก็ต XMP ที่มีอยู่; หากไฟล์ EPS ไม่มี Aspose จะสร้างอ็อบเจกต์ XMP ใหม่โดยดึงข้อมูลจากคอมเมนต์ PS

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### ขั้นตอนที่ 3: เพิ่มค่าแบบมีชื่อ
**NamedValue** คือคู่คีย์‑ค่าที่เก็บอยู่ในเนมสเปซเมตาดาต้า XMP แทรกค่าแบบมีชื่อที่กำหนดเองลงในโครงสร้าง XMP ในตัวอย่างนี้เราจะเพิ่มคีย์ใหม่ภายใต้เนมสเปซ `xmpTPg:MaxPageSize`

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **ทำไมเรื่องนี้ถึงสำคัญ:** ค่าแบบมีชื่อทำให้คุณสามารถเก็บคู่คีย์‑ค่าแบบ任意ที่แอปพลิเคชันต่อมาสามารถอ่านได้โดยไม่ต้องพาร์สเอกสารทั้งหมด

### ขั้นตอนที่ 4: เริ่มต้นสตรีมไฟล์ EPS ออก
**FileOutputStream** เป็นคลาส I/O ของ Java ที่เขียนไบต์ดิบลงไฟล์ เตรียม `FileOutputStream` ที่จะบันทึกไฟล์ EPS ที่แก้ไขแล้ว

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### ขั้นตอนที่ 5: บันทึกเอกสาร
เมธอด `save` จะบันทึกการเปลี่ยนแปลง มันเขียนแพ็กเก็ต XMP ที่อัปเดตกลับเข้าไฟล์ EPS เพื่อให้แน่ใจว่าค่าแบบมีชื่อใหม่กลายเป็นส่วนหนึ่งของเมตาดาต้าเอกสาร

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### ขั้นตอนที่ 6: ปิดสตรีมไฟล์ EPS เข้า
การปิดตัวจัดการไฟล์ต้นฉบับช่วยป้องกันการรั่วของทรัพยากรและทำให้ไฟล์ไม่ถูกล็อกสำหรับการดำเนินการต่อไป

```java
psStream.close();
```

โดยทำตามขั้นตอนหกขั้นตอนนี้ คุณได้ **เพิ่มค่าแบบมีชื่อในเมตาดาต้า XMP** อย่างสำเร็จโดยใช้ **Aspose.Page for Java**.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| `NullPointerException` on `xmp` | ไฟล์ EPS ไม่มี XMP และ Aspose ล้มเหลวในการสร้าง | ตรวจสอบให้แน่ใจว่า EPS มีคอมเมนต์ PS อย่างน้อยหนึ่งรายการหรือสร้างอ็อบเจกต์ `XmpMetadata` ใหม่ด้วยตนเอง |
| Output file is empty | สตรีมเอาต์พุตไม่ได้ flush/close | ตรวจสอบว่าได้เรียก `outPsStream.close()` ในบล็อก `finally` (ตามที่แสดง) |
| Duplicate key error | เพิ่มค่าแบบมีชื่อเดียวกันสองครั้ง | ตรวจสอบว่าคีย์มีอยู่แล้วหรือยังด้วย `xmp.containsNamedValue(...)` ก่อนทำการเพิ่ม |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Page for Java ร่วมกับไลบรารี Java อื่นได้หรือไม่?**  
A: ได้, Aspose.Page for Java ถูกออกแบบให้ทำงานร่วมกับไลบรารี Java อื่นอย่างราบรื่น ให้ความยืดหยุ่นในสภาพแวดล้อมการพัฒนาของคุณ  

**Q: มีรุ่นทดลองฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
A: มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Page for Java ได้ที่ [Aspose releases page](https://releases.aspose.com/)  

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: ไปที่ [temporary license page](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page for Java  

**Q: ฉันจะหา tutorial และตัวอย่างเพิ่มเติมสำหรับ Aspose.Page for Java ได้จากที่ไหน?**  
A: สำรวจ [documentation](https://reference.aspose.com/page/java/) เพื่อดู tutorial และตัวอย่างอย่างครบถ้วน  

**Q: Aspose.Page for Java เหมาะกับโครงการขนาดใหญ่หรือไม่?**  
A: แน่นอน, Aspose.Page for Java ถูกออกแบบให้จัดการโครงการขนาดใหญ่ได้อย่างมีประสิทธิภาพ พร้อมความสามารถในการจัดการเอกสารที่แข็งแกร่ง  

## สรุป
ในคู่มือนี้เราได้สาธิตว่า **Aspose.Page for Java** ทำให้การ **เพิ่มค่าแบบมีชื่อในเมตาดาต้า XMP** ภายในไฟล์ EPS เป็นเรื่องง่าย ด้วยขั้นตอนข้างต้น คุณสามารถเพิ่มเมตาดาต้าตามต้องการให้กับเอกสารของคุณ ปรับปรุงการค้นหา และเปิดใช้งานการประมวลผลขั้นต่อไปที่ชาญฉลาดยิ่งขึ้น

---

**Last Updated:** 2026-09-19  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเพิ่มเนมสเปซ XMP ในไฟล์ EPS ด้วย Aspose.Page – คู่มือ Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [เพิ่มเมตาดาต้า XMP ไปยังไฟล์ EPS ด้วย Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [อ่าน XMP ด้วย Aspose.Page – คู่มือ Java](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}