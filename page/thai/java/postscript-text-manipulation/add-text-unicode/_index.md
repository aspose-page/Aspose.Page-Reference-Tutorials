---
date: 2025-12-17
description: เรียนรู้วิธีเพิ่มข้อความ Unicode ใน Java PostScript ด้วย Aspose.Page
  – คู่มือขั้นตอนต่อขั้นตอนในการเพิ่มสตริง Unicode อย่างง่ายดาย.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: วิธีเพิ่มข้อความ Unicode ใน Java PostScript ด้วย Aspose.Page
url: /th/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มข้อความ Unicode ใน Java PostScript ด้วย Aspose.Page

## คำแนะนำ
หากคุณกำลังสงสัย **วิธีเพิ่ม Unicode** ลงในกระบวนการทำงาน PostScript (หรือ XPS) ที่ใช้ Java คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะอธิบายขั้นตอนที่จำเป็นเพื่อฝังสตริง Unicode ด้วยไลบรารี Aspose.Page สำหรับ Java เมื่อจบคู่มือคุณจะสามารถแทรกข้อความในภาษาต่าง ๆ — ภาษาอาหรับ, จีน, อีโมจิ หรืออะไรก็ตาม — ลงในผลลัพธ์ PostScript ของคุณได้โดยตรง

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for Java  
- **ฉันสามารถเพิ่มสคริปต์จากขวาไปซ้ายได้หรือไม่?** ได้, ตั้งค่า Bidi level ตามที่แสดงในโค้ด  
- **ต้องใช้ไลเซนส์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีได้สำหรับการทดสอบ; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการผลิต  
- **IDE ที่เหมาะสมที่สุดคืออะไร?** IDE ใดก็ได้ที่รองรับ Java (IntelliJ IDEA, Eclipse, NetBeans)  
- **โค้ดนี้ทำงานข้ามแพลตฟอร์มหรือไม่?** แน่นอน — สามารถรันบน Windows, macOS หรือ Linux ได้

## “วิธีเพิ่ม Unicode” หมายถึงอะไรในบริบทของ PostScript?
การเพิ่ม Unicode หมายถึงการแทรกอักขระที่มีรหัสจุดเกินเหนือช่วง ASCII พื้นฐาน Aspose.Page จัดการรายละเอียดการเข้ารหัสระดับต่ำให้คุณโฟกัสที่เนื้อหาข้อความและตำแหน่งการแสดงผลได้เลย

## ทำไมต้องใช้ Aspose.Page สำหรับข้อความ Unicode?
- **รองรับ Unicode อย่างเต็มรูปแบบ** – จัดการสคริปต์ซับซ้อน, ตัวเชื่อม, และภาษาที่เขียนจากขวาไปซ้าย  
- **ไม่มีการพึ่งพาไลบรารีภายนอก** – ไม่ต้องจัดการไฟล์ฟอนต์ด้วยตนเอง; API ทำงานกับฟอนต์ระบบได้  
- **API ที่ใช้งานง่าย** – เพียงไม่กี่คำเรียกใช้ก็สามารถเรนเดอร์ข้อความหลายภาษาได้

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดเตรียมสิ่งต่อไปนี้ให้พร้อม:

1. **Java Development Kit (JDK)** – เวอร์ชันล่าสุดใดก็ได้ (8 หรือใหม่กว่า)  
2. **Aspose.Page for Java** – ดาวน์โหลดและติดตั้งไลบรารีจาก [download link](https://releases.aspose.com/page/java/)  
3. **IDE ที่คุณชอบ** – IntelliJ IDEA, Eclipse หรือ IDE Java ใด ๆ ที่คุณถนัด

## นำเข้าแพ็กเกจ
เพิ่มคลาส Aspose.Page ที่จำเป็นลงในไฟล์ซอร์ส Java ของคุณ:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
สร้างโปรเจกต์ Java ใหม่, เพิ่มไฟล์ JAR ของ Aspose.Page ไปยังเส้นทางการสร้าง, และสร้างโฟลเดอร์ที่จะใช้เก็บไฟล์ XPS ที่สร้างขึ้น โฟลเดอร์นี้จะอ้างอิงต่อไปในโค้ดเป็น `dataDir`

## ขั้นตอนที่ 2: เริ่มต้นเอกสาร XPS
สร้างเอกสาร XPS เปล่าที่จะใช้เก็บเนื้อหา:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 3: เพิ่มข้อความ Unicode
ต่อไปเราจะเพิ่มสตริง Unicode จริง ตัวอย่างด้านล่างเขียนประโยคกลับด้าน “AVAJ rof SPX.esopsA” ซึ่งเป็นอักขระ ASCII เท่านั้น, แต่คุณสามารถแทนที่ด้วยข้อความ Unicode ใดก็ได้ (เช่น ภาษาอาหรับ “مرحبا” หรือภาษาจีน “你好”)

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **เคล็ดลับ:** เพื่อให้ภาษาที่เขียนจากขวาไปซ้ายแสดงผลอย่างถูกต้อง, ตั้งค่า `glyphs.setBidiLevel(1);` สำหรับสคริปต์จากซ้ายไปขวา สามารถละบรรทัดนี้ได้

## ขั้นตอนที่ 4: บันทึกเอกสาร
บันทึกไฟล์ XPS ลงดิสก์:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

หลังจากรันโปรแกรมแล้ว, เปิดไฟล์ `AddEncodingText_out.xps` ด้วยโปรแกรมดู XPS ใดก็ได้เพื่อดูข้อความ Unicode ที่แสดงตามพิกัดที่กำหนด

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| ข้อความแสดงเป็นสี่เหลี่ยม | ไม่พบฟอนต์หรือฟอนต์ไม่รองรับอักขระนั้น | ใช้ฟอนต์ที่มี glyph ที่ต้องการ (เช่น “Arial Unicode MS”) |
| ข้อความจากขวาไปซ้ายแสดงจากซ้ายไปขวา | ไม่ได้ตั้งค่า Bidi level | เรียก `glyphs.setBidiLevel(1);` |
| ไฟล์ไม่ถูกบันทึก | เส้นทาง `dataDir` ไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ตรวจสอบให้แน่ใจว่าโฟลเดอร์มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน |

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?
Aspose.Page ถูกออกแบบมาสำหรับ Java เป็นหลัก, แต่ Aspose มีไลบรารีสำหรับหลายภาษาโปรแกรม

### มีรุ่นทดลองฟรีหรือไม่?
ใช่, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.Page [ที่นี่](https://releases.aspose.com/)

### จะหาแหล่งสนับสนุนและการสนทนาเกี่ยวกับ Aspose.Page ได้จากที่ไหน?
เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนและการสนทนา

### จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page ได้อย่างไร?
คุณสามารถขอรับไลเซนส์ชั่วคราว [ที่นี่](https://purchase.aspose.com/temporary-license/)

### ฟอนต์สไตล์ที่รองรับใน Aspose.Page มีอะไรบ้าง?
Aspose.Page รองรับสไตล์ฟอนต์เช่น Regular, Bold, Italic, และ BoldItalic

## สรุป
คุณได้เรียนรู้ **วิธีเพิ่มข้อความ Unicode** ลงในเอกสาร Java PostScript (XPS) ด้วย Aspose.Page แล้ว ความสามารถนี้เปิดประตูสู่การสร้างรายงานหลายภาษา, ใบแจ้งหนี้สากล, หรือสถานการณ์ใด ๆ ที่ต้องการอักขระที่ไม่ใช่ ASCII อย่าลังเลที่จะสำรวจฟีเจอร์เพิ่มเติมเช่น การหมุนข้อความ, เส้นทางคลิป, หรือการฝังฟอนต์แบบกำหนดเอง — รายละเอียดเพิ่มเติมอยู่ใน [documentation](https://reference.aspose.com/page/java/) อย่างเป็นทางการ

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
