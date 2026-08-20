---
date: 2026-03-19
description: เรียนรู้วิธี **remove page xps** เอกสารและ **delete page at index** โดยใช้
  Aspose.Page สำหรับ .NET – คู่มือเต็มขั้นตอนพร้อมข้อกำหนดเบื้องต้น ตัวอย่างโค้ด และคำถามที่พบบ่อย
linktitle: Remove Page from XPS Document
second_title: Aspose.Page .NET API
title: ลบหน้าจากเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET
url: /th/net/page-manipulation/remove-page-from-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ลบหน้าออกจากเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

## บทนำ

หากคุณต้องการ **remove page xps** ไฟล์โดยอัตโนมัติ, Aspose.Page สำหรับ .NET จะมอบวิธีที่สะอาดและเชื่อถือได้ในการทำเช่นนั้น ในบทเรียนนี้เราจะอธิบายขั้นตอนที่จำเป็นเพื่อทำการลบหน้าที่ระบุจากเอกสาร XPS, อธิบายว่าการดำเนินการนี้สำคัญอย่างไร, และแสดงวิธีบันทึกไฟล์ที่อัปเดตกลับไปยังดิสก์.

## คำตอบอย่างรวดเร็ว
- **What does “remove page xps” mean?** หมายถึงการลบหน้าเดียวจากเอกสาร XPS (XML Paper Specification).  
- **Which method deletes a page?** ใช้ `RemovePageAt(index)` โดยที่ index เริ่มจากศูนย์.  
- **Can I delete a page at any position?** ใช่ – คุณสามารถ **delete page at index** 0, 1, 2, ฯลฯ ตามต้องการ.  
- **Do I need a license for Aspose.Page?** จำเป็นต้องมีใบอนุญาตชั่วคราวสำหรับการทดสอบ; ใบอนุญาตเต็มจำเป็นสำหรับการใช้งานจริง.  
- **Is the code compatible with .NET 6?** แน่นอน – Aspose.Page รองรับ .NET Framework, .NET Core, และ .NET 5/6.

## “remove page xps” คืออะไร?
การลบหน้าจากเอกสาร XPS หมายถึงการเอาหนึ่งหน้าของเอกสารออกโดยยังคงรักษาเนื้อหา, การจัดวาง, และเมตาดาต้าอื่น ๆ ไว้ การดำเนินการนี้มีประโยชน์เมื่อคุณต้องการตัด PDF, สร้างรายงานที่กำหนดเอง, หรือปฏิบัติตามขีดจำกัดขนาดเอกสาร.

## ทำไมต้องใช้ Aspose.Page สำหรับ .NET?
- **No external dependencies** – ไลบรารี .NET แท้.  
- **High fidelity** – รักษากราฟิกเวกเตอร์และความแม่นยำของการจัดวาง.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS.  
- **Simple API** – การเรียกเมธอดเดียว (`RemovePageAt`) จัดการงานหนักทั้งหมด.

## ข้อกำหนดเบื้องต้น
ก่อนจะลงลึกในโค้ด, โปรดตรวจสอบว่าคุณมี:

- **Aspose.Page for .NET** – ดาวน์โหลดจาก [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).  
- **.NET development environment** (Visual Studio, VS Code, หรือ IDE ที่คุณชอบ).  
- **sample XPS document** (เช่น `Sample.xps`) ที่วางไว้ในโฟลเดอร์ที่คุณสามารถอ้างอิงจากโปรเจคของคุณ.

## นำเข้า Namespaces
เพิ่ม namespaces ที่จำเป็นที่ส่วนหัวของไฟล์ C# ของคุณเพื่อให้คอมไพเลอร์รู้ว่าจะหา class ของ XPS จากที่ไหน.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ขั้นตอนที่ 1: ตั้งค่าโฟลเดอร์เอกสาร

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **เคล็ดลับ:** ใช้ `Path.Combine` สำหรับการสร้างเส้นทางแบบข้ามแพลตฟอร์ม.

## ขั้นตอนที่ 2: สร้าง XPS Document ใหม่

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// ExEnd:4
```

บรรทัดนี้โหลดไฟล์ XPS ที่มีอยู่ (`Sample.xps`) เข้าไปในอ็อบเจ็กต์ `XpsDocument` พร้อมสำหรับการจัดการ.

## ขั้นตอนที่ 3: ลบหน้าตาม Index

```csharp
// ExStart:5
// Remove the first page (at index 1).
doc.RemovePageAt(1);
// ExEnd:5
```

เมธอด `RemovePageAt` **ลบหน้าที่ตำแหน่งที่ระบุ** จำไว้ว่าการนับเริ่มจาก 0, ดังนั้น `1` จะลบหน้าที่สอง ปรับค่า index เพื่อกำหนดหน้าที่คุณต้องการลบ.

## ขั้นตอนที่ 4: บันทึก XPS Document ที่ได้

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "Sample_out.xps");
// ExEnd:6
```

หลังจากลบ, เอกสารจะถูกบันทึกเป็น `Sample_out.xps`. ตอนนี้คุณสามารถเปิดไฟล์นี้เพื่อยืนยันว่าหน้าที่ไม่ต้องการได้ถูกลบออกแล้ว.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **Index out of range** | พยายามลบหน้าที่ไม่มีอยู่. | ตรวจสอบจำนวนหน้าด้วย `doc.Pages.Count` ก่อนเรียก `RemovePageAt`. |
| **File locked** | ไฟล์ XPS เปิดอยู่ในโปรแกรมอื่น. | ปิดโปรแกรมดูไฟล์หรือให้แน่ใจว่าไฟล์ไม่ได้ถูกใช้งานก่อนรันโค้ด. |
| **License not applied** | ใช้ไลบรารีโดยไม่มีใบอนุญาตที่ถูกต้องในสภาพการผลิต. | ใช้ใบอนุญาตชั่วคราวหรือถาวรโดยใช้ `License license = new License(); license.SetLicense("Aspose.Page.lic");` |

## คำถามที่พบบ่อย

**Q1: Can I remove multiple pages at once using Aspose.Page for .NET?**  
A1: ใช่, เพียงเรียก `RemovePageAt` หลายครั้งหรือวนลูปผ่านรายการของ index (จำไว้ว่าให้ลบจาก index ที่สูงสุดไปยังต่ำสุดเพื่อให้ index ที่เหลือยังคงถูกต้อง).

**Q2: Is Aspose.Page compatible with the latest .NET framework?**  
A2: Aspose.Page มีการอัปเดตอย่างสม่ำเสมอเพื่อรองรับ .NET รุ่นใหม่ล่าสุด, รวมถึง .NET 6 และ .NET 7.

**Q3: Can I use Aspose.Page for commercial applications?**  
A3: แน่นอน. สำหรับรายละเอียดการให้ใบอนุญาต, เยี่ยมชมหน้า [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q4: Where can I find additional support and discussions on Aspose.Page?**  
A4: เข้าร่วมชุมชนที่ [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับเคล็ดลับ, ตัวอย่าง, และการช่วยแก้ปัญหา.

**Q5: Do I need a temporary license for testing Aspose.Page?**  
A5: ใช่, คุณสามารถรับ [temporary license](https://purchase.aspose.com/temporary-license/) เพื่อประเมินไลบรารีก่อนซื้อ.

**Q6: How do I preserve document metadata after removing a page?**  
A6: เมธอด `RemovePageAt` จะรักษาเมตาดาต้าต้นฉบับโดยอัตโนมัติ. หากต้องการแก้ไข, ใช้คอลเลกชัน `doc.DocumentProperties`.

## สรุป

คุณได้เรียนรู้วิธี **remove page xps** เอกสารและ **delete page at index** ด้วย Aspose.Page สำหรับ .NET แล้ว วิธีการที่กระชับนี้ทำให้คุณสามารถรวมตรรกะการลบหน้าเข้าไปในแอปพลิเคชัน .NET ของคุณได้โดยตรง, ให้คุณควบคุมเนื้อหาเอกสาร XPS ได้เต็มที่.

---

**อัปเดตล่าสุด:** 2026-03-19  
**ทดสอบด้วย:** Aspose.Page 24.12 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}