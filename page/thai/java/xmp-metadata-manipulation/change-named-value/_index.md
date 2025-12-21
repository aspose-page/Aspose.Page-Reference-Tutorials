---
date: 2025-12-21
description: บทเรียน Aspose.Page XMP – เรียนรู้วิธีแก้ไขเมตาดาต้า XMP ในไฟล์ EPS ด้วย
  Aspose.Page สำหรับ Java อย่างชัดเจนและเป็นขั้นตอนทีละขั้นตอน
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: บทแนะนำ Aspose.Page XMP – การเปลี่ยนค่า Named Value ใน XMP ด้วย Java
url: /th/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose page xmp tutorial – การเปลี่ยนค่า Named Value ใน XMP ด้วย Java

ในกระบวนการทำงานกับเอกสารสมัยใหม่, **Aspose.Page for Java** ทำให้การอ่าน, แก้ไข, และเขียนเมตาดาต้า XMP ภายในไฟล์ EPS เป็นเรื่องง่าย. **aspose page xmp tutorial** นี้จะพาคุณผ่านขั้นตอนการเปลี่ยนค่า Named Value ในแพ็กเก็ต XMP, เพื่อให้เมตาดาต้าเอกสารของคุณแม่นยำและค้นหาได้ง่าย. ไม่ว่าคุณจะอัปเดตขนาดหน้า, ข้อมูลผู้เขียน, หรือแท็กที่กำหนดเอง, ขั้นตอนด้านล่างจะแสดงวิธีทำใน Java อย่างชัดเจน.

## Quick Answers
- **บทเรียนนี้ครอบคลุมอะไร?** การเปลี่ยนค่า XMP ที่มีชื่อในไฟล์ EPS โดยใช้ Aspose.Page for Java.  
- **ต้องใช้เวอร์ชันไลบรารีใด?** เวอร์ชัน Aspose.Page for Java ใดก็ได้ที่เป็นรุ่นล่าสุด (API มีความเสถียรมาหลายปี).  
- **ต้องมีลิขสิทธิ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ชั่วคราวหรือเต็มสำหรับการใช้งานจริง; เวอร์ชันทดลองฟรีใช้ได้สำหรับการทดสอบ.  
- **ใช้เวลานำไปใช้เท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับนักพัฒนาที่คุ้นเคยกับ Java I/O.  
- **สามารถใช้กับรูปแบบไฟล์อื่นได้หรือไม่?** API ของ XMP ยังพร้อมใช้งานสำหรับ PDF, SVG, และรูปแบบอื่นที่สนับสนุนโดย Aspose.Page.

## What is XMP metadata?
XMP (Extensible Metadata Platform) เป็นรูปแบบมาตรฐานสำหรับฝังเมตาดาต้าที่มีความละเอียดสูง—เช่น ผู้สร้าง, ชื่อเรื่อง, และคุณสมบัติกำหนดเอง—โดยตรงภายในไฟล์. ในเอกสาร EPS, XMP อยู่คู่กับคอมเมนต์ PostScript แบบดั้งเดิม, ทำให้แอปพลิเคชันสามารถอ่านและแก้ไขเมตาดาต้าโดยไม่กระทบต่อเนื้อหาภาพ.

## Why use Aspose.Page for Java to edit XMP?
- **Full control** – เข้าถึงคุณสมบัติ XMP ใดก็ได้, รวมถึงโครงสร้างกำหนดเอง, โดยไม่ต้องพาร์ส XML ดิบ.  
- **Cross‑format consistency** – API เดียวกันทำงานกับ EPS, PDF, และ SVG, ช่วยลดความซับซ้อนของโค้ด.  
- **No external dependencies** – ไลบรารี Java แท้, ไม่ต้องใช้โค้ดเนทีฟหรือพาร์สเซอร์เพิ่มเติม.  
- **Robust error handling** – การตรวจสอบในตัวรับประกันว่า EPS ที่ได้ยังคงเป็นไปตามมาตรฐาน.

## Introduction
Aspose.Page for Java เป็นไลบรารี Java ที่แข็งแกร่งสำหรับการจัดการและประมวลผลไฟล์ EPS. เมื่อพูดถึงการจัดการเมตาดาต้า XMP ภายในไฟล์เหล่านี้, Aspose.Page มอบชุดคุณสมบัติที่ครบถ้วนให้กับนักพัฒนา. ในบทเรียนนี้เราจะมุ่งเน้นที่การเปลี่ยนค่า Named Value ใน XMP, พร้อมคำแนะนำที่ชัดเจนและกระชับสำหรับนักพัฒนาที่ต้องการเพิ่มศักยภาพการประมวลผลเอกสารของตน.

## Prerequisites
ก่อนเริ่มบทเรียน, โปรดตรวจสอบว่าคุณมีเงื่อนไขต่อไปนี้พร้อมใช้งาน:
1. **Java Development Environment** – ตรวจสอบว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนเครื่องของคุณแล้ว.  
2. **Aspose.Page for Java Library** – ดาวน์โหลดและผสานรวมไลบรารี Aspose.Page for Java เข้ากับโปรเจกต์ของคุณ. คุณสามารถหาไลบรารีและเอกสารรายละเอียดได้ [ที่นี่](https://reference.aspose.com/page/java/).  
3. **Sample EPS File** – เตรียมไฟล์ EPS ตัวอย่างสำหรับการทดลอง. หากคุณไม่มีไฟล์, สามารถใช้ไฟล์ตัวอย่างที่ชื่อ **"xmp4.eps."**

## Import Packages
เพื่อเริ่มกระบวนการ, ให้นำเข้าแพ็กเกจที่จำเป็นในโค้ด Java ของคุณ. แพ็กเกจเหล่านี้สำคัญต่อการโต้ตอบกับ Aspose.Page for Java. เพิ่มบรรทัดต่อไปนี้ที่ส่วนหัวของไฟล์ Java ของคุณ:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

ตอนนี้เราจะอธิบายขั้นตอนการเปลี่ยนค่า Named Value ใน XMP ด้วย Aspose.Page for Java อย่างละเอียด:

## Step 1: Initialize Input EPS File Stream
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Step 2: Initialize PsDocument
```java
PsDocument document = new PsDocument(psStream);
```

## Step 3: Get XMP Metadata
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Step 4: Set New Value in XMP
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Step 5: Initialize Output EPS File Stream
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Step 6: Save Document with Changed XMP Metadata
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Step 7: Close Input EPS Stream
```java
// Close input EPS stream
psStream.close();
```

คำแนะนำแบบขั้นตอนนี้ช่วยให้คุณเปลี่ยนค่า Named Value ใน XMP อย่างเป็นระบบโดยใช้ Aspose.Page for Java. เพียงทำตามขั้นตอนเหล่านี้, คุณก็สามารถผสานฟังก์ชันนี้เข้าไปในแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น.

## Common Issues and Solutions
- **FileNotFoundException** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและไฟล์ `xmp4.eps` มีอยู่จริง.  
- **LicenseException** – หากพบข้อผิดพลาดเกี่ยวกับลิขสิทธิ์, ให้แน่ใจว่าได้โหลดไฟล์ลิขสิทธิ์ Aspose.Page ที่ถูกต้องก่อนสร้าง `PsDocument`.  
- **Metadata Not Updated** – หลังจากบันทึก, เปิด EPS ที่ได้ในโปรแกรมดูเมตาดาต้า (เช่น Adobe Bridge) เพื่อตรวจสอบว่าค่าใหม่ปรากฏหรือไม่.

## Conclusion
สรุปได้ว่า Aspose.Page for Java ทำให้การทำงานกับเมตาดาต้า XMP ในไฟล์ EPS ง่ายขึ้น. บทเรียนนี้ได้ให้ความรู้แก่คุณในการเปลี่ยนค่า Named Value ใน XMP อย่างมีประสิทธิภาพ, เพิ่มศักยภาพการประมวลผลเอกสารของคุณ.

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page รองรับหลักการสำหรับ Java เป็นหลัก, แต่ Aspose มีไลบรารีที่คล้ายกันสำหรับหลายภาษาโปรแกรมอื่น.

### Is there a free trial available for Aspose.Page for Java?
ใช่, คุณสามารถทดลองใช้ Aspose.Page for Java ฟรีได้ [ที่นี่](https://releases.aspose.com/).

### Where can I find additional support and discussions about Aspose.Page for Java?
เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชนและการสนทนาต่าง ๆ.

### How can I obtain a temporary license for Aspose.Page for Java?
คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

### Where can I purchase Aspose.Page for Java?
หากต้องการซื้อ Aspose.Page for Java, ไปที่ [purchase page](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose