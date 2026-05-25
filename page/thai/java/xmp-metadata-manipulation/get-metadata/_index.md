---
date: 2026-05-25
description: เรียนรู้วิธีการอ่าน XMP ด้วย Aspose.Page บน Java คู่มือแบบขั้นตอนนี้แสดงการสกัด
  metadata XMP, ข้อมูลผู้สร้าง, timestamps, thumbnails, และอื่น ๆ
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: วิธีอ่าน XMP Metadata ด้วย Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: อ่าน XMP ด้วย Aspose.Page – คู่มือ Java
url: /th/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับ Metadata จาก XMP ด้วย Java

## วิธีอ่าน XMP ด้วย Aspose.Page (Java)?

โหลดไฟล์ EPS ด้วย `new Document("file.eps")` — คลาส `Document` แสดงถึงไฟล์ที่โหลดแล้ว เรียก `getXmpMetadata()` เพื่อดึงแพ็กเกจ XMP แล้วสอบถามอ็อบเจกต์ `XmpMetadata` ที่คืนค่า ซึ่งเป็นอินเทอร์เฟซแบบแผนที่สำหรับคุณสมบัติ XMP เพื่อดึงคีย์ที่ต้องการ ทั้งหมดนี้เป็นขั้นตอนที่จำเป็นสำหรับการอ่าน XMP ด้วย Aspose.Page API จะทำการแยกข้อมูลระดับล่างให้โดยอัตโนมัติ ทำให้คุณได้แผนที่คุณสมบัติพร้อมใช้งานในเพียงสองบรรทัดของโค้ด

ยินดีต้อนรับสู่บทแนะนำแบบขั้นตอนที่แสดง **วิธีอ่าน XMP** metadata ด้วย Java และไลบรารี Aspose.Page XMP (Extensible Metadata Platform) เป็นมาตรฐานที่ได้รับการยอมรับอย่างกว้างขวางสำหรับการฝัง metadata ที่มีความหมายลึกลงในเอกสาร เมื่ออ่านจบคุณจะสามารถอ่าน XMP ของรูปแบบเอกสาร ดึงข้อมูลผู้สร้าง เวลา สร้างภาพย่อ และอื่น ๆ อีกมากมาย — ช่วยให้คุณสร้างโซลูชันการวิเคราะห์เอกสารที่ฉลาดขึ้นได้

## คำตอบสั้น ๆ
- **“อ่าน XMP” หมายความว่าอะไร?** หมายถึงการดึงแพ็กเกจ XMP ที่เก็บ metadata ภายในไฟล์โดยอัตโนมัติผ่านโปรแกรม  
- **ต้องใช้ไลบรารีใด?** Aspose.Page for Java (ดาวน์โหลดจากหน้าอย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/page/java/))  
- **ต้องมีลิขสิทธิ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์แบบชั่วคราวหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์; เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมินผล  
- **รองรับเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า  
- **สามารถอ่าน XMP จากรูปแบบอื่นได้หรือไม่?** ได้ — Aspose.Page ดึง XMP จาก EPS, PDF, JPEG, PNG และกว่า 20 รูปแบบอื่น ๆ  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มเขียนโค้ด ให้ตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK)** – ติดตั้ง Java 8+ และตั้งค่าให้พร้อมใช้งานบนเครื่องของคุณ  
- **Aspose.Page for Java** – ดาวน์โหลดไลบรารีจากเว็บไซต์อย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/page/java/)  
- ไฟล์ EPS ที่มี metadata XMP (เช่น `xmp1.eps`)  

## นำเข้าแพ็กเกจ
คลาส `XmpMetadata` อยู่ในเนมสเปซ `com.aspose.page.xmp` ส่วนคลาส `Document` อยู่ใน `com.aspose.page` ให้นำเข้าทั้งสองเพื่อให้สามารถทำงานกับไฟล์ EPS และ metadata ของมันได้  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## ขั้นตอนที่ 1: เริ่มต้นสตรีมไฟล์ EPS อินพุต
กำหนดเส้นทางไปยังโฟลเดอร์เอกสารของคุณและเริ่มต้นสตรีมไฟล์ EPS อินพุต  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## ขั้นตอนที่ 2: ดึง XMP Metadata
`XmpMetadata` คืออ็อบเจกต์ของ Aspose.Page ที่เก็บแพ็กเกจ XMP ที่สกัดจากเอกสาร ดึงมันด้วย `document.getXmpMetadata()` หากไฟล์ไม่มี XMP API จะสร้างแพ็กเกจขั้นต่ำจากคอมเมนต์ PostScript ที่มีอยู่  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## ขั้นตอนที่ 3: ดึงข้อมูล CreatorTool
คีย์ `CreatorTool` อยู่ภายใต้เนมสเปซ `xmp` และบันทึกแอปพลิเคชันที่สร้างไฟล์ ตรวจสอบว่ามีหรือไม่และพิมพ์ค่าออกมา  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## ขั้นตอนที่ 4: ดึงข้อมูล CreateDate
`CreateDate` เก็บเวลาที่เอกสารถูกสร้างครั้งแรก ใช้รูปแบบ `containsKey`/`get` เดียวกันเพื่ออ่านค่า  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## ขั้นตอนที่ 5: ดึงความกว้างของ Thumbnail
หากมี thumbnail อยู่, อาร์เรย์ `xmp:Thumbnails` จะมีรายการหนึ่งหรือหลายรายการ แต่ละรายการมี `width`, `height` และข้อมูลไบนารี ตัวอย่างนี้ดึงความกว้างของ thumbnail แรกออกมา  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## ขั้นตอนที่ 6: ดึงข้อมูล Format
คีย์ `format` บอกรูปแบบไฟล์ต้นฉบับ (เช่น “application/postscript”) มีประโยชน์เมื่อคุณต้องบันทึกหรือยืนยันประเภทแหล่งที่มา  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## ขั้นตอนที่ 7: ดึง DocumentID
`DocumentID` เป็นตัวระบุที่ไม่ซ้ำกันที่สร้างโดยแอปพลิเคชันผู้สร้าง สามารถใช้สำหรับการกำจัดข้อมูลซ้ำในคลังสินทรัพย์ขนาดใหญ่  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## ทำไมเรื่องนี้ถึงสำคัญ
Aspose.Page สามารถอ่าน XMP จาก **กว่า 20** รูปแบบไฟล์และประมวลผลเอกสารขนาด **สูงสุด 500 MB** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ทำให้คุณเข้าถึง metadata ที่สำคัญได้อย่างรวดเร็วและใช้ทรัพยากรต่ำ ความสามารถนี้เป็นหัวใจสำคัญสำหรับไพพ์ไลน์การประมวลผลแบบชุด ระบบจัดการสินทรัพย์ดิจิทัล และโซลูชันใด ๆ ที่ต้องอาศัยคุณลักษณะเอกสารที่ค้นหาได้และอ่านได้โดยเครื่อง

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ไม่มี XMP:** บางไฟล์ EPS อาจไม่มี XMP การเรียก `getXmpMetadata()` จะสร้างชุดข้อมูลขั้นต่ำจากคอมเมนต์ PS ที่มีอยู่ แต่คุณจะไม่ได้รับ metadata เต็มรูปแบบหากไม่ได้ฝังไว้  
- **อาร์เรย์ Thumbnail:** คีย์ `xmp:Thumbnails` สามารถมีหลายรายการ ตัวอย่างนี้ดึงเฉพาะรายการแรก หากต้องการทั้งหมดให้วนลูปอาร์เรย์  
- **ความเข้าใจเนมสเปซ:** คีย์ XMP ใช้เนมสเปซ (เช่น `xmp:`, `dc:`) ตรวจสอบให้แน่ใจว่าอ้างอิงชื่อคีย์อย่างถูกต้อง มิฉะนั้น `containsKey` จะคืนค่า false  

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?
ได้, Aspose.Page รองรับ Java, .NET และหลายภาษาอื่น ดูรายการเต็มใน [เอกสาร](https://reference.aspose.com/page/java/)  

### มีเวอร์ชันทดลองฟรีสำหรับ Aspose.Page for Java หรือไม่?
มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรี [ที่นี่](https://releases.aspose.com/)  

### จะหาการสนับสนุนสำหรับ Aspose.Page for Java ได้จากที่ไหน?
เยี่ยมชม [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อรับความช่วยเหลือจากชุมชนและการสนับสนุนอย่างเป็นทางการ  

### จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
คุณสามารถรับลิขสิทธิ์ชั่วคราว [ที่นี่](https://purchase.aspose.com/temporary-license/)  

### มีแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Page for Java หรือไม่?
สำรวจ [เอกสารฉบับเต็ม](https://reference.aspose.com/page/java/) และดาวน์โหลดไลบรารี [ที่นี่](https://releases.aspose.com/page/java/)  

## คำถามเพิ่มเติม
**ถาม: วิธีนี้ทำงานกับไฟล์ PDF ที่มี XMP หรือไม่?**  
ตอบ: ใช่, Aspose.Page สามารถอ่าน XMP จาก PDF, EPS และหลายรูปแบบภาพอื่น ๆ  

**ถาม: ฉันสามารถแก้ไข metadata XMP หลังจากอ่านได้หรือไม่?**  
ตอบ: แน่นอน, อ็อบเจกต์ `XmpMetadata` สามารถแก้ไขได้; คุณสามารถเพิ่ม, ปรับปรุง หรือเอาคีย์ออกแล้วบันทึกเอกสาร  

**ถาม: มีวิธีดึงภาพ thumbnail ทั้งหมด ไม่ใช่แค่ขนาดหรือไม่?**  
ตอบ: คุณสามารถดึงข้อมูลไบนารีจากคุณสมบัติ `xmpGImg:data` ของแต่ละรายการ thumbnail แล้วบันทึกเป็นไฟล์ได้  

## สรุป
คุณได้เรียนรู้ **วิธีอ่าน XMP** metadata ด้วย Java และ Aspose.Page แล้ว โดยทำตามขั้นตอนเหล่านี้คุณสามารถดึงเครื่องมือผู้สร้าง, เวลา, thumbnail, ข้อมูลรูปแบบไฟล์, และ DocumentID — ให้คุณเห็นข้อมูลเมตาที่ฝังอยู่ในไฟล์ EPS อย่างครบถ้วน อย่าลังเลที่จะทดลองใช้เนมสเปซ XMP เพิ่มเติมเพื่อดึงข้อมูลที่ลึกซึ้งยิ่งขึ้นสำหรับแอปพลิเคชันของคุณ  

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [บทแนะนำ Aspose Page Java – เพิ่ม Metadata XMP ให้ไฟล์ EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [บทแนะนำ aspose.page xmp – เพิ่ม Namespace ใน XMP ด้วย Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [บทแนะนำ aspose page xmp – เปลี่ยน Named Value ใน XMP ด้วย Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}