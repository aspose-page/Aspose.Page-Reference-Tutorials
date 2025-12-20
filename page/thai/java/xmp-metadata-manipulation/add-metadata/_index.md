---
date: 2025-12-20
description: เรียนรู้วิธีเพิ่มเมตาดาต้า XMP ลงในไฟล์ EPS ด้วยบทแนะนำ Aspose Page Java
  ทำตามคำแนะนำทีละขั้นตอนนี้เพื่อปรับปรุงการจัดการเอกสารของคุณ
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: บทเรียน Aspose Page Java – เพิ่มข้อมูลเมตา XMP ให้ไฟล์ EPS
url: /th/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มเมตาดาต้าใน XMP ด้วย Java

## Introduction
ใน **aspose page java tutorial** นี้ คุณจะได้เรียนรู้วิธีเพิ่มเมตาดาต้าให้กับเอกสารของคุณโดยการเพิ่มข้อมูล XMP ด้วย Java คู่มือแบบขั้นตอนนี้จะพาคุณผ่านการอ่านไฟล์ EPS ที่มีอยู่แล้ว การสกัดเมตาดาต้า XMP ของมัน และการบันทึกการเปลี่ยนแปลงกลับไปยังดิสก์ด้วยไลบรารี Aspose.Page for Java เมื่อจบบทเรียนคุณจะมีรูปแบบที่มั่นคงและนำกลับมาใช้ใหม่ได้สำหรับการทำงานกับ XMP ในกระบวนการทำงาน EPS ใด ๆ

## Quick Answers
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for Java  
- **ฉันสามารถเพิ่ม XMP ให้กับไฟล์ EPS ใดก็ได้หรือไม่?** ใช่ – API จะสร้างบล็อก XMP ใหม่หากยังไม่มี  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 และรุ่นต่อไป  
- **การดำเนินการใช้เวลานานเท่าไหร่?** โดยทั่วไปใช้เวลาน้อยกว่า 10 นาทีสำหรับการอัปเดตเมตาดาต้าพื้นฐาน  

## Aspose Page Java Tutorial Overview
บทแนะนำนี้แสดงขั้นตอนหลักที่คุณต้องทำเพื่อจัดการเมตาดาต้า XMP ในไฟล์ EPS การเข้าใจขั้นตอนเหล่านี้จะช่วยให้คุณรวมการจัดการเมตาดาต้าเข้าไปในไพป์ไลน์การประมวลผลเอกสารที่ใหญ่ขึ้น ปรับปรุงการค้นหา และปฏิบัติตามมาตรฐานอุตสาหกรรมสำหรับการจัดการสินทรัพย์ดิจิทัล  

## Prerequisites
ก่อนที่เราจะเริ่มบทแนะนำ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/page/java/)  
- ไฟล์ EPS ที่คุณต้องการแก้ไข  

## Import Packages
ก่อนอื่น ให้นำเข้าแพ็กเกจที่จำเป็นเข้าสู่โปรแกรม Java ของคุณ:

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

แทนที่ `"Your Document Directory"` ด้วยเส้นทางจริงที่เก็บเอกสารของคุณ  

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

## Conclusion
ใน **aspose page java tutorial** นี้ เราได้สำรวจวิธีเพิ่มเมตาดาต้า XMP ให้กับไฟล์ EPS ด้วยไลบรารี Aspose.Page for Java API ที่ทรงพลังนี้ทำให้คุณสามารถจัดการเมตาดาต้าเอกสารได้โดยโปรแกรม ช่วยให้คุณจัดระเบียบและค้นหาสินทรัพย์ได้อย่างมีประสิทธิภาพ  

## Frequently Asked Questions

**Q: Aspose.Page for Java ใช้ได้ฟรีหรือไม่?**  
A: Aspose.Page for Java เป็นผลิตภัณฑ์เชิงพาณิชย์ คุณสามารถสำรวจคุณลักษณะของมันผ่านการทดลองใช้ฟรี [ที่นี่](https://releases.aspose.com/)  

**Q: จะหาเอกสารอ้างอิงสำหรับ Aspose.Page for Java ได้จากที่ไหน?**  
A: เอกสารอ้างอิงพร้อมให้บริการ [ที่นี่](https://reference.aspose.com/page/java/)  

**Q: จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: คุณสามารถรับไลเซนส์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)  

**Q: Aspose.Page for Java รองรับรูปแบบไฟล์อะไรบ้าง?**  
A: Aspose.Page for Java รองรับหลายรูปแบบ รวมถึง EPS, PDF, และ XPS  

**Q: สามารถซื้อ Aspose.Page for Java ได้หรือไม่?**  
A: ได้ คุณสามารถซื้อ Aspose.Page for Java [ที่นี่](https://purchase.aspose.com/buy)  

**Q: จะจัดการกับไฟล์ EPS ขนาดใหญ่เมื่อเพิ่มเมตาดาต้าอย่างไร?**  
A: ประมวลผลไฟล์ในรูปแบบสตรีมมิ่ง (ตามที่แสดง) เพื่อรักษาการใช้หน่วยความจำให้ต่ำและปิดสตรีมโดยเร็ว  

**Q: สามารถแก้ไขฟิลด์ XMP ที่มีอยู่แทนการอ่านอย่างเดียวได้หรือไม่?**  
A: แน่นอน – คุณสามารถใช้ `xmp.put(key, value)` เพื่ออัปเดตหรือเพิ่มรายการใหม่ก่อนบันทึก  

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}