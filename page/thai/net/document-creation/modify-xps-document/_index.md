---
date: 2026-01-12
description: เรียนรู้วิธีแก้ไขเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET และค้นพบวิธีเพิ่มข้อความลงในไฟล์
  XPS ด้วยตัวอย่างโค้ดง่าย ๆ
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: แก้ไขเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET
url: /th/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แก้ไขเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

## บทนำ

ยินดีต้อนรับสู่คู่มือแบบขั้นตอนของเราเกี่ยวกับ **วิธีแก้ไขไฟล์เอกสาร xps** ด้วย Aspose.Page สำหรับ .NET ไม่ว่าคุณจะต้องการแทรกลายเซ็น, เพิ่มลายน้ำ, หรือเพียงแค่วางข้อความกำหนดเองบนหน้า, บทเรียนนี้จะแสดงให้คุณเห็น **วิธีเพิ่มข้อความ** ลงในเอกสาร XPS ภายในไม่กี่นาที เราจะเดินผ่านทุกบรรทัดของโค้ด, อธิบายว่าทำไมแต่ละขั้นตอนจึงสำคัญ, และให้เคล็ดลับเพื่อหลีกเลี่ยงข้อผิดพลาดทั่วไป

### คำตอบอย่างรวดเร็ว
- **บทเรียนนี้ครอบคลุมอะไร?** การเพิ่มข้อความลายเซ็น (“Confirmed”) ไปยังหน้าที่เลือกของไฟล์ XPS  
- **ต้องใช้ไลบรารีใด?** Aspose.Page สำหรับ .NET (เวอร์ชันล่าสุด)  
- **ต้องมีไลเซนส์หรือไม่?** ไลเซนส์ชั่วคราวใช้สำหรับการทดสอบ; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10 นาทีสำหรับการแทรกลายเซ็นพื้นฐาน

## การแก้ไขเอกสาร XPS คืออะไร?

XPS (XML Paper Specification) เป็นรูปแบบเอกสารแบบจัดหน้าแบบคงที่ของ Microsoft คล้ายกับ PDF การแก้ไขเอกสาร XPS หมายถึงการเปลี่ยนแปลงเนื้อหาภาพแบบโปรแกรม—การเพิ่มข้อความ, รูปภาพ, หรือรูปทรง—โดยไม่ต้องแปลงไฟล์เป็นรูปแบบอื่น Aspose.Page มีโมเดลออบเจ็กต์ที่สมบูรณ์ซึ่งทำให้คุณสามารถแก้ไขไฟล์ XPS โดยตรงจากโค้ด .NET ของคุณได้

## ทำไมต้องใช้ Aspose.Page เพื่อแก้ไขเอกสาร XPS?

* **การควบคุมเต็มรูปแบบ** – ทำงานกับหน้า, glyphs, brushes, และ transforms ในระดับต่ำ  
* **ไม่มีการพึ่งพาภายนอก** – ไลบรารี .NET แท้, ไม่ต้องใช้ Office หรือคอมโพเนนต์ของ Adobe  
* **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS ผ่าน .NET Core  
* **ประสิทธิภาพที่มั่นคง** – จัดการเอกสารขนาดใหญ่ได้อย่างมีประสิทธิภาพและรองรับการพิมพ์ขั้นสูง

## ข้อกำหนดเบื้องต้น

ก่อนเริ่ม, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Aspose.Page สำหรับ .NET** – ติดตั้งแพคเกจ NuGet หรือดาวน์โหลดไลบรารีจากเอกสารอย่างเป็นทางการ **[ที่นี่](https://reference.aspose.com/page/net/)**  
- **ไฟล์ XPS อินพุต** – รับตัวอย่างเอกสาร XPS (เช่น `input1.xps`) จาก **[หน้า releases ของ Aspose](https://releases.aspose.com/page/net/)**  
- **ไดเรกทอรีทำงาน** – สร้างโฟลเดอร์บนเครื่องของคุณเพื่อเก็บไฟล์อินพุตและเอาต์พุตและจดบันทึกพาธเต็มของมัน; คุณจะกำหนดพาธนี้ให้กับตัวแปร `dir` ในโค้ด  
- **สภาพแวดล้อมการพัฒนา** – Visual Studio 2019/2022, .NET Framework 4.7.2 หรือใหม่กว่า, หรือโครงการ .NET Core/5/6 ใด ๆ

เมื่อทุกอย่างพร้อม, มาเริ่มดูโค้ดกัน

## นำเข้า Namespaces

ในโครงการ .NET ของคุณ, เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็นสำหรับ Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## ขั้นตอนที่ 1: เปิดสตรีมเอกสาร XPS

เราจะเปิดไฟล์ XPS ต้นฉบับเป็นสตรีมและสร้างอ็อบเจ็กต์ `XpsDocument` ที่แทนเอกสารทั้งหมด

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*เคล็ดลับ:* ห่อสตรีมด้วยบล็อก `using` เพื่อให้แน่ใจว่าการจัดการไฟล์จะถูกปล่อยอัตโนมัติ

## ขั้นตอนที่ 2: สร้างข้อความลายเซ็น

ต่อไป, เราจะสร้าง brush สีทึบที่จะใช้ในการวาด glyphs ของลายเซ็น

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

คุณสามารถเปลี่ยน `Color.BlueViolet` เป็น `System.Drawing.Color` ใดก็ได้ที่ตรงกับแบรนด์ของคุณ

## ขั้นตอนที่ 3: กำหนดหน้าและเพิ่มลายเซ็น

เราจะระบุว่าหน้าใดบ้างที่ต้องการเพิ่มลายเซ็นและจากนั้นเพิ่ม glyphs ไปยังแต่ละหน้า

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*ทำไมต้องใช้พิกัดเหล่านี้?* ค่า X และ Y วัดเป็นจุด (1/72 นิ้ว) ปรับค่าเหล่านี้เพื่อวางข้อความให้ตรงกับตำแหน่งที่ต้องการบนเลย์เอาต์ของหน้า

## ขั้นตอนที่ 4: บันทึกการเปลี่ยนแปลงลงในเอกสาร XPS

สุดท้าย, เขียนเอกสารที่แก้ไขแล้วกลับไปยังดิสก์

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

ไฟล์ใหม่ `input1_out.xps` ตอนนี้มีลายเซ็น “Confirmed” อยู่บนหน้า 1‑3

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|----------|
| **ลายเซ็นไม่ปรากฏ** | พิกัดผิดหรือไม่ได้เลือกหน้า | ตรวจสอบให้แน่ใจว่าได้เรียก `SelectActivePage` สำหรับแต่ละหน้าและปรับค่า X/Y |
| **เกิดข้อยกเว้นที่ `AddGlyphs`** | ฟอนต์ไม่ได้ติดตั้งบนเซิร์ฟเวอร์ | ตรวจสอบว่าฟอนต์ที่ระบุ (เช่น Arial) มีอยู่, หรือฝังฟอนต์กำหนดเองด้วย `document.AddFont` |
| **ไฟล์เอาต์พุตเสียหาย** | สตรีมไม่ถูกปิดอย่างถูกต้อง | ใช้คำสั่ง `using` สำหรับสตรีมทั้งหมดและเรียก `document.Dispose()` หากจำเป็น |
| **ประสิทธิภาพช้าลงกับไฟล์ขนาดใหญ่** | โหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ | ประมวลผลหน้าเป็นชุดหรือใช้ `XpsLoadOptions` กับตัวเลือกสตรีม (หากมีในเวอร์ชันใหม่) |

## คำถามที่พบบ่อย

**Q: Aspose.Page รองรับ .NET เวอร์ชันล่าสุดหรือไม่?**  
A: ใช่, Aspose.Page มีการอัปเดตเป็นประจำเพื่อรองรับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5, และ .NET 6

**Q: สามารถปรับแต่งฟอนต์และสไตล์ของข้อความที่เพิ่มได้หรือไม่?**  
A: แน่นอน. ปรับพารามิเตอร์ของ `AddGlyphs` (ชื่อฟอนต์, ขนาด, `FontStyle`) ให้ตรงกับการออกแบบของคุณ

**Q: มีขนาดจำกัดสำหรับไฟล์ XPS หรือไม่?**  
A: Aspose.Page สามารถจัดการเอกสารขนาดใหญ่ได้, แต่การใช้หน่วยความจำจะเพิ่มตามขนาดไฟล์ สำหรับไฟล์ใหญ่มาก, ควรประมวลผลหน้าแยกส่วน

**Q: จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.Page ได้อย่างไร?**  
A: คุณสามารถรับไลเซนส์ชั่วคราว **[ที่นี่](https://purchase.aspose.com/temporary-license/)**

**Q: จะหาความช่วยเหลือหรือเข้าร่วมชุมชน Aspose ได้จากที่ไหน?**  
A: เยี่ยมชม **[ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39)** เพื่อถามคำถามและแบ่งปันประสบการณ์

## สรุป

ในบทเรียนนี้เราได้สาธิตวิธี **แก้ไขเอกสาร xps** โดยการเพิ่มข้อความลายเซ็นกำหนดเองด้วย Aspose.Page สำหรับ .NET ตอนนี้คุณมีพื้นฐานที่มั่นคงสำหรับการแทรกข้อความ, ลายน้ำ, หรือคำอธิบายใด ๆ ลงบนหน้าที่ระบุของไฟล์ XPS ทดลองใช้ฟอนต์, สี, และตำแหน่งที่ต่างกันเพื่อให้ตรงกับความต้องการของแอปพลิเคชันของคุณ, และสำรวจ API ของ Aspose.Page สำหรับความสามารถกราฟิกและการจัดเลย์เอาต์ขั้นสูงอื่น ๆ

---

**อัปเดตล่าสุด:** 2026-01-12  
**ทดสอบกับ:** Aspose.Page 24.11 for .NET (เวอร์ชันล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}