---
date: 2026-02-23
description: เรียนรู้วิธีสร้างเอกสาร XPS ที่มีการไล่สีแนวทแยงโดยใช้ Aspose.Page สำหรับ
  .NET และยกระดับการนำเสนอภาพของคุณอย่างง่ายดาย
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: สร้าง XPS แบบไล่สีทแยงมุมด้วย Aspose.Page สำหรับ .NET
url: /th/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

 final content with all translations.

Check for any missed items: "Now, let’s dive into the code." translated.

Make sure to keep markdown formatting.

Proceed to final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง XPS แบบไล่สีแนวทแยงด้วย Aspose.Page สำหรับ .NET

## บทนำ

หากคุณต้องการ **สร้าง XPS แบบไล่สีแนวทแยง** ที่ดึงดูดสายตา Aspose.Page สำหรับ .NET ทำให้ขั้นตอนง่ายขึ้น ในบทเรียนนี้คุณจะได้เรียนรู้วิธีเพิ่มไล่สีแนวทแยงลงในเอกสาร XPS ทีละขั้นตอนโดยใช้ Aspose.Page API เมื่อเสร็จคุณจะมีรูปแบบที่นำกลับมาใช้ใหม่ได้และสามารถปรับใช้กับรูปทรงหรือโทนสีใดก็ได้

## คำตอบอย่างรวดเร็ว
- **วิธีการของ API ทำอะไร?** มันสร้างแปรงไล่สีเชิงเส้นที่ขยายแนวทแยงผ่านเส้นทาง.  
- **คลาสใดที่เป็นตัวแทนของเอกสาร XPS?** `XpsDocument`.  
- **ฉันต้องมีลิขสิทธิ์เพื่อรันตัวอย่างหรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานจริง.  
- **ฉันสามารถเปลี่ยนทิศทางของไล่สีได้หรือไม่?** ได้—ปรับค่า `PointF` เริ่มต้นและสิ้นสุด.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## อะไรคือ **create diagonal gradient xps**?
ไล่สีแนวทแยงคือการเปลี่ยนสีอย่างราบรื่นที่วิ่งจากมุมหนึ่งของรูปทรงไปยังมุมตรงข้าม ใน XPS เอฟเฟกต์นี้ทำได้โดยการใช้ `LinearGradientBrush` กับคุณสมบัติ fill ของเส้นทาง ไลบรารี Aspose.Page จะทำให้ซับซ้อนของการทำเครื่องหมาย XPS ระดับต่ำเป็นนามธรรม ช่วยให้คุณมุ่งเน้นที่สีและรูปทรงเรขาคณิต

## ทำไมต้องใช้ Aspose.Page สำหรับไล่สีแนวทแยง?
- **การเรนเดอร์ความละเอียดสูง** – ผลลัพธ์ตรงตามสเปคของ XPS อย่างแม่นยำ.  
- **การบูรณาการกับ .NET อย่างเต็มรูปแบบ** – ทำงานกับ C#, VB.NET และภาษาที่ใช้ .NET ใดก็ได้.  
- **ไม่มีการพึ่งพาภายนอก** – ทุกอย่างจัดการในกระบวนการเดียว ไม่ต้องใช้ COM หรือ Office.  
- **ขยายได้สำหรับเอกสารซับซ้อน** – คุณสามารถรวมหลายไล่สี, รูปภาพ, และข้อความบนหน้าเดียวกันได้.

## ข้อกำหนดเบื้องต้น

1. **Aspose.Page for .NET Library** – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/net/).  
2. **Development Environment** – Visual Studio, Rider หรือเครื่องมือแก้ไขใด ๆ ที่รองรับโครงการ .NET  

ตอนนี้เรามาเจาะลึกโค้ดกัน

## นำเข้า Namespaces

ในโครงการ .NET ของคุณ ให้รวม Namespaces ที่จำเป็นจากไลบรารี Aspose.Page เพื่อเข้าถึงคลาสและเมธอดที่ต้องการ เพิ่ม Namespaces ต่อไปนี้ที่ส่วนต้นของโค้ดของคุณ:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

เริ่มต้นด้วยการระบุเส้นทางไปยังไดเรกทอรีเอกสารของคุณ นี่คือที่ที่เอกสาร XPS ที่มีไล่สีแนวทแยงจะถูกบันทึก

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง XPS Document ใหม่

สร้าง `XpsDocument` ใหม่โดยใช้ไลบรารี Aspose.Page

```csharp
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 3: กำหนดสีไล่สี

สร้างรายการของอ็อบเจ็กต์ `XpsGradientStop` แต่ละอันแทนสีในไล่สีแนวทแยง

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## ขั้นตอนที่ 4: เพิ่มไล่สีแนวทแยงลงใน Path

สร้าง Path ใหม่ด้วยเรขาคณิตที่กำหนด และใช้ไล่สีแนวทแยงกับมัน ปรับการแปลงการเรนเดอร์และคุณสมบัติ fill ตามต้องการ

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## ขั้นตอนที่ 5: บันทึก XPS Document ที่ได้ผลลัพธ์

สุดท้าย บันทึกเอกสาร XPS ที่แก้ไขแล้วไปยังไดเรกทอรีที่ระบุ

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

คุณได้ **สร้างไฟล์ XPS แบบไล่สีแนวทแยง** สำเร็จแล้ว ตอนนี้คุณสามารถทดลองกับสีหยุดต่าง ๆ, สตริงเรขาคณิต หรือเมทริกซ์การแปลงเพื่อสร้างเอฟเฟกต์ภาพที่หลากหลายได้

## ปัญหาทั่วไปและวิธีแก้
- **ไล่สีไม่แสดง** – ตรวจสอบว่าเรขาคณิตของ Path ปิดอยู่และจุดเริ่มต้น/สิ้นสุดของแปรงอยู่ภายในขอบเขตของ Path.  
- **สีไม่ถูกต้อง** – ตรวจสอบว่าคุณใช้ `CreateColor` กับค่า ARGB ที่ถูกต้อง; เมธอดต้องการค่าที่อยู่ในช่วง 0‑255.  
- **ไฟล์ไม่บันทึก** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ไล่สีหลายแบบกับส่วนต่าง ๆ ของเอกสารได้หรือไม่?**  
A: ได้, คุณสามารถสร้างหลาย Path และใช้ไล่สีที่แตกต่างกันกับแต่ละอัน.

**Q: มีสไตล์ไล่สีที่กำหนดไว้ล่วงหน้าหรือไม่?**  
A: Aspose.Page รองรับไล่สีแบบกำหนดเอง ให้คุณควบคุมการเปลี่ยนสีได้อย่างเต็มที่.

**Q: ฉันสามารถใช้ Aspose.Page สำหรับ .NET กับรูปแบบเอกสารอื่นได้หรือไม่?**  
A: Aspose.Page มุ่งเน้นที่การจัดการเอกสาร XPS เป็นหลัก.

**Q: ฉันจะจัดการกับข้อผิดพลาดที่เกี่ยวกับการประมวลผลเอกสารอย่างไร?**  
A: ดูที่ [documentation](https://reference.aspose.com/page/net/) เพื่อเรียนรู้แนวทางปฏิบัติที่ดีที่สุดในการจัดการข้อผิดพลาด.

**Q: มีเวอร์ชันทดลองก่อนซื้อหรือไม่?**  
A: มี, คุณสามารถสำรวจ [free trial](https://releases.aspose.com/) เพื่อทดลองใช้ Aspose.Page สำหรับ .NET.

**Q: ฉันจะเปลี่ยนทิศทางของไล่สีเป็นแนวตั้งหรือแนวนอนได้อย่างไร?**  
A: ปรับค่าอาร์กิวเมนต์ `PointF` ใน `CreateLinearGradientBrush` เพื่อกำหนดจุดเริ่มต้นและสิ้นสุดใหม่.

**Q: ไลบรารีนี้รองรับความโปร่งใสในไล่สีหรือไม่?**  
A: มี—ใส่ค่าอัลฟาเมื่อสร้างสีด้วย `CreateColor`.

## สรุป

Aspose.Page สำหรับ .NET ทำให้กระบวนการเพิ่มไล่สีแนวทแยงในเอกสาร XPS ง่ายขึ้น คู่มือนี้ได้แนะนำคุณตั้งแต่การเตรียมความพร้อมจนถึงการบันทึกไฟล์สุดท้าย อย่าหยุดทดลองกับรูปทรงและพาเลตสีต่าง ๆ เพื่อทำให้รายงาน, โบรชัวร์ หรือใบแจ้งหนี้ XPS ของคุณโดดเด่นจริง ๆ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-02-23  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose