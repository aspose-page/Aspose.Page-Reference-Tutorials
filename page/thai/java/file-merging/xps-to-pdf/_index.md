---
date: 2025-11-29
description: เรียนรู้วิธีบันทึก XPS เป็น PDF ใน Java ด้วย Aspose.Page Java. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการแปลง
  XPS เป็น PDF อย่างมีประสิทธิภาพและการตั้งค่าการบีบอัด PDF.
language: th
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: แปลง XPS เป็น PDF ใน Java ด้วย Aspose.Page Java
url: /java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XPS เป็น PDF ใน Java ด้วย Aspose.Page Java

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีการแปลง XPS เป็น PDF ใน Java ด้วย Aspose.Page Java** ซึ่งเป็นไลบรารีที่แข็งแกร่งออกแบบมาสำหรับการแปลงเอกสารใน Java ไม่ว่าคุณจะต้องการประมวลผลใบแจ้งหนี้เป็นชุด, สร้างรายงานที่สามารถพิมพ์ได้, หรือเพียงแค่ย้ายไฟล์ XPS เก่า Aspose.Page Java จะทำงานได้อย่างรวดเร็ว, น่าเชื่อถือ, และปรับแต่งได้เต็มที่

## คำตอบสั้น
- **ไลบรารีที่จัดการการแปลง XPS เป็น PDF คืออะไร?** Aspose.Page Java  
- **การแปลงพื้นฐานใช้เวลานานเท่าไหร่?** โดยทั่วไปใช้เวลาน้อยกว่าวินาทีหนึ่งสำหรับไฟล์ XPS หนึ่งหน้า  
- **ต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีสามารถใช้สำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานจริง  
- **ฉันสามารถควบคุมการบีบอัด PDF ได้หรือไม่?** ใช่ – ใช้ `PdfSaveOptions` เพื่อตั้งค่าการบีบอัดภาพและข้อความ  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือใหม่กว่า (แนะนำ JDK 11+)

## Aspose.Page Java คืออะไร?
Aspose.Page Java เป็น **API ประสิทธิภาพสูง** ที่ช่วยให้นักพัฒนาสามารถสร้าง, แก้ไข, และแปลงเอกสาร XPS ด้วยโปรแกรมได้ รองรับการแปลง XPS เป็น PDF, PNG, JPEG และรูปแบบอื่น ๆ พร้อมให้การควบคุมละเอียดของการตั้งค่าเอาต์พุต เช่น **ตั้งค่าการบีบอัด PDF**

## ทำไมต้องใช้ Aspose.Page Java สำหรับการแปลง XPS‑to‑PDF?
- **การเรนเดอร์ไม่มีการพึ่งพา** – ไม่ต้องใช้ไลบรารีเนทีฟหรือเครื่องมือภายนอก  
- **การรักษาเลย์เอาต์ที่แม่นยำ** – ผลลัพธ์ PDF จะสะท้อนลักษณะเดิมของ XPS อย่างตรงกัน  
- **การควบคุมผลลัพธ์ PDF อย่างเต็มที่** – คุณสามารถปรับคุณภาพภาพ, เลือกอัลกอริทึมการบีบอัด, และเลือกหน้าที่ต้องการเรนเดอร์  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS กับ JDK มาตรฐานใดก็ได้  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

1. **Java Development Kit (JDK) 8+** – แนะนำให้ใช้ JDK เวอร์ชันล่าสุดเพื่อประสิทธิภาพและความปลอดภัย  
2. **ไลบรารี Aspose.Page for Java** – ดาวน์โหลดไฟล์ JAR จาก [เอกสาร Aspose.Page Java อย่างเป็นทางการ](https://reference.aspose.com/page/java/)  
3. **IDE** (IntelliJ IDEA, Eclipse, VS Code) หรือเครื่องมือแก้ไขข้อความง่าย ๆ พร้อมเครื่องมือสร้างจากบรรทัดคำสั่ง (Maven/Gradle)  

## นำเข้าแพ็กเกจ
เพิ่มการนำเข้าที่จำเป็นในคลาส Java ของคุณเพื่อให้สามารถทำงานกับเอกสาร XPS และผลลัพธ์ PDF ได้

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร
กำหนดโฟลเดอร์ที่บรรจุไฟล์ XPS ต้นฉบับของคุณและที่ที่ PDF จะถูกบันทึก

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### ขั้นตอนที่ 2: เริ่มต้นสตรีมเอาต์พุต PDF
สร้าง `FileOutputStream` ที่ชี้ไปยังไฟล์ PDF ปลายทาง

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **เคล็ดลับมืออาชีพ:** ใช้ `try‑with‑resources` เพื่อปิดสตรีมโดยอัตโนมัติและหลีกเลี่ยงการรั่วของทรัพยากร

### ขั้นตอนที่ 3: โหลดเอกสาร XPS
สร้างอ็อบเจ็กต์ `XpsDocument` โดยโหลดไฟล์ XPS ต้นฉบับ

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### ขั้นตอนที่ 4: เริ่มต้น PDF Save Options (ตั้งค่าการบีบอัด PDF)
กำหนดวิธีการบีบอัด PDF ขั้นตอนนี้ให้คุณ **ตั้งค่าการบีบอัด PDF** สำหรับภาพและข้อความ ซึ่งช่วยลดขนาดไฟล์โดยไม่สูญเสียคุณภาพ

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **ทำไมเรื่องนี้สำคัญ:** การปรับคุณภาพ JPEG และประเภทการบีบอัดสามารถทำให้ PDF ขนาด 10 MB ลดลงเหลือใต้ 2 MB พร้อมรักษาความคมชัดที่คุณต้องการ

### ขั้นตอนที่ 5: สร้างอุปกรณ์เรนเดอร์สำหรับรูปแบบ PDF
`PdfDevice` จะส่งหน้าที่เรนเดอร์ไปยังสตรีมเอาต์พุต PDF

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### ขั้นตอนที่ 6: บันทึกเอกสาร
สุดท้าย, เรนเดอร์เนื้อหา XPS ไปเป็น PDF โดยใช้ตัวเลือกที่กำหนดไว้

```java
document.save(device, options);
```

> **ผลลัพธ์:** หลังจากรัน, `XPStoPDF.pdf` จะปรากฏในโฟลเดอร์ `dataDir` ซึ่งมีหน้าที่แปลงพร้อมการตั้งค่าการบีบอัดที่คุณระบุ

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **`FileNotFoundException`** | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบว่าไดเรกทอรีมีอยู่และแอปพลิเคชันมีสิทธิ์อ่าน/เขียน |
| **หน้า PDF ว่าง** | ขาดการเริ่มต้น `PdfDevice` | ตรวจสอบว่าได้สร้าง `PdfDevice` ด้วย `FileOutputStream` เดียวกันที่ใช้สำหรับเอาต์พุต |
| **ขนาด PDF ใหญ่** | การบีบอัดเริ่มต้นต่ำ | เพิ่มค่า `setJpegQualityLevel` หรือเปลี่ยนเป็น `PdfImageCompression.Jpeg` พร้อมระดับคุณภาพที่ต่ำลง |
| **บางหน้าปรากฏเท่านั้น** | ตัวกรอง `setPageNumbers` กำจัดหน้าบางหน้า | ปรับอาร์เรย์ให้รวมหมายเลขหน้าที่ต้องการทั้งหมด หรือเอาการเรียกออกเพื่อส่งออกทุกหน้า |

## คำถามที่พบบ่อย

**ถาม: Aspose.Page Java รองรับเวอร์ชัน Java ต่าง ๆ หรือไม่?**  
**ตอบ:** ใช่, Aspose.Page Java รองรับ Java 8 ถึง Java 21 รวมถึงการแจกจ่ายของ Oracle และ OpenJDK  

**ถาม: ฉันสามารถปรับแต่งการตั้งค่าการบีบอัดสำหรับ PDF ที่แปลงได้หรือไม่?**  
**ตอบ:** แน่นอน. ใช้ `PdfSaveOptions` เพื่อตั้งค่าคุณภาพ JPEG, ประเภทการบีบอัดภาพ, และการบีบอัดข้อความตามที่แสดงในขั้นตอนที่ 4  

**ถาม: ฉันจะหาแหล่งสนับสนุนเพิ่มเติมหรือการสนทนาชุมชนได้จากที่ไหน?**  
**ตอบ:** เยี่ยมชม [Aspose.Page Forum](https://forum.aspose.com/c/page/39) เพื่อรับความช่วยเหลือจากชุมชน, ตัวอย่างโค้ด, และเคล็ดลับการแก้ปัญหา  

**ถาม: มีการทดลองใช้ฟรีสำหรับ Aspose.Page หรือไม่?**  
**ตอบ:** มี, คุณสามารถดาวน์โหลดรุ่นทดลองที่ทำงานเต็มรูปแบบได้จาก [หน้าดาวน์โหลดของ Aspose](https://releases.aspose.com/)  

**ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page ได้อย่างไร?**  
**ตอบ:** สามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)  

## สรุป
ด้วยการใช้ **Aspose.Page Java**, คุณสามารถ **บันทึก XPS เป็น PDF** ได้อย่างง่ายดายและควบคุมทุกด้านของผลลัพธ์ ตั้งแต่การเลือกหน้าไปจนถึงการบีบอัด บทแนะนำนี้ครอบคลุมทุกสิ่งที่คุณต้องการเพื่อรวมการแปลง XPS‑to‑PDF เข้าไปในแอปพลิเคชัน Java ของคุณ ไม่ว่าจะเป็นการสร้างยูทิลิตี้แบบครั้งเดียวหรือระบบประมวลผลเอกสารขนาดใหญ่

---

**อัปเดตล่าสุด:** 2025-11-29  
**ทดสอบด้วย:** Aspose.Page for Java 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}