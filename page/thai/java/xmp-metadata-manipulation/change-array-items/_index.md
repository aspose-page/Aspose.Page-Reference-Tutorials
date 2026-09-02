---
date: 2026-05-15
description: สำรวจ aspose.page xmp tutorial สำหรับ Java — เรียนรู้วิธีเปลี่ยนรายการอาร์เรย์ในเมตาดาต้า
  XMP, อัปเดตชื่อ EPS, ผู้สร้าง, และอื่น ๆ เพียงไม่กี่บรรทัดของโค้ด
keywords:
- aspose.page xmp tutorial
- change array items java
- xmp metadata java
linktitle: เปลี่ยนรายการอาร์เรย์ใน XMP ด้วย Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  headline: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  type: TechArticle
- description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  name: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  steps:
  - name: Get XMP Metadata
    text: Call `document.getXmpMetadata()` to retrieve the XMP metadata object associated
      with the EPS file.
  - name: Set "dc:title" Array Item
    text: Use `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` to replace the
      first title entry.
  - name: Set "dc:creator" Array Item
    text: Similarly, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` updates
      the first creator entry.
  - name: Initialize Output EPS File Stream
    text: Create a `FileOutputStream` pointing to the destination EPS file to write
      the updated document.
  - name: Save Document with Changed XMP Metadata
    text: The `PsDocument` class represents an EPS document and provides the `save`
      method to write changes to a stream.
  type: HowTo
- questions:
  - answer: No. You must invoke `setArrayItem` for each index you wish to modify;
      the API does not provide a bulk‑update method.
    question: Can I update multiple array items in one call?
  - answer: Yes. Provide the full prefix (e.g., `myNS:customProp`) when calling `setArrayItem`
      or `removeArrayItem`.
    question: Does aspose.page xmp java support custom namespaces?
  - answer: Reload the EPS with `PsDocument`, call `getXmpMetadata()`, and inspect
      the returned values, or open the file in an XMP viewer.
    question: How do I verify that the metadata was updated correctly?
  - answer: Use `removeArrayItem(namespace, index)` to delete a specific entry from
      an XMP array.
    question: Is it possible to remove an array item entirely?
  - answer: No. XMP metadata is stored separately from the graphic content and does
      not alter how the EPS renders.
    question: Will the changes affect the visual appearance of the EPS?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'aspose.page xmp tutorial: เปลี่ยนรายการอาร์เรย์ใน XMP ด้วย Java'
url: /th/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp tutorial: การเปลี่ยนรายการอาเรย์ใน XMP ด้วย Java

## บทนำ
ยินดีต้อนรับสู่ **aspose.page xmp tutorial** อย่างครบถ้วนของเรา ในคู่มือนี้เราจะสาธิตขั้นตอนการเปลี่ยนรายการในอาเรย์ของเมตาดาต้า XMP ภายในไฟล์ EPS ด้วย Aspose.Page สำหรับ Java ไม่ว่าคุณจะต้องการอัปเดตชื่อเอกสาร รายชื่อผู้เขียน หรืออาเรย์ XMP ใด ๆ กระบวนการนี้ตรงไปตรงมา ทำงานโดยโปรแกรมทั้งหมด และทำงานกับ Java 8 + ได้อย่างเต็มที่

## คำตอบอย่างรวดเร็ว
- **aspose.page xmp java ทำอะไร?** อ่านและเขียนเมตาดาต้า XMP ในไฟล์ EPS โดยตรงจาก Java  
- **ต้องมีลิขสิทธิ์เพื่อทดลองใช้งานหรือไม่?** ใช่ — มีรุ่นทดลองฟรี 30 วัน; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน JDK ใด?** Java 8 หรือใหม่กว่า (รวมถึง Java 11, 17, และ 21)  
- **สามารถแก้ไขฟิลด์เมตาดาต้าอื่นได้หรือไม่?** แน่นอน — คุณสมบัติ XMP ใด ๆ รวมถึงเนมสเปซที่กำหนดเอง สามารถอ่านหรืออัปเดตได้  
- **API ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** การดำเนินการอ่าน/เขียนส่วนใหญ่ปลอดภัยเมื่อแต่ละเธรดทำงานกับอินสแตนซ์ `PsDocument` ของตนเอง

## aspose.page xmp java คืออะไร?
`aspose.page xmp java` คือส่วนประกอบของ Aspose.Page สำหรับ Java ที่ทำให้ Extensible Metadata Platform (XMP) กลายเป็นอ็อบเจ็กต์ Java ที่ใช้งานง่าย ช่วยให้คุณจัดการอาเรย์, bag, และคุณสมบัติโครงสร้างโดยไม่ต้องจัดการ XML ดิบ ในการใช้งานจริง คุณจะใช้เมธอดระดับสูงเช่น `setArrayItem` และ `removeArrayItem` เพื่อแก้ไขเมตาดาต้าได้ทันที

## ทำไมต้องใช้ aspose.page xmp java สำหรับเมตาดาต้า EPS?
คุณควรใช้ไลบรารีนี้เมื่อจำเป็นต้องควบคุมเมตาดาต้า EPS อย่างแม่นยำและอัตโนมัติในระดับใหญ่ Aspose.Page รองรับ **ฟิลด์สคีม่า XMP มากกว่า 30 รายการ** และสามารถประมวลผลไฟล์ขนาด **สูงสุด 500 MB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ ทำให้ได้ความเร็วสูงและใช้หน่วยความจำน้อย API ยังรับประกันว่าการเปลี่ยนแปลงจะคงกราฟิกเดิมไว้ ดังนั้นการเรนเดอร์ภาพจะไม่ถูกกระทบ

## ข้อกำหนดเบื้องต้น
- ติดตั้ง Java Development Kit (JDK) 8 หรือใหม่กว่า  
- ไลบรารี Aspose.Page สำหรับ Java ดาวน์โหลด JAR ล่าสุดจาก [ที่นี่](https://releases.aspose.com/page/java/)  
- ไฟล์ลิขสิทธิ์ Aspose ที่ถูกต้อง (หรือไลเซนส์ทดลอง) วางไว้ใน classpath

## วิธีการเปลี่ยนรายการอาเรย์ด้วย aspose.page xmp java
ส่วนนี้จะแสดงเวิร์กโฟลว์เต็มขั้นตอน: เปิดไฟล์ EPS, ดึงอ็อบเจ็กต์เมตาดาต้า XMP, แก้ไขรายการอาเรย์ที่ต้องการ, แล้วบันทึกเอกสารที่อัปเดตกลับไปยังดิสก์ แต่ละขั้นตอนมีโค้ด Java สั้น ๆ ชัดเจน ทำให้ง่ายต่อการนำไปใช้ในแอปพลิเคชันของคุณ

### ขั้นตอนที่ 1: ดึงเมตาดาต้า XMP
เรียก `document.getXmpMetadata()` เพื่อรับอ็อบเจ็กต์เมตาดาต้า XMP ที่เชื่อมโยงกับไฟล์ EPS

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

### ขั้นตอนที่ 2: ตั้งค่ารายการอาเรย์ "dc:title"
ใช้ `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` เพื่อแทนที่รายการหัวเรื่องแรก

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### ขั้นตอนที่ 3: ตั้งค่ารายการอาเรย์ "dc:creator"
เช่นเดียวกัน `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` จะอัปเดตรายการผู้สร้างแรก

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### ขั้นตอนที่ 4: เริ่มต้นสตรีมไฟล์ EPS ปลายทาง
สร้าง `FileOutputStream` ชี้ไปยังไฟล์ EPS ปลายทางเพื่อบันทึกเอกสารที่อัปเดต

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### ขั้นตอนที่ 5: บันทึกเอกสารพร้อมเมตาดาต้า XMP ที่เปลี่ยนแปลง
คลาส `PsDocument` แทนเอกสาร EPS และมีเมธอด `save` เพื่อเขียนการเปลี่ยนแปลงลงสตรีม

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## ข้อผิดพลาดทั่วไป & เคล็ดลับ
- **Index Out of Bounds:** ตรวจสอบให้แน่ใจว่าดัชนีที่ต้องการมีอยู่ มิฉะนั้น Aspose จะโยน `ArrayIndexOutOfBoundsException`  
- **การจัดการสตรีม:** ปิดสตรีมเสมอในบล็อก `finally` หรือใช้ try‑with‑resources เพื่อป้องกันการล็อกไฟล์  
- **การเปิดใช้งานลิขสิทธิ์:** ลืมใส่ลิขสิทธิ์ที่ถูกต้องจะทำให้ไฟล์ EPS แสดงลายน้ำในโหมดทดลอง  
- **ไฟล์ขนาดใหญ่:** สำหรับไฟล์ EPS ที่ใหญ่กว่า 200 MB ควรเพิ่มขนาด heap ของ JVM (`-Xmx2g`) เพื่อหลีกเลี่ยงความกดดันของหน่วยความจำ

## คำถามที่พบบ่อย

**Q: สามารถอัปเดตหลายรายการอาเรย์ในคำสั่งเดียวได้หรือไม่?**  
A: ไม่ได้ คุณต้องเรียก `setArrayItem` สำหรับแต่ละดัชนีที่ต้องการแก้ไข; API ไม่รองรับวิธีอัปเดตแบบ bulk

**Q: aspose.page xmp java รองรับเนมสเปซที่กำหนดเองหรือไม่?**  
A: รองรับ ให้ระบุพรีฟิกซ์เต็ม (เช่น `myNS:customProp`) เมื่อเรียก `setArrayItem` หรือ `removeArrayItem`

**Q: จะตรวจสอบว่าเมตาดาต้าอัปเดตถูกต้องหรือไม่?**  
A: โหลด EPS ใหม่ด้วย `PsDocument`, เรียก `getXmpMetadata()` แล้วตรวจสอบค่าที่คืนกลับ, หรือเปิดไฟล์ในโปรแกรมดู XMP

**Q: สามารถลบรายการอาเรย์ออกทั้งหมดได้หรือไม่?**  
A: ใช้ `removeArrayItem(namespace, index)` เพื่อลบรายการเฉพาะจากอาเรย์ XMP

**Q: การเปลี่ยนแปลงนี้จะส่งผลต่อการแสดงผลของ EPS หรือไม่?**  
A: ไม่เลย เมตาดาต้า XMP ถูกเก็บแยกจากเนื้อหากราฟิกและไม่กระทบการเรนเดอร์ของ EPS

## สรุป
คุณได้เรียนรู้ **aspose.page xmp tutorial** สำหรับ Java และสามารถเปลี่ยนรายการอาเรย์ในเมตาดาต้า XMP ของ EPS ได้อย่างมั่นใจ ความสามารถนี้ช่วยให้คุณสร้างไพป์ไลน์เอกสารอัตโนมัติ, อัปเดตเมตาดาต้าเป็นกลุ่ม, และจัดการสินทรัพย์ได้ดีขึ้นโดยไม่ต้องยุ่งกับข้อมูลภาพ

---

**อัปเดตล่าสุด:** 2026-05-15  
**ทดสอบกับ:** Aspose.Page for Java 24.11 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## บทแนะนำที่เกี่ยวข้อง

- [เพิ่มรายการอาเรย์ในเมตาดาต้า XMP ด้วย Java](/page/java/xmp-metadata-manipulation/add-array-items/)
- [aspose page xmp tutorial – การเปลี่ยนค่า Named Value ใน XMP ด้วย Java](/page/java/xmp-metadata-manipulation/change-named-value/)
- [วิธีอ่านเมตาดาต้า XMP ด้วย Java – คู่มือ Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}