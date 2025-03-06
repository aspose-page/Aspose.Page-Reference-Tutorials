---
title: การจัดการข้อความ Java Aspose.Page
linktitle: เพิ่มข้อความใน Java PostScript
second_title: Aspose.Page Java API
description: สำรวจพลังของ Aspose.Page สำหรับ Java ในบทช่วยสอนของเราเกี่ยวกับการเพิ่มข้อความลงในเอกสาร PostScript เรียนรู้การใช้ระบบและแบบอักษรที่กำหนดเองได้อย่างง่ายดาย
weight: 10
url: /th/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการข้อความ Java Aspose.Page

## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนในการเพิ่มข้อความใน Java PostScript โดยใช้ Aspose.Page สำหรับ Java Aspose.Page สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาจัดการเอกสาร PostScript ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มข้อความ การใช้ระบบและแบบอักษรที่กำหนดเอง การสรุปข้อความ และการใช้ลายเส้นเพื่อให้ได้ผลลัพธ์ที่ดึงดูดสายตา
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
-  ติดตั้ง Aspose.Page สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Page สำหรับหน้าดาวน์โหลด Java](https://releases.aspose.com/page/java/).
-  แบบอักษรที่จำเป็นมีอยู่ในโฟลเดอร์ที่ระบุ คุณสามารถค้นหาข้อมูลเพิ่มเติมได้ใน[Aspose.Page สำหรับเอกสาร Java](https://reference.aspose.com/page/java/).
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Page สำหรับ Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## ขั้นตอนที่ 1: ตั้งค่าเอกสาร
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// สร้างกระแสเอาท์พุทสำหรับเอกสาร PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// สร้างตัวเลือกการบันทึกด้วยขนาด A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// ข้อความที่จะเขียนลงในไฟล์ PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// สร้างเอกสาร PS 1 หน้าใหม่
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ขั้นตอนที่ 2: การใช้แบบอักษรของระบบเพื่อเติมข้อความ
```java
// การใช้แบบอักษรของระบบในการกรอกข้อความ
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// กรอกข้อความด้วยสีเริ่มต้นหรือสีที่กำหนดไว้แล้ว (สีดำ)
document.fillText(str, font, 50, 100);
// เติมข้อความด้วยสีน้ำเงิน
document.fillText(str, font, 50, 150, Color.BLUE);
```
## ขั้นตอนที่ 3: การใช้แบบอักษรที่กำหนดเองสำหรับการกรอกข้อความ
```java
// การใช้แบบอักษรที่กำหนดเองสำหรับการกรอกข้อความ
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// กรอกข้อความด้วยสีเริ่มต้นหรือสีที่กำหนดไว้แล้ว (สีดำ)
document.fillText(str, drFont, 50, 200);
// เติมข้อความด้วยสีน้ำเงิน
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## ขั้นตอนที่ 4: การสรุปข้อความด้วยแบบอักษรของระบบ
```java
// การใช้แบบอักษรของระบบสำหรับการสรุปข้อความ
document.outlineText(str, font, 50, 300);
// ข้อความเค้าร่างด้วยปากกาความกว้าง 2 จุด สีฟ้าม่วง
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// เติมข้อความสีส้มและขีดด้วยปากกาความกว้าง 2 จุดสีน้ำเงิน
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## ขั้นตอนที่ 5: การสรุปข้อความด้วยแบบอักษรที่กำหนดเอง
```java
// การใช้แบบอักษรที่กำหนดเองสำหรับการสรุปข้อความ
document.outlineText(str, drFont, 50, 450);
// ข้อความเค้าร่างด้วยปากกาความกว้าง 2 จุด สีฟ้าม่วง
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// เติมข้อความสีส้มและขีดด้วยปากกาความกว้าง 2 จุดสีน้ำเงิน
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## ขั้นตอนที่ 6: บันทึกเอกสาร
```java
// ปิดหน้าปัจจุบัน
document.closePage();
// บันทึกเอกสาร
document.save();
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มข้อความใน Java PostScript โดยใช้ Aspose.Page สำหรับ Java เรียบร้อยแล้ว ทดลองใช้แบบอักษร สี และตัวเลือกโครงร่างต่างๆ เพื่อปรับปรุงเอกสารของคุณให้ดียิ่งขึ้น
## คำถามที่พบบ่อย
### ฉันสามารถใช้แบบอักษรที่กำหนดเองกับ Aspose.Page สำหรับ Java ได้หรือไม่
 ได้ คุณสามารถใช้แบบอักษรที่กำหนดเองได้โดยการระบุชื่อแบบอักษรและขนาดใน`DrFont` ระดับ.
### ฉันจะเปลี่ยนสีของข้อความได้อย่างไร?
 คุณสามารถตั้งค่าสีที่ต้องการได้โดยใช้`Color` คลาสเมื่อเติมหรือสรุปข้อความ
### เป็นไปได้ไหมที่จะเพิ่มหลายหน้าในเอกสาร PostScript
อย่างแน่นอน! คุณสามารถสร้างหลายหน้าได้โดยทำซ้ำการสร้างเอกสารและบันทึกขั้นตอน
###  จุดประสงค์ของ..คืออะไร.`ExternalFontCache` class?
`ExternalFontCache` ใช้เพื่อดึงแบบอักษรที่กำหนดเอง เพื่อให้แน่ใจว่าพร้อมใช้งานสำหรับการจัดการข้อความ
### ฉันสามารถใช้จังหวะที่แตกต่างกันกับข้อความที่จัดเค้าร่างได้หรือไม่
 ใช่ คุณสามารถปรับแต่งความกว้างและสีของเส้นโครงร่างได้โดยใช้`Stroke` ชั้นเรียนและ`Color` ชั้นเรียนตามลำดับ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
