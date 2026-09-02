---
date: 2026-05-05
description: เรียนรู้วิธีเพิ่มค่า XMP ที่มีชื่อให้กับไฟล์ EPS โดยใช้ Aspose.Page สำหรับ
  Java – คู่มือแบบขั้นตอนพร้อมตัวอย่างโค้ด.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: เพิ่มค่าแบบมีชื่อใน XMP ด้วย Java
second_title: Aspose.Page Java API
title: วิธีเพิ่มค่า XMP ที่กำหนดชื่อในไฟล์ EPS ด้วย Java
url: /th/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มค่า Named Value ในเมตาดาต้า XMP ด้วย Java

## บทนำ
ในการพัฒนา Java สมัยใหม่ การเรียนรู้ **วิธีการเพิ่มเมตาดาต้า XMP** ภายในไฟล์ EPS เป็นสิ่งสำคัญสำหรับการรักษาที่มาของเอกสารและเพิ่มการค้นหาได้ง่ายขึ้น ด้วย **asp** (Aspose.Page for Java) คุณสามารถแทรกค่า named value ที่กำหนดเองลงในแพ็กเกจ XMP ได้อย่างง่ายดาย บทแนะนำนี้จะพาคุณผ่านขั้นตอนที่ชัดเจน—พร้อมตัวอย่างโค้ด—เพื่อให้คุณเริ่มเพิ่มเมตาดาต้า XMP ให้กับเอกสาร EPS ของคุณได้ทันที

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.Page for Java (asp)  
- **ประเภทไฟล์ที่มุ่งเป้าหมายคืออะไร?** ไฟล์ EPS ที่มีเมตาดาต้า XMP  
- **กรณีการใช้งานหลักคืออะไร?** เพิ่มค่า named values (เช่น ขีดจำกัดขนาดหน้า) ไปยัง XMP  
- **ข้อกำหนดเบื้องต้นคืออะไร?** JDK 8+ และไลบรารี Aspose.Page for Java  
- **ระยะเวลาการทำงานโดยทั่วไปคือเท่าไหร่?** 5–10 นาทีหลังจากตั้งค่าไลบรารีแล้ว  

## asp คืออะไร?
*asp* คือรูปแบบสั้นของ **Aspose** ซึ่งเป็นชุดของ API สำหรับ .NET และ Java ที่ทำให้การประมวลผลเอกสารง่ายขึ้น ส่วนประกอบ Aspose.Page for Java ช่วยให้คุณสร้าง แก้ไข และแปลงไฟล์ PostScript และ EPS พร้อมให้การเข้าถึงเมตาดาต้าของไฟล์โดยโปรแกรมได้อย่างเต็มที่ รวมถึง XMP

## ทำไมต้องเพิ่ม named values ไปยังเมตาดาต้า XMP?
- **ความเป็นมิตรต่อเครื่องมือค้นหา:** แท็กที่กำหนดเองช่วยเพิ่มการค้นพบ  
- **การอัตโนมัติของเวิร์กโฟลว์:** เครื่องมือ downstream สามารถอ่านค่าที่กำหนดของคุณเพื่อทำการตัดสินใจ  
- **การปฏิบัติตามกฎระเบียบ:** ฝังข้อมูลตามกฎหมายโดยตรงลงในแพ็กเกจเอกสาร  

## ทำไมเรื่องนี้ถึงสำคัญ
การเพิ่ม named values ไปยัง XMP ทำให้คุณสามารถเก็บคู่คีย์‑ค่าแบบ任意 ที่สามารถอ่านได้โดยไม่ต้องพาร์สไฟล์ EPS ทั้งหมด ความสามารถนี้มีคุณค่ามากในสายการผลิตการเผยแพร่อัตโนมัติ ระบบจัดการสินทรัพย์ดิจิทัล และเวิร์กโฟลว์ที่ขับเคลื่อนด้วยการปฏิบัติตามกฎระเบียบที่เมตาดาต้ากำหนดการทำงานของ downstream

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ควรตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Java Development Kit (JDK):** JDK รุ่นล่าสุด (8 หรือสูงกว่า) ที่ติดตั้งบนเครื่องของคุณ  
- **ไลบรารี Aspose.Page for Java:** ดาวน์โหลดจาก [download link](https://releases.aspose.com/page/java/) อย่างเป็นทางการ แล้วเพิ่มไฟล์ JAR ไปยัง classpath ของโปรเจกต์  
- **ไฟล์ EPS** ที่มีเมตาดาต้า XMP อยู่แล้วหรือจะถูกสร้างโดยอัตโนมัติ  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจ Java ที่จำเป็น การนำเข้าต่าง ๆ นี้จะทำให้คุณเข้าถึงสตรีมไฟล์ โมเดลเอกสาร EPS และคลาสจัดการ XMP

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## วิธีเพิ่ม XMP Named Value ในไฟล์ EPS ด้วย Java
ด้านล่างเป็นขั้นตอนสั้น ๆ ที่จัดเป็นลำดับเลขเพื่อแสดง **วิธีการเพิ่ม XMP** named values ไปยังเอกสาร EPS อย่างชัดเจน

### ขั้นตอนที่ 1: เริ่มต้นสตรีมไฟล์ EPS อินพุต
โหลดไฟล์ EPS ต้นฉบับเข้าสู่ `FileInputStream` สตรีมนี้จะส่งเอกสารไปยัง API ของ Aspose

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **เคล็ดลับ:** ทำให้ตัวแปร `dataDir` สามารถกำหนดค่าได้ เพื่อให้โค้ดเดียวทำงานได้ในหลายสภาพแวดล้อม

### ขั้นตอนที่ 2: ดึงเมตาดาต้า XMP
ดึงแพ็กเกจ XMP ที่มีอยู่ หากไฟล์ EPS ไม่มี Aspose จะสร้างอ็อบเจกต์ XMP ใหม่โดยใช้ข้อมูลจากคอมเมนต์ PS

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### ขั้นตอนที่ 3: เพิ่ม Named Value
แทรกค่า named value ที่กำหนดเองลงในโครงสร้าง XMP ในตัวอย่างนี้เราจะเพิ่มคีย์ใหม่ภายใต้เนมสเปซ `xmpTPg:MaxPageSize`

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **ทำไมเรื่องนี้สำคัญ:** Named values ช่วยให้คุณเก็บคู่คีย์‑ค่าแบบ任意 ที่แอปพลิเคชัน downstream สามารถอ่านได้โดยไม่ต้องพาร์สเอกสารทั้งหมด

### ขั้นตอนที่ 4: เริ่มต้นสตรีมไฟล์ EPS เอาต์พุต
เตรียม `FileOutputStream` ที่จะบันทึกไฟล์ EPS ที่แก้ไขแล้ว

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### ขั้นตอนที่ 5: บันทึกเอกสาร
บันทึกการเปลี่ยนแปลง การเรียก `save` จะเขียนแพ็กเกจ XMP ที่อัปเดตกลับไปยังไฟล์ EPS

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### ขั้นตอนที่ 6: ปิดสตรีมไฟล์ EPS อินพุต
ปล่อยตัวจัดการไฟล์เดิมเพื่อป้องกันการรั่วของทรัพยากร

```java
psStream.close();
```

โดยทำตามหกขั้นตอนนี้ คุณได้ **เพิ่ม named value ในเมตาดาต้า XMP** อย่างสำเร็จโดยใช้ **asp** (Aspose.Page for Java)

## ปัญหาทั่วไปและวิธีแก้
| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `xmp` | ไฟล์ EPS ไม่มี XMP และ Aspose ไม่สามารถสร้างได้ | ตรวจสอบว่า EPS มีคอมเมนต์ PS อย่างน้อยหนึ่งรายการ หรือสร้างอ็อบเจกต์ `XmpMetadata` ใหม่ด้วยตนเอง |
| Output file is empty | สตรีมเอาต์พุตไม่ได้ flush/close | ตรวจสอบว่าได้เรียก `outPsStream.close()` ในบล็อก `finally` (ตามตัวอย่าง) |
| Duplicate key error | เพิ่ม named value เดียวกันสองครั้ง | ตรวจสอบว่าคีย์มีอยู่แล้วหรือยังด้วย `xmp.containsNamedValue(...)` ก่อนทำการเพิ่ม |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Page for Java กับไลบรารี Java อื่น ๆ ได้หรือไม่?**  
A: ใช่, Aspose.Page for Java ถูกออกแบบให้ทำงานร่วมกับไลบรารี Java อื่น ๆ อย่างราบรื่น ให้ความยืดหยุ่นในสภาพแวดล้อมการพัฒนาของคุณ

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
A: มี, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.Page for Java ได้ที่ [here](https://releases.aspose.com/).

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: เยี่ยมชม [this link](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวสำหรับ Aspose.Page for Java.

**Q: ฉันจะหา tutorial และตัวอย่างเพิ่มเติมสำหรับ Aspose.Page for Java ได้จากที่ไหน?**  
A: สำรวจ [documentation](https://reference.aspose.com/page/java/) เพื่อดู tutorial และตัวอย่างอย่างครบถ้วน

**Q: Aspose.Page for Java เหมาะกับโครงการขนาดใหญ่หรือไม่?**  
A: แน่นอน, Aspose.Page for Java ถูกออกแบบให้จัดการโครงการขนาดใหญ่ได้อย่างมีประสิทธิภาพ พร้อมความสามารถในการจัดการเอกสารที่แข็งแกร่ง

## สรุป
ในคู่มือนี้ เราได้แสดงให้เห็นว่า **asp** (Aspose.Page for Java) ทำให้การ **เพิ่ม named values ไปยังเมตาดาต้า XMP** ภายในไฟล์ EPS เป็นเรื่องง่าย ด้วยขั้นตอนข้างต้น คุณสามารถเพิ่มเมตาดาต้าตามต้องการให้กับเอกสารของคุณ ปรับปรุงการค้นหา และเปิดใช้งานการประมวลผล downstream ที่ชาญฉลาดยิ่งขึ้น

---

**Last Updated:** 2026-05-05  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}