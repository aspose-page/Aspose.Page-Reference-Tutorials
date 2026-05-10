---
date: 2026-02-07
description: เรียนรู้วิธีตัดไฟล์ EPS ใน Java ด้วย Aspose.Page – คู่มือแบบขั้นตอนที่แสดงวิธีตัด
  EPS, ตัดภาพ EPS และตัดไฟล์ EPS ด้วยไลบรารี Aspose.Page
linktitle: Crop EPS File in Java
second_title: Aspose.Page Java API
title: วิธีตัดไฟล์ EPS ใน Java – คู่มือ Aspose.Page
url: /th/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการตัดไฟล์ EPS ใน Java – คู่มือขั้นตอนโดยละเอียดกับ Aspose.Page

## Introduction
หากคุณต้องการ **how to crop eps** ไฟล์โดยโปรแกรมในแอปพลิเคชัน Java คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมดของการตัดภาพ EPS ด้วยไลบรารี Aspose.Page for Java ที่ทรงพลัง เมื่อจบคู่มือคุณจะเข้าใจว่าทำไมการตัด EPS ถึงสำคัญ ดูโค้ดที่ต้องใช้ และพร้อมที่จะผสานโซลูชันนี้เข้ากับโปรเจกต์ของคุณ

## Quick Answers
- **ไลบรารีใดที่จัดการการตัด EPS ใน Java?** Aspose.Page for Java.  
- **ใช้เวลาประมาณเท่าไหร่ในการทำการตัดพื้นฐาน?** ประมาณ 5‑10 นาที.  
- **ต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีเพียงพอสำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน Java ที่รองรับ?** Java 8 และใหม่กว่า.  
- **ฉันสามารถกำหนด bounding box แบบกำหนดเองได้หรือไม่?** ได้ – คุณระบุพิกัดที่ต้องการ.

## What is EPS Cropping and Why Use It?
Encapsulated PostScript (EPS) เป็นรูปแบบกราฟิกที่เก็บภาพเวกเตอร์พร้อมกับ bounding box ที่กำหนดพื้นที่ที่มองเห็นได้ การตัดไฟล์ EPS หมายถึงการสร้าง bounding box ใหม่เพื่อให้เก็บเฉพาะส่วนที่คุณต้องการเท่านั้น ซึ่งมีประโยชน์เมื่อคุณต้องการลบขอบสีขาว, ดึงโลโก้ออก, หรือทำให้กราฟิกพอดีกับเลย์เอาต์ที่แคบลงโดยไม่ต้องสร้างไฟล์ต้นฉบับใหม่

## Why Crop EPS Files?
- **Reduce file size** – การตัดส่วนที่เป็นช่องว่างที่ไม่จำเป็นทำให้ไฟล์เบาขึ้น.  
- **Improve layout consistency** – EPS ที่ตัดเรียบร้อยจะผสานกับ PDF หรือรายงานได้ดียิ่งขึ้น.  
- **Automate batch processing** – เมื่อคุณรู้ **how to crop eps** คุณสามารถใช้ตรรกะเดียวกันกับไฟล์หลายสิบไฟล์ได้โดยอัตโนมัติ.

## Prerequisites
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:

- ไลบรารี **Aspose.Page for Java** ติดตั้งแล้ว – ดาวน์โหลดจากหน้าอย่างเป็นทางการ [here](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ.  
- **โฟลเดอร์** เพื่อเก็บไฟล์ EPS เข้า (`input.eps`) และไฟล์ที่ถูกตัด (`output_crop.eps`).

## Import Packages
ก่อนอื่นให้ import คลาส Java ที่จำเป็น ส่วนนี้จะคงเหมือนเดิมกับบทแนะนำต้นฉบับ:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## How to Crop EPS Image in Java
ด้านล่างเป็นขั้นตอนแบบละเอียด แต่ละขั้นจะอธิบายด้วยภาษาง่าย ๆ ก่อนโค้ดบล็อก เพื่อให้คุณเข้าใจ *ทำไม* เราถึงทำเช่นนั้น

### Step 1: Set Document Directory and Input Stream
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
ที่นี่เรากำหนดโฟลเดอร์ที่เก็บไฟล์ EPS ต้นฉบับและเปิดสตรีมเพื่ออ่านไฟล์

### Step 2: Initialize PsDocument Object
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
คลาส `PsDocument` แทนเอกสาร EPS ในหน่วยความจำ ทำให้เราสามารถสอบถามและจัดการคุณสมบัติต่าง ๆ ได้

### Step 3: Extract Initial Bounding Box
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
การดึง bounding box เดิมจะให้พิกัดของพื้นที่ที่มองเห็นอยู่ในขณะนั้น – เป็นข้อมูลที่มีประโยชน์สำหรับการตัดส่วนที่ต้องการ

### Step 4: Create Output Stream
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
เราเปิดสตรีมที่ไฟล์ EPS ที่ถูกตัดจะถูกเขียนลงไป

### Step 5: Define New Bounding Box and Crop
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
ระบุพิกัดสี่ค่า (lower‑left x, lower‑left y, upper‑right x, upper‑right y) ที่กำหนดพื้นที่ที่คุณต้องการเก็บ วิธี `cropEps` จะทำการตัดและเขียนผลลัพธ์ไปยัง `output_crop.eps`

## Common Issues and Solutions
- **พิกัดไม่ถูกต้อง:** EPS ใช้หน่วยจุด (1/72 นิ้ว). หากการตัดดูผิดพลาด ให้ตรวจสอบการแปลงหน่วยอีกครั้ง.  
- **ข้อผิดพลาดไฟล์ไม่พบ:** ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทางที่เหมาะสม (`/` หรือ `\`).  
- **ข้อยกเว้นไลเซนส์:** การรันโค้ดโดยไม่มีไลเซนส์ที่ถูกต้องอาจทำให้มีลายน้ำบนผลลัพธ์. ให้ใช้ไลเซนส์ชั่วคราวหรือถาวรก่อนการใช้งานจริง.

## Frequently Asked Questions

**Q: Aspose.Page รองรับ Java 8 หรือไม่?**  
A: Yes, Aspose.Page works with Java 8 and any later version.

**Q: ฉันสามารถใช้ Aspose.Page สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: Absolutely. A commercial license is required for production deployments. You can obtain one [here](https://purchase.aspose.com/buy).

**Q: ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนจากชุมชนได้จากที่ไหน?**  
A: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39) for discussions, code samples, and troubleshooting tips.

**Q: มีการทดลองใช้ฟรีสำหรับการทดสอบหรือไม่?**  
A: Yes, you can download a free trial of Aspose.Page from the releases page [here](https://releases.aspose.com/).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับการประเมินระยะสั้นได้อย่างไร?**  
A: A temporary license can be requested from the licensing portal [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
คุณตอนนี้รู้ **how to crop eps** ไฟล์ใน Java ด้วย Aspose.Page แล้ว โดยการกำหนด bounding box แบบกำหนดเองและเรียกใช้ `cropEps` คุณสามารถตัดขอบที่ไม่ต้องการหรือแยกส่วนเฉพาะของกราฟิก EPS ได้ด้วยเพียงไม่กี่บรรทัดของโค้ด ผสานสคริปต์นี้เข้ากับสายงานการประมวลผลเอกสารของคุณเพื่ออัตโนมัติการจัดการ EPS, **crop eps image** assets, และ **trim eps file** อย่างมีประสิทธิภาพ

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}