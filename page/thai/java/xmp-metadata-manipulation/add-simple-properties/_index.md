---
date: 2026-05-20
description: เรียนรู้วิธีเพิ่ม XMP metadata ให้กับไฟล์ EPS ด้วย Aspose.Page for Java.
  คู่มือขั้นตอนโดยละเอียดเพื่อฝังคุณสมบัติ XMP อย่างง่ายโดยโปรแกรม.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: เพิ่มคุณสมบัติอย่างง่ายใน XMP ด้วย Java
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: เพิ่ม XMP Metadata ให้กับไฟล์ EPS ด้วย Java
url: /th/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มเมตาดาต้า XMP ให้ไฟล์ EPS ด้วย Java

## บทนำ
ในสายงานกราฟิกสมัยใหม่ การที่สามารถ **เพิ่มเมตาดาต้า XMP** ให้ไฟล์ EPS ด้วยโปรแกรมทำให้คุณควบคุมได้อย่างเต็มที่ว่าภาพประกอบของคุณถูกอธิบาย ค้นหา และจัดเก็บอย่างไร ด้วย Aspose.Page for Java คุณสามารถอ่าน แก้ไข และเขียนแพ็กเกจ XMP ภายในเอกสาร EPS ได้โดยไม่ต้องออกจากระบบนิเวศของ Java ในบทเรียนนี้ เราจะพาคุณผ่านขั้นตอนที่แน่นอนเพื่อเพิ่มคุณสมบัติ XMP อย่างง่ายให้กับไฟล์ EPS เพื่อให้คุณสามารถเสริมกราฟิกของคุณด้วยเมตาดาต้าตามต้องการได้อย่างรวดเร็วและเชื่อถือได้.

## คำตอบด่วน
- **อะไรหมายถึง “add XMP metadata to EPS”?** การฝังแพ็กเกจ XMP (เมตาดาต้าแบบ XML) ไว้ในไฟล์ EPS.  
- **ต้องใช้ไลบรารีใด?** Aspose.Page for Java (downloadable from the Aspose site).  
- **ต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** การทดลองใช้งานฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **จำนวนบรรทัดของโค้ดเท่าไหร่?** น้อยกว่า 30 บรรทัดของ Java พร้อมกับคำสั่ง import จำนวนเล็กน้อย.  
- **ฉันสามารถเพิ่มประเภทข้อมูลอื่นได้หรือไม่?** ได้ – วันที่, จำนวนเต็ม, จำนวนทศนิยม, สตริง, และแม้กระทั่งอาร์เรย์ก็รองรับ.

## วิธีเพิ่มเมตาดาต้า XMP ให้ไฟล์ EPS ด้วย Java?
โหลดไฟล์ EPS ด้วย `new PsDocument("input.eps")` ดึงหรือสร้างแพ็กเกจ XMP ของมัน แทรกคุณสมบัติที่ต้องการ แล้วบันทึกเอกสารกลับไปยังดิสก์ – ทั้งหมดในโค้ด Java ไม่เกินสิบบรรทัด วิธีนี้ทำให้คุณสามารถฝังเมตาดาต้าที่ค้นหาได้และเป็นไปตามมาตรฐานโดยไม่ต้องแก้ไขไฟล์ EPS ด้วยตนเอง.

## XMP metadata ใน EPS คืออะไร?
XMP metadata ใน EPS คือแพ็กเกจ XML ที่อยู่ภายในไฟล์ EPS และเก็บข้อมูลเช่น ผู้เขียน, วันที่สร้าง, และแท็กที่กำหนดเอง การฝังแพ็กเกจนี้ทำให้เครื่องมือที่ตามมาสามารถอ่านและดำเนินการกับข้อมูลได้โดยไม่ต้องใช้ไฟล์แยกเพิ่มเติม.

## ทำไมต้องเพิ่มเมตาดาต้า XMP ให้ไฟล์ EPS?
การฝังเมตาดาต้า XMP ทำให้สินทรัพย์ EPS สามารถค้นหาได้ทันที, รับประกันการปฏิบัติตามกฎระเบียบโดยการเก็บข้อมูลลิขสิทธิ์ภายในไฟล์, ทำให้สายงานอัตโนมัติสามารถตัดสินใจโดยอิงจากแท็กที่ฝังไว้, และรับประกันว่าเมตาดาต้าจะเดินทางพร้อมกับกราฟิกไปยังทุกแพลตฟอร์ม Aspose.Page สามารถประมวลผลไฟล์ได้ถึง 500 MB โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ, ให้ประสิทธิภาพที่เร็วสำหรับงานขนาดใหญ่.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานของการเขียนโปรแกรม Java.  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้ **[here](https://releases.aspose.com/page/java/)**.  
- ไฟล์ EPS ตัวอย่างที่มีเมตาดาต้า หากคุณไม่มีไฟล์ดังกล่าว สามารถใช้ไฟล์ **`xmp3.eps`** ที่ให้มาได้.

## นำเข้าแพ็กเกจ
แรกเริ่ม, นำเข้าคลาสที่คุณต้องการใช้ การนำเข้าจะเหมือนกับตัวอย่างต้นฉบับโดยตรง:

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

## ขั้นตอนที่ 1: โหลดเอกสาร EPS และดึงเมตาดาต้า XMP
`PsDocument` เป็นคลาสที่แสดงถึงไฟล์ EPS และให้เมธอดเพื่อเข้าถึงเนื้อหาและเมตาดาต้าของมัน.  
`XmpMetadata` เป็นอ็อบเจ็กต์ที่เก็บแพ็กเกจ XMP ที่เชื่อมโยงกับเอกสาร.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## ขั้นตอนที่ 2: เพิ่มคุณสมบัติวันที่
`Date` เป็นคลาสที่แสดงถึงช่วงเวลาที่เฉพาะเจาะจง, มีความแม่นยำระดับมิลลิวินาที.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## ขั้นตอนที่ 3: เพิ่มคุณสมบัติจำนวนเต็ม
`Integer` เป็นคลาสที่ห่อหุ้มค่า primitive `int` เป็นอ็อบเจ็กต์.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## ขั้นตอนที่ 4: เพิ่มคุณสมบัติจำนวนทศนิยม
`Double` เป็นคลาสที่ห่อหุ้มค่า primitive `double` เป็นอ็อบเจ็กต์.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## ขั้นตอนที่ 5: เพิ่มคุณสมบัติสตริง
`String` เป็นคลาสที่แสดงถึงลำดับของอักขระ.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## ขั้นตอนที่ 6: บันทึกไฟล์ EPS ที่อัปเดต
เมธอด `save` จะเขียนเอกสารที่แก้ไขแล้วกลับไปยังดิสก์, คงโครงสร้างของ EPS ไว้.

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
ควรปิดสตรีมเสมอเพื่อหลีกเลี่ยงการรั่วไหลของไฟล์แฮนด์เดิลและรับประกันว่าบัฟเฟอร์ทั้งหมดถูกล้าง.

```java
// Close input EPS stream
psStream.close();
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **เมตาดาต้า XMP ว่าง** | ไฟล์ EPS ไม่มีแพ็กเกจ XMP และไลบรารีไม่สามารถสรุปคอมเมนต์ PS ได้. | ตรวจสอบให้แน่ใจว่า EPS ต้นทางมีคอมเมนต์ PS อย่างน้อยหนึ่งรายการ (เช่น `%%Creator`). ไลบรารีจะสร้างแพ็กเกจ XMP ขั้นพื้นฐานโดยอัตโนมัติ. |
| **ความไม่ตรงกันของโซนเวลา** | วันที่แสดงการเปลี่ยนแปลงเมื่อเปิดในแอปพลิเคชันอื่น. | ตั้งค่า `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` ก่อนสร้างอ็อบเจ็กต์ `Date` ตามที่แสดงในขั้นตอน 2. |
| **ข้อยกเว้นไลเซนส์** | Runtime ขว้าง `LicenseException`. | ใช้ไลเซนส์ Aspose.Page ที่ถูกต้องก่อนใช้ API, หรือรันในโหมดทดลองสำหรับการประเมินผล. |

## คำถามที่พบบ่อย
**Q:** ฉันสามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?  
**A:** Aspose.Page รองรับ Java เป็นหลัก, แต่มีไลบรารีที่เทียบเท่าสำหรับ .NET, C++, และ Python.

**Q:** มีการทดลองใช้งานฟรีสำหรับ Aspose.Page for Java หรือไม่?  
**A:** ใช่, คุณสามารถสำรวจคุณสมบัติของ Aspose.Page ได้โดยรับการทดลองใช้งานฟรี **[here](https://releases.aspose.com/)**.

**Q:** ฉันสามารถหาเอกสารรายละเอียดสำหรับ Aspose.Page for Java ได้ที่ไหน?  
**A:** เอกสารพร้อมให้บริการ **[here](https://reference.aspose.com/page/java/)**.

**Q:** ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?  
**A:** คุณสามารถขอรับไลเซนส์ชั่วคราวได้ **[here](https://purchase.aspose.com/temporary-license/)**.

**Q:** ฉันสามารถซื้อ Aspose.Page for Java ได้ที่ไหน?  
**A:** คุณสามารถซื้อผลิตภัณฑ์ได้ **[here](https://purchase.aspose.com/buy)**.

---

**อัปเดตล่าสุด:** 2026-05-20  
**ทดสอบด้วย:** Aspose.Page for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [วิธีอ่านเมตาดาต้า XMP ด้วย Java – คู่มือ Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [บทเรียน XMP ของ aspose.page – เพิ่ม Namespace ใน XMP ด้วย Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [เพิ่มรายการอาร์เรย์ในเมตาดาต้า XMP ด้วย Java](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}