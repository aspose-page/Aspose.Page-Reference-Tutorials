---
date: 2026-02-25
description: เรียนรู้วิธีสร้างเอกสาร XPS และใช้ไลเนียร์เกรเดียนท์กับ Aspose.Page สำหรับ
  .NET. ทำตามคู่มือขั้นตอนต่อขั้นตอนของเราเพื่อบันทึกไฟล์ XPS.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: สร้างเอกสาร XPS ด้วยการไล่สีแนวตั้งโดยใช้ Aspose.Page
url: /th/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่ม Gradient แนวตั้งใน XPS ด้วย Aspose.Page สำหรับ .NET

## Introduction

ในบทแนะนำนี้คุณจะ **สร้างเอกสาร XPS** ที่มี gradient แนวตั้งเรียบ การเพิ่ม gradient เป็นวิธีทั่วไปที่ทำให้ไฟล์ XPS ดูเป็นมืออาชีพมากขึ้น—เหมาะสำหรับรายงาน, โบรชัวร์, หรือกราฟิกที่ต้องพิมพ์ เราจะเดินผ่านทุกขั้นตอน ตั้งแต่การตั้งค่าโปรเจกต์จนถึงการบันทึกไฟล์ XPS สุดท้าย เพื่อให้คุณสามารถใช้ linear gradient กับ path ใดก็ได้อย่างรวดเร็ว

## Quick Answers
- **What does this tutorial cover?** การเพิ่ม vertical linear gradient ให้กับ path ในเอกสาร XPS.  
- **Which library is required?** Aspose.Page for .NET.  
- **Do I need a license?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **How long does implementation take?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน.  
- **Can I save the result as an XPS file?** ได้, เมธอด `Save` จะเขียนไฟล์ลงดิสก์.

## What is a vertical gradient in XPS?

Vertical gradient คือการเปลี่ยนสีที่ไหลจากด้านบนของรูปไปยังด้านล่าง ใน XPS สิ่งนี้ทำได้ด้วย **linear gradient brush** ที่กำหนดจุดเริ่มต้นและจุดสิ้นสุด พร้อมกับชุดของ gradient stops ที่ควบคุมสีในตำแหน่งต่าง ๆ

## Why use Aspose.Page to create XPS document with gradients?

- **Full .NET integration** – ทำงานกับ .NET Framework, .NET Core, และ .NET 5/6+.  
- **No external dependencies** – การเรนเดอร์ทั้งหมดจัดการโดยไลบรารี.  
- **High fidelity** – gradient แสดงผลตรงตามที่กำหนด, สอดคล้องกับสเปค XPS.  
- **Easy to maintain** – โมเดลอ็อบเจ็กต์ที่ชัดเจนสำหรับ path, brush, และสี.

## Prerequisites

- Aspose.Page for .NET Library: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.Page for .NET ในสภาพแวดล้อมการพัฒนาแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/page/net/).
- Development Environment: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ด้วย IDE ที่คุณชอบ เช่น Visual Studio.

ตอนนี้ทุกอย่างพร้อมแล้ว, ไปดูกันที่โค้ดกันเถอะ

## Import Namespaces

ในแอปพลิเคชัน .NET ของคุณ, ให้รวม namespace ที่จำเป็นเพื่อเข้าถึงคลาสและเมธอดของ Aspose.Page

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set Up Your Document Directory

กำหนดโฟลเดอร์ที่ไฟล์ XPS ที่สร้างขึ้นจะถูกบันทึก

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

สร้างอินสแตนซ์ของเอกสาร XPS ใหม่ที่เราจะเติมด้วย path ที่มี gradient‑filled

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Define Gradient Stops

Gradient stops กำหนดสีและตำแหน่งของมันตามเส้น gradient ที่นี่เราสร้างห้าจุดเพื่อให้ได้การเปลี่ยนสีแนวตั้งที่เรียบ

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Step 4: Create a Path with Gradient

เราวาด path รูปสี่เหลี่ยมและใช้ **linear gradient brush** ที่วิ่งแนวตั้งจากจุด (10, 110) ไปยังจุด (10, 200). brush จะรับ gradient stops ที่กำหนดไว้ก่อนหน้า

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

สุดท้าย, เขียนเอกสาร XPS ลงดิสก์ ขั้นตอน **save XPS file** นี้จะสร้างไฟล์ `AddVerticalGradient_outXPS.xps` ในโฟลเดอร์ที่คุณระบุ

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Pro tip:** ตรวจสอบผลลัพธ์โดยเปิดไฟล์ XPS ใน Windows XPS Viewer หรือโปรแกรมดูไฟล์อื่นใดเพื่อให้แน่ใจว่า gradient แสดงตามที่คาดหวัง

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Gradient appears as solid color | Gradient stops not added to brush | ตรวจสอบให้แน่ใจว่าได้เรียก `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` แล้ว. |
| File not found on save | `dataDir` points to a non‑existent folder | สร้างโฟลเดอร์ก่อนหรือใช้เส้นทางแบบ absolute. |
| Colors look different | Color values use ARGB order; verify channel order | ใช้ `CreateColor(alpha, red, green, blue)` อย่างถูกต้อง. |

## Frequently Asked Questions

**Q: Is Aspose.Page compatible with Visual Studio 2019?**  
**A:** รองรับ, Aspose.Page ทำงานกับ Visual Studio 2019. ตรวจสอบว่าคุณได้ติดตั้งเวอร์ชันที่ถูกต้องของไลบรารี.

**Q: Can I use Aspose.Page for commercial projects?**  
**A:** ได้, Aspose.Page สามารถใช้ในโครงการเชิงพาณิชย์ได้. เยี่ยมชม [ที่นี่](https://purchase.aspose.com/buy) เพื่อดูตัวเลือกการให้ลิขสิทธิ์.

**Q: Is there a free trial available?**  
**A:** มี, คุณสามารถรับเวอร์ชันทดลองฟรีของ Aspose.Page ได้จาก [ที่นี่](https://releases.aspose.com/).

**Q: Where can I find Aspose.Page documentation?**  
**A:** เอกสารพร้อมให้บริการที่ [ที่นี่](https://reference.aspose.com/page/net/).

**Q: How can I get support or ask questions?**  
**A:** เยี่ยมชม [ฟอรั่ม Aspose.Page](https://forum.aspose.com/c/page/39) เพื่อรับการสนับสนุนจากชุมชน.

## Conclusion

ตอนนี้คุณรู้วิธี **สร้างเอกสาร XPS**, **ใช้ linear gradient**, และ **บันทึกไฟล์ XPS** ด้วย Aspose.Page สำหรับ .NET วิธีนี้ให้คุณควบคุมการออกแบบภาพได้อย่างเต็มที่ในผลลัพธ์ XPS ทำให้เอกสารที่พิมพ์ออกมาน่าสนใจยิ่งขึ้น

---  

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}