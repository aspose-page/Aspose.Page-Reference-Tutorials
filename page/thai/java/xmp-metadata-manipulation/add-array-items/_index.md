---
date: 2025-12-18
description: เรียนรู้วิธีเพิ่มเมตาดาต้าโดยการแทรกรายการอาร์เรย์ลงในเมตาดาต้า XMP ของไฟล์
  EPS ด้วย Aspose.Page สำหรับ Java. ตามคู่มือขั้นตอนโดยขั้นตอนของเรา.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: วิธีเพิ่มเมตาดาต้า – เพิ่มรายการอาเรย์ใน XMP (Java)
url: /th/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มรายการอาเรย์ในเมตาดาต้า XMP ด้วย Java

## วิธีการเพิ่มเมตาดาต้า
ยินดีต้อนรับสู่คู่มือแบบขั้นตอนของเราเกี่ยวกับ **วิธีการเพิ่มเมตาดาต้า** ให้กับไฟล์ EPS ด้วย Aspose.Page for Java ในบทเรียนนี้เราจะพาคุณผ่านการเพิ่มรายการอาเรย์ในเมตาดาต้า XMP ซึ่งเป็นความต้องการทั่วไปเมื่อคุณต้องการเสริมข้อมูลเอกสาร เช่น ชื่อเรื่องหรือผู้สร้าง เมื่อจบบทเรียนคุณจะเข้าใจว่าทำไม XMP ถึงมีคุณค่า วิธีการจัดการโปรแกรมเมตาดาต้า และวิธีการบันทึกไฟล์ EPS ที่อัปเดตแล้ว

## คำตอบสั้น
- **ใช้ไลบรารีอะไร?** Aspose.Page for Java  
- **ไฟล์ฟอร์แมตเป้าหมายคืออะไร?** EPS (Encapsulated PostScript)  
- **สามารถเพิ่มหลายชื่อเรื่องได้หรือไม่?** ได้, ใช้ `xmp.addArrayItem("dc:title", ...)` ซ้ำหลายครั้ง  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานจริงหรือไม่?** ต้องมี, จำเป็นต้องใช้ลิขสิทธิ์ Aspose.Page ที่- **โค้ดนี้เข้ากันได้กับ Java 8+ หรือไม่?** แน่นอน, ทำงานได้กับทุกเวอร์ชัน Java สมัยใหม่  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทเรียน โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Page for Java แล้ว
- มีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- มีไฟล์ EPS ที่มีเมตาดาต้า XMP หรือคอมเมนต์เมตาดาต้า PS อยู่แล้ว

## การนำเข้าแพคเกจ
เพื่อเริ่มต้น คุณต้องนำเข้าแพคเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Page รวมบรรทัดต่อไปนี้ไว้ที่ส่วนต้นของไฟล์ Java ของคุณ:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## ขั้นตอนที่ 1: ดึงเมตาดาต้า XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
ในขั้นตอนนี้ เราจะดึงเมตาดาต้า XMP ที่มีอยู่จากไฟล์ EPS หากไฟล์ EPS ยังไม่มีเมตาดาต้า XMP Aspose.Page จะสร้างใหม่และเติมค่าจากคอมเมนต์เมตาดาต้า PS

## ขั้นตอนที่ 2: เพิ่มรายการอาเรย์ "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
ต่อไป เราจะเพิ่มรายการอาเรย์ใหม่ให้กับคุณสมบัติ **dc:title** ในเมตาดาต้า XMP แทนที่ `"NewTitle"` ด้วยชื่อเรื่องที่ต้องการ

## ขั้นตอนที่ 3: เพิ่มรายการอาเรย์ "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
ในทำนองเดียวกัน เราจะเพิ่มรายการอาเรย์ใหม่ให้กับคุณสมบัติ **dc:creator** ในเมตาดาต้า XMP แทนที่ `"NewCreator"` ด้วยข้อมูลผู้สร้างที่ต้องการ

## ขั้นตอนที่ 4: เริ่มต้นสตรีมไฟล์ EPS ขาออก
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
เตรียมสตรีมไฟล์ EPS ขาออกที่เอกสารที่แก้ไขแล้วพร้อมเมตาดาต้า XMP ที่อัปเดตจะถูกบันทึกลงไป

## ขั้นตอนที่ 5: บันทึกเอกสารพร้อมเมตาดาต้า XMP ที่เปลี่ยนแปลง
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
บันทึกเอกสารพร้อมเมตาดาต้า XMP ที่อัปเดตลงในไฟล์ EPS ขาออก

## สรุป
ขอแสดงความยินดี! คุณได้เรียนรู้ **วิธีการเพิ่มเมตาดาต้า** โดยการแทรกรายการอาเรย์ในเมตาดาต้า XMP ด้วย Aspose.Page for Java แล้ว ไลบรารีที่ทรงพลังนี้ทำให้การจัดการไฟล์ EPS ง่ายขึ้นและให้ฟังก์ชันการทำงานที่ครอบคลุมสำหรับการประมวลผลเอกสาร

## คำถามที่พบบ่อย

### ฉันสามารถใช้ Aspose.Page for Java กับฟอร์แมตเอกสารอื่นได้หรือไม่?
ได้, Aspose.Page รองรับฟอร์แมตเอกสารหลายประเภท รวมถึง EPS, PDF, และ XPS

### มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?
มี, คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](https://releases.aspose.com/)

### จะหาเอกสารประกอบการใช้งานสำหรับ Aspose.Page for Java ได้จากที่ไหน?
เอกสารประกอบการใช้งานมีให้ [ที่นี่](https://reference.aspose.com/page/java/)

### จะซื้อ Aspose.Page for Java ได้อย่างไร?
คุณสามารถซื้อผลิตภัณฑ์ได้ [ที่นี่](https://purchase.aspose.com/buy)

### มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java หรือไม่?
มี, คุณสามารถรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

## คำถามเพิ่มเติมที่พบบ่อย

**Q: ฉันสามารถเพิ่มรายการอาเรย์มากกว่าหนึ่งรายการให้กับคุณสมบัติเดียวกันได้หรือไม่?**  
A: แน่นอน. เรียก `xmp.addArrayItem` หลายครั้งสำหรับคุณสมบัติเดียวกันเพื่อสร้างรายการค่า

**Q: วิธีนี้ทำงานกับสคีม่า XMP ที่มีอยู่ที่ไม่ใช่ Dublin Core หรือไม่?**  
A: ใช่, คุณสามารถเพิ่มรายการอาเรย์ให้กับคุณสมบัติ XMP ใดก็ได้ตราบใดที่อ้างอิงเนมสเปซอย่างถูกต้อง

**Q: ฉันจะตรวจสอบว่าเมตาดาต้าได้ถูกเพิ่มอย่างถูกต้องหรือไม่?**  
A: เปิดไฟล์ EPS ที่ได้ในโปรแกรมดูที่รองรับ XMP (เช่น Adobe Bridge) หรือดึงเมตาดาต้าออกโดยโปรแกรมด้วยเมธอด `XmpMetadata`

---

**อัปเดตล่าสุด:** 2025-12-18  
**ทดสอบกับ:** Aspose.Page for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}