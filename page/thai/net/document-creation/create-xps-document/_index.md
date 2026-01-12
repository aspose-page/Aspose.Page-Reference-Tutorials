---
date: 2026-01-12
description: เรียนรู้วิธีสร้างเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET – คู่มือแบบขั้นตอนต่อขั้นตอนเพื่อสร้างเอกสารอิเล็กทรอนิกส์คุณภาพสูง
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: สร้างเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET
url: /th/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET

## Introduction

ยินดีต้อนรับสู่คู่มือแบบขั้นตอนของเราว่า **วิธีสร้างเอกสาร XPS** ด้วย Aspose.Page สำหรับ .NET ในบทเรียนนี้ เราจะสำรวจกระบวนการสร้างไฟล์ XPS ซึ่งเป็นรูปแบบที่ใช้กันอย่างแพร่หลายสำหรับเอกสารอิเล็กทรอนิกส์ ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นกับ Aspose.Page คู่มือนี้ออกแบบมาเพื่อช่วยคุณสร้างเอกสาร XPS อย่างราบรื่นด้วยตัวอย่างที่ชัดเจนและคำอธิบายที่ละเอียด

## Quick Answers
- **What library do I need?** Aspose.Page for .NET  
- **Can I run this on .NET Core?** Yes, the library fully supports .NET Core and .NET 5/6  
- **How many lines of code?** Less than 20 lines to produce a basic XPS file  
- **Do I need a license for testing?** A free trial is available; a license is required for production  
- **What format does the output have?** XPS (XML Paper Specification)  

## How to create XPS document using Aspose.Page for .NET

ด้านล่างนี้คุณจะพบทุกอย่างที่ต้องการก่อนเริ่มเขียนโค้ด พร้อมด้วยขั้นตอนสั้น ๆ ที่เรียงลำดับเป็นหมายเลข

## Prerequisites

ก่อนที่เราจะลงลึกในบทเรียน โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้ครบถ้วน:

1. Aspose.Page for .NET Library: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Page จาก [download link](https://releases.aspose.com/page/net/)  

2. Your Document Directory: เลือกหรือสร้างโฟลเดอร์บนระบบของคุณที่ต้องการบันทึกไฟล์ XPS ที่สร้างขึ้น  

ตอนนี้มาลงมือทำบทเรียนกันเลย!

## Import Namespaces

เพื่อใช้ Aspose.Page สำหรับ .NET คุณต้องนำเข้า namespace ที่จำเป็นเข้าสู่โปรเจกต์ของคุณ ทำตามขั้นตอนต่อไปนี้:

### Step 1: Add Reference to Aspose.Page

ในโปรเจกต์ของคุณ ให้เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Page สำหรับ .NET คุณสามารถค้นหาไฟล์ DLL ที่ต้องการในแพคเกจที่ดาวน์โหลดมา

### Step 2: Import Namespaces

เพิ่ม namespace ต่อไปนี้ในไฟล์โค้ดของคุณ:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

เมื่อเราตั้งค่าข้อกำหนดเบื้องต้นและนำเข้า namespace ที่จำเป็นแล้ว เราจะมาวิเคราะห์กระบวนการสร้างเอกสาร XPS เป็นหลายขั้นตอน

## Step 1: Set Document Directory

```csharp
string dir = "Your Document Directory";
```

อย่าลืมแทนที่ `"Your Document Directory"` ด้วยพาธจริงที่คุณต้องการบันทึกไฟล์ XPS

## Step 2: Create XPS Document

```csharp
XpsDocument xDocs = new XpsDocument();
```

สร้างเอกสาร XPS ใหม่โดยใช้คลาส `XpsDocument`

## Step 3: Add Glyphs to the Document

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

ใช้เมธอด `AddGlyphs` เพื่อเพิ่ม glyphs (ข้อความ) ลงในเอกสาร ปรับแต่งฟอนต์ ขนาด สไตล์ และตำแหน่งตามต้องการ

## Step 4: Set Glyph Fill Color

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

กำหนดสีเติมสำหรับ glyphs ที่เพิ่มเข้ามา ในตัวอย่างนี้เราใช้สีดำ แต่คุณสามารถเลือกสีใดก็ได้

## Step 5: Save the Result

```csharp
xDocs.Save(dir + "output.xps");
```

สุดท้าย ให้บันทึกเอกสาร XPS ไปยังโฟลเดอร์ที่ระบุพร้อมชื่อไฟล์ที่ต้องการ ไฟล์ XPS ที่ได้จะมีข้อความ "Hello World!"

Congratulations! You've successfully created an XPS document using Aspose.Page for .NET.

## Common Tips & Gotchas

- **Directory Path** – ใช้ `Path.Combine(dir, "output.xps")` เพื่อหลีกเลี่ยงปัญหาเครื่องหมายแยกพาธที่แตกต่างกันบนระบบปฏิบัติการต่าง ๆ  
- **Font Availability** – ฟอนต์ที่คุณระบุต้องติดตั้งอยู่บนเครื่องที่รันโค้ด มิฉะนั้น Aspose จะใช้ฟอนต์เริ่มต้นแทน  
- **Multiple Pages** – หากต้องการสร้างไฟล์ XPS หลายหน้า ให้สร้างอ็อบเจกต์ `XpsPage` เพิ่มเติมและเพิ่มเนื้อหาในแต่ละหน้า ก่อนทำการบันทึก

## Conclusion

ในบทเรียนนี้ เราได้อธิบายขั้นตอนการสร้างเอกสาร XPS ด้วย Aspose.Page สำหรับ .NET ไลบรารีที่ทรงพลังนี้ช่วยให้คุณสร้างเอกสารอิเล็กทรอนิกส์ได้อย่างง่ายดาย ลองทดลองใช้ฟอนต์ สไตล์ และเนื้อหาต่าง ๆ เพื่อปรับแต่งไฟล์ XPS ให้ตรงกับความต้องการของคุณ

## FAQ's

### Q1: Can I use custom fonts in my XPS document?

A1: Yes, you can specify the font family and size when adding glyphs to your XPS document.

### Q2: Is Aspose.Page compatible with .NET Core?

A2: Yes, Aspose.Page supports .NET Core, allowing you to use it in cross‑platform applications.

### Q3: How can I add images to an XPS document?

A3: Aspose.Page provides methods to add images to your XPS document. Refer to the documentation for detailed examples.

### Q4: Can I create multi‑page XPS documents?

A4: Absolutely! You can add multiple pages to an XPS document using the Aspose.Page library.

### Q5: Is there a trial version available?

A5: Yes, you can explore the features of Aspose.Page by downloading the [free trial](https://releases.aspose.com/).

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}