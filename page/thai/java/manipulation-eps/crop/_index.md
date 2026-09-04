---
date: 2026-09-04
description: เรียนรู้วิธีลดขนาดไฟล์ EPS ด้วยการตัดครอปไฟล์ EPS ใน Java โดยใช้ Aspose.Page
  – คู่มือขั้นตอนต่อขั้นตอนที่แสดงวิธีการ crop eps, crop eps image และ trim eps file.
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: ตัดครอปไฟล์ EPS ใน Java
og_description: เรียนรู้วิธีลดขนาดไฟล์ EPS ด้วยการตัดครอปไฟล์ EPS ใน Java โดยใช้ Aspose.Page
  – คู่มือสั้น ๆ พร้อมโค้ดและเคล็ดลับ
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: วิธีตัดครอปไฟล์ EPS ใน Java เพื่อลดขนาดไฟล์ EPS
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: วิธีตัดครอปไฟล์ EPS ใน Java เพื่อลดขนาดไฟล์ EPS
url: /th/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตัดไฟล์ EPS ใน Java เพื่อลดขนาดไฟล์ EPS

## บทนำ
หากคุณต้องการ **crop EPS** ไฟล์โดยโปรแกรมในแอปพลิเคชัน Java และต้องการ **reduce EPS file size** คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะอธิบายขั้นตอนทั้งหมดของการตัดภาพ EPS ด้วยไลบรารี Aspose.Page for Java ที่มีประสิทธิภาพ เมื่อจบคู่มือคุณจะเข้าใจว่าทำไมการตัด EPS จึงสำคัญ, ดูโค้ดที่ต้องใช้, และพร้อมผสานโซลูชันนี้เข้าสู่โปรเจกต์ของคุณ

## คำตอบอย่างรวดเร็ว
- **ไลบรารีอะไรที่จัดการการตัด EPS ใน Java?** Aspose.Page for Java.  
- **การตัดพื้นฐานใช้เวลานานเท่าไหร่ในการทำงาน?** Approximately 5‑10 minutes.  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** A free trial works for evaluation; a commercial license is required for production.  
- **เวอร์ชัน Java ไหนที่รองรับ?** Java 8 and newer.  
- **ฉันสามารถกำหนด bounding box แบบกำหนดเองได้หรือไม่?** Yes – you provide the coordinates you need.

## การตัด EPS คืออะไรและทำไมต้องใช้?
**การตัด EPS สร้าง bounding box ใหม่ที่กำหนดพื้นที่ที่มองเห็นของไฟล์ EPS.**  
การตัดไฟล์ EPS จะลบพื้นที่ว่างที่ไม่ต้องการและตัดกราฟิกให้เหลือเฉพาะพื้นที่ที่คุณต้องการจริง ๆ ซึ่งจะ **reduce EPS file size** โดยตรงและปรับปรุงความสอดคล้องของเลย์เอาต์ในเอกสารต่อไปเช่น PDF หรือรายงาน.

## ทำไมต้องตัดไฟล์ EPS?
การตัดไฟล์ EPS ทำให้คุณ **shrink file size by up to 30 %**, กำจัดขอบที่เกินและทำให้กราฟิกเป็นมาตรฐานสำหรับกระบวนการประมวลผลแบบชุด มันมีประโยชน์เป็นพิเศษเมื่อคุณต้องฝังหลาย EPS assets ลงใน PDF เดียวหรือเมื่อคุณต้องการเร่งการเรนเดอร์บนอุปกรณ์ที่มีพลังงานต่ำ.

## ข้อกำหนดเบื้องต้น
Before we dive into the code, make sure you have:

- **Aspose.Page for Java** library installed – download it from the official page [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 or later installed on your machine.  
- **A folder** to store your input EPS (`input.eps`) and the resulting cropped file (`output_crop.eps`).

## นำเข้าแพ็กเกจ
First, import the necessary Java classes. This snippet stays exactly the same as in the original tutorial:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## วิธีตัดภาพ EPS ใน Java
Load your source EPS, define a new bounding box, and call the cropping API – the whole operation is completed in five concise steps.

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารและ input stream
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
ที่นี่เรากำหนดโค้ดให้ชี้ไปยังโฟลเดอร์ที่เก็บไฟล์ EPS ต้นฉบับของเราและเปิดสตรีมเพื่ออ่านไฟล์

### ขั้นตอนที่ 2: เริ่มต้นอ็อบเจ็กต์ PsDocument
The `PsDocument` class represents an EPS file in memory, allowing you to read and modify its properties.  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
อ็อบเจ็กต์นี้ให้คุณเข้าถึง bounding box ดั้งเดิมและเมตาดาต้าอื่น ๆ.

### ขั้นตอนที่ 3: ดึง bounding box เริ่มต้น
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
การดึง bounding box ดั้งเดิมจะให้พิกัดของพื้นที่ที่มองเห็นในปัจจุบัน – มีประโยชน์สำหรับการตัดสินใจว่าต้องตัดเท่าไหร่.

### ขั้นตอนที่ 4: สร้าง output stream
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
เราเปิดสตรีมที่ EPS ที่ถูกตัดจะถูกเขียนลงไป.

### ขั้นตอนที่ 5: กำหนด bounding box ใหม่และตัด
The `cropEps` method trims the document to a new bounding box and writes the result to an output stream.  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
ระบุพิกัดสี่ค่า (lower‑left x, lower‑left y, upper‑right x, upper‑right y) ที่กำหนดพื้นที่ที่คุณต้องการเก็บ วิธีนี้จะทำการตัดและเขียนผลลัพธ์ไปยัง `output_crop.eps`.

## ปัญหาที่พบบ่อยและวิธีแก้
- **พิกัดไม่ถูกต้อง:** EPS uses points (1/72 inch). If the crop looks off, double‑check the unit conversion.  
- **ข้อผิดพลาดไฟล์ไม่พบ:** Ensure `dataDir` ends with the appropriate path separator (`/` or `\`).  
- **ข้อยกเว้นใบอนุญาต:** Running the code without a valid license may add a watermark to the output. Apply your temporary or permanent license before production use.

## คำถามที่พบบ่อย

**Q: Aspose.Page รองรับ Java 8 หรือไม่?**  
A: Yes, Aspose.Page works with Java 8 and any later version.

**Q: สามารถใช้ Aspose.Page สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: แน่นอน. จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต. คุณสามารถขอได้จาก [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนจากชุมชนได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) อย่างเป็นทางการสำหรับการสนทนา, ตัวอย่างโค้ด, และเคล็ดลับการแก้ปัญหา.

**Q: มีการทดลองใช้ฟรีสำหรับการทดสอบหรือไม่?**  
A: ใช่, คุณสามารถดาวน์โหลดการทดลองใช้ฟรีของ Aspose.Page จากหน้า releases [Aspose.Page releases page](https://releases.aspose.com/).

**Q: ฉันจะขอใบอนุญาตชั่วคราวสำหรับการประเมินระยะสั้นได้อย่างไร?**  
A: ใบอนุญาตชั่วคราวสามารถขอได้จากพอร์ทัลการให้ใบอนุญาต [temporary license request page](https://purchase.aspose.com/temporary-license/).

## สรุป
ตอนนี้คุณรู้แล้วว่า **วิธีตัด EPS** ไฟล์ใน Java ด้วย Aspose.Page เพื่อ **ลดขนาดไฟล์ EPS**. โดยการกำหนด bounding box แบบกำหนดเองและเรียก `cropEps`, คุณสามารถตัดขอบที่ไม่ต้องการหรือแยกส่วนเฉพาะของกราฟิก EPS ด้วยเพียงไม่กี่บรรทัดของโค้ด. ผสานสคริปต์นี้เข้ากับ pipeline การประมวลผลเอกสารของคุณเพื่ออัตโนมัติการจัดการ EPS, **crop EPS image** assets, และ **trim EPS file** อย่างมีประสิทธิภาพ.

---

**อัปเดตล่าสุด:** 2026-09-04  
**ทดสอบด้วย:** Aspose.Page for Java 24.11  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีปรับขนาดไฟล์ EPS ใน Java ด้วย Aspose.Page](/page/java/manipulation-eps/resize/)
- [แปลง EPS เป็น PNG ด้วย Aspose.Page Java (Metered License)](/page/java/license-management/set-metered-license/)
- [Aspose Page Java Tutorial – เพิ่ม XMP Metadata ให้ไฟล์ EPS](/page/java/xmp-metadata-manipulation/add-metadata/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}