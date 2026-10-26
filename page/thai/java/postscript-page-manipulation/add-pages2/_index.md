---
date: 2026-10-25
description: เรียนรู้วิธีตั้งค่าขนาดหน้าที่กำหนดเองและเพิ่มหน้าในเอกสาร Java PostScript
  ด้วย Aspose.Page ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการจัดการเอกสารที่ราบรื่น
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: การเพิ่มหน้าใน PostScript
og_description: เรียนรู้วิธีตั้งค่าขนาดหน้าที่กำหนดเองใน PostScript ด้วย Aspose.Page
  สำหรับ Java ปฏิบัติตามคำแนะนำขั้นตอนต่อขั้นตอนเพื่อเพิ่มหน้า ตั้งค่ามิติ และบันทึกเอกสารอย่างมีประสิทธิภาพ
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: ตั้งค่าขนาดหน้าที่กำหนดเองใน PostScript ด้วย Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: บทเรียน Aspose.Page Java – ตั้งค่าขนาดหน้าที่กำหนดเองขณะเพิ่มหน้าใน PostScript
url: /th/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – ตั้งค่าขนาดหน้ากำหนดเองขณะเพิ่มหน้าใน PostScript

## บทนำ

ในแอปพลิเคชัน Java สมัยใหม่ การ **set custom page size** สำหรับผลลัพธ์ PostScript มักจำเป็น—ไม่ว่าจะเป็นการสร้างใบแจ้งหนี้, ตั๋ว, หรือกราฟิกแบบกำหนดเอง บทเรียนนี้จะแสดงวิธีตั้งค่าขนาดหน้ากำหนดเองสำหรับแต่ละหน้า, เพิ่มหลายหน้า, และสร้างไฟล์ PostScript ที่ตรงกับความต้องการการจัดวางของคุณอย่างแม่นยำ คุณจะได้รับตัวอย่างที่สมบูรณ์และสามารถรันได้ซึ่งสามารถนำไปใช้ในโครงการ Java 8+ ใดก็ได้.

## คำตอบด่วน
- **ฉันสามารถตั้งค่าขนาดหน้าที่แตกต่างกันสำหรับแต่ละหน้าได้หรือไม่?** ใช่—คุณสามารถเปิดหน้าด้วยมิติที่กำหนดเองโดยใช้ `document.openPage(width, height)`.  
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานในสภาพแวดล้อมการผลิตหรือไม่?** จำเป็นต้องมีใบอนุญาต Aspose.Page ที่ถูกต้องสำหรับการใช้งานที่ไม่ใช่การประเมินผล.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** ไลบรารีทำงานกับ Java 8 และรุ่นใหม่กว่า.  
- **API นี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** อินสแตนซ์ของ Document ไม่ปลอดภัยต่อการทำงานหลายเธรด; สร้าง `PsDocument` แยกสำหรับแต่ละเธรด.  
- **ไฟล์ PostScript สามารถมีขนาดใหญ่ได้เท่าใด?** Aspose.Page จัดการไฟล์หลายเมกะไบต์ได้อย่างมีประสิทธิภาพ; การใช้หน่วยความจำเพิ่มตามเนื้อหา ไม่ใช่จำนวนหน้า.  
- **ฉันสามารถใช้ overload ของ open page width/height ได้หรือไม่?** แน่นอน—`openPage(double width, double height)` ให้คุณระบุมิติใด ๆ ในหน่วย points.  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- Aspose.Page for Java ที่เพิ่มในโครงการของคุณ (Maven/Gradle หรือ JAR แบบแมนนวล).  
- สภาพแวดล้อมการพัฒนา Java (IDE, JDK 8+).  

## นำเข้าแพ็กเกจ
คลาสต่อไปนี้จำเป็นต้องใช้: `FileOutputStream` สำหรับเขียนไฟล์, `PsDocument` สำหรับสร้างเอกสาร PostScript, และ `PsSaveOptions` สำหรับกำหนดค่าตัวเลือกการส่งออก.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ขั้นตอนที่ 1: สร้างเอกสาร postscript แบบหลายหน้า
`PsDocument` เป็นคลาสหลักที่แทนเอกสาร PostScript ซึ่งสามารถมีหลายหน้า.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## ขั้นตอนที่ 2: เพิ่มเนื้อหาไปยังหน้าที่หนึ่ง
เมื่อเอกสารพร้อม, คุณสามารถเพิ่มเนื้อหาใด ๆ ที่ต้องการไปยังหน้าที่หนึ่งได้ เมื่อเสร็จแล้ว, ปิดหน้าด้วยการเรียก `closePage` เพื่อบันทึกเนื้อหา.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## วิธีตั้งค่าขนาดหน้ากำหนดเอง
คุณตั้งค่าขนาดหน้ากำหนดเองโดยเรียก `document.openPage(width, height)` พร้อมด้วยมิติที่ต้องการในหน่วย points ก่อนวาดเนื้อหาใด ๆ `openPage(width, height)` จะเปิดหน้าที่ใหม่ด้วยความกว้างและความสูงที่ระบุ, ให้คุณควบคุมแคนวาสของหน้าได้อย่างเต็มที่ หากขนาดหน้าตั้งต้นไม่ตรงกับความต้องการของคุณ, คุณสามารถ **set a custom page size** เมื่อเปิดหน้าที่ใหม่ได้ ซึ่งเป็นประโยชน์สำหรับใบเสร็จ, ป้าย, หรือการจัดวางที่ไม่เป็นมาตรฐานใด ๆ.

## ขั้นตอนที่ 3: เพิ่มหน้าที่สองด้วยขนาดที่แตกต่าง
ด้านล่างเราจะเปิดหน้าที่สองและระบุความกว้างและความสูงที่กำหนดเอง (ในหน่วย points) อย่างชัดเจน สิ่งนี้แสดงวิธีตั้งค่าขนาดหน้ากำหนดเองสำหรับแต่ละหน้า, ให้คุณสามารถทำงานกับ **different page sizes** ภายในเอกสารเดียวได้.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
สุดท้าย, บันทึกการเปลี่ยนแปลงโดยการบันทึกเอกสาร ทุกหน้ารวมถึงหน้าที่มีขนาดกำหนดเองจะถูกเขียนลงในไฟล์ผลลัพธ์.

```java
// Save the document
document.save();
```

โดยทำตามขั้นตอนเหล่านี้, คุณสามารถเพิ่มหน้าและ **set custom page size** ในเอกสาร Java PostScript ด้วย Aspose.Page ได้อย่างราบรื่น, ให้คุณควบคุมการจัดวางของแต่ละหน้าได้อย่างเต็มที่.

## ทำไมต้องใช้ Aspose.Page เพื่อกำหนดขนาดหน้ากำหนดเอง?
Aspose.Page ให้การควบคุมที่แม่นยำต่อมิติของหน้า, ทำให้คุณสามารถกำหนดความกว้างและความสูงใด ๆ ในหน่วย points, ผสมหลายขนาดหน้าในเอกสารเดียว, และสตรีมเนื้อหาอย่างมีประสิทธิภาพสำหรับการสร้าง PostScript ที่มีประสิทธิภาพสูง ซึ่งทำให้เหมาะสำหรับใบแจ้งหนี้, ตั๋ว, และการประมวลผลแบบแบตช์ขนาดใหญ่ที่ต้องการการใช้หน่วยความจำน้อย.

Aspose.Page ให้คุณกำหนดมิติหน้าที่แม่นยำในหน่วย points, ผสมหลายขนาดในไฟล์เดียว, และสตรีมเนื้อหาอย่างมีประสิทธิภาพ, ซึ่งให้การควบคุมที่แม่นยำและประสิทธิภาพสูงสำหรับการสร้าง PostScript.  
- **ความแม่นยำ:** มิติถูกกำหนดในหน่วย points, ดังนั้นคุณจะได้การควบคุมที่แม่นยำต่อความกว้างและความสูงของหน้า.  
- **ความยืดหยุ่น:** ผสมและจับคู่ **different page sizes** ในไฟล์ PostScript เดียว.  
- **ประสิทธิภาพ:** ไลบรารีสตรีมเนื้อหาโดยตรงไปยังไฟล์ผลลัพธ์, รองรับไฟล์ขนาดถึง 500 MB โดยคงการใช้ heap ต่ำกว่า 100 MB, ทำให้เหมาะกับสถานการณ์การ **generate PostScript file** ขนาดใหญ่.  
- **API ครบครัน:** รองรับ primitive กราฟิกมากกว่า 30 ชนิด, รูปแบบภาพ 10 รูปแบบ, และออบเจ็กต์ข้อความไม่จำกัดต่อหน้า—ทั้งหมดนี้ยังคงเคารพมิติที่คุณกำหนดเอง.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **มิติของหน้าปรากฏสลับกัน** | จำไว้ว่า `openPage(width, height)` ต้องการความกว้างก่อน, จากนั้นความสูง (ทั้งสองเป็นหน่วย points). |
| **เนื้อหาเกินขอบหน้ากระดาษ** | ใช้ระบบพิกัด `PsGraphics` เพื่อวางตำแหน่งองค์ประกอบภายในขอบเขตที่กำหนดเอง, หรือปรับสเกลการวาดของคุณ. |
| **ข้อผิดพลาด Out‑of‑memory ในเอกสารขนาดใหญ่** | เปิดใช้งานการสตรีมโดยเขียนโดยตรงไปยัง `FileOutputStream` ตามที่แสดง, และหลีกเลี่ยงการโหลดภาพขนาดใหญ่เข้าสู่หน่วยความจำทั้งหมดในครั้งเดียว. |

## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มหน้าที่มีขนาดต่างกันในเอกสาร PostScript เดียวได้หรือไม่?
ได้, ตามที่แสดงในบทเรียนนี้, คุณสามารถเพิ่มหน้าที่มีขนาดต่างกันในเอกสาร PostScript แบบหลายหน้า.

### มีข้อจำกัดใด ๆ เกี่ยวกับจำนวนหน้าที่ฉันสามารถเพิ่มได้หรือไม่?
Aspose.Page รองรับการเพิ่มจำนวนหน้าที่เกือบไม่จำกัดในเอกสาร.

### ฉันสามารถเพิ่มเนื้อหากำหนดเอง เช่น รูปภาพหรือกราฟิก ไปยังหน้าได้หรือไม่?
แน่นอน! Aspose.Page อนุญาตให้คุณเพิ่มเนื้อหาหลากหลาย รวมถึงข้อความ, รูปภาพ, และองค์ประกอบกราฟิกอื่น ๆ.

### Aspose.Page เหมาะสำหรับจัดการเอกสารขนาดใหญ่หรือไม่?
ใช่, Aspose.Page ถูกออกแบบมาเพื่อจัดการเอกสารขนาดเล็กและขนาดใหญ่ได้อย่างมีประสิทธิภาพ.

### ฉันสามารถหาแหล่งข้อมูลและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Page ได้ที่ไหน?
สำรวจ [เอกสาร Aspose.Page](https://reference.aspose.com/page/java/), หรือเยี่ยมชม [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชน.  

**คำถามและคำตอบเพิ่มเติม**

**Q:** *รูปแบบภาพใดบ้างที่รองรับเมื่อวาดบนหน้า PostScript?*  
**A:** คุณสามารถฝังภาพ PNG, JPEG, BMP, และ GIF ได้โดยตรงโดยใช้ Drawing API.  

**Q:** *ฉันจะเปลี่ยน DPI เริ่มต้นของเอกสารได้อย่างไร?*  
**A:** ตั้งค่า `PsSaveOptions.setResolution(int dpi)` ก่อนสร้าง `PsDocument`.  

**Q:** *ฉันสามารถเข้ารหัสไฟล์ PostScript ด้วยรหัสผ่านได้หรือไม่?*  
**A:** PostScript เองไม่รองรับการเข้ารหัส, แต่คุณสามารถห่อผลลัพธ์ในไฟล์ PDF และกำหนดการตั้งค่าความปลอดภัยได้หากต้องการ.

---

**อัปเดตล่าสุด:** 2026-10-25  
**ทดสอบกับ:** Aspose.Page for Java 24.10  
**ผู้เขียน:** Aspose  

## บทเรียนที่เกี่ยวข้อง

- [วิธีตั้งค่าขนาดหน้า A4 และสร้าง PostScript ใน Java ด้วย Aspose.Page](/page/java/document-creation/postscript/)
- [วิธีแปลง PostScript เป็น PDF ด้วย Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [วิธีวาดสี่เหลี่ยมใน Java PostScript ด้วย Aspose.Page](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}