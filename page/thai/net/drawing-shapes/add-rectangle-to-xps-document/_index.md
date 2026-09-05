---
date: 2026-07-19
description: เรียนรู้วิธีสร้างเอกสาร XPS ด้วย .NET และเพิ่มสี่เหลี่ยมโดยใช้ Aspose.Page
  for .NET ในคู่มือสั้น ๆ แบบขั้นตอนต่อขั้นตอน
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: เพิ่มสี่เหลี่ยมในเอกสาร XPS
og_description: สร้างเอกสาร XPS .NET อย่างรวดเร็ว บทเรียนนี้แสดงวิธีเพิ่มสี่เหลี่ยมลงในไฟล์
  XPS โดยใช้ Aspose.Page for .NET พร้อมโค้ดและเคล็ดลับที่ชัดเจน
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: สร้างเอกสาร XPS .NET – เพิ่มสี่เหลี่ยมโดยใช้ Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: สร้างเอกสาร XPS .NET – เพิ่มสี่เหลี่ยมโดยใช้ Aspose.Page
url: /th/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเอกสาร XPS .NET – เพิ่มสี่เหลี่ยมผืนผ้าด้วย Aspose.Page

## บทนำ

In this tutorial you’ll learn how to **create XPS document .NET** and draw a rectangle inside it using Aspose.Page for .NET. Whether you are building a reporting engine, a printable invoice, or a custom graphics layer, the ability to generate XPS files programmatically gives you full control over layout and fidelity. Follow the steps below and you’ll have a ready‑to‑use XPS file in minutes.

## คำตอบสั้น
- **What is the primary goal?** สร้างเอกสาร XPS .NET และเพิ่มรูปสี่เหลี่ยมผืนผ้า.  
- **Which library is required?** Aspose.Page for .NET (ดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการ).  
- **Do I need a license for testing?** การทดลองใช้งานฟรีทำงานสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **What .NET versions are supported?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does implementation take?** ประมาณ 5‑10 นาทีสำหรับสี่เหลี่ยมพื้นฐาน.

## Aspose.Page for .NET คืออะไร?
Aspose.Page for .NET is a high‑performance, fully managed API that enables developers to programmatically create, edit, and render XPS (XML Paper Specification) documents without relying on external components. It offers a rich object model for drawing shapes, text, and images, and supports advanced features such as color management, compression, and PDF conversion, making it suitable for a wide range of document generation scenarios.

## ทำไมต้องใช้ Aspose.Page เพื่อสร้างเอกสาร XPS .NET?
Aspose.Page supports **30+ XPS features**—including vector graphics, text layout, and color management—and can generate files up to **500 MB** without loading the entire document into memory. This quantified capability ensures smooth performance even for large‑scale printing jobs.

## ข้อกำหนดเบื้องต้น

Before you begin with this tutorial, make sure you have the following prerequisites in place:

1. Aspose.Page for .NET Library: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Page for .NET ในสภาพแวดล้อมการพัฒนาแล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/page/net/).

2. Document Directory: ตั้งค่าไดเรกทอรีที่คุณต้องการเก็บเอกสาร XPS ของคุณ.

## นำเข้า Namespaces

In your .NET application, include the necessary namespaces to use Aspose.Page functionalities.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## วิธีเพิ่มสี่เหลี่ยมผืนผ้าในเอกสาร XPS ด้วย .NET?

Load the XPS document, create a `Graphics` object, define a `RectangleF` with the desired size, and call `DrawRectangle`. This sequence draws a rectangle in a single line of code and automatically handles DPI scaling. For typical A4‑size pages, a 200 × 100 pt rectangle appears centered without extra calculations.

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### ขั้นตอนที่ 2: สร้างเอกสาร XPS ใหม่

The `XpsDocument` class represents the XPS file you are building and provides methods to add pages, graphics, and other resources.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### ขั้นตอนที่ 3: เพิ่มสี่เหลี่ยมผืนผ้า

`XpsPath` defines a drawable path object within the XPS document, allowing you to set geometry, stroke, fill, and other visual properties.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### ขั้นตอนที่ 4: บันทึกเอกสาร

The `Save` method writes the constructed XPS document to the specified file path on disk.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

ยินดีด้วย! คุณได้เพิ่มสี่เหลี่ยมผืนผ้าในเอกสาร XPS ด้วย Aspose.Page for .NET อย่างสำเร็จ.

## ปัญหาทั่วไปและเคล็ดลับ

- **Missing fonts:** ตรวจสอบว่าแบบอักษรที่คุณอ้างอิงได้ติดตั้งบนเซิร์ฟเวอร์; หากไม่เช่นนั้น Aspose.Page จะใช้แบบอักษรเริ่มต้นแทน ซึ่งอาจทำให้การจัดวางเปลี่ยนแปลง.  
- **Large documents:** เมื่อสร้างไฟล์ที่ใหญ่กว่า 200 MB ให้พิจารณาเรียก `document.SaveOptions.Compress = true` เพื่อลดการใช้หน่วยความจำ.  
- **Coordinate system:** XPS ใช้หน่วยจุด (1/72 inch). อย่าลืมแปลงพิกเซลเป็นจุดหากคุณทำงานกับมิติที่อิงจากหน้าจอ.

## คำถามที่พบบ่อย

**Q: Is Aspose.Page compatible with all .NET applications?**  
A: ใช่, Aspose.Page ทำงานร่วมกับแอปพลิเคชัน .NET บนเดสก์ท็อป, เว็บ, และคลาวด์ได้อย่างราบรื่น.

**Q: Where can I find the documentation for Aspose.Page for .NET?**  
A: เอกสารอ้างอิง API เต็มรูปแบบสามารถดูได้ที่ [here](https://reference.aspose.com/page/net/).

**Q: Can I try Aspose.Page for .NET for free before purchasing?**  
A: ใช่, คุณสามารถทดลองใช้งานฟรีได้ที่ [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page for .NET?**  
A: เยี่ยมชม [this link](https://purchase.aspose.com/temporary-license/) เพื่อรับลิขสิทธิ์ชั่วคราว.

**Q: Where can I seek community support or ask questions related to Aspose.Page for .NET?**  
A: เยี่ยมชม [Aspose.Page forum](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชน.

---

**อัปเดตล่าสุด:** 2026-07-19  
**ทดสอบด้วย:** Aspose.Page for .NET 24.9  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างเอกสาร XPS ด้วย Aspose.Page for .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – วาดรูปทรง](/page/net/drawing-shapes/)
- [เพิ่มข้อความในเอกสาร XPS ด้วย Aspose.Page for .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}