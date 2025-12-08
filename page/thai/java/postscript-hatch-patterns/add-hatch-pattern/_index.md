---
date: 2025-12-08
description: เรียนรู้วิธีเพิ่มลายเส้นจัตุรัสในเอกสาร Java PostScript ด้วย Aspose.Page
  Java คู่มือแบบทีละขั้นตอนนี้จะแสดงวิธีเพิ่มกราฟิกลายเส้นจัตุรัสอย่างมีประสิทธิภาพ
language: th
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: เพิ่มลายเส้นจัตุรัสใน Java PostScript'
url: /java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มลวดลาย Hatch ใน Java PostScript

## บทนำ
หากคุณกำลังทำงานกับ **Aspose.Page Java** และต้องการเพิ่มกราฟิกที่มีพื้นผิวลงในผลลัพธ์ PostScript ของคุณ ลวดลาย Hatch เป็นวิธีที่รวดเร็วและยืดหยุ่น ในบทเรียนนี้เราจะอธิบาย **วิธีเพิ่มลวดลาย Hatch** ลงในเอกสาร PostScript, ทำให้คุณเข้าใจว่ามันมีประโยชน์อย่างไร, และให้ตัวอย่างโค้ดที่พร้อมรันครบถ้วน หลังจากอ่านจบคุณจะสามารถสร้างรูปทรงและข้อความที่เติมลวดลาย Hatch อย่างสวยงามได้ด้วยเพียงไม่กี่บรรทัดของ Java

## คำตอบอย่างรวดเร็ว
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java (SDK “aspose page java”)  
- **เรากำลังเพิ่มเอฟเฟกต์ภาพแบบไหน?** ลวดลาย Hatch (เช่น เส้นทแยงมุม, การขีดไขว้)  
- **ต้องมีลิขสิทธิ์เพื่อรันตัวอย่างหรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์สำหรับการใช้งานจริง  
- **ต้องเขียนโค้ดกี่บรรทัด?** ประมาณ 70 บรรทัด แบ่งเป็นขั้นตอนที่ชัดเจน  
- **สามารถใช้แนวทางเดียวกันกับ PDF ได้หรือไม่?** ได้—Aspose.Page รองรับหลายรูปแบบผลลัพธ์รวมถึง PDF

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

- **สภาพแวดล้อมการพัฒนา Java** – JDK 8 หรือสูงกว่าและ IDE ที่คุณชอบ  
- **ไลบรารี Aspose.Page for Java** – ดาวน์โหลด JAR ล่าสุดจากเว็บไซต์อย่างเป็นทางการ [ที่นี่](https://releases.aspose.com/page/java/)  
- **สิทธิ์การเขียน** ไปยังโฟลเดอร์ที่ไฟล์ PostScript ที่สร้างจะถูกบันทึก

## นำเข้าแพ็กเกจ
ก่อนอื่นให้เพิ่มคลาสที่จำเป็นลงในโปรเจกต์ของคุณ การนำเข้าต่อไปนี้ทำให้คุณเข้าถึง primitive การวาด, การจัดการสี, และ API ของ Aspose.Page

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ขั้นตอนที่ 1: ตั้งค่าพารามิเตอร์เริ่มต้น
สร้าง output stream, กำหนดขนาดหน้า (A4) และกำหนดตัวแปรเลย์เอาต์บางอย่างที่จะใช้ซ้ำเมวาดสี่เหลี่ยมที่เติม Hatch แต่ละอัน

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## ขั้นตอนที่ 2: บันทึกสถานะกราฟิกและแปลตำแหน่ง
การบันทึกสถานะกราฟิกทำให้เรากลับไปยังระบบพิกัดเดิมได้ในภายหลัง, ส่วน `translate` จะย้ายจุดกำเนิดไปยังตำแหน่งเริ่มต้นที่สะดวก

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## ขั้นตอนที่ 3: สร้างสี่เหลี่ยมสำหรับแต่ละลวดลาย
กำหนดสี่เหลี่ยมที่สามารถนำกลับมาใช้ใหม่ได้ ซึ่งจะเป็นตัวแทนของแต่ละเซลล์ที่เติม Hatch

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## ขั้นตอนที่ 4: ตั้งค่า Pen สำหรับกรอบสี่เหลี่ยมลวดลาย
`BasicStroke` ขนาด 2 points จะให้เส้นขอบที่คมชัดรอบทุกสี่เหลี่ยม

```java
BasicStroke stroke = new BasicStroke(2);
```

## ขั้นตอนที่ 5: วนลูปผ่านลวดลาย Hatch
วนลูปผ่านค่าทั้งหมดใน enum `HatchStyle`, เติมแต่ละสี่เหลี่ยมด้วยพื้นผิวที่สอดคล้อง, แล้ววาดกรอบของมัน นี่คือแกนหลักของ **การเพิ่มลวดลาย Hatch** 

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## ขั้นตอนที่ 6: คืนค่าสถานะกราฟิก
กลับไปยังระบบพิกัดเดิมหลังจากวาดตารางสี่เหลี่ยมเสร็จเรียบร้อย

```java
document.writeGraphicsRestore();
```

## ขั้นตอนที่ 7: เติมข้อความด้วยลวดลาย Hatch
ในขั้นตอนนี้เราจะแสดงวิธีการทาสีข้อความโดยใช้พื้นผิว Hatch ตัวอย่างเติมคำว่า “ABC” ด้วยลวดลายเส้นทแยงมุม‑ขีดไขว้

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## ขั้นตอนที่ 8: วาดกรอบข้อความด้วยลวดลาย Hatch
ต่อไปเราจะวาดกรอบให้ข้อความเดียวกัน แต่ครั้งนี้ใช้สไตล์ Hatch 70 % และเส้นขอบที่หนากว่า

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## ขั้นตอนที่ 9: ปิดและบันทึกเอกสาร
สรุปหน้ากระดาษ, เขียนไฟล์ลงดิสก์, และปล่อยทรัพยากร

```java
document.closePage();
document.save();
```

ทำตามขั้นตอนเหล่านี้ คุณจะได้ไฟล์ PostScript ที่แสดงชุดลวดลาย Hatch ครบถ้วน ทั้งบนรูปทรงและข้อความ—ทั้งหมดขับเคลื่อนโดย **aspose page java**

## ทำไมต้องใช้ Hatch Patterns กับ Aspose.Page Java?
- **ความแตกต่างทางภาพ** – การเติม Hatch ทำงานได้แม้เมื่อเครื่องพิมพ์จำกัดเพียงการพิมพ์สีขาว-ดำ  
- **ประสิทธิภาพ** – พื้นผิวถูกสร้างแบบเรียลไทม์ ทำให้ไม่ต้องใช้ไฟล์ภาพขนาดใหญ่  
- **รองรับหลายรูปแบบ** – โค้ดเดียวกันสามารถใช้กับ PDF, EPS, หรือ SVG ได้ด้วยการเปลี่ยนแปลงเล็กน้อย

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ข้อผิดพลาดของเส้นทางไฟล์** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ที่เหมาะสม (`/` หรือ `\`)  
- **สีที่ไม่รองรับ** – ตัวแปล PostScript รุ่นเก่าอาจไม่รองรับบาง color space; ใช้ RGB พื้นฐานเพื่อความเข้ากันได้สูงสุด  
- **คำเตือนลิขสิทธิ์** – รันตัวอย่างโดยไม่มีลิขสิทธิ์ที่ถูกต้องจะทำให้มีลายน้ำแทรกในผลลัพธ์

## สรุป
การนำลวดลาย Hatch มาใช้สามารถปรับปรุงความอ่านง่ายและความสวยงามของภาพเทคนิค, แผนที่, หรือกราฟิกใด ๆ ที่สร้างด้วย Java ได้อย่างมาก ด้วย **Aspose.Page Java** คุณจะได้ API ที่กระชับซึ่งแยกคำสั่ง PostScript ระดับล่างออกไป ทำให้คุณมุ่งเน้นที่การออกแบบมากกว่าการจัดการรูปแบบไฟล์

## คำถามที่พบบ่อย

**Q: สามารถใช้ Aspose.Page Java กับเฟรมเวิร์ก Java อื่น ๆ ได้หรือไม่?**  
A: ใช่, ไลบรารีนี้เป็นอิสระจากเฟรมเวิร์กและทำงานร่วมกับ Spring, Jakarta EE, Android (จำกัด), และ Java SE ธรรมดาได้

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.Page Java หรือไม่?**  
A: มีแน่นอน. ดาวน์โหลดเวอร์ชันทดลองฟรี 30 วัน [ที่นี่](https://releases.aspose.com/)

**Q: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับการพัฒนาได้อย่างไร?**  
A: ขอรับลิขสิทธิ์ชั่วคราว [ที่นี่](https://purchase.aspose.com/temporary-license/). จะลบลายน้ำการประเมินออก

**Q: จะหา tutorial และการสนับสนุนจากชุมชนได้จากที่ไหน?**  
A: เยี่ยมชมฟอรั่มอย่างเป็นทางการ [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) เพื่อดูตัวอย่างเพิ่มเติมและถาม‑ตอบ

**Q: มีเอกสารอธิบายคลาสและเมธอดทั้งหมดหรือไม่?**  
A: มี, API reference เต็มรูปแบบพร้อมให้ใช้งาน [ที่นี่](https://reference.aspose.com/page/java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-08  
**ทดสอบกับ:** Aspose.Page for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose