---
date: 2025-12-23
description: เรียนรู้วิธีแปลง XPS เป็น PDF ใน Java ด้วย Aspose.Page คู่มือนี้แสดงขั้นตอนการแปลงแบบทีละขั้นตอน
  วิธีการเรนเดอร์ PDF จาก XPS และการระบุหมายเลขหน้า PDF
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: วิธีแปลง XPS เป็น PDF ใน Java
url: /th/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง XPS เป็น PDF ด้วย Java

## วิธีแปลง XPS เป็น PDF ด้วย Java
ในโลกของการพัฒนา Java, **วิธีแปลง XPS เป็น PDF** เป็นคำถามที่พบบ่อย ไม่ว่าคุณจะสร้างระบบจัดการเอกสารหรือจำเป็นต้องสร้างรายงานที่สามารถพิมพ์ได้ การแปลงไฟล์ XPS อย่างน่าเชื่อถือสามารถเปลี่ยนเกมได้อย่างมาก โชคดีที่ Aspose.Page for Java ทำให้การ **เรนเดอร์ PDF จาก XPS** เป็นเรื่องง่ายด้วยเพียงไม่กี่บรรทัดของโค้ด

## คำตอบสั้น ๆ
- **ไลบรารีที่ทำการแปลงคืออะไร?** Aspose.Page for Java  
- **ใช้เวลาในการทำงานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับการตั้งค่าเบื้องต้น  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการประเมิน; ต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์  
- **สามารถแปลงเฉพาะหน้าที่เลือกได้หรือไม่?** ใช่ – ใช้ตัวเลือก *specify PDF page numbers*  
- **การแปลงเป็น loss‑less หรือไม่?** ไลบรารีจะรักษาความแม่นยำของกราฟิกเวกเตอร์และข้อความไว้

## XPS to PDF conversion คืออะไร?
XPS (XML Paper Specification) เป็นรูปแบบเอกสารแบบจัดหน้าแบบคงที่ของ Microsoft การแปลงเป็น PDF ทำให้คุณสามารถแชร์, พิมพ์ หรือเก็บเอกสารโดยใช้มาตรฐาน PDF ที่เป็นที่ยอมรับทั่วโลก

## ทำไมต้องใช้ Aspose.Page for Java เพื่อเรนเดอร์ PDF จาก XPS?
- **ความแม่นยำสูง** – รักษากราฟิกเวกเตอร์, ฟอนต์, และการจัดหน้า  
- **การควบคุมระดับละเอียด** – สามารถตั้งค่าคุณภาพภาพ, การบีบอัด, และเลือกหน้าเฉพาะได้  
- **ไม่มีการพึ่งพาไลบรารีภายนอก** – เป็น Java แท้ ๆ ทำงานบนทุกแพลตฟอร์มที่รองรับ JDK

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK)** – เวอร์ชันล่าสุด (แนะนำ 8+)  
- **Aspose.Page for Java** – ดาวน์โหลดไลบรารีจาก [documentation](https://reference.aspose.com/page/java/) อย่างเป็นทางการ  
- ไฟล์ XPS ที่ต้องการแปลง

## นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ, ให้นำเข้าแพ็กเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Page for Java ขั้นตอนนี้สำคัญสำหรับการเข้าถึงฟังก์ชันที่ต้องใช้ในการแปลง XPS เป็น PDF

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ XPS ต้นฉบับของคุณ

```java
String dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: เริ่มต้น PDF Output Stream
สร้าง `FileOutputStream` ที่จะรับไฟล์ PDF ที่สร้างขึ้น

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### ขั้นตอนที่ 3: โหลดเอกสาร XPS
โหลดไฟล์ XPS ด้วย Aspose.Page

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### ขั้นตอนที่ 4: เริ่มต้น PDF Save Options  
สร้างตัวเลือกสำหรับการแปลง ที่นี่คุณสามารถ **specify PDF page numbers**, ปรับคุณภาพภาพ, และตั้งค่าการบีบอัดได้

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### ขั้นตอนที่ 5: สร้าง PDF Rendering Device  
ตั้งค่าอุปกรณ์เรนเดอร์ที่จะเขียนผลลัพธ์เป็น PDF

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### ขั้นตอนที่ 6: บันทึกเอกสาร  
สุดท้าย, บันทึกเอกสาร XPS เป็น PDF โดยใช้ตัวเลือกและอุปกรณ์ที่คุณกำหนดไว้

```java
document.save(device, options);
```

ทำซ้ำขั้นตอนเหล่านี้โดยปรับเส้นทางไฟล์และตัวเลือกตามสถานการณ์ของคุณ

## วิธีระบุหมายเลขหน้า PDF เมื่อแปลง XPS
หากคุณต้องการเพียงส่วนหนึ่งของหน้าใน XPS ดั้งเดิม ให้เติมค่าในอาร์เรย์ `setPageNumbers` ด้วยดัชนีหน้าที่ต้องการ (เริ่มจาก 1) วิธีนี้ช่วยลดขนาดไฟล์และเวลาในการประมวลผล

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **FileNotFoundException** – ตรวจสอบให้แน่ใจว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและชื่อไฟล์ XPS ตรงกัน  
- **LicenseException** – จำเป็นต้องมีลิขสิทธิ์ Aspose.Page ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์; หากไม่มีไลบรารีจะทำงานในโหมดประเมินผลพร้อมลายน้ำ  
- **Low image quality** – เพิ่มค่า `setJpegQualityLevel` หรือเปลี่ยนเป็นการบีบอัดแบบ lossless หากต้องการ

## คำถามที่พบบ่อย
### ฉันสามารถแปลงไฟล์ XPS ที่มีหลายหน้าโดยใช้ Aspose.Page for Java ได้หรือไม่?
ใช่, คุณสามารถ **specify PDF page numbers** ใน `PdfSaveOptions` (ดูขั้นตอน 4) เพื่อรวมหน้าที่ต้องการได้

### ฉันจะหาแหล่งสนับสนุนเพิ่มเติมหรือพูดคุยเกี่ยวกับคำถามเกี่ยวกับ Aspose.Page ได้ที่ไหน?
เยี่ยมชม [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา

### มีรุ่นทดลองฟรีสำหรับ Aspose.Page for Java หรือไม่?
มี, คุณสามารถสำรวจคุณสมบัติต่าง ๆ ด้วย [การทดลองใช้ฟรี](https://releases.aspose.com/)

### ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
เยี่ยมชม [ลิงก์นี้](https://purchase.aspose.com/temporary-license/) เพื่อดูรายละเอียดลิขสิทธิ์ชั่วคราว

### ฉันสามารถซื้อไลเซนส์ Aspose.Page for Java ได้จากที่ไหน?
คุณสามารถซื้อไลเซนส์ได้ [ที่นี่](https://purchase.aspose.com/buy)

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบกับ:** Aspose.Page for Java 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}