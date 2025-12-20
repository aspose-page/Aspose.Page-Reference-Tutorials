---
date: 2025-12-20
description: เรียนรู้วิธีเพิ่มเนมสเปซ XMP ในไฟล์ EPS ด้วย Aspose.Page สำหรับ Java
  ในบทแนะนำ aspose.page xmp ที่ครอบคลุมนี้
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: บทเรียน aspose.page xmp – เพิ่มเนมสเปซใน XMP ด้วย Java
url: /th/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บทแนะนำ aspose.page xmp – เพิ่ม Namespace ใน XMP ด้วย Java

## Introduction

หากคุณต้องการแก้ไขหรือเพิ่มความสมบูรณ์ให้กับเมตาดาต้าของไฟล์ EPS, **aspose.page xmp tutorial** จะสาธิตให้คุณเห็นอย่างชัดเจน **วิธีเพิ่ม XMP namespace** ด้วย Java ในคู่มือนี้เราจะเดินผ่านแต่ละขั้นตอน—เริ่มจากการโหลดเอกสาร EPS, ลงทะเบียน namespace แบบกำหนดเอง, แทรก property ใหม่, และสุดท้ายบันทึกไฟล์ที่อัปเดตแล้ว เมื่อเสร็จสิ้นคุณจะได้รูปแบบที่ชัดเจนและนำกลับมาใช้ใหม่ได้สำหรับการทำงานกับเมตาดาต้า XMP ในโครงการ Java ที่ใช้ Aspose.Page ใด ๆ

## Quick Answers
- **What is the primary goal?** เพิ่ม Namespace และ property XMP แบบกำหนดเองลงในไฟล์ EPS.  
- **Which library is required?** Aspose.Page for Java.  
- **Do I need a license for testing?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **How many code changes are needed?** มีเพียงห้าชิ้นส่วนโค้ดสั้น—หนึ่งส่วนต่อแต่ละขั้นตอน.  
- **Can I reuse this pattern for other namespaces?** ได้ เพียงเปลี่ยน prefix และ URI ในการเรียก `registerNamespaceURI`.

## What is an XMP Namespace?

XMP (Extensible Metadata Platform) namespace คือ ตัวระบุที่ไม่ซ้ำกันซึ่งจัดกลุ่ม property เมตาดาต้าที่เกี่ยวข้องภายใต้ URI ร่วม การลงทะเบียน namespace ทำให้คุณสามารถเก็บข้อมูลแบบกำหนดเอง—เช่นแท็กเฉพาะของบริษัท—โดยไม่ชนกับมาตรฐานที่มีอยู่

## Why Use Aspose.Page for XMP Manipulation?

- **Full control** over EPS and PDF metadata without needing Adobe tools.  
- **Automatic creation** of XMP blocks when none exist, based on PS comments.  
- **Cross‑platform Java support**, making it easy to integrate into existing pipelines.

## Prerequisites

- Aspose.Page for Java: ตรวจสอบว่าคุณได้ติดตั้งไลบรารีแล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/java/).  
- Java Development Environment: ตั้งค่าสภาพแวดล้อม Java บนระบบของคุณ.  
- Document File: มีไฟล์ EPS ที่มีเมตาดาต้า XMP หากไม่มีเมตาดาต้า XMP ไลบรารีจะสร้างขึ้นโดยอิงจากคอมเมนต์เมตาดาต้า PS.

## Import Packages

เพื่อเริ่มต้น ให้นำเข้าแพ็กเกจที่จำเป็นเข้าสู่โครงการ Java ของคุณ:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Step 1: Get XMP Metadata

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### Why this matters
การดึงอ็อบเจ็กต์ `XmpMetadata` ให้คุณได้ตัวจับเมตาดาต้าของเอกสารแบบเรียลไทม์ ทำให้คุณสามารถอ่าน, แก้ไข หรือขยายข้อมูลก่อนบันทึกได้

## Step 2: Register New Namespace *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### Explanation
เมธอด `registerNamespaceURI` ทำการแมป prefix สั้น (`tmp`) ไปยัง URI เต็มขั้นตอนนี้สำคัญสำหรับการดำเนินการต่อไป เพราะ property ของ XMP ต้องมีการระบุ namespace ที่ลงทะเบียนแล้ว

## Step 3: Add New Property

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### What’s happening?
ที่นี่เราสร้าง property แบบกำหนดเองชื่อ `tmp:newKey` และกำหนดค่าเป็น `"NewValue"` คุณสามารถเปลี่ยนคีย์และค่าตามที่ตรงกับตรรกะธุรกิจของคุณได้

## Step 4: Save Document

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

### Tip
ควรห่อการเรียก `save` ไว้ในบล็อก `try/finally` (หรือใช้ try‑with‑resources) เพื่อรับประกันว่าการสตรีมเอาต์พุตจะถูกปิด แม้จะเกิดข้อยกเว้นก็ตาม

## Step 5: Close Streams

```java
// Close input EPS stream
psStream.close();
```

### Best practice
การปิดสตรีมอินพุตจะปล่อยไฟล์แฮนด์เดิลอย่างรวดเร็ว ป้องกันปัญหาไฟล์ล็อกบนระบบ Windows

## Common Issues and Solutions

| Issue | Likely Cause | Fix |
|-------|--------------|-----|
| No XMP block appears after saving | Original EPS lacked XMP and comments were insufficient | Ensure the EPS contains standard PS comments (`%%Creator`, `%%Title`, etc.) or manually create an empty `XmpMetadata` object before registering a namespace. |
| `registerNamespaceURI` throws an exception | Prefix already used | Choose a unique prefix or check existing namespaces via `xmp.getRegisteredNamespaces()`. |
| Saved file is corrupted | Output stream not flushed | Use `try‑with‑resources` or explicitly call `outPsStream.flush()` before closing. |

## Conclusion

โดยทำตาม **aspose.page xmp tutorial** นี้ คุณจะได้วิธีการทำซ้ำสำหรับการเพิ่ม namespace และ property แบบกำหนดเองลงในไฟล์ EPS ด้วย Aspose.Page for Java ความสามารถนี้เปิดประตูสู่กลยุทธ์เมตาดาต้าที่ลึกซึ้งกว่า—ไม่ว่าจะเป็นการฝังตัวระบุเวิร์กโฟลว์, แท็กเฉพาะของบริษัท, หรือข้อมูลการบูรณาการสำหรับระบบ downstream

## FAQs

### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page primarily supports Java, but there are versions available for other languages such as .NET.

### Is there a free trial available?
Yes, you can explore a free trial [here](https://releases.aspose.com/).

### Where can I find comprehensive documentation?
Refer to the documentation [here](https://reference.aspose.com/page/java/).

### How can I obtain a temporary license?
You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Are there community forums for Aspose.Page?
Yes, you can engage with the community on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

---

**อัปเดตล่าสุด:** 2025-12-20  
**ทดสอบด้วย:** Aspose.Page for Java 23.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}