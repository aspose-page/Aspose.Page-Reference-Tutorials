---
title: การรวมใบอนุญาตแบบมิเตอร์กับ Aspose.Page Java ได้อย่างง่ายดาย
linktitle: ตั้งค่าใบอนุญาตแบบมิเตอร์ใน Java
second_title: Aspose.Page Java API
description: สำรวจการผสานรวม Aspose.Page กับ Java ได้อย่างราบรื่น ตั้งค่าใบอนุญาตแบบมิเตอร์ได้อย่างง่ายดายและเพิ่มความสามารถในการประมวลผลเอกสารของคุณ
weight: 10
url: /th/java/license-management/set-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การรวมใบอนุญาตแบบมิเตอร์กับ Aspose.Page Java ได้อย่างง่ายดาย

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมของเราเกี่ยวกับการตั้งค่าใบอนุญาตแบบมิเตอร์ใน Java โดยใช้ Aspose.Page หากคุณต้องการปรับปรุงความสามารถในการประมวลผลเอกสารและรับประกันการผสานรวมกับ Aspose.Page ได้อย่างราบรื่น แสดงว่าคุณมาถูกที่แล้ว ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการ โดยแบ่งแต่ละขั้นตอนออกเป็นส่วนที่ย่อยง่าย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้งไลบรารี Aspose.Page แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/page/java/).
- กุญแจสาธารณะและกุญแจส่วนตัวแบบมิเตอร์ ซึ่งคุณสามารถรับผ่านบัญชี Aspose ของคุณ
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นสำหรับโปรแกรม Java ของเรา ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Page เข้ากับโปรเจ็กต์ของคุณ
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## ขั้นตอนที่ 1: เริ่มต้นรูปแบบเอกสารและรูปภาพ
ขั้นตอนแรกคือการตั้งค่าเอกสารและกำหนดรูปแบบภาพที่ต้องการ
```java
// ตั้งค่าคีย์สาธารณะและคีย์ส่วนตัวแบบมิเตอร์
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// เข้าถึงคุณสมบัติ setMeteredKey และส่งคีย์สาธารณะและคีย์ส่วนตัวเป็นพารามิเตอร์
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## ขั้นตอนที่ 2: เริ่มต้นสตรีมอินพุต PostScript
ในขั้นตอนนี้ เราจะเริ่มต้นสตรีมอินพุต PostScript สำหรับการประมวลผล
```java
// เริ่มต้นสตรีมอินพุต PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## ขั้นตอนที่ 3: ตรวจสอบใบอนุญาตเอกสาร
ก่อนดำเนินการต่อ สิ่งสำคัญคือต้องตรวจสอบว่าเอกสารได้รับอนุญาตอย่างถูกต้องหรือไม่
```java
// ตรวจสอบว่าเอกสารได้รับอนุญาตหรือไม่
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## ขั้นตอนที่ 4: เริ่มต้นตัวเลือกและอุปกรณ์รูปภาพ
ตอนนี้ เรามาเริ่มต้นตัวเลือกและอุปกรณ์รูปภาพด้วยพารามิเตอร์เริ่มต้นกัน
```java
// เริ่มต้นวัตถุตัวเลือกด้วยพารามิเตอร์เริ่มต้น
ImageSaveOptions options = new ImageSaveOptions();
// เริ่มต้นวัตถุ ImageDevice ด้วยพารามิเตอร์เริ่มต้น
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## ขั้นตอนที่ 5: บันทึกไฟล์ EPS เป็นรูปภาพ
บันทึกไฟล์ EPS เป็นรูปภาพโดยใช้ตัวเลือกและอุปกรณ์ที่กำหนดไว้
```java
// บันทึกไฟล์ EPS เป็นรูปภาพ
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## ขั้นตอนที่ 6: รับและบันทึกไบต์รูปภาพ
ดึงข้อมูลไบต์ของรูปภาพและบันทึกลงในไฟล์
```java
// รับไบต์รูปภาพ อาร์เรย์หนึ่งไบต์สำหรับหนึ่งหน้า ในกรณีของเรา เรามีหนึ่งหน้า
byte[][] imagesBytes = device.getImagesBytes();
// บันทึกไบต์รูปภาพลงในไฟล์
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## บทสรุป
ยินดีด้วย! คุณได้ตั้งค่าใบอนุญาตแบบคิดค่าบริการตามปริมาณข้อมูลใน Java โดยใช้ Aspose.Page เรียบร้อยแล้ว บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนเพื่อให้แน่ใจว่ากระบวนการรวมระบบจะราบรื่น
## คำถามที่พบบ่อย
### ถาม: ฉันจะรับคีย์สาธารณะและคีย์ส่วนตัวแบบคิดค่าบริการตามปริมาณข้อมูลได้อย่างไร
คุณสามารถรับกุญแจเหล่านี้ได้ผ่านบัญชี Aspose ของคุณ
### ถาม: ไลบรารี Aspose.Page ฟรีหรือไม่
 Aspose.Page มีทั้งเวอร์ชันทดลองใช้ฟรีและเวอร์ชันชำระเงิน เยี่ยม[ที่นี่](https://releases.aspose.com/) เพื่อทดลองใช้ฟรี
### ถาม: ฉันสามารถใช้ Aspose.Page สำหรับโครงการเชิงพาณิชย์ได้หรือไม่
 ใช่ Aspose.Page เสนอใบอนุญาตเชิงพาณิชย์ คุณสามารถซื้อได้[ที่นี่](https://purchase.aspose.com/buy).
### ถาม: ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?
 โปรดดูเอกสารประกอบ[ที่นี่](https://reference.aspose.com/page/java/).
### ถาม: ฉันจะรับใบอนุญาตชั่วคราวได้อย่างไร
 สามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
