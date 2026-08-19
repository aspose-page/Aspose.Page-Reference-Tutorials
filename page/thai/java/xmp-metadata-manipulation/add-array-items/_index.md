---
date: 2026-03-05
description: เรียนรู้วิธีเพิ่มรายการอาเรย์ dc:title ในเมตาดาต้า XMP ของไฟล์ EPS ด้วย Aspose.Page สำหรับ Java.
  ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อผลลัพธ์ที่รวดเร็ว.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: วิธีเพิ่มรายการอาเรย์ dc:title ในเมตาดาต้า XMP ด้วย Java
url: /th/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรายการอาเรย์ในเมตาดาต้า XMP ด้วย Java

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีเพิ่ม dc:title** (และรายการอาเรย์อื่น ๆ) ไปยังเมตาดาต้า XMP ภายในไฟล์ EPS ด้วย Aspose.Page for Java การอัปเดตเมตาดาต้า XMP มีประโยชน์เมื่อคุณต้องการฝังข้อมูลที่สามารถค้นหาได้—เช่น ชื่อเรื่อง, ผู้สร้าง, หรือคีย์เวิร์ด—โดยตรงในไฟล์กราฟิกของคุณ เราจะเดินผ่านแต่ละขั้นตอน, อธิบายว่าทำไมบรรทัดนั้นสำคัญ, และแสดงวิธีตรวจสอบการเปลี่ยนแปลง

## คำตอบด่วน
- **“dc:title” หมายถึงอะไร?** เป็นคุณสมบัติชื่อเรื่องของ Dublin Core ที่เก็บเป็นอาเรย์ XMP  
- **ทำไมต้องแก้ไขเมตาดาต้า XMP?** เพื่อเพิ่มการจัดการสินทรัพย์, ความสามารถในการค้นหา, และการปฏิบัติตามมาตรฐาน  
- **ต้องมีบล็อก XMP อยู่แล้วหรือไม่?** ไม่—Aspose.Page จะสร้างบล็อกจากคอมเมนต์ PS หากไม่มี  
- **ต้องใช้เวอร์ชันไลบรารีใด?** ใด ๆ ที่เป็น Aspose.Page for Java รุ่นล่าสุด (ทดสอบกับรุ่น 2026 ล่าสุด)  
- **สามารถเพิ่มคุณสมบัติอาเรย์อื่นได้หรือไม่?** ได้—ใช้เมธอด `addArrayItem` เดียวกันสำหรับคุณสมบัติเช่น `dc:creator`

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว (เพิ่ม JAR ไปยัง classpath ของโปรเจกต์)  
- ประสบการณ์พื้นฐานการพัฒนา Java (แนะนำ JDK 8+ )  
- ไฟล์ EPS ที่มีเมตาดาต้า XMP อยู่แล้วหรืออย่างน้อยคอมเมนต์เมตาดาต้า PS (เช่น `%%Title`, `%%Creator`)  

## นำเข้าแพ็กเกจ
เพื่อเริ่มต้น, นำเข้าคลาสที่จำเป็นสำหรับการอ่าน, แก้ไข, และบันทึกไฟล์ EPS:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## ขั้นตอนที่ 1: โหลดเอกสาร EPS และดึงเมตาดาต้า XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

ที่นี่เราจะเปิดไฟล์ EPS และขอให้ Aspose.Page ให้บล็อก XMP หากไฟล์ไม่มี XMP ไลบรารีจะสร้างอัตโนมัติจากคอมเมนต์ PS ที่มีอยู่, ทำให้คุณมีคอนเทนเนอร์เมตาดาต้าให้ทำงานเสมอ

## ขั้นตอนที่ 2: เพิ่มรายการอาเรย์ **dc:title** ใหม่  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

บรรทัดนี้แสดง **วิธีเพิ่ม dc:title** แทนที่ `"NewTitle"` ด้วยชื่อเรื่องที่คุณต้องการฝัง เมธอดจะเพิ่มค่าลงในอาเรย์ชื่อเรื่องที่มีอยู่, รักษาชื่อเรื่องก่อนหน้าที่อาจมีอยู่

## ขั้นตอนที่ 3: เพิ่มรายการอาเรย์ **dc:creator** ใหม่  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

ในลักษณะเดียวกัน, คุณสามารถเพิ่มคุณสมบัติ `dc:creator` ได้หลายค่า; การเรียกแต่ละครั้งจะเพิ่มรายการใหม่เข้าไป

## ขั้นตอนที่ 4: เตรียมสตรีมเอาต์พุต  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

เราจะสร้างสตรีมสำหรับไฟล์ EPS ที่แก้ไขแล้ว การใช้ชื่อไฟล์ต่างกัน (`xmp3_changed.eps`) จะทำให้ไฟล์ต้นฉบับไม่ถูกเปลี่ยนแปลง

## ขั้นตอนที่ 5: บันทึกเอกสารพร้อมเมตาดาต้า XMP ที่อัปเดต  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

การเรียก `save` จะเขียนข้อมูล EPS พร้อมบล็อก XMP ที่อัปเดต `finally` บล็อกจะรับประกันว่าการจัดการไฟล์จะถูกปล่อยแม้เกิดข้อยกเว้น

## ทำไมเรื่องนี้ถึงสำคัญ
การฝังค่า `dc:title` และ `dc:creator` ที่แม่นยำช่วยปรับปรุง:

- **ความสามารถในการค้นหา** ในระบบจัดการสินทรัพย์ดิจิทัล (DAM)  
- **การปฏิบัติตาม** มาตรฐานการเผยแพร่ที่ต้องการเมตาดาต้า  
- **การทำงานร่วมกัน**, เนื่องจากทีมงานสามารถระบุเนื้อหาไฟล์ได้อย่างรวดเร็วโดยไม่ต้องเปิด EPS

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ข้อผิดพลาด:** เขียนทับรายการอาเรย์ที่มีอยู่โดยไม่ตั้งใจ  
  **เคล็ดลับ:** ใช้ `xmp.getArrayItems("dc:title")` เพื่อตรวจสอบค่าปัจจุบันก่อนเพิ่มใหม่  
- **ข้อผิดพลาด:** ลืมปิดสตรีม ทำให้ไฟล์ล็อกอยู่  
  **เคล็ดลับ:** ห่อ I/O ด้วย try‑with‑resources หรือบล็อก `finally` ตามตัวอย่าง  
- **เคล็ดลับ:** สามารถเชื่อมต่อหลายการเรียก `addArrayItem` เพื่อเพิ่มหลายชื่อเรื่องหรือผู้สร้างในขั้นตอนเดียวได้

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Page for Java กับรูปแบบเอกสารอื่นได้หรือไม่?
ได้, Aspose.Page รองรับรูปแบบเอกสารหลายประเภท รวมถึง EPS, PDF, และ XPS

### มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?
มี, คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](https://releases.aspose.com/)

### จะหาเอกสารสำหรับ Aspose.Page for Java ได้จากที่ไหน?
เอกสารพร้อมใช้งาน [ที่นี่](https://reference.aspose.com/page/java/)

### ฉันจะซื้อ Aspose.Page for Java ได้อย่างไร?
คุณสามารถซื้อผลิตภัณฑ์ได้ [ที่นี่](https://purchase.aspose.com/buy)

### มีใบอนุญาตชั่วคราวสำหรับ Aspose.Page for Java หรือไม่?
มี, คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

---

**อัปเดตล่าสุด:** 2026-03-05  
**ทดสอบกับ:** Aspose.Page for Java (รุ่นล่าสุด 2026)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}