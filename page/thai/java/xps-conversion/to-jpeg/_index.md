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

## การแนะนำ
ในบทแนะนำนี้ ** เราจะแปลง XPS เป็น JPEG** ด้วยไลบรารี Aspose.Page สำหรับ Java ไฟล์ XPS เป็นรูปภาพที่ต้องการทั่วไปเมื่อต้องการแสดง ดูตัวอย่าง หรืออย่างเป็นทางการของเอกสารในแอปพลิเคชันเว็บหรือตามคำขอ สิ่งสำคัญในแต่ละขั้นตอน อธิบายว่าทำไมแต่ละบรรทัดจึงมีความสำคัญ และให้เคล็ดลับเชิงปฏิบัติเพื่อให้คุณสามารถใช้แนวทางปฏิบัติสำหรับโครงการของคุณได้อย่างมั่นใจ

## คำตอบด่วน
- **ไลบรารีใดที่จัดการการแปลง** Aspose.Page สำหรับ Java
- **ฉันสามารถเลือกหน้าที่ต้องการได้หรือไม่** ได้ – ใช้ `setPageNumbers` ใน `JpegSaveOptions`
- **ฉันสามารถควบคุมคุณภาพของภาพแบบใดได้** โหมดการปรับให้เรียบ ความละเอียด และการตั้งค่าคุณภาพ JPEG
- **ฉันต้องมีใบอนุญาตสำหรับการผลิตหรือไม่** ใช่ จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์ (สามารถทดลองใช้ฟรีได้)
- **โค้ด Java8 เข้ากันได้หรือไม่** แน่นอน – API ใช้งานได้กับ Java8 และใหม่กว่า

## XPS คืออะไร และเหตุใดจึงต้องแปลงเป็น JPEG
XPS (XML Paper Specification) ในรูปแบบเอกสารแบบจัดวางความเสียหายที่มีความสำคัญ PDF. ไฟล์ XPS เป็น JPEG มีประโยชน์เมื่อต้องการให้ภาพเรสเตอร์สำหรับภาพขนาดย่อ, แนบอีเมล์, หรือเมื่อท่องเที่ยวกับระบบที่รับไฟล์รูปภาพเท่านั้น JPEG ให้ความสมดุลที่ดีระหว่างคุณภาพภาพและขนาดไฟล์ ซึ่งเหมาะสำหรับการแสดงตัวอย่างคำอธิบาย

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- **Java Development Environment** – ติดตั้งและกำหนดค่า JDK 8 หรือใหม่กว่า
- **Aspose.Page สำหรับ Java** – ดาวน์โหลดไลบรารีล่าสุดจากเว็บไซต์อย่างเป็นทางการ[ที่นี่](https://releases.aspose.com/page/java/)
- **ตัวอย่างเอกสาร XPS** – ไฟล์ XPS ที่คุณต้องการแปลงเป็นภาพ JPEG

## แพคเกจนำเข้า
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็นลงในซอร์สไฟล์ Java ของคุณ:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## ขั้นตอนที่ 1: เริ่มต้นเส้นทางและโหลดเอกสาร XPS
ตั้งค่าไดเรกทอรีที่มีไฟล์ XPS ต้นทางของคุณและสร้างอินสแตนซ์ `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **เคล็ดลับมือโปร:** ใช้ `Paths.get()` จาก `java.nio.file` สำหรับการจัดการเส้นทางที่ไม่ขึ้นอยู่กับแพลตฟอร์ม

คำแนะนำ: ใช้ `Paths.get()` จาก `java.nio.file` เพื่อควบคุมเส้นทางที่เรียกดูต่อแพลตฟอร์ม

## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการบันทึก JPEG
กำหนดวิธีการเรนเดอร์ภาพ JPEG เช่น ความละเอียด การปรับให้เรียบ และหน้าที่จะส่งออก:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` ให้เอาต์พุตที่มีความละเอียดสูงซึ่งเหมาะสำหรับการพิมพ์ 
`setResolution(300)` สร้างผลลัพธ์ที่ยอดเยี่ยมสำหรับการพิมพ์
- `setPageNumbers` ช่วยให้คุณสามารถเลือกเฉพาะหน้าที่คุณต้องการ ซึ่งช่วยประหยัดเวลาและหน่วยความจำ 
`setPageNumbers` ให้คุณเลือกเฉพาะหน้าที่ต้องการ ช่วยประหยัดเวลาและคำอธิบาย

## ขั้นตอนที่ 3: สร้างอุปกรณ์แสดงผล
`ImageDevice` จับหน้าที่แสดงผลเป็นอาร์เรย์ไบต์:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## ขั้นตอนที่ 4: เรนเดอร์เอกสาร XPS เป็น JPEG
เรียกใช้เมธอด "บันทึก" โดยส่งอุปกรณ์และตัวเลือกที่คุณกำหนดค่า:

```java
document.save(device, options);
```

ณ จุดนี้ "อุปกรณ์" จะเก็บอาร์เรย์สองมิติโดยที่แต่ละองค์ประกอบแสดงถึงหน้าที่เข้ารหัส JPEG

ในขั้นตอนนี้ `อุปกรณ์` จะถืออาเรย์สองมิติที่แต่ละเรื่องราวเป็นหน้าที่ของ JPEG

## ขั้นตอนที่ 5: วนซ้ำผลลัพธ์และเขียนไฟล์
วนซ้ำหน้าที่แสดงผลและเขียนแต่ละอาร์เรย์ไบต์ไปยังไฟล์ JPEG แยกกัน:

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

แต่ละไฟล์จะมีชื่อว่า `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg` ทำให้ง่ายต่อการระบุเอกสารต้นฉบับและหมายเลขหน้า

ไฟล์ที่สามารถตรวจพบได้คือ `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, ซึ่งส่วนใหญ่จะระบุเอกสารต้นฉบับและหมายเลขหน้า

## ปัญหาทั่วไปและการแก้ไขปัญหา
| นั่น | สาเหตุที่ทำให้ | วิธีแก้ |
|---------|--------------|-----|
| ** ไฟล์ JPEG สลิง** | สตรีมดังกล่าวไม่ได้ทำการล้างหรือปิด | เครื่องตัด `imageStream.close()` มีประโยชน์เรียกภายในอันงดงามภายใน (ตามอุปกรณ์เสริม) |
| **เสื้อ Out‑of‑memory** บนไฟล์ XPS ขนาดใหญ่ | การเรนเดอร์ทุกหน้าพร้อมกันใช้ RAM เพิ่มเติม | กำหนดให้หน้าเป็นชุดเล็ก ๆ หรือเพิ่มขนาด heap ของ JVM (`-Xmx`) |
| **หน้าหายไป** | `setPageNumbers` เพื่อการรวมหน้าที่ต้องการ | เพื่อตรวจสอบหมายเลขหน้าดัชนีหน้าจริงของ XPS (ส่วนที่ 1) |

## คำถามที่พบบ่อย

### ถาม: Aspose.Page สำหรับโครงการของเราหรือไม่?
คำตอบ: ถูกต้อง, Aspose.Page เป็นผลิตภัณฑ์ที่เป็นความเชื่อส่วนบุคคลเท่านั้น รายละเอียดการถ่ายภาพได้ที่ [ที่นี่](https://purchase.aspose.com/buy)

### Q: และลอง Aspose.Page ก่อนที่จะซื้อก็ได้?
ตอบ: จริง ๆ แล้วไม่เคยยอมรับการใช้งานฟรีได้ [ที่นี่](https://releases.aspose.com/)

### ถาม: เอกสารประกอบของ Aspose.Page จากที่ไหน?
A: เอกสารประกอบพร้อมใช้งาน [ที่นี่](https://reference.aspose.com/page/java/)

### ถาม: จะขอรับพิเศษสำหรับ Aspose.Page ได้อย่างไร?
ตอบ: [Aspose.Page Forum](https://forum.aspose.com/c/page/39) จะได้รับในชุมชนนี้

### ถาม: ยืนยันอีกครั้งชั่วคราวสำหรับการทดสอบหรือไม่?
ตอบ: เป็นไปได้ไม่เคยรับเลยชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

## บทสรุป
ตอนนี้คุณเชี่ยวชาญ **วิธีแปลง XPS เป็น JPEG** โดยใช้ Aspose.Page สำหรับ Java แล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถรวมไปป์ไลน์การแปลงนี้เข้ากับแอปพลิเคชัน Java ใดก็ได้ ไม่ว่าจะเป็นเครื่องมือเดสก์ท็อป บริการบนเว็บ หรือยูทิลิตีการประมวลผลแบบแบตช์ คุณสามารถทดลองใช้ความละเอียด การเลือกหน้า และรูปแบบรูปภาพต่างๆ ได้ตามต้องการเพื่อให้เหมาะกับความต้องการของโปรเจ็กต์ของคุณ

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบด้วย:** Aspose.Page 24.11 for Java (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}