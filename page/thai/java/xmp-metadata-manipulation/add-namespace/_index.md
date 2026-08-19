---
date: 2026-03-08
description: เรียนรู้วิธีเพิ่มเนมสเปซ XMP ในไฟล์ EPS ด้วย Aspose.Page สำหรับ Java
  – คู่มือสอนแบบขั้นตอนต่อขั้นตอนเกี่ยวกับการเพิ่ม XMP และเนมสเปซ XMP สำหรับ Java.
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: วิธีเพิ่ม XMP Namespace ในไฟล์ EPS ด้วย Aspose.Page – บทเรียน Java
url: /th/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม XMP Namespace ในไฟล์ EPS ด้วย Aspose.Page – คู่มือ Java

หากคุณต้องการแก้ไขหรือเพิ่มข้อมูลเมตาของไฟล์ EPS คู่มือ **วิธีเพิ่ม xmp** นี้จะแสดงให้คุณเห็นขั้นตอนการเพิ่ม XMP namespace ด้วย Java และ Aspose.Page อย่างชัดเจน เมื่อจบคู่มือคุณจะได้รูปแบบที่นำกลับมาใช้ซ้ำได้สำหรับการแทรกเมตากำหนดเองลงในเอกสาร EPS ใด ๆ

## คำตอบสั้น ๆ
- **เป้าหมายหลักคืออะไร?** เพิ่ม XMP namespace และ property ที่กำหนดเองลงในไฟล์ EPS  
- **ต้องใช้ไลบรารีใด?** Aspose.Page for Java  
- **ต้องมีลิขสิทธิ์สำหรับการทดสอบหรือไม่?** สามารถใช้เวอร์ชันทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ต้องเปลี่ยนแปลงโค้ดกี่ส่วน?** มีเพียงห้าชุดโค้ดสั้น ๆ — หนึ่งชุดต่อขั้นตอน  
- **สามารถนำรูปแบบนี้ไปใช้กับ namespace อื่นได้หรือไม่?** ใช่ เพียงเปลี่ยน prefix และ URI ในการเรียก `registerNamespaceURI`

## XMP Namespace คืออะไร?

XMP (Extensible Metadata Platform) namespace คือ ตัวระบุที่ไม่ซ้ำกันซึ่งจัดกลุ่มคุณสมบัติเมตาที่เกี่ยวข้องไว้ภายใต้ URI ร่วม การลงทะเบียน namespace ทำให้คุณสามารถเก็บข้อมูลกำหนดเอง—เช่นแท็กเฉพาะบริษัท—โดยไม่ชนกับมาตรฐานที่มีอยู่

## ทำไมต้องใช้ Aspose.Page สำหรับการจัดการ XMP?

- **ควบคุมเต็มรูปแบบ** ของเมตา EPS และ PDF โดยไม่ต้องพึ่งเครื่องมือของ Adobe  
- **สร้างบล็อก XMP อัตโนมัติ** หากไม่มีอยู่แล้ว โดยอิงจากคอมเมนต์ PS  
- **รองรับหลายแพลตฟอร์มบน Java** ทำให้ง่ายต่อการรวมเข้ากับ pipeline ที่มีอยู่

## ข้อกำหนดเบื้องต้น

- Aspose.Page for Java: ตรวจสอบว่าคุณได้ติดตั้งไลบรารีแล้ว สามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/java/)  
- สภาพแวดล้อมการพัฒนา Java: ตั้งค่าระบบ Java บนเครื่องของคุณ  
- ไฟล์เอกสาร: มีไฟล์ EPS ที่มีเมตา XMP หากไฟล์ไม่มีเมตา XMP ไลบรารีจะสร้างให้โดยอิงจากคอมเมนต์เมตา PS

## นำเข้าแพ็กเกจ

เริ่มต้นโดยนำเข้าแพ็กเกจที่จำเป็นเข้าสู่โปรเจกต์ Java ของคุณ:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## ขั้นตอนที่ 1: รับ XMP Metadata

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### ทำไมจึงสำคัญ
การดึงอ็อบเจ็กต์ `XmpMetadata` จะให้คุณเข้าถึงเมตาของเอกสารแบบเรียลไทม์ ทำให้สามารถอ่าน, แก้ไข หรือขยายข้อมูลก่อนบันทึกได้

## ขั้นตอนที่ 2: ลงทะเบียน Namespace ใหม่ *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### คำอธิบาย
เมธอด `registerNamespaceURI` จะแมป prefix สั้น (`tmp`) ไปยัง URI เต็มขั้นตอนนี้จำเป็นสำหรับการดำเนินการต่อไป เพราะคุณสมบัติ XMP ต้องมี namespace ที่ลงทะเบียนแล้ว

## ขั้นตอนที่ 3: เพิ่ม Property ใหม่

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### เกิดอะไรขึ้น?
ที่นี่เราสร้าง property กำหนดเองชื่อ `tmp:newKey` และกำหนดค่าเป็น `"NewValue"` คุณสามารถเปลี่ยนคีย์และค่าให้ตรงกับตรรกะธุรกิจของคุณได้ตามต้องการ

## ขั้นตอนที่ 4: บันทึกเอกสาร

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### เคล็ดลับ
ควรห่อการเรียก `save` ไว้ในบล็อก `try/finally` (หรือใช้ try‑with‑resources) เพื่อรับประกันว่ากระแสเอาต์พุตจะถูกปิด แม้เกิดข้อยกเว้น

## ขั้นตอนที่ 5: ปิด Stream

```java
// Close input EPS stream
psStream.close();
```

### แนวทางที่ดีที่สุด
การปิด input stream จะปล่อยไฟล์แฮนด์เดิลอย่างรวดเร็ว ป้องกันปัญหาไฟล์ล็อคบนระบบ Windows

## ปัญหาที่พบบ่อยและวิธีแก้

| Issue | Likely Cause | Fix |
|-------|--------------|-----|
| No XMP block appears after saving | Original EPS lacked XMP and comments were insufficient | Ensure the EPS contains standard PS comments (`%%Creator`, `%%Title`, etc.) or manually create an empty `XmpMetadata` object before registering a namespace. |
| `registerNamespaceURI` throws an exception | Prefix already used | Choose a unique prefix or check existing namespaces via `xmp.getRegisteredNamespaces()`. |
| Saved file is corrupted | Output stream not flushed | Use `try‑with‑resources` or explicitly call `outPsStream.flush()` before closing. |

## สรุป

โดยทำตามคู่มือ **how to add xmp** นี้ คุณจะได้วิธีที่ทำซ้ำได้สำหรับการเพิ่ม namespace และ property กำหนดเองลงในไฟล์ EPS ด้วย Aspose.Page for Java ความสามารถนี้เปิดประตูสู่กลยุทธ์เมตาที่ลึกซึ้งยิ่งขึ้น — ไม่ว่าจะเป็นการฝังตัวระบุ workflow, แท็กเฉพาะบริษัท, หรือข้อมูลการบูรณาการสำหรับระบบ downstream

## คำถามที่พบบ่อย

### สามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?
Aspose.Page รองรับหลัก ๆ ที่ Java แต่ก็มีเวอร์ชันสำหรับภาษาอื่นเช่น .NET

### มีเวอร์ชันทดลองฟรีหรือไม่?
มี คุณสามารถสำรวจเวอร์ชันทดลองได้ [ที่นี่](https://releases.aspose.com/)

### จะหาเอกสารอ้างอิงอย่างครบถ้วนได้จากที่ไหน?
ดูเอกสารได้ที่ [นี่](https://reference.aspose.com/page/java/)

### จะขอรับลิขสิทธิ์ชั่วคราวได้อย่างไร?
คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

### มีฟอรั่มชุมชนสำหรับ Aspose.Page หรือไม่?
มี คุณสามารถเข้าร่วมสนทนากับชุมชนได้ที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39)

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Page for Java 24.10 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}