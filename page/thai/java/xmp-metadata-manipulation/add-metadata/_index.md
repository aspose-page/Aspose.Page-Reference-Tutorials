---
date: 2026-03-08
description: เรียนรู้วิธีเพิ่มเมตาดาต้า XMP ลงในไฟล์ EPS ด้วยบทแนะนำ Aspose Page สำหรับ
  Java. ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อยกระดับการจัดการเอกสารของคุณ.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: บทเรียน Aspose Page Java – การเพิ่มข้อมูลเมตา XMP ในไฟล์ EPS
url: /th/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่ม Metadata ใน XMP ด้วย Java

## Introduction
ใน **aspose page java tutorial** นี้ คุณจะได้เรียนรู้วิธีการเพิ่มข้อมูลเมตาดาต้า XMP ให้กับเอกสารของคุณโดยใช้ Java คำแนะนำแบบขั้นตอนนี้จะพาคุณผ่านการอ่านไฟล์ EPS ที่มีอยู่แล้ว การสกัดข้อมูลเมตาดาต้า XMP และการบันทึกการเปลี่ยนแปลงกลับไปยังดิสก์ด้วยไลบรารี Aspose.Page for Java เมื่อจบบทเรียนแล้ว คุณจะมีรูปแบบการทำงานที่มั่นคงและนำกลับมาใช้ใหม่ได้สำหรับการทำงานกับ XMP ในกระบวนการ EPS ใด ๆ

## Quick Answers
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java  
- **สามารถเพิ่ม XMP ให้ไฟล์ EPS ใดก็ได้หรือไม่?** ได้ – API จะสร้างบล็อก XMP ใหม่หากยังไม่มีอยู่  
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน Java ใด?** Java 8 ขึ้นไป  
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับการอัปเดตเมตาดาต้าเบื้องต้น

## What is Aspose Page Java?
Aspose.Page for Java (ที่มักเรียกว่า **aspose page java**) เป็น API ประสิทธิภาพสูงที่ช่วยให้นักพัฒนาสร้าง แก้ไข และแปลงไฟล์ PostScript และ EPS ได้โดยไม่ต้องพึ่งซอฟต์แวร์ Adobe อีกต่อไป นอกจากนี้ยังให้การเข้าถึงเมตาดาต้า XMP อย่างเต็มรูปแบบ ทำให้คุณสามารถฝังข้อมูลที่ค้นหาได้โดยตรงลงในไฟล์กราฟิกของคุณ

## Why add XMP metadata to EPS files?
การฝังเมตาดาต้า XMP ช่วยปรับปรุงการจัดการสินทรัพย์ การค้นหา และการปฏิบัติตามมาตรฐานอุตสาหกรรม เช่น IPTC และ Dublin Core เมื่อคุณเพิ่มฟิลด์เช่น creator, title หรือ creation date ระบบ downstream (เช่น DAM, เครื่องมือค้นหา หรือเวิร์กโฟลว์การพิมพ์) จะสามารถทำดัชนีและจัดระเบียบสินทรัพย์ EPS ของคุณโดยอัตโนมัติ

## Aspose Page Java Tutorial Overview
บทเรียนนี้แสดงขั้นตอนหลักที่คุณต้องทำเพื่อจัดการเมตาดาต้า XMP ในไฟล์ EPS การเข้าใจขั้นตอนเหล่านี้จะช่วยให้คุณรวมการจัดการเมตาดาต้าเข้าไปใน pipeline การประมวลผลเอกสารที่ใหญ่ขึ้น เพิ่มความสามารถในการค้นหา และปฏิบัติตามมาตรฐานอุตสาหกรรมสำหรับการจัดการสินทรัพย์ดิจิทัล

## Prerequisites
ก่อนที่เราจะเริ่มบทเรียน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/java/)  
- ไฟล์ EPS ที่ต้องการแก้ไข

## Import Packages
แรกสุด ให้ทำการ import แพ็กเกจที่จำเป็นเข้าสู่โปรแกรม Java ของคุณ:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Step 1: Get XMP Metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

แทนที่ `"Your Document Directory"` ด้วยพาธจริงที่เก็บเอกสารของคุณ

## Step 2: Retrieve CreatorTool Value
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Step 3: Retrieve CreateDate Value
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Step 4: Retrieve Title Value
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Step 5: Retrieve Format Value
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Step 6: Retrieve Creator Value
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Step 7: Retrieve MetadataDate Value
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Step 8: Save Document with New XMP Metadata
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

สุดท้าย อย่าลืมปิดสตรีม EPS อินพุต:

```java
// Close input EPS stream
psStream.close();
```

ตอนนี้คุณได้เพิ่มเมตาดาต้าให้กับไฟล์ EPS ของคุณสำเร็จโดยใช้ Aspose.Page for Java แล้ว!

## Common Issues and Solutions
- **Missing XMP block** – API จะสร้างบล็อกให้โดยอัตโนมัติ แต่ต้องตรวจสอบว่าไฟล์ EPS ไม่เสียหาย  
- **Unsupported characters** – ค่าของ XMP ต้องเป็น UTF‑8; หลีกเลี่ยงสัญลักษณ์ที่ไม่เป็นมาตรฐานในฟิลด์เมตาดาต้า  
- **Large EPS files** – ประมวลผลไฟล์โดยใช้สตรีม (ตามที่แสดง) เพื่อรักษาการใช้หน่วยความจำให้ต่ำ และควรปิดสตรีมในบล็อก `finally`

## Conclusion
ใน **aspose page java tutorial** นี้ เราได้สำรวจวิธีการเพิ่มเมตาดาต้า XMP ให้กับไฟล์ EPS ด้วยไลบรารี Aspose.Page for Java API ที่ทรงพลังนี้ช่วยให้คุณจัดการเมตาดาต้าเอกสารได้โดยอัตโนมัติ ช่วยให้สินทรัพย์ของคุณเป็นระเบียบและค้นหาได้ง่ายขึ้น

## Frequently Asked Questions

**Q: Aspose.Page for Java ใช้ได้ฟรีหรือไม่?**  
A: Aspose.Page for Java เป็นผลิตภัณฑ์เชิงพาณิชย์ คุณสามารถทดลองใช้ฟีเจอร์ต่าง ๆ ผ่านเวอร์ชันทดลองฟรี [ที่นี่](https://releases.aspose.com/).

**Q: จะหาเอกสารประกอบสำหรับ Aspose.Page for Java ได้จากที่ไหน?**  
A: เอกสารประกอบพร้อมใช้งาน [ที่นี่](https://reference.aspose.com/page/java/).

**Q: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: คุณสามารถรับลิขสิทธิ์ชั่วคราว [ที่นี่](https://purchase.aspose.com/temporary-license/).

**Q: Aspose.Page for Java รองรับรูปแบบไฟล์อะไรบ้าง?**  
A: Aspose.Page for Java รองรับหลายรูปแบบ รวมถึง EPS, PDF, และ XPS

**Q: สามารถซื้อ Aspose.Page for Java ได้หรือไม่?**  
A: ได้, คุณสามารถซื้อ Aspose.Page for Java [ที่นี่](https://purchase.aspose.com/buy).

**Q: จะจัดการไฟล์ EPS ขนาดใหญ่เมื่อเพิ่มเมตาดาต้าอย่างไร?**  
A: ประมวลผลไฟล์ในรูปแบบสตรีม (ตามตัวอย่าง) เพื่อรักษาการใช้หน่วยความจำให้ต่ำและปิดสตรีมโดยเร็ว

**Q: สามารถแก้ไขฟิลด์ XMP ที่มีอยู่แล้วแทนการอ่านอย่างเดียวได้หรือไม่?**  
A: แน่นอน – คุณสามารถใช้ `xmp.put(key, value)` เพื่ออัปเดตหรือเพิ่มรายการใหม่ก่อนบันทึก

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}