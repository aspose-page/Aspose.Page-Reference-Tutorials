---
date: 2026-03-21
description: Tìm hiểu cách điền văn bản và thêm văn bản vào tài liệu PS bằng Aspose.Page
  cho .NET. Hướng dẫn chi tiết từng bước kèm ví dụ mã.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Cách điền văn bản vào tài liệu PostScript (PS) bằng Aspose.Page
url: /vi/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Điền Văn Bản trong Tài Liệu PostScript (PS) bằng Aspose.Page

## Introduction

Nếu bạn cần **how to fill text** trong một tệp PostScript (PS), Aspose.Page cho .NET giúp thực hiện một cách dễ dàng. Dù bạn đang tạo báo cáo, hoá đơn hay đồ họa tùy chỉnh, việc thêm và định dạng văn bản là một yêu cầu cốt lõi. Trong hướng dẫn này, chúng tôi sẽ đi qua toàn bộ quy trình — từ thiết lập môi trường đến lưu tài liệu PS cuối cùng — để bạn tự tin thêm văn bản vào các tệp PS trong ứng dụng .NET của mình.

## Quick Answers
- **What does “fill text” mean?** It renders characters using a solid brush, painting the glyphs directly onto the page.  
- **Can I use custom fonts?** Yes—Aspose.Page supports custom fonts via the `add custom font ps` feature.  
- **How do I save the PS document?** Call `document.Save()` after closing the page; this writes the file to disk (`save ps document`).  
- **Is “fill and stroke text” supported?** Absolutely; use `FillAndStrokeText` to apply both fill and outline.  
- **What .NET versions are required?** Any .NET Framework 4.5+ or .NET Core/5/6+ runtime.

## What is “how to fill text” in a PS document?

Việc điền văn bản có nghĩa là tô màu các ký tự bằng một màu (hoặc brush) đồng nhất mà không có viền. Trong PostScript, điều này tương tự như toán tử `fill`. Aspose.Page trừu tượng hoá nó thành các phương thức dễ dùng như `FillText` và `FillAndStrokeText`.

## Why use Aspose.Page for adding custom font ps?

- **Full font support** – system fonts and external TrueType/OpenType fonts work out of the box.  
- **Precise positioning** – you control X/Y coordinates, size, and style.  
- **Rich styling** – combine fills, strokes, and pens for effects such as “fill and stroke text”.  
- **Cross‑platform** – works on Windows, Linux, and macOS with the same API.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- **Aspose.Page for .NET** – download the library from the [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/).  
- **Document Directory** – a folder on your machine where the source and output PS files will live (referred to as *Your Document Directory* in the code).  
- **Fonts Folder** – a sub‑folder that contains any custom fonts you plan to use.

## Import Namespaces

First, import the required namespaces so the compiler knows where to find the classes we’ll use:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step‑by‑Step Guide

### Step 1: Create Output Stream for PS Document  

We open a `FileStream` that will hold the generated PS file, configure `PsSaveOptions` to point at our custom fonts folder, and instantiate a `PsDocument`.

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

> **Pro tip:** Keep the `using` block to ensure the stream is closed automatically, which also finalizes the PS file (`save ps document`).

### Step 2: Fill Text with a System Font  

Here we demonstrate the basic **how to fill text** operation using the built‑in *Times New Roman* font.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Step 3: Fill Text with a Custom Font  

If you need a specific look, load a custom font from the fonts folder using `ExternalFontCache.FetchDrFont`. This satisfies the **add custom font ps** requirement.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Step 4: Outline (Stroke) Text with a System Font  

Outlining draws the glyph’s contour. Combine it with a fill for a “fill and stroke” effect.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Why this matters:** The `FillAndStrokeText` call shows how to **fill and stroke text** in a single step, giving you richer typographic control.

### Step 5: Outline Text with a Custom Font  

The same outline technique works with any custom font you’ve loaded.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Step 6: Close Page and Save the Document  

Finishing up is simple: close the current page and invoke `Save()` to write the PS file to disk.

```csharp
document.ClosePage();
document.Save();
}
```

> **Result:** You’ll find `AddText_outPS.ps` in *Your Document Directory*, containing both filled and stroked text rendered with system and custom fonts.

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **Custom font not found** | Verify that the font file (.ttf/.otf) exists in the folder referenced by `AdditionalFontsFolders`. |
| **Text appears at wrong position** | Adjust the X/Y coordinates passed to `FillText`/`OutlineText`. Remember that PostScript uses points (1/72 inch). |
| **Colors look different** | Ensure you are using `SolidBrush` or `Pen` with the correct `Color` values. |
| **Document not saving** | Confirm the `using` block completes without exceptions and that the application has write permissions to the target folder. |

## Frequently Asked Questions

**Q: Can I use Aspose.Page with other .NET libraries?**  
A: Yes, Aspose.Page integrates smoothly with other .NET components, allowing you to combine PDF, image, or chart libraries in the same solution.

**Q: Are custom fonts essential for this process?**  
A: While system fonts work fine, custom fonts give you full design freedom and are useful when brand‑specific typography is required.

**Q: Is Aspose.Page suitable for large‑scale document processing?**  
A: Absolutely. The library is optimized for high‑throughput scenarios and can handle thousands of PS files efficiently.

**Q: Can I modify the position of the text in the PS document?**  
A: Certainly—simply change the numeric X/Y values in the `FillText` or `OutlineText` calls.

**Q: Where can I seek assistance for Aspose.Page‑related queries?**  
A: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) to connect with the community and get expert help.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose