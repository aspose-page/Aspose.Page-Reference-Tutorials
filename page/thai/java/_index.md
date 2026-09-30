---
date: 2026-09-29
description: เรียนรู้การแปลง postscript เป็น pdf ด้วย Java, การรวม pdfs ด้วย Java
  และการเชี่ยวชาญไลบรารีการแปลง pdf ของ Java ด้วย Aspose.Page.
keywords:
- postscript to pdf java
- merge pdfs java
- java pdf conversion library
lastmod: 2026-09-29
linktitle: บทเรียน Aspose.Page สำหรับ Java
og_description: เชี่ยวชาญการแปลง postscript เป็น pdf ด้วย Java ด้วย Aspose.Page. เรียนรู้วิธีการรวม
  pdfs ด้วย Java, จัดการ batch jobs, และใช้ไลบรารีการแปลง pdf ของ Java ชั้นนำ.
og_image_alt: Screenshot of Aspose.Page Java conversion example showing PostScript
  to PDF output
og_title: Postscript to PDF ใน Java – คู่มือ Aspose.Page ฉบับเต็ม
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn postscript to pdf java conversion, merge pdfs java and master
    java pdf conversion library using Aspose.Page.
  headline: Postscript to PDF in Java with Aspose.Page – Full guide
  type: TechArticle
- description: Learn postscript to pdf java conversion, merge pdfs java and master
    java pdf conversion library using Aspose.Page.
  name: Postscript to PDF in Java with Aspose.Page – Full guide
  steps:
  - name: '**Add the Aspose.Page Maven dependency** to your `pom.xml` (or the equivalent
      Gradle entry).'
    text: '**Add the Aspose.Page Maven dependency** to your `pom.xml` (or the equivalent
      Gradle entry).'
  - name: '**Instantiate the PostScriptDocument** by passing the path or an `InputStream`.'
    text: '**Instantiate the PostScriptDocument** by passing the path or an `InputStream`.'
  - name: '**Call the `save` method** with `SaveFormat.PDF` to write the PDF file.'
    text: '**Call the `save` method** with `SaveFormat.PDF` to write the PDF file.'
  - name: Loop through a directory of `.ps` files.
    text: Loop through a directory of `.ps` files.
  - name: For each file, instantiate `PostScriptDocument` and save as PDF.
    text: For each file, instantiate `PostScriptDocument` and save as PDF.
  - name: Optionally, **merge pdf files java‑style** using Aspose.PDF if needed.
    text: Optionally, **merge pdf files java‑style** using Aspose.PDF if needed.
  type: HowTo
- questions:
  - answer: Yes. Aspose.Page provides separate `PostScriptDocument` and `XpsDocument`
      classes, each with a `save(..., SaveFormat.PDF)` method, allowing you to handle
      both formats side‑by‑side.
    question: Can I convert both PostScript and XPS to PDF in the same application?
  - answer: No. Aspose.Page is a pure Java library; all rendering is performed internally
      without external dependencies.
    question: Do I need to install any native PostScript interpreters?
  - answer: Use streaming APIs (`load(InputStream)`) and process files sequentially
      or in parallel threads. The library is optimized for low memory consumption.
    question: How does the library handle large files or batch conversions?
  - answer: Absolutely. Simply pass Unicode strings to the `drawString` method; the
      library embeds the necessary fonts automatically.
    question: Is Unicode text fully supported when converting PostScript to PDF?
  - answer: Aspose offers perpetual licenses, subscription plans, and metered‑usage
      licenses. A free evaluation key is available for testing.
    question: What licensing options are available for production deployments?
  type: FAQPage
tags:
- postscript conversion
- Aspose.Page
- java document generation
- pdf processing
- java tutorials
title: Postscript to PDF ใน Java ด้วย Aspose.Page – คู่มือเต็ม
url: /th/java/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง PostScript เป็น PDF ใน Java ด้วย Aspose.Page

## บทนำ

หากคุณต้องการ **postscript to pdf java** อย่างรวดเร็วและเชื่อถือได้ Aspose.Page for Java ให้โซลูชันแบบ pure‑Java, zero‑dependency ที่สามารถผสานเข้ากับบริการ backend ใดก็ได้ ไม่ว่าคุณจะกำลังสร้างเอนจินออกใบกำกับ, pipeline รายงาน, หรือเครื่องมือย้ายระบบเก่า คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การแปลงไฟล์เดี่ยวจนถึงการประมวลผลแบตช์ขนาดใหญ่—เพื่อให้คุณเริ่มมอบ PDF ที่ค้นหาได้วันนี้

## คำตอบสั้น
- **วิธีที่ง่ายที่สุดในการแปลง PostScript เป็น PDF ใน Java คืออะไร?** ใช้คลาส `PostScriptDocument` ของ Aspose.Page และเรียก `save("output.pdf", SaveFormat.PDF)`  
- **ฉันสามารถแปลง XPS เป็น PDF ด้วยไลบรารีเดียวกันได้หรือไม่?** ใช่—Aspose.Page รองรับการแปลง XPS ผ่านคลาส `XpsDocument`  
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการปรับใช้; มีการทดลองใช้งานฟรีสำหรับการประเมิน  
- **เวอร์ชัน Java ใดที่รองรับ?** รองรับ Java 8 ถึง Java 21 อย่างเต็มที่  
- **มีการสนับสนุน Unicode ในตัวหรือไม่?** แน่นอน—Aspose.Page จัดการสตริง Unicode ได้โดยอัตโนมัติ

## อะไรคือ “convert PostScript to PDF”?

การแปลง PostScript เป็น PDF หมายถึงการนำคำอธิบายหน้าที่เขียนด้วยภาษา PostScript มาสร้างเป็นไฟล์ Portable Document Format (PDF) การแปลงนี้จะคงรักษาเลย์เอาต์, ฟอนต์, และกราฟิกเวกเตอร์ไว้ในขณะที่สร้างเอกสารที่เข้ากันได้กว้าง, ค้นหาได้ ไฟล์ PDF ที่ได้สามารถเปิดด้วยโปรแกรมดูมาตรฐานใดก็ได้และยังคงข้อความที่ค้นหาได้ ทำให้เหมาะสำหรับการเก็บถาวรและการประมวลผลต่อไป

## วิธีแปลง postscript เป็น pdf ด้วย Java?

คลาส `PostScriptDocument` แทนไฟล์ PostScript และให้เมธอดสำหรับโหลดและเรนเดอร์ไฟล์

โหลดไฟล์ PostScript ของคุณด้วย `new PostScriptDocument("input.ps")` แล้วเรียก `save("output.pdf", SaveFormat.PDF)` ทันที ไลบรารีจะทำการเรนเดอร์อย่างเต็มที่, จัดการฟอนต์, เกรเดียนท์, และความโปร่งใสโดยไม่ต้องใช้เครื่องมือภายนอก รูปแบบสองบรรทัดนี้ทำงานได้กับไฟล์เดี่ยวและสตรีม ทำให้เหมาะกับยูทิลิตี้เดสก์ท็อปและงานเซิร์ฟเวอร์ที่ต้องการ throughput สูง

### คู่มือขั้นตอนต่อขั้นตอน

1. **เพิ่มการพึ่งพา Aspose.Page Maven** ลงใน `pom.xml` (หรือรายการ Gradle ที่เทียบเท่า)  
2. **สร้างอินสแตนซ์ PostScriptDocument** โดยส่งพาธหรือ `InputStream` เข้าไป  
3. **เรียกเมธอด `save`** พร้อม `SaveFormat.PDF` เพื่อเขียนไฟล์ PDF  

> *โค้ดตัวอย่างจริงจะอยู่ในบทแนะนำเฉพาะด้านที่ลิงก์ด้านล่าง*

```java
import com.aspose.page.PostScriptDocument;
import com.aspose.page.SaveFormat;

public class ConvertPsToPdf {
    public static void main(String[] args) throws Exception {
        // Load the PostScript file
        PostScriptDocument psDoc = new PostScriptDocument("input.ps");
        // Save as PDF
        psDoc.save("output.pdf", SaveFormat.PDF);
    }
}
```

## ทำไมต้องใช้ Aspose.Page สำหรับ Java?

- **Zero‑dependency**: ไม่ต้องมีไบนารีเนทีฟหรือเครื่องมือภายนอก, การปรับใช้ง่ายเพียงแค่เพิ่ม JAR  
- **High fidelity**: เอนจินทำสำเนากราฟิกซับซ้อน, เกรเดียนท์, และความโปร่งใสด้วยความแม่นยำภาพ 100 %  
- **Cross‑format support**: รองรับ PostScript, XPS, EPS, และ PDF ใน API เดียว, ครอบคลุม **50+ ฟอร์แมต** เข้าและออก  
- **Scalable batch processing**: API สตรีมมิ่งช่วยให้แปลงไฟล์หลายร้อยหน้าโดยใช้หน่วยความจำต่ำกว่า 100 MB  
- **Full Unicode**: เรนเดอร์สตริง Unicode ทั้งหมดอย่างถูกต้อง, ฟอนต์ที่ต้องการสามารถฝังอัตโนมัติได้  

## ข้อกำหนดเบื้องต้น
- Java Development Kit (JDK) 8 หรือใหม่กว่า  
- Maven หรือ Gradle สำหรับการจัดการการพึ่งพา  
- ใบอนุญาต Aspose.Page for Java (หรือคีย์ประเมินชั่วคราว)  

## วิธีแปลง XPS เป็น PDF ใน Java

คลาส `XpsDocument` โหลดไฟล์ XPS และเปิดให้แปลงเป็นฟอร์แมตอื่นเช่น PDF

สร้างอินสแตนซ์ `XpsDocument` ชี้ไปที่ไฟล์ XPS ของคุณ, แล้วเรียก `save("output.pdf", SaveFormat.PDF)` เมธอด `save` ที่ใช้กับ PostScript ทำงานเช่นเดียวกัน ให้ workflow การแปลงเป็นเอกภาพ PDF ที่คงเลย์เอาต์, ฟอนต์, และกราฟิกเวกเตอร์เดิม, และสามารถแก้ไขหรือรวมกับเอกสารอื่นโดยใช้ Aspose.PDF  

> *ดูบทแนะนำ “Conversion - XPS” สำหรับตัวอย่างเต็มรูปแบบ*

## วิธีทำการแปลง PostScript ด้วย Java สำหรับงานแบตช์

สำหรับการแปลงขนาดใหญ่คุณสามารถอัตโนมัติโปรเซสโดยวนลูปไฟล์ในไดเรกทอรี, โหลดแต่ละไฟล์ด้วย `PostScriptDocument`, แล้วบันทึกเป็น PDF วิธีนี้ทำงานได้อย่างมีประสิทธิภาพบนเซิร์ฟเวอร์และสามารถทำแบบขนานเพื่อเพิ่ม throughput  

1. วนลูปไฟล์ `.ps` ในไดเรกทอรี  
2. สำหรับแต่ละไฟล์, สร้างอินสแตนซ์ `PostScriptDocument` แล้วบันทึกเป็น PDF  
3. หากต้องการ, **รวมไฟล์ pdf แบบ java‑style** ด้วย Aspose.PDF  

> *บทแนะนำ “File Merging” แสดงวิธีรวม PDF หลังการแปลง*

## กรณีการใช้งานการสร้างเอกสาร Java
- **การออกใบกำกับอัตโนมัติ**: สร้างใบกำกับ PDF จากเทมเพลต PostScript เก่า  
- **Pipeline รายงาน**: แปลงชุดรายงาน PostScript ขนาดใหญ่เป็น PDF ที่ค้นหาได้  
- **การย้ายระบบเก่า**: ย้ายทรัพยากร PostScript ไปสู่ workflow เอกสาร Java สมัยใหม่  

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- **การใช้หน่วยความจำสูงกับไฟล์ใหญ่** – ใช้ API สตรีม (`load(InputStream)`) เพื่อลดการใช้หน่วยความจำ  
- **ปัญหาการแทนที่ฟอนต์** – ตรวจสอบให้ฟอนต์ที่จำเป็นอยู่ใน classpath ของ JVM หรือฝังฟอนต์โดยเจาะจง  
- **ข้อผิดพลาดใบอนุญาต** – ตรวจสอบว่าไฟล์ใบอนุญาตถูกโหลดก่อนการประมวลผลเอกสาร; ดูบทแนะนำ **java license management** สำหรับรายละเอียด  

## การจัดการหน้า Java

เยี่ยมชมบทแนะนำ [การจัดการหน้า Java](./page-manipulation/) เพื่อเริ่มต้น  
สำรวจบทแนะนำ [การแปลง PostScript](./postscript-conversion/) เพื่อเพิ่มศักยภาพการแปลงเอกสารของคุณ  
ลึกซึ้งกับบทแนะนำ [การแปลง XPS](./xps-conversion/) เพื่อความเข้าใจที่ครบถ้วน  
เยี่ยมชม [การสร้างเอกสาร Java](./document-creation/) เพื่อเริ่มต้นการสร้างเอกสารส่วนบุคคล  
ค้นพบความลับของ [การจัดการ EPS ใน Java](./manipulation-eps/) เพื่อยกระดับทักษะเอกสารของคุณ  

ในยุคดิจิทัลที่เปลี่ยนแปลงอย่างรวดเร็วนี้, คงความได้เปรียบด้วย Aspose.Page for Java ตั้งแต่การจัดการหน้าไปจนถึงการเพิ่มเกรเดียนท์, เทกซ์เจอร์, และองค์ประกอบโปร่งใส, บทแนะนำของเราครอบคลุมหัวข้อต่าง ๆ อย่างกว้างขวาง ยกระดับความสามารถการประมวลผลเอกสารของคุณด้วย Aspose.Page, และเริ่มสร้างเอกสาร Java ที่สวยงามและไดนามิกวันนี้  

พร้อมเริ่มหรือยัง? สำรวจบทแนะนำของเราเดี๋ยวนี้และเปิดศักยภาพเต็มของ Aspose.Page for Java!

## บทแนะนำ Aspose.Page สำหรับ Java
### [การจัดการหน้า Java](./page-manipulation/)
ปลดล็อกความลับของการจัดการหน้า Java ด้วยบทแนะนำ Aspose.Page. ทำความเข้าใจการคลิปและการแปลงเพื่อสร้างเอกสารที่สวยงามโดยไม่ยาก
### [Conversion - PostScript](./postscript-conversion/)
แปลง PostScript เป็นภาพ, PDF, และบันทึกภาพเป็น EPS ใน Java ด้วยบทแนะนำ Aspose.Page. คู่มือขั้นตอน, คำถามที่พบบ่อย, และข้อกำหนดสำหรับการบูรณาการที่ราบรื่น
### [Conversion - XPS](./xps-conversion/)
แปลง XPS เป็นฟอร์แมตต่าง ๆ ใน Java อย่างง่ายดายด้วย Aspose.Page. ยกระดับการประมวลผลเอกสารด้วยคู่มือขั้นตอนของเราสำหรับการแปลงที่แม่นยำและมีประสิทธิภาพ
### [Java Document Creation](./document-creation/)
สร้างเอกสาร PostScript ใน Java อย่างง่ายดายด้วย Aspose.Page. ปรับขนาดหน้า, ระยะขอบ, และฟอนต์. ดำดิ่งสู่บทแนะนำการสร้างเอกสาร Java
### [EPS Manipulation in Java](./manipulation-eps/)
สำรวจ Aspose.Page for Java ด้วยบทแนะนำการจัดการ EPS. ครอบตัดและปรับขนาดไฟล์ EPS อย่างง่ายดายด้วยคู่มือขั้นตอน, ยกระดับทักษะเอกสารของคุณ
### [Gradient Addition - PostScript](./postscript-gradient-addition/)
ยกระดับเอกสาร PostScript Java ของคุณด้วยบทแนะนำ Aspose.Page for Java. เรียนรู้การเพิ่มเกรเดียนท์แนวทแยง, แนวนอน, รัศมี, และแนวตั้งอย่างง่ายดาย
### [Gradient Addition - XPS](./xps-gradient-addition/)
ยกระดับเอกสาร XPS Java ของคุณด้วยเกรเดียนท์ที่สวยงาม. เรียนรู้การเพิ่มเกรเดียนท์แนวทแยง, แนวนอน, และแนวตั้งอย่างง่ายดายด้วยบทแนะนำ Aspose.Page
### [Hatch Patterns - PostScript](./postscript-hatch-patterns/)
ค้นพบศิลปะการเพิ่มลายเส้น hatch ที่น่าดึงดูดให้กับเอกสาร PostScript Java ด้วย Aspose.Page. ยกระดับเนื้อหาภาพอย่างง่ายดายเพื่อผลลัพธ์ที่น่าทึ่ง
### [Image Manipulation - PostScript](./postscript-image-manipulation/)
พัฒนาทักษะการจัดการเอกสารด้วย Aspose.Page for Java. ดำดิ่งสู่บทแนะนำ PostScript, เรียนรู้การเพิ่มรูปภาพใน Java, และยกระดับความสามารถเอกสารของคุณ
### [Image Manipulation - XPS](./xps-image-manipulation/)
ค้นพบศิลปะการจัดการรูปภาพอย่างง่ายดายในเอกสาร XPS Java ด้วย Aspose.Page. เรียนรู้การเพิ่มและจัดเรียงรูปภาพอย่างต่อเนื่องเพื่อการประมวลผลเอกสารที่ดียิ่งขึ้น
### [License Management](./license-management/)
ปลดล็อกศักยภาพเต็มของ Aspose.Page for Java ด้วยบทแนะนำการจัดการใบอนุญาตของเรา. ตั้งค่าใบอนุญาตแบบตามการใช้งานอย่างราบรื่นเพื่อเพิ่มประสิทธิภาพการประมวลผลเอกสาร
### [File Merging](./file-merging/)
รวมไฟล์ PostScript เป็น PDF และแปลง XPS เป็น PDF หรือ XPS ใน Java ด้วย Aspose.Page. ทำตามบทแนะนำขั้นตอนเพื่อการแปลงเอกสารที่ราบรื่น
### [Page Manipulation - PostScript](./postscript-page-manipulation/)
สำรวจ Aspose.Page for Java ในบทแนะนำ PostScript ของเรา. เพิ่มหน้าในเอกสาร PostScript Java ของคุณได้อย่างง่ายดายด้วยคำแนะนำขั้นตอนเพื่อการจัดการที่ราบรื่น
### [Page Manipulation - XPS](./xps-page-manipulation/)
สำรวจพลังของ Aspose.Page for Java ด้วยบทแนะนำของเรา. ยกระดับเอกสาร XPS Java ของคุณโดยการเพิ่มหน้าอย่างง่ายดายเพื่อเพิ่มฟังก์ชันการทำงานของแอปพลิเคชัน
### [Shapes - PostScript](./postscript-shapes/)
สร้างเอกสาร PostScript ที่น่าดึงดูดอย่างง่ายดายด้วย Aspose.Page Java. ดำดิ่งสู่บทแนะนำการเพิ่มวงรีและสี่เหลี่ยม, สร้างเนื้อหาที่สวยงาม
### [Shapes - XPS](./xps-shapes/)
ค้นพบความมหัศจรรย์ของ XPS Java ด้วยบทแนะนำ Aspose.Page! เพิ่มวงรีและสี่เหลี่ยมที่น่าดึงดูดได้อย่างง่ายดาย. ยกระดับการสร้างเอกสารด้วยคู่มือขั้นตอนของเรา
### [Text Manipulation - PostScript](./postscript-text-manipulation/)
ปลดล็อกศักยภาพของ Aspose.Page for Java ด้วยบทแนะนำ PostScript. เพิ่มข้อความ, รวมถึงสตริง Unicode, อย่างง่ายดายเพื่อเสริมโครงการของคุณ
### [Text Manipulation - XPS](./xps-text-manipulation/)
ปฏิวัติเอกสาร XPS Java ของคุณด้วย Aspose.Page. สำรวจคู่มือขั้นตอนการจัดการข้อความ. ยกระดับทักษะของคุณเพื่อการปรับปรุงเอกสารอย่างง่ายดาย
### [Texture and Patterns - PostScript](./postscript-texture-patterns/)
ยกระดับ PostScript ด้วย Aspose.Page for Java. เพิ่มลายเทกซ์เจอร์และลายแพทเทิร์นอย่างต่อเนื่องเพื่อความเป็นไปได้เชิงสร้างสรรค์ในบทแนะนำ PostScript Java ของเรา
### [Transparency - PostScript](./postscript-transparency/)
ยกระดับ PostScript Java ด้วย Aspose.Page for Java. ผสานรูปภาพโปร่งใสและสร้าง pseudo‑transparency ที่สดใสสำหรับการแสดงผลที่น่าตื่นตาตื่นใจ
### [Transparency - XPS](./xps-transparency/)
ยกระดับเอกสาร XPS Java ของคุณอย่างง่ายดายด้วย Aspose.Page. เรียนรู้การเพิ่มวัตถุโปร่งใสและตั้งค่า opacity mask ในบทแนะนำของเราเพื่อเพิ่มเอฟเฟกต์ภาพ
### [Visual Elements - Java](./visual-elements/)
ยกระดับภาพกราฟิกเอกสาร Java ของคุณอย่างง่ายดายด้วย Aspose.Page! เรียนรู้การเพิ่มกริดโดยใช้ Visual Brush ในบทแนะนำขั้นตอนนี้
### [XMP Metadata Manipulation - Java](./xmp-metadata-manipulation/)
ปรับปรุงไฟล์ EPS อย่างง่ายดายด้วยการจัดการเมตาดาต้า XMP—จากการเพิ่มรายการจนถึงการสกัดข้อมูล. ยกระดับการจัดการเอกสารของคุณด้วยคู่มือของเรา

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถแปลงทั้ง PostScript และ XPS เป็น PDF ในแอปพลิเคชันเดียวกันได้หรือไม่?**  
ตอบ: ใช่. Aspose.Page มีคลาส `PostScriptDocument` และ `XpsDocument` แยกกัน, แต่ละคลาสมีเมธอด `save(..., SaveFormat.PDF)` ทำให้คุณจัดการทั้งสองฟอร์แมตพร้อมกันได้

**ถาม: ฉันต้องติดตั้งอินเตอร์พรีเตอร์ PostScript แบบเนทีฟหรือไม่?**  
ตอบ: ไม่. Aspose.Page เป็นไลบรารี Java แท้ ๆ; การเรนเดอร์ทั้งหมดทำภายในโดยไม่ต้องพึ่งพาเครื่องมือภายนอก

**ถาม: ไลบรารีจัดการไฟล์ขนาดใหญ่หรือการแปลงแบตช์อย่างไร?**  
ตอบ: ใช้ API สตรีม (`load(InputStream)`) และประมวลผลไฟล์ตามลำดับหรือแบบขนาน. ไลบรารีถูกออกแบบให้ใช้หน่วยความจำน้อย

**ถาม: Unicode ถูกสนับสนุนเต็มรูปแบบเมื่อแปลง PostScript เป็น PDF หรือไม่?**  
ตอบ: แน่นอน. เพียงส่งสตริง Unicode ไปยังเมธอด `drawString`; ไลบรารีจะฝังฟอนต์ที่จำเป็นโดยอัตโนมัติ

**ถาม: ตัวเลือกใบอนุญาตสำหรับการปรับใช้ในผลิตภัณฑ์มีอะไรบ้าง?**  
ตอบ: Aspose มีใบอนุญาตถาวร, แผนสมัครสมาชิก, และใบอนุญาตตามการใช้งาน. มีคีย์ทดลองฟรีสำหรับการทดสอบ

---

**Last Updated:** 2026-09-29  
**Tested With:** Aspose.Page for Java (latest)  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างไฟล์ PostScript ใน Java – การสร้างเอกสาร Java ด้วย Aspose.Page](/page/java/document-creation/)  
- [เรียนรู้การรวมไฟล์ pdf ด้วย Java – แปลง XPS เป็น PDF และการรวมไฟล์ใน Java ด้วย Aspose.Page](/page/java/file-merging/)  
- [วิธีเพิ่มหน้า PostScript ใน Java – คู่มือไร้รอยต่อด้วย Aspose.Page](/page/java/postscript-page-manipulation/add-pages1/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}