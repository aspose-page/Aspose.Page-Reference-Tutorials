---
date: 2025-12-23
description: เรียนรู้วิธีแปลง XPS เป็น JPEG ใน Java และค้นพบวิธีแปลงไฟล์ XPS อย่างมีประสิทธิภาพด้วย
  Aspose.Page คู่มือครบถ้วนพร้อมคำแนะนำทีละขั้นตอนเพื่อการบูรณาการที่ราบรื่น
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: วิธีแปลง XPS เป็น JPEG ใน Java
url: /th/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง XPS เป็น JPEG ด้วย Java

## Introduction
ในบทแนะนำนี้, **คุณจะได้เรียนรู้วิธีแปลง XPS เป็น JPEG** ด้วยไลบรารี Aspose.Page ที่ทรงพลังสำหรับ Java. การแปลงไฟล์ XPS เป็นรูปภาพเป็นความต้องการทั่วไปเมื่อคุณต้องการแสดง, ดูตัวอย่าง, หรือประมวลผลต่อหน้าของเอกสารในแอปพลิเคชันเว็บหรือเดสก์ท็อป. เราจะเดินผ่านแต่ละขั้นตอน, อธิบายว่าทำไมแต่ละบรรทัดจึงสำคัญ, และให้เคล็ดลับเชิงปฏิบัติเพื่อให้คุณสามารถผสานตรรกะการแปลงเข้าไปในโครงการของคุณได้อย่างมั่นใจ.

## Quick Answers
- **What library handles the conversion?** Aspose.Page for Java  
- **Can I select specific pages?** Yes – use `setPageNumbers` in `JpegSaveOptions`  
- **What image quality can I control?** Smoothing mode, resolution, and JPEG quality settings  
- **Do I need a license for production?** Yes, a commercial license is required (a free trial is available)  
- **Is the code Java 8 compatible?** Absolutely – the API works with Java 8 and newer  

## What is XPS and Why Convert it to JPEG?
XPS (XML Paper Specification) เป็นรูปแบบเอกสารแบบจัดวางคงที่ที่คล้ายกับ PDF. การแปลง XPS เป็น JPEG มีประโยชน์เมื่อคุณต้องการภาพเรสเตอร์สำหรับภาพขนาดย่อ, แนบอีเมล, หรือเมื่อผสานกับระบบที่รับไฟล์รูปภาพเท่านั้น. JPEG ให้สมดุลที่ดีระหว่างคุณภาพภาพและขนาดไฟล์, ทำให้เหมาะสำหรับการแสดงตัวอย่างบนเว็บ.

## Prerequisites
Before we dive into the code, ensure you have the following:

- **Java Development Environment** – JDK 8 or later installed and configured.  
- **Aspose.Page for Java** – Download the latest library from the official site [here](https://releases.aspose.com/page/java/).  
- **Sample XPS Document** – An XPS file you want to transform into JPEG images.  

## Import Packages
Begin by importing the necessary classes into your Java source file:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Step 1: Initialize Paths and Load the XPS Document
Set the directory that contains your source XPS file and create an `XpsDocument` instance:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Pro tip:** Use `Paths.get()` from `java.nio.file` for platform‑independent path handling.

เคล็ดลับระดับมืออาชีพ: ใช้ `Paths.get()` จาก `java.nio.file` เพื่อจัดการเส้นทางที่เป็นอิสระต่อแพลตฟอร์ม.

## Step 2: Configure JPEG Save Options
Define how the JPEG images should be rendered—resolution, smoothing, and which pages to export:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` produces high‑resolution output suitable for printing.  
  `setResolution(300)` สร้างผลลัพธ์ความละเอียดสูงที่เหมาะสำหรับการพิมพ์.  
- `setPageNumbers` lets you pick only the pages you need, saving time and memory.  
  `setPageNumbers` ให้คุณเลือกเฉพาะหน้าที่ต้องการ, ช่วยประหยัดเวลาและหน่วยความจำ.

## Step 3: Create the Rendering Device
The `ImageDevice` captures the rendered pages as byte arrays:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Step 4: Render the XPS Document to JPEG
Invoke the `save` method, passing the device and the options you configured:

```java
document.save(device, options);
```

At this point the `device` holds a two‑dimensional array where each element represents a JPEG‑encoded page.

ในขั้นตอนนี้ `device` จะถืออาเรย์สองมิติที่แต่ละองค์ประกอบเป็นหน้าที่เข้ารหัสเป็น JPEG.

## Step 5: Iterate Through the Result and Write Files
Loop over the rendered pages and write each byte array to a separate JPEG file:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

Each file will be named `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, making it easy to identify the source document and page number.

แต่ละไฟล์จะถูกตั้งชื่อเป็น `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, ทำให้ง่ายต่อการระบุเอกสารต้นฉบับและหมายเลขหน้า.

## Common Issues & Troubleshooting
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| **ไฟล์ JPEG ว่างเปล่า** | สตรีมเอาต์พุตไม่ได้ทำการ flush หรือ close อย่างถูกต้อง | ตรวจสอบให้แน่ใจว่า `imageStream.close()` ถูกเรียกภายในลูปภายใน (ตามที่แสดง). |
| **ข้อผิดพลาด Out‑of‑memory** บนไฟล์ XPS ขนาดใหญ่ | การเรนเดอร์ทุกหน้าพร้อมกันใช้ RAM มากเกินไป | ประมวลผลหน้าเป็นชุดเล็ก ๆ หรือเพิ่มขนาด heap ของ JVM (`-Xmx`). |
| **หน้าหายไป** | `setPageNumbers` ไม่ได้รวมหน้าที่ต้องการ | ตรวจสอบว่าอาร์เรย์หมายเลขหน้าตรงกับดัชนีหน้าจริงของ XPS (เริ่มจาก 1). |

## Frequently Asked Questions

### Q: Aspose.Page เหมาะสำหรับโครงการเชิงพาณิชย์หรือไม่?
A: ใช่, Aspose.Page เป็นผลิตภัณฑ์เชิงพาณิชย์ที่มีตัวเลือกการให้ใบอนุญาต. ตรวจสอบรายละเอียดได้ที่ [here](https://purchase.aspose.com/buy).

### Q: ฉันสามารถลอง Aspose.Page ก่อนซื้อได้หรือไม่?
A: ใช่, คุณสามารถรับการทดลองใช้งานฟรีได้ [here](https://releases.aspose.com/).

### Q: จะหาเอกสารประกอบของ Aspose.Page ได้จากที่ไหน?
A: เอกสารประกอบพร้อมให้บริการ [here](https://reference.aspose.com/page/java/).

### Q: จะขอรับการสนับสนุนสำหรับ Aspose.Page ได้อย่างไร?
A: เยี่ยมชม [Aspose.Page Forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชน.

### Q: ฉันต้องการใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่?
A: ใช่, คุณสามารถรับใบอนุญาตชั่วคราวได้ [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
You’ve now mastered **how to convert XPS to JPEG** using Aspose.Page for Java. By following the step‑by‑step guide, you can integrate this conversion pipeline into any Java application—whether it’s a desktop tool, a web service, or a batch‑processing utility. Feel free to experiment with different resolutions, page selections, and image formats to suit your project's needs.

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบด้วย:** Aspose.Page 24.11 for Java (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}