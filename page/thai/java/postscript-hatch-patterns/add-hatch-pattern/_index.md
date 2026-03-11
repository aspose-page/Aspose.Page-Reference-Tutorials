---
date: 2026-02-15
description: เรียนรู้วิธีเพิ่มลายเส้นจัตุรัสลงในไฟล์ Java PostScript ด้วย Aspose.Page
  Java คู่มือแบบขั้นตอนต่อขั้นตอนนี้แสดงโค้ดทั้งหมดและเคล็ดลับ
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: วิธีเพิ่มลายเส้นจัตุรัสใน Java PostScript ด้วย Aspose.Page
url: /th/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่ม Hatch Pattern ใน Java PostScript

## บทนำ
หากคุณกำลังทำงานกับ **Aspose.Page Java** และสงสัย **วิธีเพิ่ม hatch pattern** ให้กับผลลัพธ์ PostScript ของคุณ, hatch patterns เป็นวิธีที่รวดเร็วและยืดหยุ่น ในบทเรียนนี้เราจะอธิบาย **วิธีเพิ่ม hatch** designs ไปยังเอกสาร PostScript, แสดงว่าทำไมจึงมีประโยชน์, และให้ตัวอย่างโค้ดที่พร้อมรันครบถ้วน เพียงไม่กี่บรรทัดของ Java คุณก็จะสร้างรูปทรงและข้อความที่เติม hatch‑filled ได้อย่างสวยงาม

## คำตอบสั้น
- **ต้องการไลบรารีอะไร?** Aspose.Page for Java (the “aspose page java” SDK).  
- **เอฟเฟกต์ภาพที่เพิ่มคืออะไร?** Hatch patterns (เช่น เส้นทแยงมุม, crosshatch).  
- **ต้องใช้ไลเซนส์เพื่อรันตัวอย่างหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์สำหรับการผลิต.  
- **มีจำนวนบรรทัดโค้ดเท่าไหร่?** ประมาณ 70 บรรทัด, แบ่งเป็นขั้นตอนที่ชัดเจน.  
- **สามารถใช้วิธีเดียวกันสำหรับ PDF ได้หรือไม่?** ใช่—Aspose.Page รองรับหลายรูปแบบผลลัพธ์รวมถึง PDF.

## วิธีเพิ่ม Hatch Pattern – ภาพรวม
Hatch patterns เป็นเทกซ์เจอร์แบบเวกเตอร์ที่แสดงผลคมชัดที่ความละเอียดใดก็ได้และทำงานได้ดีบนเครื่องพิมพ์ขาว‑ดำ โดยใช้ Aspose.Page Java คุณสามารถใช้แพทเทิร์นเหล่านี้กับรูปทรง, พาธ, และแม้แต่ข้อความโดยไม่ต้องจัดการกับคำสั่ง PostScript ระดับต่ำ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

- **สภาพแวดล้อมการพัฒนา Java** – JDK 8 หรือสูงกว่าและ IDE ที่คุณเลือก.  
- **ไลบรารี Aspose.Page for Java** – ดาวน์โหลด JAR ล่าสุดจากเว็บไซต์อย่างเป็นทางการ [here](https://releases.aspose.com/page/java/).  
- **สิทธิ์การเขียน** ไปยังโฟลเดอร์ที่ไฟล์ PostScript ที่สร้างจะถูกบันทึก.

## นำเข้าแพ็กเกจ
ก่อนอื่นให้เพิ่มคลาสที่จำเป็นเข้ามาในโปรเจกต์ของคุณ การนำเข้าต่าง ๆ นี้จะทำให้คุณเข้าถึง primitive การวาด, การจัดการสี, และ API ของ Aspose.Page

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
สร้าง output stream, กำหนดขนาดหน้า (A4), และกำหนดตัวแปร layout บางตัวที่จะนำกลับมาใช้ใหม่เมื่อวาดสี่เหลี่ยมที่เติม hatch‑filled

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

## ขั้นตอนที่ 2: บันทึกสถานะกราฟิกและทำการแปลตำแหน่ง
การบันทึกสถานะกราฟิกทำให้เราสามารถกลับไปยังระบบพิกัดเดิมได้ในภายหลัง, ในขณะที่ `translate` ย้ายจุดเริ่มต้นไปยังตำแหน่งที่สะดวก

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## ขั้นตอนที่ 3: สร้างสี่เหลี่ยมจัตุรัสสำหรับแต่ละแพทเทิร์น
กำหนดสี่เหลี่ยมที่สามารถนำกลับมาใช้ใหม่ได้ซึ่งจะแทนแต่ละเซลล์ที่เติม hatch

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## ขั้นตอนที่ 4: ตั้งค่า Pen สำหรับเส้นขอบสี่เหลี่ยมแพทเทิร์น
`BasicStroke` ขนาด 2 points ให้เส้นขอบที่คมชัดรอบสี่เหลี่ยมทุกอัน

```java
BasicStroke stroke = new BasicStroke(2);
```

## ขั้นตอนที่ 5: วนลูปผ่าน Hatch Patterns
วนลูปผ่านค่าทั้งหมดใน enum `HatchStyle`, เติมแต่ละสี่เหลี่ยมด้วยเทกซ์เจอร์ที่สอดคล้อง, แล้ววาดเส้นขอบของมัน. นี่คือแกนหลักของฟังก์ชัน **adding hatch pattern**

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## ขั้นตอนที่ 6: คืนค่าสถานะกราฟิก
กลับไปยังระบบพิกัดเดิมหลังจากที่เราวาดตารางสี่เหลี่ยมเสร็จ

```java
document.writeGraphicsRestore();
```

## ขั้นตอนที่ 7: เติมข้อความด้วย Hatch Pattern
ที่นี่เราจะแสดงวิธีการทาสีข้อความโดยใช้เทกซ์เจอร์ hatch. ตัวอย่างเติมคำว่า “ABC” ด้วยแพทเทิร์นเส้นทแยงมุม‑ข้าม

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## ขั้นตอนที่ 8: วาดเส้นขอบข้อความด้วย Hatch Pattern
ตอนนี้เราวาดเส้นขอบข้อความเดียวกัน, แต่ครั้งนี้ใช้ hatch style 70 % และเส้นที่หนากว่า

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## ขั้นตอนที่ 9: ปิดและบันทึกเอกสาร
สรุปหน้าจอ, เขียนไฟล์ลงดิสก์, และปล่อยทรัพยากร

```java
document.closePage();
document.save();
```

ทำตามขั้นตอนเหล่านี้, คุณจะได้ไฟล์ PostScript ที่แสดงชุดเต็มของ hatch patterns ที่ใช้กับรูปทรงและข้อความ—ทั้งหมดขับเคลื่อนโดย **aspose page java**.

## ทำไมต้องใช้ Hatch Patterns กับ Aspose.Page Java?
- **ความแตกต่างทางภาพ** – Hatch fills ทำงานได้แม้เครื่องพิมพ์จำกัดที่การพิมพ์สีเดียว.  
- **ประสิทธิภาพ** – เทกซ์เจอร์ถูกสร้างแบบ on‑the‑fly, ทำให้หลีกเลี่ยงไฟล์ภาพขนาดใหญ่.  
- **การสนับสนุนหลายรูปแบบ** – โค้ดเดียวกันสามารถใช้กับ PDF, EPS, หรือ SVG ด้วยการเปลี่ยนแปลงเล็กน้อย.

## ข้อผิดพลาดทั่วไป & เคล็ดลับ
- **ข้อผิดพลาดเส้นทางไฟล์** – ตรวจสอบให้ `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ที่เหมาะสม (`/` หรือ `\`).  
- **สีที่ไม่รองรับ** – ตัวแปล PostScript รุ่นเก่าอาจไม่รองรับบาง color space; ใช้ RGB พื้นฐานเพื่อความเข้ากันได้สูงสุด.  
- **คำเตือนไลเซนส์** – การรันตัวอย่างโดยไม่มีไลเซนส์ที่ถูกต้องจะฝังลายน้ำในผลลัพธ์.

## สรุป
การนำ Hatch Patterns มาใช้สามารถปรับปรุงความอ่านง่ายและความสวยงามของภาพเทคนิค, แผนที่, หรือกราฟิกใด ๆ ที่สร้างด้วย Java อย่างมาก ด้วย **Aspose.Page Java**, คุณจะได้ API ที่กระชับซึ่งแยกความซับซ้อนของคำสั่ง PostScript ต่ำ ๆ ออกไป ทำให้คุณโฟกัสที่การออกแบบมากกว่ารูปแบบไฟล์ ตอนนี้คุณรู้ **วิธีเพิ่ม hatch pattern** ให้กับเอกสาร PostScript ของคุณแล้ว—ลองเปลี่ยนค่า `HatchStyle` ต่าง ๆ เพื่อสร้างลุคที่ต้องการ

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Page Java กับเฟรมเวิร์ก Java อื่นได้หรือไม่?**  
ตอบ: ใช่, ไลบรารีนี้เป็น framework‑agnostic และทำงานกับ Spring, Jakarta EE, Android (จำกัด), และ Java SE ธรรมดา.

**ถาม: มีเวอร์ชันทดลองสำหรับ Aspose.Page Java หรือไม่?**  
ตอบ: มีแน่นอน. ดาวน์โหลดเวอร์ชันทดลองฟรี 30‑วัน [here](https://releases.aspose.com/).

**ถาม: ฉันจะขอไลเซนส์ชั่วคราวสำหรับการพัฒนาอย่างไร?**  
ตอบ: ขอไลเซนส์ชั่วคราว [here](https://purchase.aspose.com/temporary-license/). จะลบลายน้ำการประเมินผลออก.

**ถาม: ฉันจะหา tutorial และการสนับสนุนจากชุมชนเพิ่มเติมได้ที่ไหน?**  
ตอบ: เยี่ยมชมฟอรั่มอย่างเป็นทางการ [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) เพื่อดูตัวอย่างเพิ่มเติมและ Q&A.

**ถาม: มีเอกสารครบถ้วนสำหรับทุกคลาสและเมธอดหรือไม่?**  
ตอบ: มี, เอกสารอ้างอิง API ทั้งหมดพร้อมให้ดู [here](https://reference.aspose.com/page/java/).

**ถาม: ฉันสามารถเรนเดอร์ Hatch Pattern เดียวกันเป็น PDF แทน PostScript ได้หรือไม่?**  
ตอบ: แน่นอน. เปลี่ยน `PsSaveOptions` เป็น `PdfSaveOptions` (หรือเทียบเท่า) ส่วนที่เหลือของโค้ดจะไม่เปลี่ยนแปลง.

**ถาม: ควรทำอย่างไรหากไฟล์ที่สร้างขึ้นเป็นไฟล์ว่าง?**  
ตอบ: ตรวจสอบว่า output stream ชี้ไปยังไดเรกทอรีที่สามารถเขียนได้และว่า `document.save()` ถูกเรียกหลังจากการวาดทั้งหมด.

**อัปเดตล่าสุด:** 2026-02-15  
**ทดสอบกับ:** Aspose.Page for Java 24.12 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}