---
date: 2026-06-20
description: เรียนรู้วิธีตั้งขนาดหน้า A4, สร้างไฟล์ PostScript ใน Java, และเพิ่มฟอนต์ที่กำหนดเองโดยใช้
  Aspose.Page. ทดลองใช้รุ่นทดลองฟรีวันนี้!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: สร้างเอกสารใน Java ด้วย PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: วิธีตั้งขนาดหน้า A4 และสร้างไฟล์ PostScript ใน Java ด้วย Aspose.Page
url: /th/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งขนาดหน้า A4 และสร้าง PostScript ใน Java ด้วย Aspose.Page

## บทนำ
หากคุณต้อง **ตั้งขนาดหน้า A4** ขณะสร้างไฟล์ PostScript จาก Java, Aspose.Page มี API ที่เร็วและเชื่อถือได้ซึ่งซ่อนรายละเอียดระดับล่างไว้ ในบทแนะนำนี้เราจะเดินผ่านขั้นตอนทั้งหมด—การสร้างเอกสาร PostScript, การกำหนดขนาดหน้า A4, และ **การเพิ่มฟอนต์แบบกำหนดเอง** เมื่อจำเป็น. เมื่อเสร็จคุณจะได้โค้ดสแนปช็อตที่พร้อมใช้งานซึ่งสามารถนำไปใส่ในโปรเจกต์ Java ใดก็ได้.

## คำตอบสั้น
- **ไลบรารีใดสร้าง PostScript ใน Java?** Aspose.Page for Java.  
- **ขนาดหน้าที่คู่มือมุ่งหมายคืออะไร?** A4 (210 มม × 297 มม).  
- **ฉันสามารถฝังฟอนต์ของฉันเองได้หรือไม่?** ได้ – ตั้งค่าโฟลเดอร์ฟอนต์เพิ่มเติมในตัวเลือกการบันทึก.  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์; มีรุ่นทดลองฟรีให้ใช้.  
- **รองรับเวอร์ชัน Java ใดบ้าง?** Java 8 ขึ้นไป.

## วิธีตั้งขนาดหน้า a4 และสร้าง postscript ใน Java
โหลดไลบรารี Aspose.Page, กำหนด `PsSaveOptions` ด้วยค่าคงที่ A4, แล้วเขียนเอกสารลงไฟล์ – ทั้งหมดในไม่กี่บรรทัดของโค้ด. วิธีการโดยตรงนี้รับประกันขนาดหน้าที่ถูกต้องและให้คุณเพิ่มฟอนต์แบบกำหนดเองโดยไม่ต้องตั้งค่าเพิ่มเติม.

## PostScript A4 คืออะไร?
PostScript A4 คือมาตรฐาน ISO 216 (210 มม × 297 มม) ที่แสดงในภาษาการอธิบายหน้าของ PostScript. มันกำหนดพื้นที่ที่พิมพ์ได้ซึ่งเครื่องพิมพ์และโปรแกรมดูจะตีความ, ทำให้การจัดหน้าเป็นแบบเดียวกันบนทุกแพลตฟอร์ม. เนื่องจาก PostScript อธิบายเนื้อหาหน้าแบบอิสระจากอุปกรณ์, การใช้ขนาด A4 รับประกันว่าเอกสารจะปรากฏเหมือนกันบนเครื่องพิมพ์หรือโปรแกรมดูที่รองรับ A4 ทั่วโลก.

## ทำไมต้องใช้ Aspose.Page เพื่อตั้งขนาดหน้า postscript?
Aspose.Page รองรับ **30+ ตัวดำเนินการ PostScript** และสามารถสร้างไฟล์ได้ถึง **500 MB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ. สิ่งนี้ให้คุณควบคุมขนาดหน้าได้อย่างแม่นยำพร้อมจัดการงานขนาดใหญ่อย่างมีประสิทธิภาพ. ไลบรารียังทำให้ซินแทกซ์ PostScript ที่ซับซ้อนเป็นเรื่องง่าย, จัดการทรัพยากรอัตโนมัติ, และให้การสตรีมที่มีประสิทธิภาพสูง, ทำให้เหมาะกับทั้งโบรชัวร์หน้าเดียวและรายงานหลายหน้าที่ซับซ้อน.

## วิธีเพิ่มฟอนต์แบบกำหนดเอง java
การฝังแบบอักษรของคุณเองทำให้เอกสารที่สร้างขึ้นดูเหมือนตามการออกแบบบนเครื่องพิมพ์หรือโปรแกรมดูใดก็ได้, และ Aspose.Page จะค้นหาแบบอักษรที่วางไว้ในโฟลเดอร์ที่ระบุโดยอัตโนมัติ. โดยการลงทะเบียนโฟลเดอร์ฟอนต์เพิ่มเติม, คุณสามารถใช้ฟอนต์ TrueType หรือ OpenType ใดก็ได้, ป้องกันการแทนที่ด้วยฟอนต์สำรอง, และรักษาความสอดคล้องของแบรนด์บนอุปกรณ์ผลลัพธ์ทั้งหมด.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานการเขียนโปรแกรม Java.  
- Aspose.Page for Java ติดตั้งแล้ว. คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/java/).  
- โฟลเดอร์ชื่อ `necessary_fonts` (หรือชื่อใดก็ได้ที่คุณต้องการ) ที่บรรจุฟอนต์แบบกำหนดเองที่ต้องการฝัง.

## นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ, นำเข้าคลาส Aspose.Page ที่จำเป็น:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

ตอนนี้เราจะแบ่งตัวอย่างออกเป็นขั้นตอนที่ชัดเจนและลำดับเลข.

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
ค่าคงที่ `OUTPUT_DIR` บอกไลบรารีว่าจะเขียนไฟล์ที่สร้างขึ้นไปที่ไหน.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### ขั้นตอนที่ 2: กำหนดโฟลเดอร์ฟอนต์
`FONTS_FOLDER` ชี้ไปยังไดเรกทอรีที่เก็บฟอนต์ TrueType หรือ OpenType ที่คุณต้องการใช้.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 3: สร้าง Output Stream สำหรับเอกสาร PostScript
`FileOutputStream` เปิดสตรีมที่จะรับผลลัพธ์ PostScript A4 สุดท้าย.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### ขั้นตอนที่ 4: สร้าง Save Options ด้วยขนาด A4
`PsSaveOptions` ให้คุณระบุขนาดหน้าที่ต้องการ.  
**คำนิยาม:** `PsPageSize` เป็น enumeration ที่มีค่าคงที่ของขนาดหน้ามาตรฐาน เช่น A4, Letter, และ Legal.  
การตั้งค่า `options.setPageSize(PsPageSize.A4)` จะกำหนดเอกสารให้ใช้ขนาด A4 มาตรฐาน.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### ขั้นตอนที่ 5: ตั้งค่าขอบหน้าและเพิ่มโฟลเดอร์ฟอนต์แบบกำหนดเอง
`options.setMargins(0, 0, 0, 0)` ลบขอบทั้งหมดเพื่อให้ได้หน้าที่เต็มขอบ, และ `options.setAdditionalFontsFolder(FONTS_FOLDER)` ลงทะเบียนฟอนต์ของคุณ.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### ขั้นตอนที่ 6: สร้างเอกสาร PS แบบหลายหน้า หรือหน้าเดียว
`PsDocument document = new PsDocument(outputStream, options)` สร้างเอกสาร. `PsDocument` แทนเอกสาร PostScript ที่อาจมีหนึ่งหรือหลายหน้า. ตั้งค่า `multiPaged` เป็น `true` หากต้องการผลลัพธ์หลายหน้า.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### ขั้นตอนที่ 7: ปิดหน้าและบันทึกเอกสาร
การเรียก `document.close()` จะสรุปไฟล์และเขียนผลลัพธ์ **PostScript A4 size** ลงดิสก์.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## ปัญหาทั่วไปและเคล็ดลับ
- **ฟอนต์ไม่แสดง?** ตรวจสอบว่าไฟล์ฟอนต์เป็นรูปแบบ TrueType หรือ OpenType ที่รองรับและ `FONTS_FOLDER` ลงท้ายด้วยเครื่องหมายทับ (`/`).  
- **ขอบยังคงแสดง?** เรียก `options.setMargins(...)` **ก่อน** สร้าง `PsDocument`.  
- **ผลลัพธ์หลายหน้าเป็นสีขาว?** อย่าลืมเรียก `document.newPage()` สำหรับแต่ละหน้าที่ต้องการเพิ่ม.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ฟอนต์แบบกำหนดเองในเอกสาร PostScript ของฉันได้หรือไม่?**  
ตอบ: ได้, ตั้งค่าโฟลเดอร์ฟอนต์เพิ่มเติมในตัวเลือกการบันทึก (ดูขั้นตอน 5) และ Aspose.Page จะฝังฟอนต์โดยอัตโนมัติ.

**ถาม: มีรุ่นทดลองของ Aspose.Page for Java หรือไม่?**  
ตอบ: มี, คุณสามารถรับรุ่นทดลองฟรีได้ [ที่นี่](https://releases.aspose.com/).

**ถาม: จะเข้าถึงเอกสารอ้างอิง API ทั้งหมดได้อย่างไร?**  
ตอบ: ดูเอกสารอ้างอิง [ที่นี่](https://reference.aspose.com/page/java/).

**ถาม: จะซื้อไลเซนส์สำหรับ Aspose.Page for Java ได้จากที่ไหน?**  
ตอบ: คุณสามารถซื้อไลเซนส์ได้ [ที่นี่](https://purchase.aspose.com/buy).

**ถาม: จะขอความช่วยเหลือจากชุมชนได้ที่ไหน?**  
ตอบ: เยี่ยมชมฟอรั่ม Aspose.Page ที่ [forum](https://forum.aspose.com/c/page/39).

**ถาม: สามารถสร้างไฟล์ PostScript หลายหน้าได้หรือไม่?**  
ตอบ: แน่นอน—ตั้งค่า `multiPaged` เป็น `true` ในขั้นตอน 6 และเรียก `document.newPage()` สำหรับแต่ละหน้าที่เพิ่ม.

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้ **วิธีตั้งขนาดหน้า a4** และสร้างไฟล์ **PostScript** ใน Java ด้วย Aspose.Page, พร้อมทั้ง **เพิ่มฟอนต์แบบกำหนดเอง java** และควบคุมตัวเลือกขนาดหน้า. Aspose.Page จัดการส่วนที่ซับซ้อนให้คุณ, เพื่อให้คุณมุ่งเน้นที่เนื้อหาเอกสารของคุณ.

---

**อัปเดตล่าสุด:** 2026-06-20  
**ทดสอบด้วย:** Aspose.Page for Java 24.11  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [Aspose.Page Java Tutorial – set custom page size while Adding Pages in PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [How to Add Text in PostScript with Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial - Convert PostScript to PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```