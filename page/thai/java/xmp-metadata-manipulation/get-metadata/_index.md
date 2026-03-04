---
date: 2025-12-21
description: เรียนรู้วิธีอ่านข้อมูลเมตา XMP ด้วย Java และ Aspose.Page คู่มือขั้นตอนนี้จะแสดงวิธีอ่าน
  XMP ของรูปแบบเอกสารและสกัดคุณสมบัติสำคัญออกมา
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: วิธีอ่านข้อมูลเมตาดาต้า XMP ด้วย Java – คู่มือ Aspose.Page
url: /th/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ดึงข้อมูล Metadata จาก XMP ด้วย Java

## วิธีอ่าน Metadata ของ XMP ด้วย Java

ยินดีต้อนรับสู่บทแนะนำแบบขั้นตอนที่แสดง **วิธีอ่าน XMP** metadata ด้วย Java และไลบรารี Aspose.Page  XMP (Extensible Metadata Platform) เป็นมาตรฐานที่ได้รับการยอมรับอย่างกว้างขวางสำหรับการฝัง metadata ที่มีความละเอียดสูงไว้ในเอกสาร  เมื่อคุณอ่านคู่มือนี้เสร็จแล้ว คุณจะสามารถอ่าน XMP ของรูปแบบเอกสาร ดึงข้อมูลผู้สร้าง เวลา สร้างภาพขนาดย่อ และอื่น ๆ อีกมากมาย — ช่วยให้คุณสร้างโซลูชันการวิเคราะห์เอกสารที่ฉลาดขึ้นได้

## คำตอบสั้น ๆ
- **“วิธีอ่าน xmp” หมายถึงอะไร?** หมายถึงการสกัด metadata ของ XMP จากไฟล์โดยอัตโนมัติ  
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java (ดาวน์โหลดได้จากหน้า Aspose)  
- **ต้องมีลิขสิทธิ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ชั่วคราวหรือเต็มสำหรับการใช้งานในผลิตภัณฑ์; มีรุ่นทดลองฟรีให้ใช้  
- **รองรับเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า  
- **สามารถอ่าน XMP จากรูปแบบอื่นได้หรือไม่?** ได้, Aspose.Page รองรับ EPS, PDF และรูปภาพหลายประเภทที่ฝัง XMP

## ข้อกำหนดเบื้องต้น
ก่อนจะลงมือเขียนโค้ด โปรดตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK)** – ติดตั้ง Java 8+ และตั้งค่าให้พร้อมใช้งานบนเครื่องของคุณ  
- **Aspose.Page for Java** – ดาวน์โหลดไลบรารีจากเว็บไซต์อย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/page/java/)  
- ไฟล์ EPS ที่มี metadata ของ XMP (เช่น `xmp1.eps`)  

## นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ ให้ import แพ็กเกจที่จำเป็น:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## ขั้นตอนที่ 1: เริ่มต้น Input EPS File Stream
กำหนดพาธไปยังโฟลเดอร์เอกสารของคุณและสร้างสตรีมไฟล์ EPS เข้า:
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## ขั้นตอนที่ 2: ดึง XMP Metadata
ดึง XMP metadata จากไฟล์ EPS หากไฟล์ไม่มี XMP metadata ระบบจะสร้างใหม่โดยใช้ค่าจากคอมเมนต์ PS:
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## ขั้นตอนที่ 3: สกัดข้อมูล CreatorTool
ตรวจสอบและพิมพ์ค่า "CreatorTool" จาก XMP metadata:
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## ขั้นตอนที่ 4: สกัดข้อมูล CreateDate
ตรวจสอบและพิมพ์ค่า "CreateDate" จาก XMP metadata:
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## ขั้นตอนที่ 5: ดึงความกว้างของ Thumbnail
หากมี thumbnail อยู่ ให้สกัดและพิมพ์ความกว้างของ thumbnail ตัวแรก:
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## ขั้นตอนที่ 6: สกัดข้อมูล Format
ตรวจสอบและพิมพ์ค่า "format" จาก XMP metadata:
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## ขั้นตอนที่ 7: ดึง DocumentID
ตรวจสอบและพิมพ์ค่า "DocumentID" จาก XMP metadata:
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## ทำไมเรื่องนี้ถึงสำคัญ
การอ่าน XMP metadata ทำให้คุณสามารถค้นพบแหล่งที่มาของเอกสาร วันที่สร้าง และคุณลักษณะสำคัญอื่น ๆ ได้โดยไม่ต้องเปิดไฟล์ในโปรแกรมดูเอกสาร  สิ่งนี้มีประโยชน์อย่างยิ่งสำหรับการประมวลผลเป็นชุด ระบบจัดการเนื้อหา และไหลงานสินทรัพย์ดิจิทัลที่อาศัย metadata ในการทำดัชนีและการค้นหา

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ไม่มี XMP:** บางไฟล์ EPS อาจไม่มี XMP. การเรียก `getXmpMetadata()` จะสร้างชุดข้อมูลขั้นต่ำจากคอมเมนต์ PS ที่มีอยู่, แต่คุณจะไม่ได้รับ metadata ครบถ้วนหากไม่มีการฝังไว้  
- **อาเรย์ Thumbnail:** คีย์ `xmp:Thumbnails` สามารถเก็บหลายรายการได้ ตัวอย่างนี้สกัดเฉพาะรายการแรก; หากต้องการทั้งหมดให้วนลูปอาเรย์  
- **ความเข้าใจ Namespace:** คีย์ XMP ใช้ namespace (เช่น `xmp:`, `dc:`) ตรวจสอบให้แน่ใจว่าอ้างอิงชื่อคีย์อย่างถูกต้อง มิฉะนั้น `containsKey` จะคืนค่า false  

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?
ได้, Aspose.Page รองรับหลายภาษา รวมถึง Java, .NET และอื่น ๆ ดูรายละเอียดใน [เอกสาร](https://reference.aspose.com/page/java/)  

### มีรุ่นทดลองฟรีสำหรับ Aspose.Page for Java หรือไม่?
มี, คุณสามารถเข้าถึงรุ่นทดลองฟรีได้ [ที่นี่](https://releases.aspose.com/)  

### จะหาการสนับสนุนสำหรับ Aspose.Page for Java ได้จากที่ไหน?
เยี่ยมชม [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชน  

### จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?
คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)  

### มีแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Page for Java หรือไม่?
สำรวจ [เอกสารเต็มรูปแบบ](https://reference.aspose.com/page/java/) และดาวน์โหลดไลบรารีได้ [ที่นี่](https://releases.aspose.com/page/java/)  

## คำถามเพิ่มเติม
**ถาม: วิธีนี้ทำงานกับไฟล์ PDF ที่มี XMP หรือไม่?**  
ตอบ: ใช่, Aspose.Page สามารถอ่าน XMP จาก PDF, EPS และรูปภาพหลายประเภทได้  

**ถาม: ฉันสามารถแก้ไข XMP metadata หลังจากอ่านได้หรือไม่?**  
ตอบ: แน่นอน, วัตถุ `XmpMetadata` สามารถแก้ไขได้; คุณสามารถเพิ่ม, ปรับปรุง หรือเอาคีย์ออกแล้วบันทึกเอกสารต่อไป  

**ถาม: มีวิธีดึงภาพ thumbnail ทั้งหมด ไม่ใช่แค่ขนาดหรือไม่?**  
ตอบ: คุณสามารถดึงข้อมูลไบนารีจากคุณสมบัติ `xmpGImg:data` ของแต่ละรายการ thumbnail แล้วบันทึกเป็นไฟล์ได้  

## สรุป
คุณได้เรียนรู้ **วิธีอ่าน XMP** metadata ด้วย Java และ Aspose.Page แล้ว  ด้วยขั้นตอนเหล่านี้คุณสามารถสกัดเครื่องมือผู้สร้าง, เวลา, thumbnail, ข้อมูลรูปแบบ, และ DocumentID — ให้คุณเห็นข้อมูลเมตาที่ฝังอยู่ในไฟล์ EPS ของคุณอย่างครบถ้วน  อย่าลังเลที่จะทดลองใช้ namespace ของ XMP เพิ่มเติมเพื่อดึงข้อมูลที่ลึกซึ้งยิ่งขึ้นสำหรับแอปพลิเคชันของคุณ

---

**อัปเดตล่าสุด:** 2025-12-21  
**ทดสอบกับ:** Aspose.Page for Java 24.12 (ล่าสุด)  
**ผู้เขียน:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
