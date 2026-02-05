---
date: 2026-02-05
description: เรียนรู้วิธีบันทึก EPS เป็น PNG ด้วย Aspose.Page สำหรับ Java พร้อมการกำหนดค่าใบอนุญาตแบบมิเตอร์
  คู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ดเต็ม
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: บันทึก EPS เป็น PNG ด้วย Aspose.Page Java (ใบอนุญาตแบบจ่ายตามการใช้งาน)
url: /th/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึก EPS เป็น PNG ด้วย Aspose.Page Java (ใบอนุญาตแบบ Metered)

## คำแนะนำ
หากคุณต้องการ **บันทึก EPS เป็น PNG** ในแอปพลิเคชัน Java และต้องการวิธีจัดการใบอนุญาตที่ไม่ยุ่งยาก คุณมาถูกที่แล้ว บทเรียนนี้จะพาคุณผ่านการตั้งค่าใบอนุญาตแบบ Metered สำหรับ Aspose.Page, การโหลดไฟล์ PostScript (EPS) และการแปลงเป็นภาพ PNG — ทั้งหมดด้วยขั้นตอนสั้น ๆ ที่คุณทำตามได้ทันที เมื่อเสร็จสิ้นคุณจะเข้าใจวิธี **เรนเดอร์ EPS เป็น PNG** อย่างมีประสิทธิภาพและ **เขียนไฟล์ PNG ด้วย Java** ที่ทำงานได้ในสภาพแวดล้อมการผลิต

## คำตอบสั้น ๆ
- **“บันทึก EPS เป็น PNG” หมายความว่าอย่างไร?** มันแปลงไฟล์ EPS แบบเวกเตอร์ให้เป็นภาพ PNG แบบแรสเตอร์  
- **ทำไมต้องใช้ใบอนุญาตแบบ Metered?** คุณจ่ายเฉพาะจำนวนหน้าที่ประมวลผล เหมาะกับงานที่มีปริมาณเปลี่ยนแปลง  
- **ต้องการการเชื่อมต่ออินเทอร์เน็ตหรือไม่?** ไม่จำเป็น คีย์ Metered ตรวจสอบได้ภายในเครื่อง  
- **ต้องใช้ Java เวอร์ชันใด?** Java 8 หรือสูงกว่า  
- **การตั้งค่าต้องใช้เวลานานเท่าไหร่?** ประมาณ 10 นาทีสำหรับการทำงานพื้นฐาน  

## “บันทึก EPS เป็น PNG” คืออะไร?
การบันทึก EPS เป็น PNG จะเปลี่ยนเอกสาร Encapsulated PostScript ที่สามารถขยายได้ให้เป็นรูปแบบบิตแมปที่ได้รับการสนับสนุนอย่างกว้างขวาง PNG รักษาความโปร่งใสและให้การบีบอัดแบบไม่มีการสูญเสีย ทำให้เหมาะกับกราฟิกเว็บ, รูปย่อ, และตัวอย่างการพิมพ์

## ทำไมต้องเรนเดอร์ EPS เป็น PNG ด้วย Aspose.Page?
- **Pure Java API** – ไม่มีการพึ่งพาไลบรารีเนทีฟ จึงสามารถทำงานได้ทุกที่ที่ JVM รองรับ  
- **การเรนเดอร์คุณภาพสูง** – กราฟิกเวกเตอร์ถูกแรสเตอร์อย่างแม่นยำ คงคุณภาพเส้น  
- **ใบอนุญาตแบบ Metered** – จ่ายเฉพาะที่คุณแปลง ทำให้ค่าใช้จ่ายคาดเดาได้  
- **ตัวเลือกผลลัพธ์หลายรูปแบบ** – นอกจาก PNG ยังสามารถสร้าง JPEG, TIFF ฯลฯ ให้คุณเลือกใช้ตามโครงการต่าง ๆ  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมี:

- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  
- ไลบรารี Aspose.Page ติดตั้งแล้ว – ดาวน์โหลดจาก [ที่นี่](https://releases.aspose.com/page/java/)  
- คีย์ Metered สาธารณะและส่วนตัว ซึ่งสามารถรับได้จากบัญชี Aspose ของคุณ  

## นำเข้าแพ็กเกจ
แรกสุด ให้นำเข้าคลาสที่จำเป็น รักษาบล็อกการนำเข้าให้เหมือนเดิมเพื่อให้โค้ดคอมไพล์โดยไม่มีการเปลี่ยนแปลง

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## วิธีบันทึก EPS เป็น PNG ด้วย Aspose.Page Java
ต่อไปนี้เป็นคำแนะนำแบบขั้นตอนต่อขั้นตอนที่รวมการตั้งค่าใบอนุญาต, การโหลด, การเรนเดอร์, และการเขียนไฟล์ PNG สุดท้าย

### ขั้นตอนที่ 1: เริ่มต้น Document และรูปแบบภาพ
ที่นี่เราตั้งค่าคีย์ Metered และกำหนดรูปแบบผลลัพธ์ (PNG) ซึ่งเป็นพื้นฐานของการ **บันทึก EPS เป็น PNG**

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### ขั้นตอนที่ 2: เริ่มต้น PostScript Input Stream
เปิดไฟล์ EPS ที่ต้องการแปลง สตรีมนี้จะส่งข้อมูลเข้า Aspose.Page

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### ขั้นตอนที่ 3: ตรวจสอบใบอนุญาต Document
ตรวจสอบเสมอว่าใบอนุญาตแบบ Metered ถูกนำไปใช้อย่างถูกต้องก่อนทำการประมวลผล

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### ขั้นตอนที่ 4: เริ่มต้น Options และ Image Device
สร้างอ็อบเจกต์ Options ที่ควบคุมการตั้งค่าการแปลงและอุปกรณ์ที่รับภาพที่เรนเดอร์แล้ว

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### ขั้นตอนที่ 5: บันทึกไฟล์ EPS เป็นภาพ
นี่คือการเรียก **บันทึก EPS เป็น PNG** หลัก ๆ เอกสารจะถูกเรนเดอร์เข้าสู่ Image Device ด้วย Options ที่กำหนดไว้

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### ขั้นตอนที่ 6: ดึงและบันทึกไบต์ของภาพ
ดึงไบต์ PNG จากอุปกรณ์และเขียนลงไฟล์บนดิสก์ ขั้นตอนนี้แสดงวิธี **เขียนไฟล์ PNG ด้วย Java** อย่างปลอดภัย

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **License not recognized** | คีย์ไม่ถูกต้องหรือเรียงลำดับผิด | ตรวจสอบสตริงคีย์สาธารณะ/ส่วนตัวและให้แน่ใจว่า `setMeteredKey` ถูกเรียกก่อนการประมวลผลใด ๆ |
| **Output file is empty** | `device.getImagesBytes()` คืนค่า `null` | ยืนยันว่าไฟล์ EPS ถูกต้องและ `ImageSaveOptions` ไม่ได้ตั้งค่าเป็นแคนวาสขนาดศูนย์ |
| **OutOfMemoryError on large EPS** | การเรนเดอร์ไฟล์เวกเตอร์ขนาดใหญ่ใช้หน่วยความจำมาก | ประมวลผลหน้าแบบหนึ่งต่อหนึ่งหรือเพิ่มขนาด heap ของ JVM (`-Xmx2g`) |

## คำถามที่พบบ่อย

**ถาม: จะรับคีย์ Metered สาธารณะและส่วนตัวได้อย่างไร?**  
ตอบ: สามารถรับคีย์เหล่านี้ได้จากบัญชี Aspose ของคุณ

**ถาม: ไลบรารี Aspose.Page มีให้ใช้ฟรีหรือไม่?**  
ตอบ: Aspose.Page มีทั้งรุ่นทดลองฟรีและรุ่นที่ต้องชำระเงิน เยี่ยมชม [ที่นี่](https://releases.aspose.com/) เพื่อรับรุ่นทดลองฟรี

**ถาม: สามารถใช้ Aspose.Page ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
ตอบ: ได้, Aspose.Page มีใบอนุญาตเชิงพาณิชย์ คุณสามารถซื้อได้ [ที่นี่](https://purchase.aspose.com/buy)

**ถาม: จะหาข้อมูลเอกสารเพิ่มเติมได้จากที่ไหน?**  
ตอบ: ดูเอกสารเพิ่มเติมได้ที่ [ที่นี่](https://reference.aspose.com/page/java/)

**ถาม: จะขอใบอนุญาตชั่วคราวได้อย่างไร?**  
ตอบ: ใบอนุญาตชั่วคราวสามารถรับได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

**ถาม: หากต้องแปลงไฟล์ EPS หลายหน้า จะทำอย่างไร?**  
ตอบ: วนลูปผ่านแต่ละหน้าโดยใช้ `device.getImagesBytes()` แล้วบันทึกแต่ละอาร์เรย์ไบต์เป็นไฟล์ PNG แยกกัน

**ถาม: สามารถเปลี่ยนคุณภาพหรือความลึกสีของ PNG ได้หรือไม่?**  
ตอบ: ได้, ตั้งค่า `ImageSaveOptions` (เช่น `options.setCompressionLevel(...)`) ก่อนเรียก `document.save(...)`

---

**อัปเดตล่าสุด:** 2025-12-03  
**ทดสอบกับ:** Aspose.Page 24.12 for Java  
**ผู้เขียน:** Aspose  

**อัปเดตล่าสุด:** 2026-02-05  
**ทดสอบกับ:** Aspose.Page 24.12 for Java (ล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}