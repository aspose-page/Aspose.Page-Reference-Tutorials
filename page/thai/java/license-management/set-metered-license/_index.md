---
date: 2025-12-03
description: เรียนรู้วิธีบันทึก EPS เป็น PNG ด้วย Aspose.Page สำหรับ Java พร้อมการกำหนดใบอนุญาตแบบมิเตอร์
  คู่มือขั้นตอนต่อขั้นตอนพร้อมตัวอย่างโค้ดเต็ม
language: th
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: บันทึก EPS เป็น PNG ด้วย Aspose.Page Java (ลิขสิทธิ์แบบจ่ายตามการใช้งาน)
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# บันทึก EPS เป็น PNG ด้วย Aspose.Page Java (Metered License)

## บทนำ
หากคุณต้องการ **บันทึก EPS เป็น PNG** ในแอปพลิเคชัน Java และต้องการวิธีจัดการไลเซนส์ที่ง่ายดาย คุณมาถูกที่แล้ว บทเรียนนี้จะพาคุณผ่านการตั้งค่าไลเซนส์แบบ Metered สำหรับ Aspose.Page, การโหลดไฟล์ PostScript (EPS) และการแปลงเป็นภาพ PNG — ทั้งหมดด้วยขั้นตอนสั้น ๆ ที่คุณสามารถทำตามได้ทันที

## คำตอบอย่างรวดเร็ว
- **“บันทึก EPS เป็น PNG” หมายถึงอะไร?** มันจะแปลงไฟล์ EPS แบบเวกเตอร์ให้เป็นภาพ PNG แบบแรสเตอร์  
- **ทำไมต้องใช้ไลเซนส์แบบ Metered?** คุณจ่ายเฉพาะจำนวนหน้าที่ประมวลผล เหมาะกับงานที่มีปริมาณเปลี่ยนแปลง  
- **ต้องการการเชื่อมต่ออินเทอร์เน็ตหรือไม่?** ไม่จำเป็น คีย์ Metered จะตรวจสอบในเครื่อง  
- **ต้องใช้ Java เวอร์ชันใด?** Java 8 หรือสูงกว่า  
- **การตั้งค่าต้องใช้เวลานานเท่าไหร่?** ประมาณ 10 นาทีสำหรับการนำไปใช้พื้นฐาน

## “บันทึก EPS เป็น PNG” คืออะไร?
การบันทึก EPS เป็น PNG จะเปลี่ยนเอกสาร Encapsulated PostScript ที่ขยายได้เป็นรูปแบบบิตแมปที่ได้รับการสนับสนุนอย่างกว้างขวาง PNG รักษาความโปร่งใสและให้การบีบอัดแบบไม่มีการสูญเสีย ทำให้เหมาะสำหรับกราฟิกเว็บ, รูปภาพขนาดย่อ, และตัวอย่างการพิมพ์

## ทำไมต้องใช้ Aspose.Page สำหรับงานนี้?
- **Pure Java API** – ไม่ต้องพึ่งพาไลบรารีเนทีฟ  
- **ความแม่นยำสูง** – การเรนเดอร์กราฟิกเวกเตอร์เป็นภาพได้อย่างถูกต้อง  
- **ไลเซนส์แบบ Metered** – จ่ายเฉพาะที่คุณแปลงจริง  
- **รองรับหลายรูปแบบผลลัพธ์** – PNG, JPEG, TIFF ฯลฯ  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานด้านการเขียนโปรแกรม Java  
- ไลบรารี Aspose.Page ติดตั้งแล้ว – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/java/)  
- คีย์ Metered สาธารณะและส่วนตัว ซึ่งสามารถรับได้จากบัญชี Aspose ของคุณ  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่จำเป็น คัดลอกบล็อกการนำเข้าให้ตรงกับตัวอย่างเพื่อให้โค้ดคอมไพล์ได้โดยไม่มีการเปลี่ยนแปลง

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## ขั้นตอนที่ 1: เริ่มต้น Document และรูปแบบภาพ
ที่นี่เราตั้งค่าคีย์ Metered และกำหนดรูปแบบผลลัพธ์เป็น PNG ซึ่งเป็นพื้นฐานของการ **บันทึก EPS เป็น PNG**

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

## ขั้นตอนที่ 2: เริ่มต้น PostScript Input Stream
เปิดไฟล์ EPS ที่ต้องการแปลง สตรีมนี้จะส่งข้อมูลเข้า Aspose.Page

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## ขั้นตอนที่ 3: ตรวจสอบไลเซนส์ของ Document
ตรวจสอบให้แน่ใจว่าไลเซนส์แบบ Metered ถูกนำมาใช้อย่างถูกต้องก่อนทำการประมวลผลใด ๆ

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## ขั้นตอนที่ 4: เริ่มต้น Options และ Image Device
สร้างอ็อบเจ็กต์ Options ที่ควบคุมการตั้งค่าการแปลงและอุปกรณ์ที่รับภาพที่เรนเดอร์แล้ว

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## ขั้นตอนที่ 5: บันทึกไฟล์ EPS เป็นภาพ
นี่คือการเรียก **บันทึก EPS เป็น PNG** หลัก ๆ เอกสารจะถูกเรนเดอร์เข้าสู่ Image Device ตาม Options ที่กำหนด

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## ขั้นตอนที่ 6: ดึงและบันทึกไบต์ของภาพ
ดึงไบต์ PNG จากอุปกรณ์และเขียนลงไฟล์บนดิสก์

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
| **Output file is empty** | `device.getImagesBytes()` คืนค่า `null` | ยืนยันว่าไฟล์ EPS ถูกต้องและ `ImageSaveOptions` ไม่ได้ตั้งค่าแคนวาสขนาดศูนย์ |
| **OutOfMemoryError on large EPS** | การเรนเดอร์ไฟล์เวกเตอร์ขนาดใหญ่ใช้หน่วยความจำมาก | ประมวลผลหน้าแบบทีละหน้า หรือเพิ่มขนาด heap ของ JVM (`-Xmx2g`) |

## คำถามที่พบบ่อย

**ถาม: จะรับคีย์ Metered สาธารณะและส่วนตัวได้อย่างไร?**  
ตอบ: คุณสามารถรับคีย์เหล่านี้ได้จากบัญชี Aspose ของคุณ

**ถาม: ไลบรารี Aspose.Page มีให้ใช้ฟรีหรือไม่?**  
ตอบ: Aspose.Page มีทั้งรุ่นทดลองใช้ฟรีและรุ่นชำระเงิน เยี่ยมชม [here](https://releases.aspose.com/) เพื่อดาวน์โหลดรุ่นทดลอง

**ถาม: สามารถใช้ Aspose.Page ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
ตอบ: ได้, Aspose.Page มีไลเซนส์เชิงพาณิชย์ คุณสามารถซื้อได้ที่ [here](https://purchase.aspose.com/buy)

**ถาม: จะหาเอกสารเพิ่มเติมได้จากที่ไหน?**  
ตอบ: ดูเอกสารเพิ่มเติมได้ที่ [here](https://reference.aspose.com/page/java/)

**ถาม: จะขอไลเซนส์ชั่วคราวได้อย่างไร?**  
ตอบ: ไลเซนส์ชั่วคราวสามารถขอได้ที่ [here](https://purchase.aspose.com/temporary-license/)

---

**อัปเดตล่าสุด:** 2025-12-03  
**ทดสอบกับ:** Aspose.Page 24.12 for Java  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
