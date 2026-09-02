---
date: 2026-05-05
description: เรียนรู้วิธีเพิ่มลวดลายการเรียงเทกซ์เจอร์ลงในเอกสาร PostScript ด้วย Aspose.Page
  สำหรับ Java คู่มือนี้จะแสดงวิธีเพิ่มเทกซ์เจอร์อย่างมีประสิทธิภาพและสำรวจความเป็นไปได้เชิงสร้างสรรค์
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: เพิ่มลายเทกเจอร์แบบต่อเรียงใน Java PostScript
second_title: Aspose.Page Java API
title: วิธีเพิ่มลายการต่อพื้นผิวใน Java PostScript
url: /th/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มลายเทกเจอร์แบบต่อกันใน Java PostScript

## บทนำ
ในโลกของการพัฒนา Java การเรียนรู้ **how to add texture** ในเอกสาร PostScript เป็นความต้องการทั่วไป Aspose.Page for Java ทำให้งานนี้ง่ายขึ้น ช่วยให้คุณมุ่งเน้นที่การออกแบบแทนการจัดการไวยากรณ์ PostScript ระดับต่ำ ในบทแนะนำนี้ เราจะอธิบายขั้นตอนทั้งหมดที่จำเป็นสำหรับการเพิ่มลายเทกเจอร์แบบต่อกัน, เติมรูปทรง, และแม้กระทั่งเติมเทกเจอร์ให้กับข้อความในเอกสาร Java PostScript

## คำตอบสั้น
- **ต้องการไลบรารีอะไร?** Aspose.Page for Java  
- **คีย์เวิร์ดหลักที่คู่มือนี้มุ่งเป้าไปที่?** *how to add texture*  
- **ต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** มีการทดลองใช้ฟรี; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 หรือสูงกว่า.  
- **ฉันสามารถใช้แปรงเทกเจอร์ซ้ำสำหรับหลายรูปทรงได้หรือไม่?** ใช่ – สร้าง `TexturePaint` ครั้งเดียวแล้วนำไปใช้กับรูปทรงใดก็ได้.  
- **ฉันจะเติมสี่เหลี่ยมผืนผ้าด้วยเทกเจอร์อย่างไร?** ใช้ `document.fill(shape)` หลังจากตั้งค่า `TexturePaint` เป็นสีปัจจุบัน.

## ลายเทกเจอร์แบบต่อกันคืออะไร?
ลายเทกเจอร์แบบต่อกันทำซ้ำภาพขนาดเล็ก (แผ่น) ทั่วพื้นที่ขนาดใหญ่ ช่วยให้คุณ **fill shape with texture** โดยไม่ต้องวาดแผ่นแต่ละอันด้วยตนเอง เทคนิคนี้เหมาะสำหรับพื้นหลัง, การเติมสี, และเอฟเฟกต์ข้อความตกแต่งใน PostScript

## ทำไมต้องใช้ Aspose.Page for Java?
- **Zero‑dependency rendering** – ไม่ต้องใช้ตัวแปล PostScript ภายนอก.  
- **Full control over graphics** – ผสานรูปเวกเตอร์, ข้อความ, และเทกเจอร์บิตแมป.  
- **Cross‑platform** – ทำงานบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มบทแนะนำ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมแล้ว:
- ความเข้าใจพื้นฐานของภาษาโปรแกรม Java.  
- ความคุ้นเคยกับโครงสร้างเอกสาร PostScript.  
- ติดตั้งไลบรารี Aspose.Page for Java แล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/java/).

## นำเข้าแพ็กเกจ
เริ่มต้นโดยนำเข้าแพ็กเกจที่จำเป็นสำหรับโครงการ Java ของคุณ:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## วิธีเพิ่มลายเทกเจอร์แบบต่อกันใน Java PostScript
ต่อไปนี้เป็นคู่มือขั้นตอนต่อขั้นตอน แต่ละขั้นตอนมีคำอธิบายสั้น ๆ ตามด้วยโค้ดที่ต้องคัดลอกอย่างแม่นยำ.

### ขั้นตอนที่ 1: สร้างเอกสาร PostScript
เริ่มต้นโดยสร้างเอกสาร PostScript ใหม่ ระบุสตรีมเอาต์พุตและตัวเลือกการบันทึก ตรวจสอบให้แน่ใจว่าคุณได้กำหนดเส้นทางที่จำเป็นแล้ว.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### ขั้นตอนที่ 2: ตั้งค่าสภาพแวดล้อมกราฟิก
ย้ายตำแหน่งต้นกำเนิดไปยังตำแหน่งที่สะดวกและโหลดบิตแมปที่จะใช้เป็นแผ่นเทกเจอร์.

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### ขั้นตอนที่ 3: สร้างแปรงเทกเจอร์
กำหนด `TexturePaint` ที่ทำซ้ำบิตแมปทั่วพื้นที่ของรูปทรง ปรับขนาดสี่เหลี่ยมถ้าต้องการให้แผ่นใหญ่หรือเล็กลง.

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### ขั้นตอนที่ 4: วาดและเติมรูปทรง
สร้างสี่เหลี่ยมผืนผ้าและ **fill rectangle with texture** ด้วยแปรง จากนั้นวาดขอบรูปทรงเพื่อให้ผลลัพธ์โดดเด่น.

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### ขั้นตอนที่ 5: เพิ่มข้อความด้วยลายเทกเจอร์
คุณยังสามารถใช้เทกเจอร์เดียวกันกับ glyph ของข้อความได้ สิ่งนี้แสดงให้เห็น **how to fill texture** บนตัวอักษรในขณะที่ยังสามารถวาดเส้นขอบได้.

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### ขั้นตอนที่ 6: บันทึกและปิด
สุดท้าย ปิดหน้า, บันทึกเอกสาร, และปล่อยทรัพยากร.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## ปัญหาทั่วไปและเคล็ดลับ
- **Missing texture file** – ตรวจสอบว่าเส้นทางไปยัง `TestTexture.bmp` ถูกต้องและไฟล์สามารถเข้าถึงได้.  
- **Incorrect image dimensions** – หากเทกเจอร์ดูบิดเบี้ยว ปรับ `imageArea` ให้ตรงกับขนาดภาพต้นฉบับ.  
- **Performance** – ใช้ `TexturePaint` ตัวเดียวกันซ้ำสำหรับหลายรูปทรงเพื่อหลีกเลี่ยงการสร้างอ็อบเจ็กต์ที่ไม่จำเป็น.  
- **Pro tip:** ใช้บิตแมปความละเอียดสูงสำหรับแผ่นเพื่อให้เทกเจอร์คมชัดเมื่อขยาย.

## คำถามที่พบบ่อย

**Q: Aspose.Page for Java เหมาะสำหรับผู้เริ่มต้นหรือไม่?**  
A: แน่นอน! Aspose.Page for Java มีเอกสารที่ครอบคลุม ทำให้เข้าถึงได้สำหรับนักพัฒนาทุกระดับทักษะ.

**Q: ฉันสามารถรวม Aspose.Page for Java เข้ากับโครงการ Java ที่มีอยู่ของฉันได้หรือไม่?**  
A: ได้ คุณสามารถรวม Aspose.Page for Java เข้ากับโครงการของคุณได้อย่างง่ายดายโดยทำตามเอกสารที่ให้ไว้ [ที่นี่](https://reference.aspose.com/page/java/).

**Q: ฉันจะหาแหล่งสนับสนุนหรือพูดคุยเกี่ยวกับคำถามเกี่ยวกับ Aspose.Page ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อเข้าร่วมกับชุมชนและขอความช่วยเหลือ.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
A: มี คุณสามารถสำรวจการทดลองใช้ฟรีได้จาก [ที่นี่](https://releases.aspose.com/).

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
A: เยี่ยมชม [ลิงก์นี้](https://purchase.aspose.com/temporary-license/) เพื่อขอรับไลเซนส์ชั่วคราว.

## สรุป
ยินดีด้วย! คุณได้เรียนรู้ **how to add texture** ลายเทกเจอร์แบบต่อกันในเอกสาร Java PostScript ด้วย Aspose.Page for Java อย่างสำเร็จ อย่าลังเลที่จะทดลองใช้แผ่นบิตแมปต่าง ๆ, ปัจจัยการสเกล, และการดำเนินการผสมเพื่อปลดปล่อยศักยภาพเชิงสร้างสรรค์เต็มรูปแบบของการเติมเทกเจอร์.

---

**อัปเดตล่าสุด:** 2026-05-05  
**ทดสอบกับ:** Aspose.Page for Java 24.12 (latest)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}