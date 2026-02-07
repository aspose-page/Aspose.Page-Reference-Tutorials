---
date: 2026-02-07
description: เรียนรู้วิธีปรับขนาดไฟล์ EPS ใน Java และเปลี่ยนขนาด EPS ด้วย Aspose.Page
  คู่มือแบบขั้นตอนนี้จะแสดงวิธีปรับขนาด EPS ด้วยหน่วยจุด นิ้ว มิลลิเมตร หรือเปอร์เซ็นต์
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: วิธีปรับขนาดไฟล์ EPS ใน Java ด้วย Aspose.Page
url: /th/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีปรับขนาดไฟล์ EPS ใน Java ด้วย Aspose.Page

## Introduction
หากคุณกำลังมองหาวิธีที่เชื่อถือได้ **วิธีปรับขนาด EPS** อย่างอัตโนมัติ คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายขั้นตอนการปรับขนาดภาพ EPS ใน Java โดยใช้ไลบรารี Aspose.Page ไม่ว่าคุณต้องการเพิ่มขนาดเป็นสองเท่า ลดขนาดให้ตรงตามการวัดที่กำหนด หรือใช้เปอร์เซ็นต์ ขั้นตอนด้านล่างจะให้คุณควบคุมมิติผลลัพธ์ได้อย่างเต็มที่ การเข้าใจ **วิธีปรับขนาด eps** เป็นสิ่งสำคัญเมื่อคุณต้องปรับกราฟิกให้เข้ากับรูปแบบการพิมพ์หรือความละเอียดหน้าจอที่ต่างกัน

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I resize using points, inches, or millimeters?** Yes – the API supports all three units plus percentages.  
- **Do I need a license for development?** A free trial works for testing; a license is required for production.  
- **What Java version is required?** Java 8 or later.  
- **Is the code thread‑safe?** Each `PsDocument` instance is isolated, so you can process files in parallel.  

## What is EPS and Why Resize It?
Encapsulated PostScript (EPS) เป็นรูปแบบกราฟิกเวกเตอร์ที่ได้รับความนิยมในงานพิมพ์และการเผยแพร่ บางครั้งไฟล์ EPS ดั้งเดิมถูกสร้างที่ขนาดไม่ตรงกับผลลัพธ์ที่ต้องการ – ตัวอย่างเช่น โลโก้ที่ออกแบบที่ 72 pts อาจต้องเป็น 144 pts สำหรับโบรชัวร์ขนาดใหญ่ การรู้ **วิธีปรับขนาด eps** จะช่วยให้คุณคงคุณภาพเวกเตอร์ไว้ขณะปรับมิติให้เข้ากับกระบวนการทำงานใด ๆ

## Why Use Aspose.Page for Resizing EPS?
- **Full‑control over units** – points, inches, millimeters, or percentages.  
- **No external dependencies** – pure Java API, no native libraries.  
- **High performance** – suitable for batch processing on servers.  
- **Preserves vector fidelity** – the output remains scalable without rasterization.

## Prerequisites
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้แล้ว:

- Java Development Kit (JDK) ติดตั้งบนเครื่องของคุณ  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/page/java/)**  
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java  

## Import Packages
ในโปรเจกต์ Java ของคุณ ให้เพิ่มการ import ที่จำเป็นเพื่อให้สามารถทำงานกับอ็อบเจกต์ของ Aspose.Page และสตรีม I/O มาตรฐานได้

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## How to Change EPS Dimensions with Different Units
ไลบรารีนี้ให้คุณ **เปลี่ยนขนาด eps** ได้ง่าย ๆ เพียงเลือกค่า `Units` ที่ต้องการ ด้านล่างเราจะอธิบายรูปแบบขั้นตอนห้าขั้นตอนเดียวกันสำหรับ points, inches, millimeters และ percentages ส่วนที่เปลี่ยนแปลงเพียงแค่หน่วยที่ส่งให้ `resizeEps`

## How to Resize EPS Using Points
ต่อไปนี้เป็นตัวอย่างครบถ้วนแบบขั้นตอนต่อขั้นตอนที่เพิ่มขนาดไฟล์ EPS เป็นสองเท่าโดยใช้ points เป็นหน่วยวัด

### Step 1: Set up the input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: Initialize the `PsDocument` object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: Extract the current size of the EPS image
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: Create an output stream for the resized file
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: Resize and save the EPS using points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## How to Resize EPS Using Inches
รูปแบบขั้นตอนห้าขั้นตอนเดียวกัน เพียงเปลี่ยน `Units.Points` เป็น `Units.Inches` และปรับค่าอัตราส่วนให้ตรงกับจำนวน inches ที่ต้องการ

## How to Resize EPS Using Millimeters
ทำตามขั้นตอนเดียวกันโดยสลับหน่วยเป็น `Units.Millimeters` ซึ่งสะดวกเมื่อต้องการขนาดตามระบบเมตริกสำหรับกระบวนการพิมพ์

## How to Resize EPS Using Percentages
สำหรับการปรับขนาดตามเปอร์เซ็นต์ ให้ใช้หน่วย `Units.Percent` คูณความกว้างและความสูงเดิมด้วยเปอร์เซ็นต์ที่ต้องการ (เช่น `0.5` สำหรับการลดลง 50 %)

## Common Pitfalls & Tips
- **Always close streams** – In production code, wrap streams in try‑with‑resources to avoid file locks.  
- **Preserve aspect ratio** – Multiply both width and height by the same factor unless you intentionally want distortion.  
- **Check DPI** – Resizing does not change the DPI; if you need a different DPI, adjust it separately after resizing.  
- **Thread safety** – Create a new `PsDocument` per thread; sharing the same instance can lead to unexpected results.  

## Frequently Asked Questions

**Q: Can I use this library for other image formats?**  
A: No, Aspose.Page is specialized for PostScript and EPS files only.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Yes, you can explore the free trial **[here](https://releases.aspose.com/)**.

**Q: Where can I find additional help and discussions?**  
A: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** for community support.

**Q: How can I obtain a temporary license?**  
A: You can get a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Are there any example projects available?**  
A: Yes, check the documentation **[here](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}