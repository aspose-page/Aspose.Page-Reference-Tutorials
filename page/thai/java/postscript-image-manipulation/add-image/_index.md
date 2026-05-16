---
date: 2026-02-15
description: เรียนรู้วิธีสร้างเอกสาร PostScript ด้วย Java และสร้างไฟล์เอกสาร PostScript
  พร้อมการแปลงภาพและการหมุนภาพโดยใช้ Aspose.Page สำหรับ Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: สร้าง PostScript ด้วย Java – เพิ่มรูปภาพใน PostScript ของ Java
url: /th/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง PostScript Java – เพิ่มรูปภาพใน Java PostScript

## คำแนะนำ
ในบทเรียนนี้ คุณจะได้เรียนรู้วิธี **สร้าง postscript java** เอกสารและฝังรูปภาพโดยใช้ไลบรารี Aspose.Page for Java เราจะเดินผ่านแต่ละขั้นตอน ตั้งแต่การเริ่มต้นไฟล์ PostScript ใหม่จนถึงการใช้การแปลง **translate and rotate image** สุดท้าย คุณจะสามารถสร้างไฟล์ PostScript อย่างอัตโนมัติและควบคุมการวางรูปภาพด้วยความแม่นยำระดับพิกเซล—เหมาะสำหรับการสร้างรายงานอัตโนมัติ, กระบวนการพิมพ์, หรือสถานการณ์ใด ๆ ที่ต้อง **generate postscript document** จาก Java

## คำตอบสั้น
- **ต้องใช้ไลบรารีอะไร?** Aspose.Page for Java  
- **สามารถเพิ่มรูปหลายรูปได้หรือไม่?** ได้ – ทำซ้ำขั้นตอนการแปลงและวาด  
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีสำหรับการทดสอบ; ต้องมีลิขสิทธิ์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน Java ใด?** Java 8 ขึ้นไป  
- **รองรับการหมุนรูปภาพหรือไม่?** แน่นอน – ใช้ `AffineTransform.rotate()`  

## create postscript java คืออะไร?
การทำงาน **create postscript java** จะสร้างไฟล์อธิบายหน้ากระดาษ PostScript ที่บรรจุข้อความ, กราฟิกเวกเตอร์, และรูปภาพแรสเตอร์ ด้วย Aspose.Page คุณสามารถสร้างไฟล์เหล่านี้โดยตรงจากโค้ด Java ทำให้คุณมีการควบคุมโปรแกรมเต็มรูปแบบต่อการจัดวาง, การสเกล, และการหมุนโดยไม่ต้องใช้ตัวแปล PostScript แยกต่างหาก

## ทำไมต้องใช้ Aspose.Page สำหรับการจัดการรูปภาพ?
- **API ระดับสูง:** แยกคำสั่ง PostScript ระดับล่างเป็นเมธอด Java ที่ง่ายต่อการใช้  
- **ข้ามแพลตฟอร์ม:** ทำงานบน OS ใดก็ได้ที่รองรับ Java  
- **ควบคุมกราฟิกสเตตเต็มรูปแบบ:** Save, restore, translate, scale, และ rotate กราฟิกได้ตามต้องการ  
- **ไม่มีการพึ่งพาภายนอก:** จัดการการโหลดรูป, การแปลงฟอร์แมต, และการฝังรูปภายในไลบรารี  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:

- Java Development Kit (JDK) ติดตั้งบนระบบของคุณ  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/java/)  
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java  

## นำเข้าแพ็กเกจ
เพื่อเริ่มต้น ให้นำเข้าแพ็กเกจที่จำเป็นในโปรเจกต์ Java ของคุณ ใช้โค้ดตัวอย่างต่อไปนี้เป็นแนวทาง:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ขั้นตอนที่ 1: เขียน Graphics Save
ขั้นตอนแรกคือการเขียนคำสั่ง graphics save ลงในเอกสาร เพื่อให้แน่ใจว่าการแปลงหรือการแก้ไขใด ๆ ที่ทำต่อไปสามารถย้อนกลับได้หากต้องการ

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## ขั้นตอนที่ 2: Translate and Transform (translate and rotate image)
ต่อไป ให้ทำการ translate เอกสารและสร้างอ็อบเจ็กต์ `BufferedImage` จากไฟล์รูปภาพ จากนั้นใช้ชุดการแปลงเช่นการสเกลและการหมุนด้วย `AffineTransform` นี่คือขั้นตอนที่ทำการ **translate and rotate image**

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## ขั้นตอนที่ 3: เพิ่มรูปภาพลงในเอกสาร
ตอนนี้ให้เพิ่มรูปภาพที่ผ่านการแปลงลงในเอกสาร

```java
document.drawImage(image, transform, null);
```

## ขั้นตอนที่ 4: เขียน Graphics Restore
หลังจากเพิ่มรูปภาพแล้ว ให้เขียนคำสั่ง graphics restore เพื่อสรุปการเปลี่ยนแปลงที่ทำไว้

```java
document.writeGraphicsRestore();
```

## ขั้นตอนที่ 5: ปิดหน้าและบันทึก
ปิดหน้าปัจจุบันและบันทึกเอกสาร

```java
document.closePage();
document.save();
```

คุณสามารถทำซ้ำขั้นตอนเหล่านี้เพื่อเพิ่มรูปหลายรูปหรือปรับแต่งการแปลงตามความต้องการของคุณได้

## ปัญหาที่พบบ่อยและวิธีแก้
- **FileNotFoundException:** ตรวจสอบให้แน่ใจว่าเส้นทาง `dataDir` ลงท้ายด้วยตัวคั่นไฟล์ (`/` หรือ `\\`) และชื่อไฟล์รูปภาพตรงกันอย่างแม่นยำ  
- **ImageIO.read คืนค่า null:** ยืนยันว่าฟอร์แมตของรูปภาพที่ใช้ได้รับการสนับสนุน (เช่น JPEG, PNG)  
- **มุมการหมุนไม่ถูกต้อง:** `AffineTransform.rotate` ต้องการค่าเป็นเรเดียน แปลงจากองศาเป็นเรเดียนด้วย (`Math.toRadians(degrees)`) หากจำเป็น  

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.Page for Java กับภาษาโปรแกรมอื่นได้หรือไม่?**  
ตอบ: Aspose.Page รองรับหลัก ๆ แค่ Java แต่ก็มีเวอร์ชันสำหรับภาษาอื่น ๆ ให้เลือกใช้เช่นกัน  

**ถาม: มีการทดลองใช้ฟรีสำหรับ Aspose.Page for Java หรือไม่?**  
ตอบ: มี, คุณสามารถเข้าถึงการทดลองใช้ได้จาก [ที่นี่](https://releases.aspose.com/)  

**ถาม: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.Page for Java ได้อย่างไร?**  
ตอบ: คุณสามารถรับลิขสิทธิ์ชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)  

**ถาม: จะหาชุมชนสนับสนุนและการสนทนาเกี่ยวกับ Aspose.Page for Java ได้จากที่ไหน?**  
ตอบ: เยี่ยมชม [Aspose.Page Forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชน  

**ถาม: มีแหล่งข้อมูลเพิ่มเติมสำหรับการซื้อ Aspose.Page for Java หรือไม่?**  
ตอบ: คุณสามารถซื้อไลบรารีได้จาก [ที่นี่](https://purchase.aspose.com/buy)  

## สรุป
ยินดีด้วย! คุณได้เรียนรู้วิธี **สร้าง postscript java** เอกสารและฝังรูปภาพโดยใช้ Aspose.Page for Java แล้ว สำรวจ [เอกสารประกอบ](https://reference.aspose.com/page/java/) เพื่อค้นหาฟีเจอร์ขั้นสูงเพิ่มเติม เช่น กราฟิกเวกเตอร์, การเรนเดอร์ข้อความ, และขนาดหน้ากระดาษที่กำหนดเอง

---

**อัปเดตล่าสุด:** 2026-02-15  
**ทดสอบกับ:** Aspose.Page for Java 23.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}