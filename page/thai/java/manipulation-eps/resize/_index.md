---
date: 2025-12-02
description: เรียนรู้วิธีปรับขนาดไฟล์ EPS ใน Java อย่างง่ายดายด้วย Aspose.Page คู่มือขั้นตอนนี้จะแสดงวิธีปรับขนาด
  EPS ด้วยหน่วยจุด นิ้ว มิลลิเมตร หรือเปอร์เซ็นต์
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

## บทนำ
หากคุณกำลังมองหาวิธีที่เชื่อถือได้ **how to resize EPS** ไฟล์โดยโปรแกรม คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะอธิบายขั้นตอนการปรับขนาดภาพ EPS ใน Java ด้วยไลบรารี Aspose.Page ไม่ว่าคุณต้องการเพิ่มขนาดเป็นสองเท่า ลดขนาดให้ตรงตามการวัดที่กำหนด หรือทำงานด้วยเปอร์เซ็นต์ ขั้นตอนด้านล่างจะให้คุณควบคุมมิติของผลลัพธ์ได้อย่างเต็มที่

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.Page for Java  
- **สามารถปรับขนาดโดยใช้ points, inches หรือ millimeters ได้หรือไม่?** ใช่ – API รองรับหน่วยทั้งสามรวมถึงเปอร์เซ็นต์ด้วย.  
- **ต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** การทดลองใช้แบบฟรีทำงานได้สำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานจริง.  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือใหม่กว่า.  
- **โค้ดนี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** แต่ละอินสแตนซ์ของ `PsDocument` แยกจากกัน ดังนั้นคุณสามารถประมวลผลไฟล์พร้อมกันได้.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Java Development Kit (JDK) ที่ติดตั้งบนเครื่องของคุณ.  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/page/java/)**.  
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java.

## นำเข้าแพ็กเกจ
ในโครงการ Java ของคุณ ให้รวมการนำเข้าที่จำเป็นเพื่อให้คุณสามารถทำงานกับวัตถุ Aspose.Page และสตรีม I/O มาตรฐานได้.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## วิธีปรับขนาด EPS ด้วย Points
ต่อไปนี้คือตัวอย่างเต็มขั้นตอนที่เพิ่มขนาดไฟล์ EPS เป็นสองเท่าโดยใช้ points เป็นหน่วยวัด.

### ขั้นตอนที่ 1: ตั้งค่า input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### ขั้นตอนที่ 2: เริ่มต้นอ็อบเจ็กต์ `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### ขั้นตอนที่ 3: ดึงขนาดปัจจุบันของภาพ EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### ขั้นตอนที่ 4: สร้าง output stream สำหรับไฟล์ที่ปรับขนาดแล้ว
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### ขั้นตอนที่ 5: ปรับขนาดและบันทึก EPS ด้วย points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## วิธีปรับขนาด EPS ด้วย Inches
รูปแบบห้าขั้นตอนเดียวกันใช้ได้; เพียงเปลี่ยน `Units.Points` เป็น `Units.Inches` และปรับค่าอัตราส่วนตามต้องการ.

## วิธีปรับขนาด EPS ด้วย Millimeters
อีกครั้ง, ทำตามขั้นตอนเดียวกันโดยเปลี่ยนหน่วยเป็น `Units.Millimeters`. สิ่งนี้มีประโยชน์เมื่อคุณต้องการขนาดตามระบบเมตริกสำหรับกระบวนการพิมพ์.

## วิธีปรับขนาด EPS ด้วย Percentages
สำหรับการปรับขนาดตามเปอร์เซ็นต์, ให้คงหน่วยเป็น `Units.Percent`. คูณความกว้างและความสูงเดิมด้วยเปอร์เซ็นต์ที่ต้องการ (เช่น `0.5` สำหรับการลดลง 50 %).

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ควรปิดสตรีมเสมอ** – ในโค้ดการผลิต ควรห่อสตรีมด้วย try‑with‑resources เพื่อหลีกเลี่ยงการล็อกไฟล์.  
- **รักษาอัตราส่วนภาพ** – คูณความกว้างและความสูงด้วยปัจจัยเดียวกัน เว้นแต่คุณต้องการบิดเบือนโดยเจตนา.  
- **ตรวจสอบ DPI** – การปรับขนาดไม่เปลี่ยน DPI; หากต้องการ DPI ที่ต่างออกไป ให้ปรับแยกหลังจากปรับขนาด.

## สรุป
ตอนนี้คุณรู้ **how to resize EPS** ไฟล์ใน Java ด้วย Aspose.Page แล้ว ไม่ว่าคุณจะเลือกใช้ points, inches, millimeters หรือ percentages ความยืดหยุ่นนี้ทำให้คุณสามารถรวมการจัดการ EPS เข้าไปใน pipeline อัตโนมัติ, ยูทิลิตี้บนเดสก์ท็อป, หรือบริการฝั่งเซิร์ฟเวอร์ได้.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ไลบรารีนี้กับรูปแบบภาพอื่นได้หรือไม่?**  
A: ไม่, Aspose.Page ถูกออกแบบเฉพาะสำหรับไฟล์ PostScript และ EPS เท่านั้น.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
A: ใช่, คุณสามารถสำรวจการทดลองใช้ฟรี **[ที่นี่](https://releases.aspose.com/)**.

**Q: ฉันจะหาแหล่งช่วยเหลือและการสนทนาเพิ่มเติมได้ที่ไหน?**  
A: เยี่ยมชม **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** เพื่อรับการสนับสนุนจากชุมชน.

**Q: ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร?**  
A: คุณสามารถรับใบอนุญาตชั่วคราว **[ที่นี่](https://purchase.aspose.com/temporary-license/)**.

**Q: มีโครงการตัวอย่างให้ใช้งานหรือไม่?**  
A: ใช่, ตรวจสอบเอกสาร **[ที่นี่](https://reference.aspose.com/page/java/)**.

---

**อัปเดตล่าสุด:** 2025-12-02  
**ทดสอบด้วย:** Aspose.Page for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}