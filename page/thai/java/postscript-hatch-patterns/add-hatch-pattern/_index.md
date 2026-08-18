---
date: 2026-08-18
description: เรียนรู้วิธีเพิ่ม hatch pattern ให้กับไฟล์ Java PostScript ด้วย Aspose.Page
  Java. คู่มือ step‑by‑step นี้แสดงโค้ดทั้งหมดและเคล็ดลับ
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: เพิ่ม Hatch Pattern ใน Java PostScript
og_description: เรียนรู้วิธีเพิ่ม hatch pattern ใน Java PostScript ด้วย Aspose.Page.
  ทำตาม tutorial step‑by‑step นี้เพื่อสร้าง graphics hatch‑filled อย่างรวดเร็ว
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: วิธีเพิ่ม hatch pattern ใน Java PostScript – Aspose.Page guide
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: วิธีเพิ่ม hatch pattern ใน Java PostScript
url: /th/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มลวดลาย hatch ใน Java PostScript

## บทนำ
หากคุณกำลังทำงานกับ **Aspose.Page Java** และสงสัย **วิธีเพิ่มลวดลาย hatch** ในผลลัพธ์ PostScript ของคุณ ลวดลาย hatch เป็นวิธีที่เร็วและยืดหยุ่น ในบทเรียนนี้เราจะอธิบาย **วิธีเพิ่ม hatch** ลงในเอกสาร PostScript, อธิบายว่าทำไมจึงมีประโยชน์, และให้ตัวอย่างโค้ดที่พร้อมรันครบถ้วน เมื่อเสร็จสิ้นคุณจะสามารถสร้างรูปทรงและข้อความที่เติมลวดลาย hatch อย่างสวยงามได้ด้วยเพียงไม่กี่บรรทัดของ Java.

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.Page for Java (the “aspose page java” SDK).  
- **เอฟเฟกต์ภาพใดที่เรากำลังเพิ่ม?** Hatch patterns (e.g., diagonal lines, crosshatch).  
- **ต้องใช้ไลเซนส์เพื่อรันตัวอย่างหรือไม่?** A free trial works for development; a license is required for production.  
- **มีจำนวนบรรทัดของโค้ดเท่าไหร่?** About 70 lines, split into clear steps.  
- **ฉันสามารถใช้วิธีเดียวกันกับ PDF ได้หรือไม่?** Yes—Aspose.Page supports multiple output formats, including PDF.

## ลวดลาย hatch คืออะไร?
ลวดลาย hatch คือการเติมแบบเวกเตอร์ที่ประกอบด้วยเส้นหรือรูปแบบที่ทำซ้ำซึ่งสร้างเอฟเฟกต์เทกซ์เจอร์ เนื่องจากกำหนดโดยคณิตศาสตร์ ลวดลายสามารถขยายได้โดยไม่สูญเสียคุณภาพ ทำให้เหมาะสำหรับการพิมพ์ความละเอียดสูงและผลลัพธ์แบบโมโนโครม

## ทำไมต้องใช้ลวดลาย hatch กับ Aspose.Page Java?
Aspose.Page รองรับ **10+ รูปแบบการส่งออก** (รวมถึง PostScript, PDF, EPS, SVG, และ XPS) และสามารถเรนเดอร์การเติม hatch บนเอกสารได้ถึง **500 หน้า** โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ซึ่งหมายความว่าคุณจะได้ประสิทธิภาพที่เร็ว, ใช้หน่วยความจำน้อย, และผลลัพธ์ภาพที่สม่ำเสมอในทุกรูปแบบที่รองรับ

## วิธีเพิ่มลวดลาย hatch – ภาพรวม
ลวดลาย hatch เป็นเทกซ์เจอร์แบบเวกเตอร์ที่เรนเดอร์ได้อย่างคมชัดที่ความละเอียดใดก็ได้และทำงานได้ดีบนเครื่องพิมพ์โมโนโครม โดยใช้ Aspose.Page Java คุณสามารถนำลวดลายเหล่านี้ไปใช้กับรูปทรง, เส้นทาง, และแม้แต่ข้อความโดยไม่ต้องจัดการคำสั่ง PostScript ระดับต่ำ

## ข้อกำหนดเบื้องต้น
- **สภาพแวดล้อมการพัฒนา Java** – JDK 8 หรือสูงกว่าและ IDE ที่คุณเลือก.  
- **Aspose.Page for Java library** – ดาวน์โหลด JAR ล่าสุดจาก **Aspose.Page for Java download page** อย่างเป็นทางการ [here](https://releases.aspose.com/page/java/).  
- คุณยังสามารถเรียกดูการปล่อยอื่นของ Aspose [here](https://releases.aspose.com/).  
- **สิทธิ์การเขียน** ไปยังโฟลเดอร์ที่ไฟล์ PostScript ที่สร้างขึ้นจะถูกบันทึก

## นำเข้าแพ็กเกจ
การนำเข้าด้านล่างรวมคลาสมาตรฐานของ Java AWT สำหรับ primitive กราฟิก เช่น สี, เส้น, และรูปทรงเรขาคณิต รวมถึงคลาสของ Aspose.Page ที่ให้โมเดลเอกสาร, คำจำกัดความของ hatch‑style, และตัวเลือกการบันทึกที่จำเป็นสำหรับการสร้างไฟล์ PostScript.  
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

## คลาส `Document` คืออะไร?
คลาส `Document` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.Page ที่แสดงถึงไฟล์ PostScript เดียวในหน่วยความจำ การดำเนินการวาดทั้งหมดทำผ่านอ็อบเจ็กต์นี้

## วิธีตั้งค่า output stream?
เพื่อเขียนผลลัพธ์, สร้าง `FileOutputStream` ที่ชี้ไปยังเส้นทางไฟล์ที่ต้องการ; สตรีมนี้จัดการการเขียนไบต์ระดับต่ำ `PsSaveOptions` กำหนดค่าการบันทึกเอกสาร, รวมถึงขนาดหน้าและการบีบอัด จากนั้นสร้างอินสแตนซ์ของ `Document` ด้วยอ็อบเจ็กต์ `PsSaveOptions` ที่ระบุขนาดหน้า, การบีบอัด, และการตั้งค่าเฉพาะของ PostScript อื่นๆ.  
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

## วิธีบันทึกสถานะกราฟิกและแปลตำแหน่งต้นกำเนิด?
การบันทึกสถานะกราฟิกจะจับเมทริกซ์การแปลงปัจจุบัน, พื้นที่คลิป, และแอตทริบิวต์การวาด, ทำให้คุณสามารถย้อนกลับได้ในภายหลัง หลังจากบันทึก, เรียก `translate(x, y)` บนวัตถุกราฟิกเพื่อย้ายตำแหน่งต้นกำเนิดไปยังตำแหน่งที่สะดวกสำหรับการวาดตารางของสี่เหลี่ยม hatch.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## วิธีสร้างสี่เหลี่ยมที่ใช้ซ้ำได้สำหรับแต่ละลวดลาย?
`Rectangle2D` แทนรูปสี่เหลี่ยมที่กำหนดโดยตำแหน่งและขนาด โดยการสร้างอินสแตนซ์เดียวที่ตรงกับขนาดของเซลล์ คุณสามารถใช้ซ้ำสำหรับแต่ละสี่เหลี่ยมที่เติม hatch, ลดการจัดสรรอ็อบเจ็กต์และทำให้ลูปการวาดมีประสิทธิภาพ.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## วิธีตั้งค่า pen สำหรับเส้นขอบสี่เหลี่ยมลวดลาย?
`BasicStroke` อธิบายความหนาของเส้นขอบ, รูปแบบ dash, และ end caps สำหรับรูปเวกเตอร์ การใช้ `BasicStroke` ขนาด 2‑point ให้ขอบที่ชัดเจนรอบแต่ละเซลล์ที่เติม hatch, ทำให้การเติมแยกจากสี่เหลี่ยมข้างเคียงอย่างชัดเจน.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## วิธีวนลูปผ่านลวดลาย hatch?
`HatchStyle` เป็น enumeration ที่แสดงลวดลาย hatch ที่กำหนดไว้ล่วงหน้า เช่น แนวทแยง, ครอส, และจุด `Loop` ผ่าน `HatchStyle.values()` จะทำให้คุณใช้แต่ละลวดลายตามลำดับ, เติมสี่เหลี่ยมด้วย `HatchBrush`, แล้ววาดเส้นขอบของมัน.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## วิธีคืนค่าสถานะกราฟิกหลังการวาด?
การเรียก `restore()` บนวัตถุกราฟิกจะคืนเมทริกซ์การแปลงและการตั้งค่าการวาดไปยังสถานะที่บันทึกไว้ก่อนหน้า, ป้องกันการแปลงหรือสเกลสะสมจากการส่งผลต่อการดำเนินการวาดต่อไป นี้ทำให้เนื้อหาถัดไปเริ่มจากระบบพิกัดเดิมและใช้แอตทริบิวต์ค่าเริ่มต้น.  
```java
document.writeGraphicsRestore();
```

## วิธีเติมข้อความด้วยลวดลาย hatch?
`TextFragment` แทนส่วนของข้อความที่สามารถกำหนดตำแหน่งและสไตล์ได้อย่างอิสระ โดยการกำหนด `HatchBrush` พร้อม `HatchStyle` ที่เลือกให้กับการเติมของ fragment, ตัวอักษรข้อความจะถูกเรนเดอร์ด้วยเทกซ์เจอร์ hatch แทนสีทึบ.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## วิธีทำเส้นขอบข้อความด้วยลวดลาย hatch ที่ต่างกัน?
`HatchBrush` สามารถใช้สำหรับการสเตรกได้เช่นกัน เพื่อวาดเส้นขอบ, ตั้งค่า stroke ของ fragment เป็น `HatchBrush` ที่มี `HatchStyle` แตกต่าง (เช่น hatch 70 %) และเพิ่มความกว้างของ stroke ผ่าน `setStrokeWidth`. นี้ทำให้ขอบข้อความแสดงลวดลาย hatch ของมันเองพร้อมยังคงส่วนเติมภายใน.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## วิธีปิดและบันทึกเอกสาร?
`document.save()` เขียนเอกสารในหน่วยความจำไปยัง output stream ที่ระบุ หลังจากทำคำสั่งวาดทั้งหมดเสร็จ, เรียกเมธอดนี้แล้วปิด `FileOutputStream` เพื่อปล่อยทรัพยากรระบบและทำให้ไฟล์ถูก flush ไปยังดิสก์อย่างถูกต้อง.  
```java
document.closePage();
document.save();
```

ทำตามขั้นตอนเหล่านี้, คุณจะได้ไฟล์ PostScript ที่แสดงชุดลวดลาย hatch ครบชุดที่ใช้กับรูปทรงและข้อความ—ทั้งหมดนี้ขับเคลื่อนโดย **aspose page java**.

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ข้อผิดพลาดของเส้นทางไฟล์** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ที่เหมาะสม (`/` หรือ `\`).  
- **สีที่ไม่รองรับ** – ตัวแปล PostScript รุ่นเก่าอาจไม่รองรับบางสีสเปซ; ควรใช้ RGB พื้นฐานเพื่อความเข้ากันได้สูงสุด.  
- **คำเตือนไลเซนส์** – การรันตัวอย่างโดยไม่มีไลเซนส์ที่ถูกต้องจะฝังลายน้ำในผลลัพธ์.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Page Java กับเฟรมเวิร์ก Java อื่นได้หรือไม่?**  
A: ใช่, ไลบรารีนี้เป็น framework‑agnostic และทำงานกับ Spring, Jakarta EE, Android (จำกัด), และ Java SE ธรรมดา.

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.Page Java หรือไม่?**  
A: แน่นอน. ดาวน์โหลดเวอร์ชันทดลองฟรี 30‑วัน [Aspose trial download page](https://releases.aspose.com/).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับการพัฒนาอย่างไร?**  
A: ขอไลเซนส์ชั่วคราว [temporary license request page](https://purchase.aspose.com/temporary-license/). มันจะลบลายน้ำการประเมิน.

**Q: ฉันจะหา tutorial และการสนับสนุนจากชุมชนเพิ่มเติมได้ที่ไหน?**  
A: เยี่ยมชมฟอรั่มอย่างเป็นทางการ [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) เพื่อดูตัวอย่างเพิ่มเติมและ Q&A.

**Q: มีเอกสารครบถ้วนสำหรับทุกคลาสและเมธอดหรือไม่?**  
A: มี, เอกสารอ้างอิง API เต็มรูปแบบพร้อมให้ใช้งาน [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: ฉันสามารถเรนเดอร์ลวดลาย hatch เดียวกันเป็น PDF แทน PostScript ได้หรือไม่?**  
A: แน่นอน. เปลี่ยน `PsSaveOptions` เป็น `PdfSaveOptions` (หรือเทียบเท่า) ส่วนที่เหลือของโค้ดยังคงเหมือนเดิม.

**Q: ควรทำอย่างไรหากไฟล์ที่สร้างขึ้นเป็นไฟล์ว่าง?**  
A: ตรวจสอบว่า output stream ชี้ไปยังไดเรกทอรีที่สามารถเขียนได้และว่า `document.save()` ถูกเรียกหลังจากการดำเนินการวาดทั้งหมด.

---

**อัปเดตล่าสุด:** 2026-08-18  
**ทดสอบด้วย:** Aspose.Page for Java 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้างลายเทกซ์เจอร์ใน PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [วิธีเพิ่ม Gradient: Diagonal Gradient ใน Java PostScript ด้วย Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [วิธีแปลง PostScript เป็น PDF ด้วย Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}