---
date: 2025-12-17
description: เรียนรู้วิธีเพิ่มลวดลายการเรียงเทกซ์เจอร์ลงในเอกสาร PostScript ด้วย Aspose.Page
  สำหรับ Java คู่มือนี้จะแสดงวิธีเพิ่มเทกซ์เจอร์อย่างมีประสิทธิภาพและสำรวจความเป็นไปได้เชิงสร้างสรรค์
linktitle: Add Texture Tiling Pattern in Java PostScript
second_title: Aspose.Page Java API
title: วิธีเพิ่มลายเทกเจอร์แบบต่อเรียงใน Java PostScript
url: /th/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มแพทเทิร์นการเรียงเทกซ์เจอร์ใน Java PostScript

## บทนำ
ในโลกของการพัฒนา Java การเรียนรู้ **วิธีเพิ่มเทกซ์เจอร์** ให้กับเอกสาร PostScript เป็นความต้องการที่พบบ่อย Aspose.Page for Java เป็นเครื่องมือที่มีคุณค่าในการทำงานนี้อย่างง่ายดาย ในบทแนะนำนี้ เราจะพาคุณผ่านกระบวนการเพิ่มแพทเทิร์นการเรียงเทกซ์เจอร์ในเอกสาร Java PostScript ด้วย Aspose.Page

## คำตอบสั้น
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java  
- **คีย์เวิร์ดหลักของคู่มือนี้คืออะไร?** *how to add texture*  
- **ต้องมีลิขสิทธิ์สำหรับการทดสอบหรือไม่?** มีรุ่นทดลองฟรี; ต้องมีลิขสิทธิ์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า  
- **สามารถใช้แปรงเทกซ์เจอร์เดียวกันกับหลายรูปได้หรือไม่?** ได้ – สร้าง `TexturePaint` ครั้งเดียวแล้วนำไปใช้กับรูปใดก็ได้

## แพทเทิร์นการเรียงเทกซ์เจอร์คืออะไร?
แพทเทิร์นการเรียงเทกซ์เจอร์ทำการซ้ำภาพขนาดเล็ก (ไทล์) ทั่วพื้นที่ที่ใหญ่กว่า ทำให้คุณ **เติมรูปด้วยเทกซ์เจอร์** ได้โดยไม่ต้องวาดไทล์แต่ละอันด้วยตนเอง เทคนิคนี้เหมาะสำหรับพื้นหลัง, การเติมสี, และเอฟเฟกต์ข้อความตกแต่งใน PostScript

## ทำไมต้องใช้ Aspose.Page for Java?
- **การเรนเดอร์ไม่มีการพึ่งพาไลบรารีภายนอก** – ไม่ต้องใช้ PostScript interpreter ภายนอก  
- **ควบคุมกราฟิกได้เต็มที่** – ผสานรูปเวกเตอร์, ข้อความ, และเทกซ์เจอร์บิตแมพได้  
- **ข้ามแพลตฟอร์ม** – ทำงานบนระบบปฏิบัติการใดก็ได้ที่รองรับ Java  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามบทแนะนำ ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาโปรแกรม Java  
- ความคุ้นเคยกับโครงสร้างเอกสาร PostScript  
- ไลบรารี Aspose.Page for Java ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/java/)

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าแพ็กเกจที่จำเป็นสำหรับโครงการ Java ของคุณ:

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

## ขั้นตอนที่ 1: สร้างเอกสาร PostScript
สร้างเอกสาร PostScript ใหม่โดยระบุสตรีมเอาต์พุตและตัวเลือกการบันทึก ตรวจสอบให้แน่ใจว่าคุณได้กำหนดเส้นทางที่จำเป็นแล้ว

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

## ขั้นตอนที่ 2: ตั้งค่าสภาพแวดล้อมกราฟิก
ตั้งค่าสภาพแวดล้อมกราฟิกโดยย้ายจุดกำเนิดและสร้าง `BufferedImage` จากไฟล์เทกซ์เจอร์

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

## ขั้นตอนที่ 3: สร้างแปรงเทกซ์เจอร์
กำหนดแปรงเทกซ์เจอร์จากภาพ โดยระบุพื้นที่ที่ต้องการให้เทกซ์เจอร์ครอบคลุม

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

## ขั้นตอนที่ 4: วาดและเติมรูป
สร้างสี่เหลี่ยมและ **เติมรูปด้วยเทกซ์เจอร์** ด้วยแปรงที่กำหนดไว้ นอกจากนี้ยังวาดและรอบรูปเพื่อความสวยงาม

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

## ขั้นตอนที่ 5: เพิ่มข้อความด้วยแพทเทิร์นเทกซ์เจอร์
เพิ่มข้อความลงในเอกสารและสาธิต **วิธีเติมเทกซ์เจอร์** บน glyphs ปรับแต่งฟอนต์, ตำแหน่ง, และพารามิเตอร์อื่น ๆ ตามต้องการ

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## ขั้นตอนที่ 6: บันทึกและปิด
สรุปกระบวนการโดยปิดหน้าปัจจุบัน, บันทึกเอกสาร, และตรวจสอบให้การทำงานเป็นไปอย่างราบรื่น

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **ไฟล์เทกซ์เจอร์หาย** – ตรวจสอบว่าเส้นทางไปยัง `TestTexture.bmp` ถูกต้องและไฟล์เข้าถึงได้  
- **ขนาดภาพไม่ตรง** – หากเทกซ์เจอร์ดูบิดเบี้ยว ปรับ `imageArea` ให้ตรงกับขนาดภาพต้นฉบับ  
- **ประสิทธิภาพ** – ใช้ตัวแปร `TexturePaint` เดียวกันหลายรูปเพื่อหลีกเลี่ยงการสร้างอ็อบเจ็กต์ซ้ำ ๆ  

## คำถามที่พบบ่อย

**ถาม: Aspose.Page for Java เหมาะกับผู้เริ่มต้นหรือไม่?**  
ตอบ: แน่นอน! Aspose.Page for Java มีเอกสารครบถ้วน ทำให้ผู้พัฒนาทุกระดับสามารถใช้งานได้

**ถาม: สามารถรวม Aspose.Page for Java เข้าในโครงการ Java ที่มีอยู่แล้วได้หรือไม่?**  
ตอบ: ได้ คุณสามารถรวม Aspose.Page for Java เข้าในโครงการของคุณได้ง่าย ๆ ตามเอกสารที่ให้ไว้ [ที่นี่](https://reference.aspose.com/page/java/)

**ถาม: จะหาแหล่งสนับสนุนหรือพูดคุยเกี่ยวกับ Aspose.Page ได้จากที่ไหน?**  
ตอบ: เยี่ยมชม [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อเข้าร่วมชุมชนและขอความช่วยเหลือ

**ถาม: มีรุ่นทดลองฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
ตอบ: มี คุณสามารถสำรวจรุ่นทดลองได้ [ที่นี่](https://releases.aspose.com/)

**ถาม: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
ตอบ: เยี่ยมชม [ลิงก์นี้](https://purchase.aspose.com/temporary-license/) เพื่อขอรับลิขสิทธิ์ชั่วคราว

## สรุป
ขอแสดงความยินดี! คุณได้เรียนรู้ **วิธีเพิ่มเทกซ์เจอร์** แบบเรียงแพทเทิร์นในเอกสาร Java PostScript ด้วย Aspose.Page for Java แล้ว อย่าลังเลที่จะสำรวจตัวเลือกการปรับแต่งเพิ่มเติม—ลองใช้ไทล์บิตแมพต่าง ๆ, ปรับสเกล, และทำการผสมผสานเพื่อเปิดศักยภาพเต็มที่ของการเติมเทกซ์เจอร์

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-17  
**ทดสอบด้วย:** Aspose.Page for Java 24.12 (ล่าสุด)  
**ผู้เขียน:** Aspose  

---