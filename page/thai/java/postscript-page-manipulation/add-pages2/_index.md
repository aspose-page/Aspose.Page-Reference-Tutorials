---
date: 2025-12-11
description: เรียนรู้วิธีตั้งค่าขนาดหน้าที่กำหนดเองและเพิ่มหน้าในเอกสาร Java PostScript
  ด้วย Aspose.Page ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการจัดการเอกสารที่ราบรื่น
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: บทเรียน Aspose.Page Java – ตั้งค่าขนาดหน้ากำหนดเองขณะเพิ่มหน้าใน PostScript
url: /th/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – ตั้งค่าขนาดหน้ากำหนดเองขณะเพิ่มหน้าใน PostScript

## บทนำ
ในแอปพลิเคชัน Java สมัยใหม่ การ **ตั้งค่าขนาดหน้ากำหนดเอง** สำหรับผลลัพธ์ PostScript มักจำเป็น—ไม่ว่าจะเป็นการสร้างใบแจ้งหนี้, ตั๋ว, หรือกราฟิกกำหนดเอง Aspose.Page for Java ทำให้งานนี้ง่ายดาย ในบทเรียนนี้คุณจะได้เรียนรู้วิธีเพิ่มหน้าและตั้งค่าขนาดหน้ากำหนดเองในเอกสาร PostScript ทีละขั้นตอน เพื่อให้คุณสร้างเลย์เอาต์ที่แม่นยำทุกครั้ง.

## คำตอบด่วน
- **ฉันสามารถตั้งค่าขนาดหน้าที่แตกต่างกันสำหรับแต่ละหน้าได้หรือไม่?** ใช่, คุณสามารถเปิดหน้าด้วยมิติกำหนดเองโดยใช้ `document.openPage(width, height)`.  
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีใบอนุญาต Aspose.Page ที่ถูกต้องสำหรับการใช้งานที่ไม่ใช่การประเมินผล.  
- **เวอร์ชัน Java ใดที่รองรับ?** ไลบรารีทำงานกับ Java 8 และใหม่กว่า.  
- **API นี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** อินสแตนซ์ของ Document ไม่ปลอดภัยต่อหลายเธรด; สร้าง `PsDocument` แยกสำหรับแต่ละเธรด.  
- **ไฟล์ PostScript สามารถมีขนาดใหญ่ได้เท่าไหร่?** Aspose.Page จัดการไฟล์หลายเมกะไบต์ได้อย่างมีประสิทธิภาพ; การใช้หน่วยความจำสเกลตามเนื้อหา ไม่ใช่จำนวนหน้า.

## ข้อกำหนดเบื้องต้น
- ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
- เพิ่ม Aspose.Page for Java ลงในโปรเจกต์ของคุณ (Maven/Gradle หรือ JAR แบบแมนนวล).  
- สภาพแวดล้อมการพัฒนา Java (IDE, JDK 8+).  

## นำเข้าแพ็กเกจ
เพื่อเริ่มต้น ให้นำเข้าคลาสที่จำเป็นจากไลบรารี Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ขั้นตอนที่ 1: สร้างเอกสาร PostScript แบบหลายหน้า
แรกสุด สร้าง `PsDocument` ใหม่ที่กำหนดให้รองรับหลายหน้า สิ่งนี้จะตั้งค่า output stream และบอกไลบรารีว่าเราจะทำงานกับไฟล์หลายหน้า.

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

## ขั้นตอนที่ 2: เพิ่มเนื้อหาในหน้าที่หนึ่ง
เมื่อเอกสารพร้อม คุณสามารถเพิ่มเนื้อหาใด ๆ ที่ต้องการในหน้าที่หนึ่ง เมื่อเสร็จแล้ว ปิดหน้าด้วยการเรียกเพื่อบันทึกเนื้อหา.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## วิธีตั้งค่าขนาดหน้ากำหนดเอง
หากขนาดหน้าตามค่าเริ่มต้นไม่ตรงกับความต้องการของคุณ คุณสามารถ **ตั้งค่าขนาดหน้ากำหนดเอง** เมื่อเปิดหน้ใหม่ได้ สิ่งนี้มีประโยชน์สำหรับใบเสร็จ, ป้าย, หรือเลย์เอาต์ที่ไม่เป็นมาตรฐานใด ๆ.

## ขั้นตอนที่ 3: เพิ่มหน้าที่สองด้วยขนาดที่แตกต่าง
ด้านล่าง เราเปิดหน้าที่สองและระบุความกว้างและความสูงกำหนดเอง (หน่วย points) อย่างชัดเจน นี่เป็นการสาธิตวิธีตั้งค่าขนาดหน้ากำหนดเองสำหรับแต่ละหน้า.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
สุดท้าย ให้บันทึกการเปลี่ยนแปลงโดยการบันทึกเอกสาร ทุกหน้ารวมถึงหน้าที่มีขนาดกำหนดเองจะถูกเขียนลงในไฟล์ผลลัพธ์.

```java
// Save the document
document.save();
```

โดยทำตามขั้นตอนเหล่านี้ คุณสามารถเพิ่มหน้าและ **ตั้งค่าขนาดหน้ากำหนดเอง** ในเอกสาร PostScript ของ Java ด้วย Aspose.Page ได้อย่างราบรื่น ให้คุณควบคุมเลย์เอาต์ของแต่ละหน้าได้อย่างเต็มที่.

## สรุป
Aspose.Page for Java มอบ API ที่แข็งแรงและเป็นมิตรต่อผู้พัฒนาเพื่อจัดการเอกสาร PostScript ตอนนี้คุณรู้วิธีเพิ่มหลายหน้า, ใช้ขนาดกำหนดเอง, และบันทึกผลลัพธ์—ทำให้คุณสามารถสร้างผลลัพธ์ที่จัดรูปแบบอย่างแม่นยำสำหรับโซลูชันที่ใช้ Java ใด ๆ.

## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มหน้าที่มีขนาดต่างกันในเอกสาร PostScript เดียวได้หรือไม่?
ได้, ตามที่แสดงในบทเรียนนี้ คุณสามารถเพิ่มหน้าที่มีขนาดต่างกันในเอกสาร PostScript แบบหลายหน้า.

### มีข้อจำกัดใดเกี่ยวกับจำนวนหน้าที่ฉันสามารถเพิ่มได้หรือไม่?
Aspose.Page รองรับการเพิ่มจำนวนหน้าที่เกือบไม่มีขีดจำกัดในเอกสาร.

### ฉันสามารถเพิ่มเนื้อหากำหนดเอง เช่น รูปภาพหรือกราฟิก ลงในหน้าได้หรือไม่?
แน่นอน! Aspose.Page ให้คุณเพิ่มเนื้อหาหลากหลาย รวมถึงข้อความ, รูปภาพ, และองค์ประกอบกราฟิกอื่น ๆ.

### Aspose.Page เหมาะสำหรับการจัดการเอกสารขนาดใหญ่หรือไม่?
ใช่, Aspose.Page ถูกออกแบบมาเพื่อจัดการเอกสารขนาดเล็กและขนาดใหญ่ได้อย่างมีประสิทธิภาพ.

### ฉันสามารถหาแหล่งข้อมูลและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Page ได้จากที่ไหน?
Explore the [Aspose.Page documentation](https://reference.aspose.com/page/java/), or visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.  

**คำถามเพิ่มเติม**

**Q:** *รูปแบบภาพใดที่รองรับเมื่อวาดบนหน้า PostScript?*  
**A:** คุณสามารถฝังภาพ PNG, JPEG, BMP, และ GIF ได้โดยตรงโดยใช้ drawing API.  

**Q:** *ฉันจะเปลี่ยน DPI เริ่มต้นของเอกสารได้อย่างไร?*  
**A:** ตั้งค่า `PsSaveOptions.setResolution(int dpi)` ก่อนสร้าง `PsDocument`.  

**Q:** *ฉันสามารถเข้ารหัสไฟล์ PostScript ด้วยรหัสผ่านได้หรือไม่?*  
**A:** PostScript เองไม่รองรับการเข้ารหัส, แต่คุณสามารถห่อผลลัพธ์เป็น PDF แล้วตั้งค่าความปลอดภัยได้หากต้องการ.  

---

**อัปเดตล่าสุด:** 2025-12-11  
**ทดสอบด้วย:** Aspose.Page for Java 24.10  
**ผู้เขียน:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
