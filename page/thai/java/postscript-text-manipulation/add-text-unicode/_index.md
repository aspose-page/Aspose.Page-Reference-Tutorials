---
date: 2025-12-13
description: เรียนรู้วิธีเพิ่มข้อความในหน้า ASP ด้วย Java, ตั้งค่ารูปแบบฟอนต์ใน Java,
  และวิธีเพิ่มข้อความยูนิโค้ดโดยใช้ Aspose.Page. ตามคู่มือขั้นตอนโดยละเอียดของเรา.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: หน้า asp เพิ่มข้อความ – Unicode ใน Java PostScript
url: /th/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode in Java PostScript

## Introduction
หากคุณต้องการ **asp page add text** ในเวิร์กโฟลว์ Java PostScript พร้อมคงอักขระ Unicode ไว้ คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายขั้นตอนการเพิ่มข้อความ Unicode, การตั้งค่าแบบอักษร, และการบันทึกผลลัพธ์โดยใช้ **Aspose.Page for Java** เมื่อเสร็จสิ้นคุณจะเข้าใจวิธีตั้งค่า font style java และวิธีเพิ่มข้อความ unicode อย่างมีประสิทธิภาพในโปรเจกต์ของคุณ

## Quick Answers
- **ไลบรารีใดที่สามารถเพิ่มข้อความ Unicode ใน Java PostScript?** Aspose.Page for Java.  
- **เมธอดหลักที่ใช้เพิ่มข้อความคืออะไร?** `doc.addGlyphs(...)` พร้อมอ็อบเจ็กต์ `XpsGlyphs`.  
- **ต้องใช้ฟอนต์พิเศษสำหรับ Unicode หรือไม่?** ฟอนต์ TrueType/OpenType ใดก็ได้ที่รองรับโค้ดพอยท์ที่ต้องการ (เช่น Arial).  
- **สามารถเปลี่ยนสไตล์ฟอนต์ได้หรือไม่?** ได้, โดยใช้ `XpsFontStyle` (Regular, Bold, Italic, ฯลฯ).  
- **ต้องมีไลเซนส์สำหรับการใช้งานในโปรดักชันหรือไม่?** ต้องมีไลเซนส์ Aspose.Page ที่ถูกต้องสำหรับการใช้งานที่ไม่ใช่แบบทดลอง

## What is asp page add text?
`asp page add text` หมายถึงกระบวนการแทรกสตริงข้อความลงในเอกสาร PostScript หรือ XPS โดยใช้ Aspose.Page API API นี้ทำหน้าที่แอบสเตรดคำสั่ง PostScript ระดับต่ำ ให้คุณทำงานกับอ็อบเจ็กต์ระดับสูงอย่าง `XpsGlyphs`

## Why use Aspose.Page to set font style java and add Unicode text?
- **รองรับ Unicode อย่างเต็มรูปแบบ** – จัดการสคริปต์จากขวาไปซ้ายและ glyph ที่ซับซ้อน  
- **API ที่เรียบง่าย** – เรียกใช้บรรทัดเดียวเพื่อเพิ่มข้อความและกำหนดสไตล์  
- **ข้ามแพลตฟอร์ม** – ทำงานได้บนสภาพแวดล้อมที่รองรับ Java ทุกประเภท  
- **ไม่มีการพึ่งพาภายนอก** – ไม่ต้องใช้เอนจินการเรนเดอร์เพิ่มเติม

## Prerequisites
ก่อนที่เราจะเริ่มทำตามบทแนะนำนี้ โปรดตรวจสอบว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้พร้อมใช้งานแล้วหรือยัง:

1. **Java Development Kit (JDK)** – ตรวจสอบให้แน่ใจว่าได้ติดตั้ง Java บนเครื่องของคุณแล้ว  
2. **Aspose.Page for Java** – ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page จาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/page/java/)  
3. **Integrated Development Environment (IDE)** – เลือก IDE สำหรับ Java ที่คุณชื่นชอบ เช่น IntelliJ IDEA หรือ Eclipse

## Import Packages
ในโปรเจกต์ Java ของคุณ ให้นำเข้าแพ็กเกจที่จำเป็นสำหรับ Aspose.Page เพิ่มบรรทัดต่อไปนี้ลงในโค้ดของคุณ:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Step 1: Set Up Your Project
สร้างโปรเจกต์ Java ใหม่ใน IDE ของคุณและตั้งค่าโครงสร้างโปรเจกต์ ตรวจสอบให้แน่ใจว่าได้เพิ่มไลบรารี Aspose.Page เข้าไปใน dependencies ของโปรเจกต์

## Step 2: Initialize XPS Document
เริ่มต้นด้วยการสร้างเอกสาร XPS ใหม่ภายในโปรเจกต์ของคุณ:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Unicode Text
ต่อไปเราจะเพิ่มข้อความ Unicode ลงในเอกสาร XPS ของคุณโดยใช้ไลบรารี Aspose.Page ใช้โค้ดตัวอย่างต่อไปนี้:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

โค้ดส่วนนี้จะเพิ่มข้อความ Unicode **"AVAJ rof SPX.esopsA"** ลงในเอกสาร XPS ที่ตำแหน่งพิกัด (400, 200) พร้อมฟอนต์และสไตล์ที่กำหนด โปรดสังเกตว่าเมธอด `setBidiLevel(1)` ทำให้การเรนเดอร์จากขวาไปซ้ายทำงานอย่างถูกต้องสำหรับการแสดงผล Unicode

## Step 4: Save the Document
บันทึกเอกสาร XPS ที่ได้โดยใช้โค้ดต่อไปนี้:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Conclusion
ยินดีด้วย! คุณได้ทำ **asp page add text** และตั้งค่า font style ในสถานการณ์ Java PostScript ด้วย Aspose.Page สำเร็จแล้ว วิธีนี้ให้การควบคุมระดับละเอียดในการเรนเดอร์ Unicode และการจัดรูปแบบ ทำให้เหมาะสำหรับรายงาน, ใบแจ้งหนี้, และกราฟิกที่ต้องการการสนับสนุนหลายภาษา

สำรวจคุณลักษณะและความสามารถเพิ่มเติมของ Aspose.Page ได้ใน [เอกสาร](https://reference.aspose.com/page/java/)

## Frequently Asked Questions

**Q:** สามารถใช้ Aspose.Page for Java ร่วมกับภาษาโปรแกรมอื่นได้หรือไม่?  
**A:** Aspose.Page ถูกออกแบบมาสำหรับ Java เป็นหลัก แต่ Aspose มีไลบรารีสำหรับหลายภาษาโปรแกรม

**Q:** มีรุ่นทดลองฟรีหรือไม่?  
**A:** มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Page [ที่นี่](https://releases.aspose.com/)

**Q:** จะหาการสนับสนุนและการสนทนาเกี่ยวกับ Aspose.Page ได้จากที่ไหน?  
**A:** เยี่ยมชม [ฟอรัม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนและการสนทนา

**Q:** จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page ได้อย่างไร?  
**A:** คุณสามารถขอรับไลเซนส์ชั่วคราว [ที่นี่](https://purchase.aspose.com/temporary-license/)

**Q:** สไตล์ฟอนต์ที่มีใน Aspose.Page มีอะไรบ้าง?  
**A:** Aspose.Page รองรับสไตล์ฟอนต์เช่น Regular, Bold, Italic, และ BoldItalic

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-13  
**Tested With:** Aspose.Page for Java (latest)  
**Author:** Aspose  

---