---
date: 2026-09-24
description: เรียนรู้วิธีใช้ Aspose.Page เพื่อแปลง EPS เป็น PNG ใน Java, กำหนดค่า
  metered license, และเขียนโค้ด Java สำหรับไฟล์ PNG อย่างมีประสิทธิภาพ
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: ตั้งค่า Metered License ใน Java
og_description: Aspose.Page แปลง EPS เป็น PNG ใน Java ด้วย metered license. คู่มือนี้แสดงขั้นตอนโดยละเอียดในการกำหนดค่า
  licensing, render EPS, และเขียนโค้ด Java สำหรับไฟล์ PNG.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page แปลง EPS เป็น PNG ใน Java (metered license)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page แปลง EPS เป็น PNG ใน Java (metered license)
url: /th/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page แปลง EPS เป็น PNG ใน Java (ใบอนุญาตแบบมีการวัด)

## บทนำ
หากคุณต้องการ **บันทึก EPS เป็น PNG** ในแอปพลิเคชัน Java พร้อมกับการจัดการใบอนุญาตที่ง่าย คุณมาถูกที่แล้ว บทเรียนนี้จะพาคุณผ่านการกำหนดค่า **ใบอนุญาตแบบมีการวัด** สำหรับ Aspose.Page, การโหลดไฟล์ EPS (Encapsulated PostScript) และการแปลงเป็นภาพ PNG. เมื่อเสร็จสิ้นคุณจะเข้าใจวิธี **เรนเดอร์ EPS เป็น PNG อย่างมีประสิทธิภาพ** และวิธี **เขียนโค้ด Java เพื่อบันทึกไฟล์ PNG** ที่ทำงานได้อย่างเชื่อถือได้ในสภาพแวดล้อมการผลิต.

## คำตอบอย่างรวดเร็ว
- **อะไรหมายถึง “save EPS as PNG”?** มันแปลงไฟล์ EPS แบบเวกเตอร์เป็นภาพ PNG แบบแรสเตอร์ โดยคงความโปร่งใสและการบีบอัดแบบไม่มีการสูญเสีย.  
- **ทำไมต้องใช้ใบอนุญาตแบบมีการวัด?** คุณจ่ายเฉพาะหน้าที่คุณประมวลผลเท่านั้น ซึ่งเหมาะกับงานที่มีปริมาณเปลี่ยนแปลง.  
- **ฉันต้องการการเชื่อมต่ออินเทอร์เน็ตหรือไม่?** ไม่, คีย์แบบมีการวัดจะได้รับการตรวจสอบในเครื่องบน JVM.  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่าได้รับการสนับสนุนเต็มที่.  
- **การตั้งค่าต้องใช้เวลานานเท่าไหร่?** ประมาณ 10 นาทีสำหรับการใช้งานพื้นฐาน.

## “save EPS to PNG” คืออะไร
การบันทึก EPS เป็น PNG จะเปลี่ยนเอกสาร Encapsulated PostScript แบบเวกเตอร์เป็นภาพ PNG แบบแรสเตอร์ โดยคงความโปร่งใสและให้การบีบอัดแบบไม่มีการสูญเสีย การแปลงนี้มีประโยชน์เมื่อคุณต้องการกราฟิกพร้อมใช้งานบนเว็บ, รูปย่อ, หรือภาพตัวอย่างที่สามารถพิมพ์ได้และสามารถแสดงในเบราว์เซอร์ใดก็ได้โดยไม่ต้องใช้ตัวแปล PostScript.

## ทำไมต้องเรนเดอร์ EPS เป็น PNG ด้วย Aspose.Page?
Aspose.Page มี API แบบ pure‑Java ที่ทำการแรสเตอร์ไฟล์ EPS ด้วยความแม่นยำสูง, รองรับรูปแบบเอาต์พุตกว่า 50 รูปแบบ, และมีใบอนุญาตแบบมีการวัดเพื่อให้คุณจ่ายเฉพาะสิ่งที่แปลง ไลบรารีนี้สามารถประมวลผลเอกสารหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ให้การเรนเดอร์ที่เร็วและแม่นยำบนแพลตฟอร์มใด ๆ ที่รองรับ JVM.

## ข้อกำหนดเบื้องต้น
ก่อนคุณเริ่ม, ตรวจสอบว่าคุณมี:

- ประสบการณ์พื้นฐานในการพัฒนา Java.  
- ไลบรารี Aspose.Page ที่ดาวน์โหลดจาก [Aspose.Page Java download page](https://releases.aspose.com/page/java/).  
- คู่คีย์สาธารณะและส่วนตัวแบบมีการวัดจากบัญชี Aspose ของคุณ.  

## นำเข้าแพ็กเกจ
คำสั่ง `import` จะนำคลาสที่จำเป็นเข้ามาในสโคป. คงบล็อกนี้ไว้ตามที่แสดงเพื่อให้โค้ดคอมไพล์โดยไม่มีการเปลี่ยนแปลง.

คลาส `java.io` จัดการกับสตรีมไฟล์, ในขณะที่คลาสของ Aspose.Page จัดการใบอนุญาต, การโหลดเอกสาร, และการเรนเดอร์ภาพ.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## วิธีบันทึก EPS เป็น PNG ด้วย Aspose.Page Java
ต่อไปนี้เป็นคู่มือขั้นตอนต่อขั้นตอนที่รวมการจัดการใบอนุญาต, การโหลด, การเรนเดอร์, และการเขียนไฟล์ PNG สุดท้าย.

### คำตอบโดยตรง
โหลดไฟล์ EPS ของคุณ, ใช้ใบอนุญาตแบบมีการวัด, กำหนดค่า `ImageSaveOptions` สำหรับ PNG, เรนเดอร์เอกสารไปยัง `ImageDevice`, และสุดท้ายเขียนอาร์เรย์ไบต์ที่ได้ลงดิสก์. ลำดับนี้ทำให้กระบวนการ **save EPS as PNG** เสร็จสมบูรณ์ด้วยเพียงไม่กี่บรรทัดของโค้ด Java.

### ขั้นตอนที่ 1: เริ่มต้นเอกสารและรูปแบบภาพ
แรกเริ่มตั้งค่าคีย์แบบมีการวัดและกำหนดรูปแบบเอาต์พุต (PNG). นี้เป็นการวางพื้นฐานสำหรับการแปลง.

คลาส `MeteredLicense` จะเก็บคีย์สาธารณะและส่วนตัวของคุณ, ในขณะที่ `ImageSaveOptions` บอก Aspose.Page ให้สร้างเอาต์พุตเป็น PNG.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### ขั้นตอนที่ 2: เริ่มต้นสตรีมอินพุต PostScript
เปิดไฟล์ EPS ที่คุณต้องการแปลง. สตรีมนี้จะส่งข้อมูลเอกสารเข้าสู่ Aspose.Page.

`FileInputStream` อ่านไฟล์ EPS จากดิสก์, ทำให้คอนสตรัคเตอร์ `Document` สามารถพาร์สข้อมูล PostScript ได้.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### ขั้นตอนที่ 3: ตรวจสอบใบอนุญาตเอกสาร
ตรวจสอบเสมอว่าใบอนุญาตแบบมีการวัดได้ถูกนำไปใช้อย่างถูกต้องก่อนการประมวลผล.

เมธอด `isLicensed()` จะคืนค่า `true` ก็ต่อเมื่อคีย์ที่ให้มาถูกต้อง, ป้องกันการใช้ไลบรารีที่ไม่มีใบอนุญาตโดยบังเอิญ.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### ขั้นตอนที่ 4: เริ่มต้นตัวเลือกและอุปกรณ์ภาพ
สร้างอ็อบเจ็กต์ตัวเลือกที่ควบคุมการตั้งค่าการแปลงและอุปกรณ์ที่จะรับภาพที่เรนเดอร์.

`ImageDevice` จับเอาต์พุตที่แรสเตอร์ไว้ในหน่วยความจำ, ในขณะที่ `ImageSaveOptions` ให้คุณปรับ DPI, ระดับการบีบอัด, และความลึกของสี.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### ขั้นตอนที่ 5: บันทึกไฟล์ EPS เป็นภาพ
นี่คือการเรียกหลักของ **save EPS as PNG**. เอกสารถูกเรนเดอร์เข้าสู่อุปกรณ์ภาพโดยใช้ตัวเลือกที่เราตั้งค่าไว้.

เมธอด `document.save(device, options)` ทำการแรสเตอร์ในขั้นตอนเดียว.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### ขั้นตอนที่ 6: ดึงและบันทึกไบต์ของภาพ
ดึงไบต์ PNG จากอุปกรณ์และเขียนลงไฟล์บนดิสก์. ขั้นตอนนี้แสดงวิธี **write PNG file Java** อย่างปลอดภัย.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` จะบันทึกภาพโดยไม่ต้องใช้ไลบรารีเพิ่มเติม.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## ปัญหาทั่วไปและวิธีแก้
| Issue | Why it happens | Fix |
|-------|----------------|-----|
| **ไม่พบใบอนุญาต** | คีย์ไม่ถูกต้องหรือ `setMeteredKey` ถูกเรียกหลังจากการประมวลผลเอกสาร. | ตรวจสอบสตริงคีย์สาธารณะ/ส่วนตัวอีกครั้งและตรวจสอบให้แน่ใจว่า `setMeteredKey` ทำงานก่อนการเรียกใช้ Aspose.Page ใด ๆ. |
| **ไฟล์ผลลัพธ์ว่างเปล่า** | `device.getImagesBytes()` คืนค่า `null` เนื่องจากไฟล์ EPS ไม่สามารถพาร์สได้. | ตรวจสอบว่าไฟล์ EPS ถูกต้องและ `ImageSaveOptions` ระบุขนาดแคนวาสที่ไม่เป็นศูนย์. |
| **OutOfMemoryError กับ EPS ขนาดใหญ่** | การเรนเดอร์ไฟล์เวกเตอร์ขนาดใหญ่ใช้หน่วยความจำ heap มาก. | ประมวลผลหน้าแบบหนึ่งต่อหนึ่งหรือเพิ่มขนาด heap ของ JVM (`-Xmx2g`). |

## คำถามที่พบบ่อย

**Q: ฉันจะรับคีย์สาธารณะและส่วนตัวแบบมีการวัดได้อย่างไร?**  
A: เข้าสู่ระบบบัญชี Aspose ของคุณ, ไปที่ส่วน **Metered License**, แล้วคัดลอกคีย์สาธารณะและส่วนตัวที่สร้างขึ้น.

**Q: ไลบรารี Aspose.Page ฟรีหรือไม่?**  
A: Aspose.Page มีรุ่นทดลองฟรีพร้อมฟังก์ชันเต็ม; การใช้ในการผลิตต้องมีใบอนุญาตแบบชำระเงิน. ดาวน์โหลดรุ่นทดลองที่ [Aspose trial download page](https://releases.aspose.com/).

**Q: ฉันสามารถใช้ Aspose.Page ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ได้, ใบอนุญาตเชิงพาณิชย์อนุญาตให้ปรับใช้ในสภาพแวดล้อมการผลิต. ซื้อใบอนุญาตที่ [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?**  
A: อ้างอิง API เต็มรูปแบบสามารถดูได้ที่ [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: ฉันจะขอใบอนุญาตชั่วคราวเพื่อการประเมินได้อย่างไร?**  
A: ใบอนุญาตชั่วคราวจะให้ผ่านพอร์ทัล Aspose ที่ [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: ถ้าฉันต้องการแปลงไฟล์ EPS หลายหน้า จะทำอย่างไร?**  
A: วนลูปผ่านแต่ละหน้าโดยใช้ `device.getImagesBytes()` และเขียนแต่ละอาร์เรย์ไบต์เป็นไฟล์ PNG แยกกัน.

**Q: ฉันสามารถเปลี่ยนคุณภาพ PNG หรือความลึกของสีได้หรือไม่?**  
A: ได้, ตั้งค่า `ImageSaveOptions` (เช่น `options.setCompressionLevel(9)`) ก่อนเรียก `document.save(...)`.

---

**อัปเดตล่าสุด:** 2026-09-24  
**ทดสอบกับ:** Aspose.Page 24.12 for Java (latest)  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีตั้งค่าใบอนุญาตสำหรับ Aspose.Page Java API – การจัดการใบอนุญาต](/page/java/license-management/)
- [แปลง PS เป็น PNG ด้วย Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [ปรับขนาด EPS ด้วย Aspose.Page – การจัดการ EPS ใน Java](/page/java/manipulation-eps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}