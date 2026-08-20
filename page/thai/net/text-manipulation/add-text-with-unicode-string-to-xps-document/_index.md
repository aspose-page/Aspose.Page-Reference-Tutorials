---
date: 2026-03-21
description: เรียนรู้วิธีเพิ่มข้อความ Unicode ลงในเอกสาร XPS ด้วย Aspose.Page สำหรับ
  .NET คู่มือนี้จะแสดงวิธีสร้างเอกสาร XPS ด้วย C# และ Aspose.Page เพื่อเพิ่มข้อความที่มีสตริง
  Unicode.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: วิธีเพิ่มข้อความยูนิโค้ดลงในเอกสาร XPS ด้วย Aspose.Page
url: /th/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มข้อความ Unicode ไปยังเอกสาร XPS ด้วย Aspose.Page

## บทนำ

หากคุณต้องการ **how to add unicode** ตัวอักษรลงในไฟล์ XPS คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะอธิบายขั้นตอนที่จำเป็นเพื่อ **create XPS document C#**‑style ด้วย Aspose.Page สำหรับ .NET และสาธิตความสามารถของ **aspose page add text** ด้วยสตริง Unicode สุดท้ายคุณจะได้เอกสาร XPS ที่ทำงานเต็มรูปแบบและแสดงข้อความ Unicode จากขวาไปซ้าย (RTL) อย่างถูกต้อง.

## คำตอบอย่างรวดเร็ว
- **บทเรียนนี้ครอบคลุมอะไร?** การเพิ่มข้อความ Unicode ไปยังเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET.  
- **ใช้ภาษาอะไร?** C# (compatible with .NET Framework and .NET Core).  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการผลิต.  
- **สามารถเปลี่ยนแบบอักษรหรือขนาดได้หรือไม่?** ใช่ – ตัวอย่างใช้ Arial 20 pt, แต่แบบอักษรที่ติดตั้งใดก็ได้ก็ทำงาน.  
- **รองรับ RTL หรือไม่?** การตั้งค่า `BidiLevel = 1` จะเปิดการแสดงผลจากขวาไปซ้ายสำหรับสตริง Unicode.

## อะไรคือ “how to add unicode” ใน XPS?

การเพิ่มข้อความ Unicode หมายถึงการแทรกอักขระจากภาษาต่าง ๆ — อาหรับ, ฮีบรู, จีน ฯลฯ — ลงในเอกสาร XPS. คลาส `XpsGlyphs` ของ Aspose.Page จัดการการวาง glyph ระดับต่ำ, ในขณะที่คุณสมบัติ `BidiLevel` ควบคุมทิศทางของข้อความสำหรับสคริปต์ RTL.

## ทำไมต้องใช้ Aspose.Page เพื่อเพิ่มข้อความ?

- **Full .NET integration** – ทำงานกับ .NET Framework, .NET Core, .NET 5/6+.  
- **No external dependencies** – โค้ดจัดการแบบบริสุทธิ์, ไม่มี COM interop.  
- **Rich typography support** – แบบอักษร, สไตล์, สี, และข้อความสองทิศทาง.  
- **High performance** – สร้างและบันทึกไฟล์ XPS อย่างรวดเร็ว, เหมาะสำหรับการสร้างบนเซิร์ฟเวอร์.

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานเกี่ยวกับ C# และการพัฒนา .NET.  
- Visual Studio (เวอร์ชันล่าสุดใดก็ได้).  
- ไลบรารี Aspose.Page สำหรับ .NET – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/net/).

## นำเข้า Namespaces

ขั้นแรก, นำเข้า namespaces ที่ให้คุณเข้าถึงโมเดล XPS และยูทิลิตี้การวาด.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ขั้นตอนที่ 1: ตั้งค่าเอกสาร – create XPS document C#

สร้างเอกสาร XPS ใหม่ที่จะเป็นที่เก็บข้อความ Unicode.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## ขั้นตอนที่ 2: เพิ่มข้อความ Unicode – aspose page add text

ตอนนี้เราจะเพิ่มสตริง Unicode จริง ๆ ในตัวอย่างนี้เราใช้แบบอักษร Arial, ขนาด 20, และวางตำแหน่งข้อความที่ (400 f, 200 f). `BidiLevel` ที่ค่า 1 จะบอก renderer ให้จัดการสตริงเป็นขวา‑ไป‑ซ้าย.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## ขั้นตอนที่ 3: บันทึกเอกสาร

สุดท้าย, บันทึกไฟล์ XPS ลงดิสก์.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

ยินดีด้วย! คุณได้เพิ่มข้อความ **how to add unicode** ลงในเอกสาร XPS อย่างสำเร็จโดยใช้ Aspose.Page สำหรับ .NET.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| ข้อความแสดงเป็นอักขระผิดพลาด | แบบอักษรไม่รองรับช่วง Unicode | ใช้แบบอักษรที่มี glyph ที่ต้องการ (เช่น Arial Unicode MS). |
| ข้อความ RTL ยังคงแสดงจากซ้ายไปขวา | `BidiLevel` ไม่ได้ตั้งหรือตั้งเป็น 0 | ตรวจสอบให้แน่ใจว่า `glyphs.BidiLevel = 1;` สำหรับสคริปต์ RTL. |
| ไฟล์ไม่ถูกบันทึก | เส้นทาง `dataDir` ไม่ถูกต้อง | ตรวจสอบว่าไดเรกทอรีมีอยู่และแอปมีสิทธิ์เขียน. |

## คำถามที่พบบ่อย

**Q: Aspose.Page รองรับ .NET framework ล่าสุดหรือไม่?**  
A: ใช่, Aspose.Page มีการอัปเดตอย่างสม่ำเสมอเพื่อรองรับ .NET Framework, .NET Core, และ .NET 5/6+.

**Q: ฉันสามารถปรับแต่งสไตล์และขนาดของแบบอักษรเมื่อเพิ่มข้อความได้หรือไม่?**  
A: ได้เลย! เมธอด `AddGlyphs` ให้คุณระบุฟอนต์ใดก็ได้, ขนาด, และ `FontStyle` ที่ต้องการ.

**Q: ฉันสามารถหาเอกสารเพิ่มเติมสำหรับ Aspose.Page ได้ที่ไหน?**  
A: คุณสามารถดูเอกสารได้ที่ [here](https://reference.aspose.com/page/net/) เพื่อรายละเอียด API อย่างครบถ้วน.

**Q: มีแหล่งข้อมูลฟรีใด ๆ ที่จะเริ่มต้นกับ Aspose.Page หรือไม่?**  
A: มี! สำรวจฟอรั่มชุมชนที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับเคล็ดลับ, ตัวอย่าง, และการสนับสนุนจากผู้ใช้.

**Q: มีเวอร์ชันทดลองให้ใช้ก่อนการซื้อหรือไม่?**  
A: แน่นอน! ดาวน์โหลดเวอร์ชันทดลองฟรีจาก [here](https://releases.aspose.com/) เพื่อประเมินไลบรารี.

---

**อัปเดตล่าสุด:** 2026-03-21  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}