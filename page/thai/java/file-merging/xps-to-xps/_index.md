---
date: 2025-11-29
description: เรียนรู้วิธีผสานไฟล์ XPS ใน Java อย่างราบรื่นด้วย Aspose.Page ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อการจัดการเอกสารที่มีประสิทธิภาพและเสริมทักษะการพัฒนา
  Java ของคุณ
language: th
linktitle: Convert XPS to XPS in Java
second_title: Aspose.Page Java API
title: วิธีรวมไฟล์ XPS ใน Java ด้วย Aspose.Page
url: /java/file-merging/xps-to-xps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการรวมไฟล์ XPS ใน Java ด้วย Aspose.Page

การรวมเอกสาร XPS เป็นงานประจำเมื่อคุณต้องการรวมรายงาน การนำเสนอ หรือคอลเลกชันใด ๆ ของไฟล์ XPS ให้เป็นแพ็คเกจเดียวที่ง่ายต่อการแชร์ ในบทแนะนำนี้คุณจะได้เรียนรู้ **how to merge xps** ด้วย Aspose.Page for Java API พร้อมคำอธิบายที่ชัดเจน เคล็ดลับจากโลกจริง และโค้ดสแนปช็อตที่พร้อมรัน

## คำตอบด่วน
- **ไลบรารีที่จัดการการรวม XPS คืออะไร?** Aspose.Page for Java.  
- **การทำงานใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับการรวมพื้นฐาน.  
- **ต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** ใช่ – มีไลเซนส์ทดลองชั่วคราวจาก Aspose.  
- **ฉันสามารถรวมไฟล์ที่มีจำนวนหน้าต่างกันได้หรือไม่?** แน่นอน; Aspose.Page จะรวมเอกสาร XPS ที่ถูกต้องใด ๆ.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 ขึ้นไป (แนะนำ JDK 11+).

## การรวมไฟล์ XPS คืออะไร?
XPS (XML Paper Specification) เป็นรูปแบบเอกสารแบบจัดวางคงที่ของ Microsoft การรวมไฟล์ XPS หมายถึงการต่อเนื่องหลายเอกสาร XPS ให้เป็นไฟล์เดียวโดยคงการจัดวาง หน้า ฟอนต์ และกราฟิกของแต่ละหน้าไว้

## ทำไมต้องรวมไฟล์ XPS ใน Java?
- **Automation:** สร้างรายงานเดียวจากหลายโมดูลโดยไม่ต้องทำด้วยตนเอง.  
- **Consistency:** รักษาความเที่ยงตรงของภาพตามต้นฉบับของหน้า XPS.  
- **Performance:** ลดจำนวนไฟล์ที่ต้องโอนหรือจัดเก็บ.  
- **Cross‑platform:** Java ทำให้คุณสามารถรันการรวมบนเซิร์ฟเวอร์ Windows, Linux หรือ macOS.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Java Development Kit (JDK):** ตรวจสอบว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.Page for Java:** ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page for Java จาก [Aspose website](https://purchase.aspose.com/buy).  
- **Integrated Development Environment (IDE):** เลือก IDE ที่คุณชอบ; ตัวเลือกยอดนิยมได้แก่ Eclipse, IntelliJ IDEA หรือ NetBeans.

ตอนนี้ทุกอย่างพร้อมแล้ว, มาดำเนินการกับโค้ดกัน

## นำเข้าแพ็กเกจ
ในโปรเจกต์ Java ของคุณ ให้เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นเพื่อใช้ Aspose.Page for Java เพิ่มบรรทัดต่อไปนี้ที่ส่วนต้นของไฟล์ Java ของคุณ:

```java
import java.io.FileOutputStream;

import com.aspose.xps.XpsDocument;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
สร้างโปรเจกต์ Java ใหม่ใน IDE ที่เลือกและเพิ่มไฟล์ JAR ของ Aspose.Page ไปยัง build path ของโปรเจกต์ เพื่อให้คอมไพเลอร์สามารถหาคลาส `XpsDocument` ได้

## ขั้นตอนที่ 2: เริ่มต้น XPS Output Stream
ตั้งค่า output stream สำหรับไฟล์ XPS ที่จะรวม ระบุไดเรกทอรีที่คุณต้องการบันทึกไฟล์ที่รวมไว้

```java
String dataDir = "Your Document Directory";
FileOutputStream outStream = new FileOutputStream(dataDir + "mergedXPSfiles.xps");
```

> **เคล็ดลับ:** ใช้เส้นทางแบบ absolute ระหว่างการพัฒนาเพื่อหลีกเลี่ยง `FileNotFoundException` จากนั้นเปลี่ยนเป็นเส้นทางแบบ relative สำหรับการใช้งานจริง.

## ขั้นตอนที่ 3: โหลดไฟล์ XPS แรก
โหลดไฟล์ XPS แรกที่ทำหน้าที่เป็นฐานสำหรับการรวม

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

คุณสมบัติของเอกสารแรก (เช่น ขนาดหน้าและการวางแนว) จะกลายเป็นค่าเริ่มต้นสำหรับไฟล์ที่รวมสุดท้าย

## ขั้นตอนที่ 4: สร้างอาเรย์ของไฟล์ XPS
เตรียมอาเรย์ของไฟล์ XPS ที่คุณต้องการรวมกับไฟล์แรก

```java
String[] filesForMerge = new String[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

คุณสามารถเพิ่มเส้นทางไฟล์ได้ตามต้องการ; อาเรย์สามารถสร้างแบบไดนามิกจากการลิสต์ไดเรกทอรีหากต้องการ

## ขั้นตอนที่ 5: รวมและบันทึก
ดำเนินการกระบวนการรวมและบันทึกผลลัพธ์ไปยัง output stream ที่ระบุ

```java
document.merge(filesForMerge, outStream);
```

หลังจากเรียกนี้, `mergedXPSfiles.xps` จะบรรจุทุกหน้าจาก `input.xps`, `Demo.xps`, และ `sample.xps` ตามลำดับที่คุณกำหนด

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **`FileNotFoundException`** | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบว่าโฟลเดอร์มีอยู่และใช้ backslashes คู่ (`\\`) บน Windows. |
| **License not found** | กำลังทำงานโดยไม่มีไลเซนส์ที่ถูกต้อง | ใช้ไลเซนส์ชั่วคราวจาก Aspose หรือซื้อไลเซนส์เต็มรูปแบบ. |
| **Merged file is empty** | Output stream ไม่ได้ flush/close | เรียก `outStream.close()` หลังจาก `document.merge(...)`. |
| **Mismatched page sizes** | ไฟล์ XPS ต้นทางมีขนาดต่างกัน | ใช้ `document.setPageSize(...)` ก่อนทำการรวมเพื่อบังคับขนาดที่สม่ำเสมอ. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถรวมไฟล์ XPS ที่มีขนาดต่างกันได้หรือไม่?**  
A: ได้. Aspose.Page จะทำการปรับขนาดหน้าต่าง ๆ ให้เป็นมาตรฐานโดยอัตโนมัติ, แต่คุณก็สามารถตั้งค่าขนาดหน้าที่กำหนดเองก่อนการรวมได้.

**Q: มีไลเซนส์ชั่วคราวสำหรับการทดสอบหรือไม่?**  
A: มี, คุณสามารถรับไลเซนส์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/) สำหรับการทดสอบ.

**Q: จะหาเอกสารรายละเอียดเพิ่มเติมได้จากที่ไหน?**  
A: ดูเอกสาร Aspose.Page for Java ที่ [here](https://reference.aspose.com/page/java/).

**Q: มีฟอรั่มชุมชนสำหรับการสนทนาเกี่ยวกับ Aspose.Page หรือไม่?**  
A: มี, เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อเข้าร่วมกับชุมชน.

**Q: จะซื้อไลบรารี Aspose.Page for Java ได้จากที่ไหน?**  
A: คุณสามารถซื้อไลบรารีได้จาก [here](https://purchase.aspose.com/buy).

## สรุป
คุณมีวิธีที่ครบถ้วนและพร้อมใช้งานในระดับ production สำหรับ **how to merge xps** ด้วย Aspose.Page for Java แล้ว ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถอัตโนมัติการรวมเอกสาร, ปรับปรุงประสิทธิภาพการทำงาน, และทำให้แอปพลิเคชัน Java ของคุณเบาและทรงพลัง

---

**อัปเดตล่าสุด:** 2025-11-29  
**ทดสอบกับ:** Aspose.Page for Java 24.12  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}