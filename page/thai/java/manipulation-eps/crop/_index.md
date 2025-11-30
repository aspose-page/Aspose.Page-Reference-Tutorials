---
date: 2025-11-30
description: เรียนรู้วิธีการตัดไฟล์ EPS ใน Java ด้วย Aspose.Page – คู่มือทีละขั้นตอนที่ชัดเจนในการตัด
  EPS ด้วยไลบรารี Aspose.Page
language: th
linktitle: Crop EPS File in Java
second_title: Aspose.Page Java API
title: วิธีตัดครอปไฟล์ EPS ใน Java – คู่มือ Aspose.Page
url: /java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตัด (Crop) ไฟล์ EPS ใน Java – คู่มือแบบขั้นตอนโดยใช้ Aspose.Page

## Introduction
หากคุณต้องการ **how to crop eps** ไฟล์โดยอัตโนมัติในแอปพลิเคชัน Java คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านกระบวนการทั้งหมดของการตัดภาพ EPS ด้วยไลบรารี Aspose.Page for Java ที่ทรงพลัง เมื่อจบคู่มือคุณจะเข้าใจว่าทำไมการตัด EPS ถึงสำคัญ ดูโค้ดที่ต้องใช้ได้อย่างชัดเจน และพร้อมนำโซลูชันไปใช้ในโปรเจกต์ของคุณเอง

## Quick Answers
- **ไลบรารีที่จัดการการตัด EPS ใน Java คืออะไร?** Aspose.Page for Java.  
- **ใช้เวลานานเท่าไหร่ในการทำการตัดพื้นฐาน?** ประมาณ 5‑10 นาที.  
- **ต้องมีไลเซนส์สำหรับการพัฒนาหรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการประเมิน; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **รองรับเวอร์ชัน Java ใดบ้าง?** Java 8 ขึ้นไป.  
- **สามารถกำหนดกล่องขอบเขต (bounding box) เองได้หรือไม่?** ได้ – เพียงระบุพิกัดที่ต้องการ.

## What is EPS Cropping and Why Use It?
Encapsulated PostScript (EPS) เป็นฟอร์แมตกราฟิกที่เก็บภาพเวกเตอร์พร้อมกับกล่องขอบเขต (bounding box) ที่กำหนดพื้นที่ที่มองเห็นได้ การตัดไฟล์ EPS หมายถึงการสร้างกล่องขอบเขตใหม่เพื่อให้เหลือเฉพาะส่วนที่ต้องการเท่านั้น ซึ่งมีประโยชน์เมื่อคุณต้องการลบขอบสีขาว, ดึงโลโก้ออก, หรือทำให้กราฟิกพอดีกับเลย์เอาต์ที่แคบลงโดยไม่ต้องสร้างไฟล์ต้นฉบับใหม่

## Prerequisites
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:

- ไลบรารี **Aspose.Page for Java** ติดตั้งแล้ว – ดาวน์โหลดจากหน้าอย่างเป็นทางการ [here](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** เวอร์ชัน 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ.  
- **โฟลเดอร์** สำหรับเก็บไฟล์ EPS ต้นฉบับ (`input.eps`) และไฟล์ที่ถูกตัด (`output_crop.eps`).

## Import Packages
ก่อนอื่นให้ import คลาส Java ที่จำเป็น ส่วนนี้ต้องคงเหมือนเดิมตามบทแนะนำต้นฉบับ:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

### Step 1: Set Document Directory and Input Stream
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
ที่นี่เรากำหนดโฟลเดอร์ที่เก็บไฟล์ EPS ต้นฉบับและเปิดสตรีมเพื่ออ่านไฟล์นั้น

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
การดึงกล่องขอบเขตเดิมจะให้พิกัดของพื้นที่ที่มองเห็นอยู่ในขณะนั้น – เป็นข้อมูลสำคัญสำหรับการตัดส่วนที่ไม่ต้องการ

### Step 4: Create Output Stream
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
เปิดสตรีมที่ไฟล์ EPS ที่ถูกตัดจะถูกเขียนลงไป

### Step 5: Define New Bounding Box and Crop
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
ระบุพิกัดสี่ค่า (lower‑left x, lower‑left y, upper‑right x, upper‑right y) ที่กำหนดพื้นที่ที่ต้องการเก็บไว้ เมธอด `cropEps` จะทำการตัดและเขียนผลลัพธ์ลงใน `output_crop.eps`

## Common Issues and Solutions
- **พิกัดไม่ถูกต้อง:** EPS ใช้หน่วย points (1/72 inch). หากผลการตัดดูแปลก ให้ตรวจสอบการแปลงหน่วยอีกครั้ง.  
- **ไฟล์ไม่พบ:** ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นพาธที่เหมาะสม (`/` หรือ `\`).  
- **ข้อยกเว้นไลเซนส์:** การรันโค้ดโดยไม่มีไลเซนส์ที่ถูกต้องอาจทำให้ไฟล์ผลลัพธ์มีลายน้ำ. ให้ใส่ไลเซนส์ชั่วคราวหรือถาวรก่อนใช้งานในสภาพแวดล้อมผลิตจริง.

## Frequently Asked Questions

**Q: Aspose.Page รองรับ Java 8 หรือไม่?**  
A: ใช่, Aspose.Page ทำงานกับ Java 8 และเวอร์ชันที่ใหม่กว่าใด ๆ

**Q: สามารถใช้ Aspose.Page ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: แน่นอน. ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต. คุณสามารถซื้อไลเซนส์ได้จาก [here](https://purchase.aspose.com/buy).

**Q: จะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนจากชุมชนได้จากที่ไหน?**  
A: เยี่ยมชมฟอรั่มอย่างเป็นทางการของ [Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อดูการสนทนา, ตัวอย่างโค้ด, และเคล็ดลับการแก้ปัญหา

**Q: มีรุ่นทดลองฟรีสำหรับการทดสอบหรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.Page ได้จากหน้า releases [here](https://releases.aspose.com/)

**Q: จะขอไลเซนส์ชั่วคราวสำหรับการประเมินผลระยะสั้นได้อย่างไร?**  
A: สามารถขอไลเซนส์ชั่วคราวได้จากพอร์ทัลไลเซนส์ [here](https://purchase.aspose.com/temporary-license/)

## Conclusion
คุณได้เรียนรู้ **how to crop eps** ไฟล์ใน Java ด้วย Aspose.Page แล้ว โดยการกำหนดกล่องขอบเขตแบบกำหนดเองและเรียกใช้ `cropEps` คุณสามารถตัดขอบที่ไม่ต้องการหรือแยกส่วนเฉพาะของกราฟิก EPS ได้ด้วยไม่กี่บรรทัดของโค้ด ผสานส่วนนี้เข้ากับ pipeline การประมวลผลเอกสารของคุณเพื่อทำให้การจัดการ EPS เป็นอัตโนมัติและทำให้ทรัพยากรภาพของคุณเป็นระเบียบ

---

**Last Updated:** 2025-11-30  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}