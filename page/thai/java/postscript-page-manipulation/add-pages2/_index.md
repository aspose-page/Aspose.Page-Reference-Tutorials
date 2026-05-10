---
date: 2026-02-18
description: เรียนรู้วิธีตั้งค่าขนาดหน้าที่กำหนดเองและเพิ่มหน้าในเอกสาร Java PostScript
  ด้วย Aspose.Page ปฏิบัติตามคำแนะนำแบบขั้นตอนของเราเพื่อการจัดการเอกสารที่ราบรื่น
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: บทเรียน Aspose.Page Java – ตั้งค่าขนาดหน้ากำหนดเองขณะเพิ่มหน้าใน PostScript
url: /th/java/postscript-page-manipulation/add-pages2/
weight: 11
---

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – ตั้งค่าขนาดหน้ากำหนดเองขณะเพิ่มหน้าใน PostScript

## Introduction
ในแอปพลิเคชัน Java สมัยใหม่ **การตั้งค่าขนาดหน้ากำหนดเอง** สำหรับผลลัพธ์ PostScript มักเป็นสิ่งที่ต้องการ—ไม่ว่าจะเป็นการสร้างใบแจ้งหนี้, ตั๋ว, หรือกราฟิกแบบกำหนดเอง ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **ตั้งค่าขนาดหน้ากำหนดเอง** สำหรับแต่ละหน้า, เพิ่มหลายหน้า, และสุดท้าย **สร้างไฟล์ PostScript** ที่ตรงกับความต้องการการจัดวางของคุณ เราจะเดินผ่านโค้ดทีละขั้นตอนเพื่อให้คุณสามารถนำเทคนิคนี้ไปใช้ในโปรเจกต์ของคุณได้อย่างรวดเร็ว

## Quick Answers
- **ฉันสามารถตั้งค่าขนาดหน้าที่แตกต่างกันสำหรับแต่ละหน้าได้หรือไม่?** ใช่, คุณสามารถเปิดหน้าด้วยมิติที่กำหนดเองโดยใช้ `document.openPage(width, height)`  
- **ฉันต้องใช้ไลเซนส์สำหรับการใช้งานในโปรดักชันหรือไม่?** จำเป็นต้องมีไลเซนส์ Aspose.Page ที่ถูกต้องสำหรับการปรับใช้ที่ไม่ใช่การประเมินผล  
- **เวอร์ชัน Java ใดที่รองรับ?** ไลบรารีทำงานกับ Java 8 ขึ้นไป  
- **API นี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** อินสแตนซ์ Document ไม่ปลอดภัยต่อการทำงานหลายเธรด; สร้าง `PsDocument` แยกต่างหากต่อเธรดหนึ่งตัว  
- **ไฟล์ PostScript สามารถมีขนาดใหญ่ได้แค่ไหน?** Aspose.Page จัดการไฟล์หลายเมกะไบต์ได้อย่างมีประสิทธิภาพ; การใช้หน่วยความจำสเกลตามเนื้อหา ไม่ใช่จำนวนหน้า  
- **ฉันสามารถใช้ overload ของ open page width/height ได้หรือไม่?** แน่นอน—`openPage(double width, double height)` ให้คุณระบุมิติใด ๆ ในหน่วย points  

## Prerequisites
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java  
- Aspose.Page for Java ที่เพิ่มเข้าในโปรเจกต์ของคุณ (Maven/Gradle หรือ JAR แบบแมนนวล)  
- สภาพแวดล้อมการพัฒนา Java (IDE, JDK 8+)  

## Import Packages
เพื่อเริ่มต้น, ให้ import คลาสที่จำเป็นจากไลบรารี Aspose.Page

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Multipaged PostScript Document
ขั้นแรก, สร้าง `PsDocument` ใหม่ที่กำหนดให้รองรับหลายหน้า ซึ่งจะตั้งค่า stream ของผลลัพธ์และบอกไลบรารีว่าเราจะทำงานกับไฟล์หลายหน้า

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

## Step 2: Add Content to the First Page
เมื่อเอกสารพร้อม, คุณสามารถเพิ่มเนื้อหาใด ๆ ที่ต้องการในหน้าที่หนึ่ง เมื่อเสร็จแล้วให้ปิดหน้าเพื่อบล็อกเนื้อหานั้น

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## How to set custom page size
หากขนาดหน้ามาตรฐานไม่ตรงกับความต้องการของคุณ, คุณสามารถ **ตั้งค่าขนาดหน้ากำหนดเอง** ขณะเปิดหน้าใหม่ ซึ่งมีประโยชน์สำหรับใบเสร็จ, ป้าย, หรือการจัดวางที่ไม่เป็นมาตรฐานใด ๆ

## Step 3: Add a Second Page with Different Size
ต่อไปเราจะเปิดหน้าที่สองและระบุความกว้างและความสูงที่กำหนดเอง (ในหน่วย points) อย่างชัดเจน นี่เป็นการสาธิตวิธีตั้งค่าขนาดหน้ากำหนดเองสำหรับแต่ละหน้า, ทำให้คุณสามารถทำงานกับ **ขนาดหน้าที่แตกต่างกัน** ภายในเอกสารเดียวกันได้

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Step 4: Save the Document
สุดท้าย, บันทึกการเปลี่ยนแปลงโดยการเซฟเอกสาร หน้าใดก็ตาม—including those with custom sizes—จะถูกเขียนลงไฟล์ผลลัพธ์

```java
// Save the document
document.save();
```

โดยทำตามขั้นตอนเหล่านี้, คุณสามารถเพิ่มหน้าและ **ตั้งค่าขนาดหน้ากำหนดเอง** ในเอกสาร PostScript ของ Java ด้วย Aspose.Page ได้อย่างราบรื่น, ให้คุณควบคุมการจัดวางของแต่ละหน้าได้เต็มที่

## Why use Aspose.Page to set custom page size?
- **Precision:** มิติถูกกำหนดในหน่วย points, ทำให้คุณได้การควบคุมที่แม่นยำต่อความกว้างและความสูงของหน้า  
- **Flexibility:** ผสมและจับคู่ **ขนาดหน้าที่แตกต่างกัน** ในไฟล์ PostScript ไฟล์เดียว  
- **Performance:** ไลบรารีสตรีมเนื้อหาโดยตรงไปยังไฟล์ผลลัพธ์, ทำให้เหมาะกับสถานการณ์ **generate PostScript file** ขนาดใหญ่  
- **Rich API:** รองรับการวาดกราฟิก, ฝังรูปภาพ, และเพิ่มข้อความ—ทั้งหมดนี้ยังคงเคารพมิติที่คุณกำหนดเอง  

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **มิติของหน้าดูเหมือนสลับกัน** | จำไว้ว่า `openPage(width, height)` รับค่าความกว้างก่อน, แล้วตามด้วยความสูง (ทั้งสองเป็น points) |
| **เนื้อหาเกินขอบหน้ากระดาษ** | ใช้ระบบพิกัด `PsGraphics` เพื่อกำหนดตำแหน่งองค์ประกอบภายในขอบเขตที่กำหนด, หรือปรับสเกลการวาดของคุณ |
| **เกิดข้อผิดพลาด out‑of‑memory กับเอกสารขนาดใหญ่** | เปิดใช้งานการสตรีมโดยเขียนโดยตรงไปยัง `FileOutputStream` ตามที่แสดง, และหลีกเลี่ยงการโหลดรูปภาพขนาดใหญ่เข้าหน่วยความจำทั้งหมดพร้อมกัน |

## Frequently Asked Questions
### ฉันสามารถเพิ่มหน้าที่มีขนาดต่างกันในเอกสาร PostScript ไฟล์เดียวได้หรือไม่?
ใช่, ตามที่สาธิตในบทแนะนำนี้, คุณสามารถเพิ่มหน้าที่มีขนาดแตกต่างกันในเอกสาร PostScript แบบหลายหน้าได้  

### มีข้อจำกัดเรื่องจำนวนหน้าที่ฉันสามารถเพิ่มได้หรือไม่?
Aspose.Page รองรับการเพิ่มจำนวนหน้าที่เกือบไม่จำกัดในเอกสาร  

### ฉันสามารถเพิ่มเนื้อหากำหนดเอง เช่น รูปภาพหรือกราฟิก ลงในหน้าได้หรือไม่?
แน่นอน! Aspose.Page อนุญาตให้คุณเพิ่มเนื้อหาหลากหลายประเภท, รวมถึงข้อความ, รูปภาพ, และองค์ประกอบกราฟิกอื่น ๆ  

### Aspose.Page เหมาะกับการจัดการเอกสารขนาดใหญ่หรือไม่?
ใช่, Aspose.Page ถูกออกแบบมาเพื่อจัดการทั้งเอกสารขนาดเล็กและขนาดใหญ่ได้อย่างมีประสิทธิภาพ  

### ฉันจะหาแหล่งข้อมูลและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Page ได้จากที่ไหน?
สำรวจ [Aspose.Page documentation](https://reference.aspose.com/page/java/), หรือเยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชน  

**Additional Q&A**

**Q:** *รูปแบบภาพใดบ้างที่รองรับเมื่อวาดบนหน้า PostScript?*  
**A:** คุณสามารถฝังภาพ PNG, JPEG, BMP, และ GIF ได้โดยตรงผ่าน drawing API  

**Q:** *ฉันจะเปลี่ยน DPI เริ่มต้นของเอกสารได้อย่างไร?*  
**A:** ตั้งค่า `PsSaveOptions.setResolution(int dpi)` ก่อนสร้าง `PsDocument`  

**Q:** *ฉันสามารถเข้ารหัสไฟล์ PostScript ด้วยรหัสผ่านได้หรือไม่?*  
**A:** PostScript เองไม่รองรับการเข้ารหัส, แต่คุณสามารถห่อผลลัพธ์เป็น PDF แล้วตั้งค่าความปลอดภัยได้หากต้องการ  

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}