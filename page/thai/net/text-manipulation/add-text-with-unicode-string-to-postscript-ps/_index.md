---
date: 2026-03-21
description: เรียนรู้วิธีสร้างเอกสาร PostScript ด้วย C# ที่มีข้อความ Unicode โดยใช้
  Aspose.Page สำหรับ .NET – วิธีที่รวดเร็วในการเพิ่มประสิทธิภาพการจัดการเอกสาร.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: สร้างเอกสาร PostScript ด้วย C# พร้อมข้อความ Unicode – Aspose.Page
url: /th/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มข้อความด้วยสตริง Unicode ไปยัง PostScript (PS) ด้วย Aspose.Page

## บทนำ

หากคุณต้องการ **create a PostScript document C#** และฝังอักขระ Unicode, Aspose.Page สำหรับ .NET ทำให้กระบวนการเป็นเรื่องง่าย ในบทเรียนนี้เราจะเดินผ่านตัวอย่างครบถ้วนแบบทำมือที่แสดงวิธีการเพิ่มข้อความภาษาญี่ปุ่น (หรือสตริง Unicode ใด ๆ) ไปยังไฟล์ PS, เลือกฟอนต์ที่กำหนดเอง, และบันทึกผลลัพธ์ เมื่อเสร็จสิ้นคุณจะได้สคริปต์ที่สามารถนำไปใช้ซ้ำในโปรเจกต์ C# ใด ๆ

## คำตอบอย่างรวดเร็ว
- **What does this tutorial cover?** การเพิ่มข้อความ Unicode ไปยังไฟล์ PostScript ด้วย Aspose.Page ใน C#.
- **Which library is required?** Aspose.Page for .NET (latest version).
- **Do I need a special font?** ฟอนต์ TrueType/OpenType ใด ๆ ที่รองรับช่วง Unicode ที่ต้องการ, เช่น *Arial Unicode MS*.
- **How many lines of code?** ประมาณ 30 บรรทัด, แบ่งเป็นขั้นตอนที่ชัดเจน.
- **Is a license needed?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; ใบอนุญาตเต็มจำเป็นสำหรับการใช้งานในผลิตภัณฑ์.

## อะไรคือ “create postscript document c#”?
การสร้างเอกสาร PostScript ใน C# หมายถึงการสร้างไฟล์ .ps อย่างโปรแกรมเมติกที่สอดคล้องกับสเปคของภาษา PostScript Aspose.Page จะจัดการรายละเอียดระดับต่ำให้คุณโฟกัสที่เนื้อหาเช่นข้อความ, กราฟิก, และฟอนต์ได้เลย

## ทำไมต้องใช้ Aspose.Page สำหรับข้อความ Unicode?
- **Full Unicode support** – เรนเดอร์อักขระจากทุกภาษาโดยไม่ต้องเข้ารหัสด้วยตนเอง
- **Device‑independent** – โค้ดเดียวทำงานได้กับ PS, EPS, และ PDF
- **No external dependencies** – ไลบรารีจัดการการโหลดฟอนต์และการแมป glyph ภายในเอง

## ข้อกำหนดเบื้องต้น

- ความคุ้นเคยพื้นฐานกับ C# และการพัฒนา .NET
- ติดตั้งไลบรารี Aspose.Page for .NET คุณสามารถดาวน์โหลดได้จาก [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/)
- โฟลเดอร์ที่บรรจุฟอนต์ที่คุณจะใช้ (เช่น *Arial Unicode MS*)

## นำเข้า Namespaces

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารและโฟลเดอร์ฟอนต์

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## ขั้นตอนที่ 2: สร้าง Output Stream สำหรับเอกสาร PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## ขั้นตอนที่ 3: เพิ่มข้อความ Unicode ด้วยฟอนต์ที่กำหนดเอง

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## ขั้นตอนที่ 4: ปิดหน้า (Page) ปัจจุบัน

```csharp
document.ClosePage();
```

## ขั้นตอนที่ 5: สรุปและบันทึกเอกสาร

```csharp
document.Save();
```

## ปัญหาทั่วไปและวิธีแก้ไข

- **Font not found** – ตรวจสอบให้แน่ใจว่าเส้นทาง `AdditionalFontsFolders` ชี้ไปยังโฟลเดอร์ที่มีไฟล์ .ttf/.otf และชื่อฟอนต์ตรงกันอย่างแม่นยำ
- **Garbage characters** – ยืนยันว่าสตริงต้นทางถูกเข้ารหัสเป็น UTF‑8 ในไฟล์ซอร์ส C# ของคุณ (ใช้ `#pragma warning disable 1591` หากจำเป็น)
- **File not created** – ตรวจสอบสิทธิ์การเขียนบน `dataDir` และให้แน่ใจว่า stream ถูกทำลายอย่างถูกต้อง (บล็อก `using` จะจัดการให้)

## คำถามที่พบบ่อย

**Q: Can I use Aspose.Page for .NET with other programming languages?**  
A: Aspose.Page ถูกออกแบบมาสำหรับ .NET เป็นหลัก, แต่มีเวอร์ชัน Java ที่เทียบเท่าให้ใช้ได้

**Q: How do I obtain a temporary license for Aspose.Page for .NET?**  
A: เยี่ยมชม [Temporary License](https://purchase.aspose.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราว

**Q: Is there a community forum for Aspose.Page discussions?**  
A: ใช่, ไปที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชน

**Q: What formats can Aspose.Page for .NET work with?**  
A: Aspose.Page รองรับหลายรูปแบบ รวมถึง XPS, PS, EPS, PDF และอื่น ๆ

**Q: Can I customize the appearance of the added text?**  
A: ได้, คุณสามารถปรับฟอนต์, ขนาด, สี, และคุณสมบัติอื่น ๆ ของข้อความใน Aspose.Page ได้ตามต้องการ

## สรุป

ในบทเรียนนี้เราได้สาธิตวิธี **create a PostScript document C#** และฝังข้อความ Unicode ด้วย Aspose.Page โดยทำตามขั้นตอนที่กล่าวมาข้างต้น คุณจะสามารถผสานการเรนเดอร์ข้อความหลายภาษาเข้าไปในแอปพลิเคชัน .NET ของคุณได้อย่างรวดเร็วและมีการควบคุมเต็มที่ต่อการสร้างและการจัดวางเอกสาร

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}