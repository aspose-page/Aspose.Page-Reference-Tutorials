---
date: 2025-12-25
description: เรียนรู้วิธีสร้างเอกสาร XPS ด้วย Java และเพิ่มไล่สีทแยงมุมที่สวยงามโดยใช้
  Aspose.Page คู่มือนี้ครอบคลุมวิธีการเพิ่มไล่สี, ใช้ไล่สีเชิงเส้น, และใช้ Aspose
  อย่างมีประสิทธิภาพ
linktitle: Add Diagonal Gradient in Java XPS
second_title: Aspose.Page Java API
title: วิธีสร้างเอกสาร XPS พร้อมไล่สีแนวทแยงใน Java
url: /th/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มไล่ระดับเชิงมุมใน Java XPS

## คำแนะนำ
ในการพัฒนา Java สมัยใหม่ การสร้างเอกสาร XPS ที่ดูเรียบหรูเป็นจุดเด่นสำคัญ ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีสร้างเอกสาร XPS** และเพิ่มไล่ระดับเชิงมุมด้วย Aspose.Page for Java เราจะเดินผ่านแต่ละขั้นตอน อธิบายว่าทำไมแต่ละส่วนสำคัญ และแสดงวิธี **เพิ่มเส้นทางไล่ระดับ**, **ใช้ไล่ระดับเชิงเส้น**, เพื่อให้ได้ผลลัพธ์ภาพระดับมืออาชีพอย่างรวดเร็ว.

## คำตอบด่วน
- **ไลบรารีหลักคืออะไร?** Aspose.Page for Java  
- **เมธอดใดที่เพิ่มไล่ระดับ?** `createLinearGradientBrush` พร้อม gradient stops  
- **ต้องการไลเซนส์หรือไม่?** รุ่นทดลองใช้ได้สำหรับการพัฒนา; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ใช้เวลานานเท่าไหร่ในการทำ?** ประมาณ 10‑15 นาทีสำหรับไล่ระดับเชิงมุมพื้นฐาน  
- **สามารถใช้กับเฟรมเวิร์ก Java อื่นได้หรือไม่?** ใช่, API ไม่ผูกกับเฟรมเวิร์กใด  

## ไล่ระดับเชิงมุมในเอกสาร XPS คืออะไร?
ไล่ระดับเชิงมุมเป็นการเปลี่ยนสีอย่างราบรื่นตามเส้นเอียง ทำให้รูปทรงมีความลึกและความน่าสนใจในเชิงภาพ ใน XPS ไล่ระดับจะถูกกำหนดโดย brush ที่มีหลาย gradient stop แต่ละ stop ระบุสีและตำแหน่งสัมพัทธ์ของมัน

## ทำไมต้องเพิ่มไล่ระดับเชิงมุมด้วย Aspose.Page?
- **คุณภาพภาพที่ยอดเยี่ยม** – ไล่ระดับถูกเรนเดอร์อย่างแม่นยำในรูปแบบ XPS.  
- **ความสอดคล้องข้ามแพลตฟอร์ม** – ไฟล์ XPS เดียวกันแสดงผลเหมือนกันบน Windows, macOS, และ Linux.  
- **API ที่ง่าย** – Aspose.Page แยกความซับซ้อนของสเปค XPS ระดับต่ำ ทำให้คุณมุ่งเน้นที่การออกแบบ.  

## ข้อกำหนดเบื้องต้น
- ความรู้พื้นฐานการเขียนโปรแกรม Java  
- ติดตั้ง JDK บนเครื่องของคุณ  
- ไลบรารี Aspose.Page for Java คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/page/java/)**.  
- IDE เช่น IntelliJ IDEA หรือ Eclipse  

## นำเข้าแพ็กเกจ
เริ่มต้นด้วยการนำเข้าคลาสที่คุณต้องการ การนำเข้าต่าง ๆ นี้ให้คุณเข้าถึง geometry, การจัดการไล่ระดับ, และการสร้างเอกสาร XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
สร้างโปรเจกต์ Java ใหม่ใน IDE ที่คุณชื่นชอบและเพิ่มไฟล์ JAR ของ Aspose.Page ไปยัง build path ของโปรเจกต์

## ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสาร
ระบุที่ตั้งที่ไฟล์ XPS ที่สร้างขึ้นจะถูกบันทึก

```java
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 3: สร้างเอกสาร XPS
สร้างอินสแตนซ์ของอ็อบเจ็กต์ XpsDocument – นี่คืออ็อบเจ็กต์หลักที่คุณจะทำงานเพื่อ **สร้างเอกสาร XPS** 

```java
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 4: เพิ่มเส้นทางไล่ระดับเชิงมุม
สร้างเส้นทางสี่เหลี่ยมที่รับไล่ระดับ การกำหนดรูปทรงของเส้นทางใช้คำสั่ง move‑line‑close อย่างง่าย

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## ขั้นตอนที่ 5: กำหนดจุดหยุดของไล่ระดับเชิงเส้น
ตั้งค่าสีและตำแหน่งของแต่ละจุดหยุด แต่ละ stop จะกำหนดจุดในไล่ระดับที่สีเฉพาะปรากฏ

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## ขั้นตอนที่ 6: ใช้ไล่ระดับเชิงเส้นกับเส้นทาง
ตอนนี้ **ใช้ไล่ระดับเชิงเส้น** กับเส้นทางที่คุณสร้าง brush จะถูกกำหนดโดยสองจุดที่กำหนดทิศทางของไล่ระดับ และจุดหยุดจะถูกแนบกับ brush

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## ขั้นตอนที่ 7: บันทึกเอกสาร
บันทึกไฟล์ XPS ลงดิสก์ ไฟล์จะมีสี่เหลี่ยมที่เติมด้วยไล่ระดับเชิงมุมที่คุณกำหนด

```java
doc.save(dataDir + "LinearGradient.xps");
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ทิศทางของไล่ระดับ** – ตรวจสอบให้แน่ใจว่าจุดเริ่มต้นและจุดสิ้นสุดของ brush สะท้อนเชิงมุมที่ต้องการ; การสลับจะทำให้ไล่ระดับกลับด้าน  
- **ความแม่นยำของสี** – Aspose ใช้ ARGB; หากต้องการความโปร่งใส ให้รวมช่อง alpha เมื่อสร้างสี  
- **เส้นทางไฟล์** – ควรใช้เส้นทางแบบ absolute เสมอหรือยืนยันว่าเส้นทาง relative ชี้ไปยังไดเรกทอรีที่สามารถเขียนได้  

## คำถามที่พบบ่อย
### คำถาม: ฉันสามารถใช้ Aspose.Page for Java กับเฟรมเวิร์ก Java อื่นได้หรือไม่?
Aspose.Page ถูกออกแบบให้ผสานรวมกับเฟรมเวิร์ก Java ต่าง ๆ ได้อย่างราบรื่น ทำให้เป็นตัวเลือกที่หลากหลายสำหรับโครงการของคุณ

### คำถาม: มีข้อพิจารณาเรื่องลิขสิทธิ์สำหรับ Aspose.Page หรือไม่?
ใช่, โปรดตรวจสอบรายละเอียดลิขสิทธิ์ที่ **[หน้าซื้อ Aspose.Page](https://purchase.aspose.com/buy)**.

### คำถาม: ฉันสามารถทดลองใช้ Aspose.Page for Java ก่อนซื้อได้หรือไม่?
แน่นอน! คุณสามารถสำรวจ **[เวอร์ชันทดลองฟรีที่นี่](https://releases.aspose.com/)**.

### คำถาม: ฉันจะรับการสนับสนุนหรือเชื่อมต่อกับชุมชน Aspose ได้อย่างไร?
เยี่ยมชม **[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39)** เพื่อเข้าร่วมกับชุมชนและขอความช่วยเหลือ

### คำถาม: มีการจัดให้มีไลเซนส์ชั่วคราวหรือไม่?
ใช่, คุณสามารถรับ **[ไลเซนส์ชั่วคราวที่นี่](https://purchase.aspose.com/temporary-license/)**.

## คำถามเพิ่มเติม (AI‑Optimized)

**Q: ฉันจะ **how to add gradient** ให้กับรูปทรง XPS ที่มีอยู่ได้อย่างไร?**  
A: สร้าง `XpsLinearGradientBrush`, กำหนด gradient stops, แล้วกำหนดให้กับ property `Fill` ของรูปทรงตามที่แสดงในขั้นตอน 6.

**Q: What does **apply linear gradient** actually do behind the scenes?**  
A: มันสร้างการกำหนดค่า brush ในแพ็กเกจ XPS ที่อ้างอิงจุดเริ่มต้น/สิ้นสุดและชุดของ gradient stops ซึ่ง viewer จะเรนเดอร์เป็นการเปลี่ยนสีอย่างราบรื่น.

**Q: Is there a quick way to **how to use aspose** for other XPS features?**  
A: ใช่, API ของ Aspose.Page มีเมธอดสำหรับเพิ่มรูปภาพ, ข้อความ, และรูปทรงกำหนดเอง—เพียงสำรวจคลาส `XpsDocument` เพื่อดูตัวช่วยเพิ่มเติม.

**Q: Can I **add gradient path** to non‑rectangular shapes?**  
A: แน่นอน. กำหนด geometry ใด ๆ ด้วย `createPathGeometry` แล้วตั้งค่า `Fill` ของมันเป็น gradient brush.

**Q: Does the gradient affect file size significantly?**  
A: เพียงเล็กน้อย; การกำหนดค่าไล่ระดับเป็น XML ที่มีน้ำหนักเบาในแพ็กเกจ XPS.

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}