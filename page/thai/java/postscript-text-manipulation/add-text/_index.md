---
date: 2025-12-14
description: เรียนรู้วิธีตั้งค่าสีข้อความใน Java ด้วย Aspose.Page for Java, เพิ่มข้อความลงใน
  PostScript, และใช้การขีดเส้นข้อความเพื่อการจัดรูปแบบเอกสารที่หลากหลาย.
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

## คำนำ
ยินดีต้อนรับสู่คู่มือแบบขั้นตอนของเราเกี่ยวกับ **การตั้งค่าสีข้อความใน Java** ขณะทำงานกับไฟล์ PostScript ด้วย Aspose.Page for Java. Aspose.Page for Java เป็นไลบรารีที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถสร้างและ **สร้างไฟล์ postscript** เอกสาร, จัดการฟอนต์, และกำหนดสไตล์ข้อความได้อย่างแม่นยำ ในบทเรียนนี้คุณจะได้เรียนรู้วิธีเพิ่มข้อความ, เปลี่ยนสี, ปรับขนาด, และแม้กระทั่ง **ใช้เส้นขอบข้อความ** เพื่อให้ได้ลุคที่ดูเป็นมืออาชีพ

## คำตอบสั้น
- **ไลบรารีใดที่ให้ฉันตั้งค่าสีข้อความใน Java?** Aspose.Page for Java  
- **ฉันสามารถใช้ฟอนต์ระบบและฟอนต์ที่กำหนดเองได้หรือไม่?** ได้, ทั้งสองประเภทรองรับ  
- **จะเปลี่ยนขนาดข้อความอย่างไร?** โดยระบุขนาดฟอนต์เมื่อสร้าง `Font` หรือ `DrFont`  
- **สามารถทำเส้นขอบและเติมสีข้อความพร้อมกันได้หรือไม่?** แน่นอน – ใช้ `fillAndStrokeText`  
- **รูปแบบผลลัพธ์ของบทเรียนนี้คืออะไร?** เอกสาร PostScript (`.ps`)

## “ตั้งค่าสีข้อความใน Java” คืออะไร?
การตั้งค่าสีข้อความใน Java หมายถึงการกำหนดอ็อบเจกต์ `Color` ที่เอนจินการเรนเดอร์ (ในที่นี้คือ Aspose.Page) จะใช้เมื่อวาดอักขระลงบนหน้า การทำเช่นนี้เป็นสิ่งสำคัญสำหรับการสร้างเอกสารที่มีความแตกต่างทางสายตา, โดยเฉพาะเมื่อสร้าง **เอกสาร postscript** ด้วยโปรแกรมอัตโนมัติ

## ทำไมต้องใช้ Aspose.Page for Java?
- **ควบคุมเต็มรูปแบบ** การสร้าง PostScript โดยไม่ต้องพึ่งพาอินเตอร์พรีเตอร์ PostScript แบบดั้งเดิม  
- **รองรับฟอนต์ระบบและฟอนต์ภายนอก** ทำให้คุณสามารถฝังตัวอักษรใดก็ได้ที่ต้องการ  
- **API ที่ง่าย** สำหรับการเติม, กำหนดเส้นขอบ, และ **เติมพร้อมเส้นขอบข้อความ**, ให้ความยืดหยุ่นในการออกแบบ  
- **ข้ามแพลตฟอร์ม** – เขียนครั้งเดียว, รันได้ทุกที่ที่ Java ทำงาน

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จาก [หน้าดาวน์โหลด Aspose.Page for Java](https://releases.aspose.com/page/java/)  
- ฟอนต์ที่จำเป็นอยู่ในโฟลเดอร์ที่ระบุ รายละเอียดเพิ่มเติมอยู่ใน [เอกสาร Aspose.Page for Java](https://reference.aspose.com/page/java/)

## นำเข้าแพ็กเกจ
ในโปรเจก ของคุณ ให้นำเข้าแพ็กเกจที่จำเป็นสำหรับ Aspose.Page for Java:

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
แรกเริ่มเราจะสร้าง **เอกสาร PostScript** ใหม่และกำหนดค่าตัวเลือกการส่งออก

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
ต่อไปเราจะสาธิต **การตั้งค่าสีข้อความใน Java** ด้วยฟอนต์ที่มาจากระบบ

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **เคล็ดลับ:** เมธอด `fillText` จะใช้สีปัจจุบันโดยอัตโนมัติหากคุณไม่ได้ส่งอาร์กิวเมนต์ `Color`, ซึ่งค่าเริ่มต้นคือสีดำ

## ใช้ฟอนต์กำหนดเองและเปลี่ยนขนาดข้อความ
คุณยังสามารถ **เปลี่ยนขนาดข้อความ** และใช้ฟอนต์กำหนดเองที่เก็บไว้ในโฟลเดอร์ฟอนต์ของคุณได้

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## การกำหนดเส้นขอบ (Stroke) ให้ข้อความ – ใช้ Stroke Text
การกำหนดเส้นขอบให้ข้อความทำให้ขอบคมชัด ที่นี่เราจะ **ใช้ stroke text** ด้วย `BasicStroke`

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

## การกำหนดเส้นขอบข้อความด้วยฟอนต์กำหนดเอง
เทคนิคเดียวกันทำงานได้กับฟอนต์ที่กำหนดเองเช่นกัน

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
สุดท้าย ปิดหน้าและเขียนไฟล์ลงดิสก์

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## ปัญหาที่พบบ่อย & วิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **ไม่พบฟอนต์** | ตรวจสอบให้แน่ใจว่าไฟล์ฟอนต์อยู่ใน `necessary_fonts` และเส้นทางโฟลเดอร์ได้ถูกเพิ่มอย่างถูกต้องผ่าน `options.setAdditionalFontsFolders` |
| **สีไม่แสดง** | ยืนยันว่าคุณเรียกเมธอด `fillText` หรือ `outlineText` ที่มีอาร์กิวเมนต์ `Color` |
| **เส้นขอบบางเกินไป** | เพิ่มความกว้างของ `BasicStroke` (เช่น `new BasicStroke(3)`) |
| **ไม่สามารถเปิดเอกสาร** | ตรวจสอบว่าไฟล์ `.ps` ที่สร้างมีนามสกุลถูกต้องและโปรแกรมดูของคุณรองรับ PostScript |

## คำถามที่พบบ่อย

**ถาม:** ฉันสามารถใช้ฟอนต์กำหนดเองกับ Aspose.Page for Java ได้หรือไม่?  
**ตอบ:** ได้, คุณสามารถใช้ฟอนต์กำหนดเองโดยระบุชื่อฟอนต์และขนาดในคลาส `DrFont`

**ถาม:** จะเปลี่ยนสีของข้อความอย่างไร?  
**ตอบ:** คุณสามารถตั้งค่าสีที่ต้องการโดยใช้คลาส `Color` เมื่อทำการเติมหรือกำหนดเส้นขอบข้อความ

**ถาม:** สามารถเพิ่มหลายหน้าในเอกสาร PostScript ได้หรือไม่?  
**ตอบ:** แน่นอน! คุณสามารถสร้างหลายหน้าโดยทำซ้ำขั้นตอนการสร้างเอกสารและบันทึก

**ถาม:** จุดประสงค์ของคลาส `ExternalFontCache` คืออะไร?  
**ตอบ:** `ExternalFontCache` ใช้เพื่อดึงฟอนต์กำหนดเอง, ทำให้ฟอนต์พร้อมใช้งานสำหรับการจัดการข้อความ

**ถาม:** สามารถกำหนดเส้นขอบที่แตกต่างให้กับข้อความที่มีเส้นขอบได้หรือไม่?  
**ตอบ:** ได้, คุณสามารถปรับความกว้างและสีของเส้นขอบโดยใช้คลาส `Stroke` และคลาส `Color` ตามลำดับ

## สรุป
ขอแสดงความยินดี! ตอนนี้คุณรู้วิธี **ตั้งค่าสีข้อความใน Java**, ปรับขนาดฟอนต์, **ใช้เส้นขอบข้อความ**, และ **สร้างไฟล์เอกสาร postscript** ด้วย Aspose.Page for Java แล้ว ลองทดลองใช้ฟอนต์, สี, และสไตล์เส้นขอบต่าง ๆ เพื่อสร้างผลลัพธ์ PostScript ที่ดูเป็นมืออาชีพ

---

**อัปเดตล่าสุด:** 2025-12-14  
**ทดสอบกับ:** Aspose.Page for Java 23.12 (ล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}