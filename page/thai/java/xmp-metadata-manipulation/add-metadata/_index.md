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

## การแนะนำ
ใน **aspose page java Tutorial** คุณจะได้เพิ่มเมตาดาต้าให้กับเอกสารของคุณโดยส่วนใหญ่เป็นข้อมูล XMP ด้วย Java ส่วนประกอบแบบขั้นตอนเพื่อให้คุณผ่านไฟล์ EPS ส่วนประกอบแล้วการสกัดเมดาต้า XMP ของมันและการวิจัยการดูดซึมของประสิทธิภาพด้วยไลบรารี Aspose.Page สำหรับ Java คุณจะมีรูปแบบใหม่และนำกลับมาใช้ใหม่ได้สำหรับ XMP การทำงาน EPS ใด ๆ

## คำตอบด่วน
- **ไลบรารีต้องการอะไร?** Aspose.Page สำหรับ Java
- **ฉันจะต้องส่ง XMP ไปยังไฟล์ EPS เพื่อดูหรือไม่** ตรวจสอบ – API สร้างบล็อก XMP ย้อนหลังหากผู้ใช้
- ** ปรับเปลี่ยนไลเซนส์สำหรับการพัฒนาหรือไม่?** เอกสารฟรีสามารถใช้ได้สำหรับพื้นที่; ควบคุมไลส์เซนส์โดยตรงจริง
- ** รองรับ Java รองรับอะไร?** Java8 และรุ่นต่อไป
- ** การดำเนินการทำได้เท่าไหร่?** ใช้เวลา 10 นาทีสำหรับเมตาดาต้าพื้นฐาน

## ภาพรวมการสอน Java Aspose Page
บทแนะนำนี้แสดงขั้นตอนหลักที่ต้องดำเนินการเพื่อจัดการกับเมตาดาต้า XMP ในไฟล์ EPS การเข้าใจขั้นตอนที่จำเป็นรวมการจัดการเมตาดาต้า...

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มแนะนำการพูดคุยของคุณอีกครั้ง:
- ความรู้พื้นฐานเกี่ยวกับ Java
- ไลบรารี Aspose.Page สำหรับ Java ดาวน์โหลดแล้วดาวน์โหลดดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/page/java/)
- รองรับ EPS ที่คุณต้องการแก้ไข

## แพคเกจนำเข้า
รับประทานอาหารที่นำเข้าและอาหารในโปรแกรม Java ของคุณ:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## ขั้นตอนที่ 1: รับข้อมูลเมตา XMP
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

## ขั้นตอนที่ 2: ดึงค่า CreatorTool
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## ขั้นตอนที่ 3: ดึงค่า CreateDate
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## ขั้นตอนที่ 4: ดึงค่า Title
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## ขั้นตอนที่ 5: ดึงค่า Format
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## ขั้นตอนที่ 6: ดึงค่า Creator
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## ขั้นตอนที่ 7: ดึงค่า MetadataDate
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## ขั้นตอนที่ 8: บันทึกเอกสารด้วยข้อมูลเมตา XMP ใหม่
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

## บทสรุป
ใน **aspose page java Tutorial** มักจะสำรวจวิธีเพิ่มเมตาดาต้า XMP ให้กับไฟล์ EPS ด้วยไลบรารี Aspose.Page สำหรับ Java API ของเบราว์เซอร์นี้ทำให้สามารถจัดการเมตาดาต้าเอกสารได้โปรแกรมที่ช่วยให้เราจัดระเบียบและค้นหาได้อย่างมีประสิทธิภาพอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

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

**อัปเดตล่าสุด:** 2025-12-20
**ทดสอบกับ:** Aspose.Page for Java 24.12 (เวอร์ชันล่าสุด)
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}