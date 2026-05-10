---
date: 2026-02-20
description: เรียนรู้วิธีตั้งค่าสีข้อความใน Java ด้วย Aspose.Page for Java, เปลี่ยนขนาดฟอนต์ใน
  Java, สร้างไฟล์ PostScript, เติมและวาดขอบข้อความ, และใช้ฟอนต์กำหนดเองใน Java ขณะสร้างเอกสาร
  PostScript.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: ตั้งค่าสีข้อความใน Java ด้วย Aspose.Page – คู่มือการจัดการข้อความ
url: /th/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าสีข้อความใน Java ด้วย Aspose.Page – คู่มือการจัดการข้อความ

## บทนำ
ยินดีต้อนรับสู่คู่มือขั้นตอนโดยละเอียดของเราเกี่ยวกับ **set text color java** ขณะทำงานกับไฟล์ PostScript ด้วย Aspose.Page for Java. Aspose.Page for Java เป็นไลบรารีที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถ **create postscript document** ไฟล์, จัดการฟอนต์, และกำหนดสไตล์ข้อความด้วยความแม่นยำ ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีการเพิ่มข้อความ, เปลี่ยนสี, **change font size java**, และแม้กระทั่ง **apply fill and stroke text** เพื่อให้ได้ผลลัพธ์ที่ดูเป็นมืออาชีพ

## คำตอบสั้น
- **ไลบรารีใดที่ทำให้ฉันตั้งค่าสีข้อความใน Java ได้?** Aspose.Page for Java.  
- **ฉันสามารถใช้ฟอนต์ระบบและฟอนต์กำหนดเองได้หรือไม่?** ได้, ทั้งสองแบบรองรับและคุณสามารถ **use custom fonts java** ได้อย่างง่ายดาย.  
- **ฉันจะเปลี่ยนขนาดข้อความอย่างไร?** โดยระบุขนาดฟอนต์เมื่อสร้าง `Font` หรือ `DrFont`.  
- **สามารถทำการขอบและเติมข้อความพร้อมกันได้หรือไม่?** แน่นอน – ใช้ `fillAndStrokeText`.  
- **ฟอร์แมตผลลัพธ์ของบทแนะนำนี้คืออะไร?** ไฟล์ PostScript (`.ps`) ซึ่งคุณสามารถ **generate postscript file** ได้โดยโปรแกรม

## “set text color java” คืออะไร?
การตั้งค่าสีข้อความใน Java หมายถึงการกำหนดอ็อบเจ็กต์ `Color` ที่เอนจินการเรนเดอร์ (ในที่นี้คือ Aspose.Page) ใช้เมื่อวาดอักขระลงบนหน้า การดำเนินการนี้สำคัญสำหรับการสร้างเอกสารที่มีความแตกต่างทางสายตา โดยเฉพาะเมื่อคุณต้อง **generate postscript file** โดยโปรแกรม

## ทำไมต้องใช้ Aspose.Page for Java?
- **Full control** บนการสร้าง PostScript โดยไม่ต้องพึ่งพาอินเตอร์พรีเตอร์เนทีฟ.  
- **Support for both system and external fonts**, ให้คุณฝังฟอนต์ใดก็ได้ที่ต้องการ.  
- **Easy API** สำหรับการเติม, ขอบ, และ **fill and stroke text**, ให้ความยืดหยุ่นในการจัดสไตล์.  
- **Cross‑platform** compatibility – เขียนครั้งเดียว, รันได้ทุกที่ที่ Java ทำงาน.  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน, โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java.  
- ไลบรารี Aspose.Page for Java ที่ติดตั้งแล้ว. คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).  
- ฟอนต์ที่จำเป็นอยู่ในโฟลเดอร์ที่กำหนด รายละเอียดเพิ่มเติมอยู่ใน [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## การนำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ, นำเข้าแพ็กเกจที่จำเป็นสำหรับ Aspose.Page for Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## ขั้นตอนที่ 1: ตั้งค่าเอกสาร
แรกเริ่มเราจะสร้าง **PostScript document** ใหม่และกำหนดตัวเลือกการส่งออก

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## วิธีตั้งค่าสีข้อความใน Java ด้วยฟอนต์ระบบ
ต่อไปเราจะสาธิต **set text color java** ด้วยฟอนต์ที่มาจากระบบ

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **เคล็ดลับ:** เมธอด `fillText` จะใช้สีปัจจุบันโดยอัตโนมัติหากคุณไม่ได้ส่งอาร์กิวเมนต์ `Color`, ซึ่งค่าเริ่มต้นคือสีดำ.

## การใช้ฟอนต์กำหนดเองและการเปลี่ยนขนาดข้อความ
คุณยังสามารถ **change font size java** และใช้ฟอนต์กำหนดเองที่เก็บไว้ในโฟลเดอร์ฟอนต์ของคุณได้

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## การขอบข้อความ (Stroke) – ใช้ Stroke Text
การขอบข้อความทำให้ได้ขอบที่คมชัด ที่นี่เราจะ **apply stroke text** ด้วย `BasicStroke`

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## การขอบข้อความด้วยฟอนต์กำหนดเอง
เทคนิคเดียวกันนี้ใช้ได้กับฟอนต์กำหนดเองเช่นกัน

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
สุดท้าย, ปิดหน้าและเขียนไฟล์ลงดิสก์

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## ทำไมเรื่องนี้ถึงสำคัญ
การสามารถ **set text color java** และรวมการเติมกับการขอบเข้าด้วยกันทำให้คุณมีอิสระศิลปะเต็มที่บนผลลัพธ์ PostScript ไม่ว่าคุณจะสร้างใบแจ้งหนี้, ใบรับรอง, หรือกราฟิกแบบกำหนดเอง ความสามารถในการ **create postscript document** ด้วยสไตล์ที่แม่นยำช่วยลดความจำเป็นในการทำหลังการประมวลผลในโปรแกรมกราฟิก

## ปัญหาที่พบบ่อย & วิธีแก้
| Issue | Solution |
|-------|----------|
| **Font not found** | ตรวจสอบให้แน่ใจว่าไฟล์ฟอนต์อยู่ใน `necessary_fonts` และเส้นทางโฟลเดอร์ได้ถูกเพิ่มอย่างถูกต้องผ่าน `options.setAdditionalFontsFolders`. |
| **Color not applied** | ยืนยันว่าคุณเรียกโอเวอร์โหลดของ `fillText` หรือ `outlineText` ที่รวมอาร์กิวเมนต์ `Color`. |
| **Stroke appears too thin** | เพิ่มความกว้างของ `BasicStroke` (เช่น `new BasicStroke(3)`). |
| **Document not opening** | ยืนยันว่าไฟล์ `.ps` ที่สร้างมีนามสกุลที่ถูกต้องและโปรแกรมดูของคุณรองรับ PostScript. |

## คำถามที่พบบ่อย

**Q:** ฉันสามารถใช้ฟอนต์กำหนดเองกับ Aspose.Page for Java ได้หรือไม่?  
A: ได้, คุณสามารถ **use custom fonts java** โดยระบุชื่อฟอนต์และขนาดในคลาส `DrFont`.

**Q:** ฉันจะเปลี่ยนสีของข้อความได้อย่างไร?  
A: คุณสามารถตั้งค่าสีที่ต้องการโดยใช้คลาส `Color` เมื่อทำการเติมหรือขอบข้อความ.

**Q:** สามารถเพิ่มหลายหน้าในเอกสาร PostScript ได้หรือไม่?  
A: แน่นอน! คุณสามารถสร้างหลายหน้าโดยทำซ้ำขั้นตอนการสร้างเอกสารและบันทึก.

**Q:** จุดประสงค์ของคลาส `ExternalFontCache` คืออะไร?  
A: `ExternalFontCache` ใช้เพื่อดึงฟอนต์กำหนดเอง, ทำให้มั่นใจว่าฟอนต์พร้อมใช้งานสำหรับการจัดการข้อความ.

**Q:** ฉันสามารถกำหนดสไตล์การขอบที่แตกต่างให้กับข้อความที่ขอบได้หรือไม่?  
A: ได้, คุณสามารถปรับความกว้างและสีของการขอบโดยใช้คลาส `Stroke` และคลาส `Color` ตามลำดับ.

## สรุป
ขอแสดงความยินดี! ตอนนี้คุณรู้วิธี **set text color java**, **change font size java**, **apply fill and stroke text**, และ **create postscript document** ด้วย Aspose.Page for Java แล้ว ลองทดลองใช้ฟอนต์, สี, และสไตล์การขอบที่หลากหลายเพื่อสร้างผลลัพธ์ PostScript ที่ดูเป็นมืออาชีพ

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}