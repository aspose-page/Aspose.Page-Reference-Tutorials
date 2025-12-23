---
date: 2025-12-23
description: แปลง XPS เป็น TIFF อย่างง่ายดายด้วย Aspose.Page Java. ทำตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการรวมระบบที่ราบรื่นด้วย
  aspose page java. ดาวน์โหลดเลย!
linktitle: Convert XSP to TIFF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: แปลง XSP เป็น TIFF ใน Java ด้วย Aspose.Page Java
url: /th/java/xps-conversion/to-tiff/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง XSP เป็น TIFF ใน Java ด้วย Aspose.Page Java

ในสภาพแวดล้อมซอฟต์แวร์ที่เคลื่อนที่เร็วในปัจจุบัน, **aspose page java** ทำให้การแปลงเอกสาร Java ง่ายและเชื่อถือได้ ไม่ว่าคุณจะต้อง **convert XPS to TIFF** เพื่อการเก็บถาวร, การพิมพ์, หรือการประมวลผลแบบชุด, บทแนะนำนี้จะพาคุณผ่านขั้นตอนที่แม่นยำ, อธิบายเหตุผลเบื้องหลังแต่ละการกระทำ, และให้เคล็ดลับที่สามารถนำไปใช้ได้ทันที.

## คำตอบด่วน
- **ไลบรารีใดที่จัดการการแปลง XPS‑to‑TIFF?** Aspose.Page Java.  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาต Aspose.Page Java ที่ถูกต้อง.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 8 หรือสูงกว่า.  
- **ฉันสามารถแปลงไฟล์ XPS หลายไฟล์พร้อมกันได้หรือไม่?** ได้ – คุณสามารถสร้างลูปการแปลง XPS แบบชุดโดยใช้โค้ดเดียวกัน.  
- **ความละเอียดใดที่เหมาะสมที่สุดสำหรับ TIFF ที่พร้อมพิมพ์?** 300 DPI เป็นตัวเลือกทั่วไป, แต่คุณสามารถปรับได้ผ่าน TiffSaveOptions.

## Aspose.Page Java คืออะไร?
Aspose.Page Java เป็น API ที่ทรงพลังที่ทำให้ **java document conversion** จาก XPS (XML Paper Specification) ไปยังรูปแบบราสเตอร์และเวกเตอร์หลากหลายรวมถึง TIFF. มันจัดการกับการจัดหน้า, ฟอนต์, และกราฟิกที่ซับซ้อนได้โดยไม่ต้องใช้ Microsoft XPS Document Writer.

## ทำไมต้องใช้ Aspose.Page Java สำหรับการแปลง XPS เป็น TIFF?
- **ความแม่นยำสูง:** รักษาข้อมูลเวกเตอร์และการแสดงผลข้อความ.  
- **ประสิทธิภาพ:** ปรับให้เหมาะกับไฟล์ขนาดใหญ่และสถานการณ์การแปลง XPS แบบชุด.  
- **ความยืดหยุ่น:** ปรับแต่งผลลัพธ์ด้วย `tiff save options` เช่น ความละเอียด, การบีบอัด, และการเลือกหน้า.  
- **ข้ามแพลตฟอร์ม:** ทำงานบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java, ทำให้เหมาะสำหรับการประมวลผลฝั่งเซิร์ฟเวอร์.

## ข้อกำหนดเบื้องต้น
ก่อนจะดำดิ่งสู่กระบวนการแปลง, โปรดตรวจสอบว่าคุณมี:
- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ.  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/java/).  
- ใบอนุญาตที่ถูกต้องสำหรับ Aspose.Page for Java คุณสามารถรับใบอนุญาตชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/), หรือซื้อใบอนุญาตเต็มได้จาก [here](https://purchase.aspose.com/buy).

## นำเข้าแพ็กเกจ
เริ่มต้นโดยการนำเข้าแพ็กเกจที่จำเป็นในโปรเจค Java ของคุณ ตรวจสอบให้แน่ใจว่า JAR ของ Aspose.Page for Java ถูกเพิ่มในเส้นทางการสร้าง (build path).

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดเส้นทางไปยังโฟลเดอร์ที่มีไฟล์ XPS ต้นฉบับของคุณ.

```java
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: โหลดเอกสาร XPS
สร้างอินสแตนซ์ `XpsDocument` ที่ชี้ไปยังไฟล์อินพุต.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

## ขั้นตอนที่ 3: เริ่มต้น TiffSaveOptions
กำหนดค่า **tiff save options** ที่ควบคุมคุณภาพภาพ, ความละเอียด, และหน้าที่จะส่งออก.

```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

## ขั้นตอนที่ 4: สร้างอุปกรณ์การเรนเดอร์
สร้างอินสแตนซ์ `ImageDevice` ที่จะเรนเดอร์หน้าต่างๆ เป็นภาพ TIFF.

```java
ImageDevice device = new ImageDevice();
```

## ขั้นตอนที่ 5: บันทึกเอกสารเป็น TIFF
เรนเดอร์เอกสาร XPS ด้วยอุปกรณ์และตัวเลือกที่กำหนดไว้ก่อนหน้า.

```java
document.save(device, options);
```

## ขั้นตอนที่ 6: วนลูปและบันทึกภาพ TIFF
วนลูปผ่านบัฟเฟอร์ภาพที่เรนเดอร์และเขียนแต่ละหน้าเป็นไฟล์ TIFF แยกกัน.

```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

ยินดีด้วย! คุณได้ทำการ **convert XPS to TIFF** ใน Java ด้วย **aspose page java** อย่างสำเร็จแล้ว อย่าลังเลที่จะสำรวจคุณลักษณะและฟังก์ชันเพิ่มเติมของไลบรารีใน [documentation](https://reference.aspose.com/page/java/).

## สรุป
ในบทแนะนำนี้ เราได้ครอบคลุมทุกสิ่งที่คุณต้องรู้เพื่อทำ **java document conversion** จาก XPS ไปเป็น TIFF ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการปรับแต่ง `tiff save options` อย่างละเอียด ด้วย Aspose.Page Java คุณยังสามารถสร้าง pipeline **batch XPS conversion** ที่ประมวลผลไฟล์หลายสิบหรือหลายร้อยไฟล์โดยอัตโนมัติ.

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page for Java ได้โดยไม่มีใบอนุญาตหรือไม่?
แม้ว่าคุณจะสามารถรับใบอนุญาตชั่วคราวเพื่อการประเมินได้, แต่จำเป็นต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์ รับใบอนุญาตของคุณได้จาก [here](https://purchase.aspose.com/buy).

### มีข้อจำกัดใดเกี่ยวกับขนาดของไฟล์ XPS สำหรับการแปลงหรือไม่?
Aspose.Page for Java รองรับเอกสารขนาดต่างๆ, แต่แนะนำให้ทดสอบกับไฟล์ขนาดใหญ่ในสภาพแวดล้อมของคุณ.

### ฉันจะขอรับการสนับสนุนหรือถามคำถามเกี่ยวกับ Aspose.Page for Java ได้อย่างไร?
เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา.

### มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?
ใช่, คุณสามารถสำรวจไลบรารีด้วยการทดลองใช้ฟรี ดาวน์โหลดได้จาก [here](https://releases.aspose.com/).

### ความละเอียดที่แนะนำสำหรับภาพ TIFF ในการแปลงนี้คืออะไร?
ตัวอย่างใช้ความละเอียด 300 DPI, แต่คุณสามารถปรับได้ตามความต้องการของคุณ.

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบด้วย:** Aspose.Page Java 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}