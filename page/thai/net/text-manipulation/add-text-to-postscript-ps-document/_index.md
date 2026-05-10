---
date: 2026-03-21
description: เรียนรู้วิธีเติมข้อความและเพิ่มข้อความในเอกสาร PS ด้วย Aspose.Page สำหรับ
  .NET คู่มือขั้นตอนโดยละเอียดพร้อมตัวอย่างโค้ด
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: วิธีเติมข้อความในเอกสาร PostScript (PS) ด้วย Aspose.Page
url: /th/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเติมข้อความในเอกสาร PostScript (PS) ด้วย Aspose.Page

## คำแนะนำ

หากคุณต้องการ **เติมข้อความ** ภายในไฟล์ PostScript (PS) Aspose.Page สำหรับ .NET ทำให้กระบวนการง่ายดาย ไม่ว่าคุณจะสร้างรายงาน ใบแจ้งหนี้ หรือกราฟิกแบบกำหนดเอง การเพิ่มและจัดรูปแบบข้อความเป็นความต้องการหลัก ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนทั้งหมด — ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการบันทึกเอกสาร PS สุดท้าย — เพื่อให้คุณมั่นใจในการเพิ่มข้อความลงในไฟล์ PS ในแอปพลิเคชัน .NET ของคุณ

## Quick Answers
- **“fill text” หมายถึงอะไร?** มันทำการเรนเดอร์อักขระโดยใช้แปรงสีทึบ ทาสี glyphs โดยตรงบนหน้า.  
- **ฉันสามารถใช้ฟอนต์แบบกำหนดเองได้หรือไม่?** ได้ — Aspose.Page รองรับฟอนต์แบบกำหนดเองผ่านฟีเจอร์ `add custom font ps`.  
- **ฉันจะบันทึกเอกสาร PS อย่างไร?** เรียก `document.Save()` หลังจากปิดหน้า; คำสั่งนี้จะเขียนไฟล์ลงดิสก์ (`save ps document`).  
- **รองรับ “fill and stroke text” หรือไม่?** แน่นอน; ใช้ `FillAndStrokeText` เพื่อทำการเติมและร่างเส้นขอบพร้อมกัน.  
- **ต้องการ .NET เวอร์ชันใด?** ใดก็ได้ที่เป็น .NET Framework 4.5+ หรือ .NET Core/5/6+ runtime.

## “fill text” คืออะไรในเอกสาร PS?

การเติมข้อความหมายถึงการทาสีอักขระด้วยสีทึบ (หรือแปรง) โดยไม่มีเส้นขอบ ใน PostScript นั้นเทียบเท่ากับโอเปอเรเตอร์ `fill` Aspose.Page ทำให้การทำงานนี้เป็นวิธีง่าย ๆ ผ่านเมธอดเช่น `FillText` และ `FillAndStrokeText`.

## ทำไมต้องใช้ Aspose.Page สำหรับการเพิ่มฟอนต์แบบกำหนดเองใน PS?

- **รองรับฟอนต์เต็มรูปแบบ** – ฟอนต์ระบบและฟอนต์ TrueType/OpenType ภายนอกทำงานได้ทันที  
- **การวางตำแหน่งที่แม่นยำ** – คุณควบคุมพิกัด X/Y, ขนาด, และสไตล์  
- **การจัดรูปแบบที่หลากหลาย** – ผสมผสานการเติมสี, การร่างเส้น, และปากกาสำหรับเอฟเฟกต์เช่น “fill and stroke text”  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS ด้วย API เดียวกัน  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบว่าคุณมี:

- **Aspose.Page for .NET** – ดาวน์โหลดไลบรารีจาก [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/).  
- **Document Directory** – โฟลเดอร์บนเครื่องของคุณที่เก็บไฟล์ PS ต้นฉบับและไฟล์ผลลัพธ์ (เรียกว่า *Your Document Directory* ในโค้ด).  
- **Fonts Folder** – โฟลเดอร์ย่อยที่บรรจุฟอนต์แบบกำหนดเองที่คุณต้องการใช้.  

## นำเข้า Namespaces

ขั้นแรก นำเข้า namespaces ที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาสที่เราจะใช้จากที่ไหน:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: สร้าง Output Stream สำหรับเอกสาร PS  

เราจะเปิด `FileStream` เพื่อเก็บไฟล์ PS ที่สร้างขึ้น ตั้งค่า `PsSaveOptions` ให้ชี้ไปที่โฟลเดอร์ฟอนต์แบบกำหนดของเรา และสร้างอินสแตนซ์ของ `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **เคล็ดลับ:** คงไว้ซึ่งบล็อก `using` เพื่อให้สตรีมปิดโดยอัตโนมัติ ซึ่งยังทำให้ไฟล์ PS เสร็จสมบูรณ์ (`save ps document`).  

### ขั้นตอนที่ 2: เติมข้อความด้วยฟอนต์ระบบ  

ที่นี่เราจะแสดงการทำงานพื้นฐานของ **การเติมข้อความ** โดยใช้ฟอนต์ *Times New Roman* ที่มาพร้อมระบบ.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### ขั้นตอนที่ 3: เติมข้อความด้วยฟอนต์แบบกำหนดเอง  

หากต้องการลุคเฉพาะ โหลดฟอนต์แบบกำหนดเองจากโฟลเดอร์ฟอนต์โดยใช้ `ExternalFontCache.FetchDrFont`. สิ่งนี้ตอบสนองความต้องการ **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### ขั้นตอนที่ 4: ร่าง (Stroke) ข้อความด้วยฟอนต์ระบบ  

การร่างเส้นจะวาดโครงร่างของ glyph. ผสมกับการเติมสีเพื่อให้ได้เอฟเฟกต์ “fill and stroke”.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **ทำไมเรื่องนี้สำคัญ:** คำสั่ง `FillAndStrokeText` แสดงวิธี **เติมและร่างเส้นข้อความ** ในขั้นตอนเดียว ให้คุณควบคุมการพิมพ์ได้หลากหลายยิ่งขึ้น.  

### ขั้นตอนที่ 5: ร่างข้อความด้วยฟอนต์แบบกำหนดเอง  

เทคนิคการร่างเดียวกันทำงานได้กับฟอนต์แบบกำหนดใด ๆ ที่คุณโหลดไว้.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### ขั้นตอนที่ 6: ปิดหน้าและบันทึกเอกสาร  

การสรุปขั้นตอนง่าย ๆ: ปิดหน้าปัจจุบันและเรียก `Save()` เพื่อเขียนไฟล์ PS ลงดิสก์.

```csharp
document.ClosePage();
document.Save();
}
```

> **ผลลัพธ์:** คุณจะพบไฟล์ `AddText_outPS.ps` ใน *Your Document Directory* ซึ่งมีข้อความที่เติมสีและร่างเส้นทั้งแบบฟอนต์ระบบและฟอนต์แบบกำหนดเอง.  

## ปัญหาที่พบบ่อยและวิธีแก้

| Issue | Solution |
|-------|----------|
| **ไม่พบฟอนต์แบบกำหนดเอง** | ตรวจสอบว่าไฟล์ฟอนต์ (.ttf/.otf) มีอยู่ในโฟลเดอร์ที่อ้างอิงโดย `AdditionalFontsFolders`. |
| **ข้อความแสดงตำแหน่งผิด** | ปรับพิกัด X/Y ที่ส่งให้กับ `FillText`/`OutlineText`. จำไว้ว่า PostScript ใช้หน่วยจุด (1/72 นิ้ว). |
| **สีแสดงผลต่างกัน** | ตรวจสอบว่าคุณใช้ `SolidBrush` หรือ `Pen` พร้อมค่าของ `Color` ที่ถูกต้อง. |
| **เอกสารไม่บันทึก** | ยืนยันว่าบล็อก `using` ทำงานจนจบโดยไม่มีข้อยกเว้นและแอปพลิเคชันมีสิทธิ์เขียนในโฟลเดอร์เป้าหมาย. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.Page กับไลบรารี .NET อื่นได้หรือไม่?**  
A: ใช่, Aspose.Page ผสานรวมได้อย่างราบรื่นกับคอมโพเนนต์ .NET อื่น ๆ ทำให้คุณสามารถรวมไลบรารี PDF, image หรือ chart ในโซลูชันเดียวกันได้.

**Q: ฟอนต์แบบกำหนดเองจำเป็นสำหรับกระบวนการนี้หรือไม่?**  
A: แม้ฟอนต์ระบบจะทำงานได้ดี แต่ฟอนต์แบบกำหนดเองให้อิสระในการออกแบบเต็มที่และมีประโยชน์เมื่อจำเป็นต้องใช้การพิมพ์ที่สอดคล้องกับแบรนด์.

**Q: Aspose.Page เหมาะกับการประมวลผลเอกสารในระดับใหญ่หรือไม่?**  
A: แน่นอน. ไลบรารีนี้ถูกปรับให้ทำงานได้อย่างมีประสิทธิภาพในสถานการณ์ที่ต้องประมวลผลจำนวนมากและสามารถจัดการไฟล์ PS หลายพันไฟล์ได้อย่างมีประสิทธิภาพ.

**Q: ฉันสามารถแก้ไขตำแหน่งของข้อความในเอกสาร PS ได้หรือไม่?**  
A: แน่นอน — เพียงเปลี่ยนค่าตัวเลข X/Y ในคำสั่ง `FillText` หรือ `OutlineText`.

**Q: ฉันจะหาความช่วยเหลือสำหรับคำถามเกี่ยวกับ Aspose.Page ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.Page Forum](https://forum.aspose.com/c/page/39) เพื่อเชื่อมต่อกับชุมชนและรับความช่วยเหลือจากผู้เชี่ยวชาญ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-21  
**ทดสอบด้วย:** Aspose.Page 24.11 for .NET  
**ผู้เขียน:** Aspose