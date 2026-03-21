---
date: 2026-03-21
description: 學習如何使用 Aspose.Page for .NET 以 C# 建立包含 Unicode 文字的 PostScript 文件——快速提升文件處理功能。
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: 在 C# 中使用 Unicode 文字建立 PostScript 文件 – Aspose.Page
url: /zh-hant/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 向 PostScript (PS) 添加 Unicode 字串文字

## 介紹

如果您需要 **create a PostScript document C#** 並嵌入 Unicode 字元，Aspose.Page for .NET 讓此過程變得簡單。在本教學中，我們將逐步示範完整的實作範例，說明如何將日文文字（或任何 Unicode 字串）加入 PS 檔案、選擇自訂字型，並儲存結果。完成後，您將擁有可直接放入任何 C# 專案的可重用程式碼片段。

## 快速答案
- **What does this tutorial cover?** Adding Unicode text to a PostScript file using Aspose.Page in C#.
- **Which library is required?** Aspose.Page for .NET (latest version).
- **Do I need a special font?** Any TrueType/OpenType font that supports the desired Unicode range, e.g., *Arial Unicode MS*.
- **How many lines of code?** About 30 lines, split into clear steps.
- **Is a license needed?** A temporary license works for evaluation; a full license is required for production.

## 什麼是 “create postscript document c#”？
在 C# 中建立 PostScript 文件意味著以程式方式產生符合 PostScript 語言規範的 .ps 檔案。Aspose.Page 抽象化了低階細節，讓您專注於文字、圖形與字型等內容。

## 為什麼使用 Aspose.Page 處理 Unicode 文字？
- **Full Unicode support** – render characters from any language without manual encoding.
- **Device‑independent** – the same code works for PS, EPS, and PDF outputs.
- **No external dependencies** – the library handles font loading and glyph mapping internally.

## 前置條件

- Basic familiarity with C# and .NET development.
- Aspose.Page for .NET library installed. You can download it from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- A folder containing the fonts you plan to use (e.g., *Arial Unicode MS*).

## 匯入命名空間

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟 1：設定文件目錄與字型資料夾

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## 步驟 2：為 PostScript 文件建立輸出串流

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

## 步驟 3：使用自訂字型加入 Unicode 文字

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## 步驟 4：關閉目前頁面

```csharp
document.ClosePage();
```

## 步驟 5：完成並儲存文件

```csharp
document.Save();
```

## 常見問題與解決方案

- **Font not found** – Ensure the `AdditionalFontsFolders` path points to the folder containing the .ttf/.otf files and that the font name matches exactly.
- **Garbage characters** – Verify that the source string is encoded as UTF‑8 in your C# source file (use `#pragma warning disable 1591` if needed).
- **File not created** – Check write permissions on `dataDir` and that the stream is properly disposed (the `using` block handles this).

## 常見問答

**Q: Can I use Aspose.Page for .NET with other programming languages?**  
A: Aspose.Page is primarily designed for .NET, but there are Java equivalents available.

**Q: How do I obtain a temporary license for Aspose.Page for .NET?**  
A: Visit [Temporary License](https://purchase.aspose.com/temporary-license/) for obtaining a temporary license.

**Q: Is there a community forum for Aspose.Page discussions?**  
A: Yes, visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

**Q: What formats can Aspose.Page for .NET work with?**  
A: Aspose.Page supports various formats, including XPS, PS, EPS, PDF, and more.

**Q: Can I customize the appearance of the added text?**  
A: Yes, you can customize the font, size, color, and other properties of the text in Aspose.Page.

## 結論

在本教學中，我們示範了如何 **create a PostScript document C#** 並使用 Aspose.Page 嵌入 Unicode 文字。依照上述步驟，您即可快速將多語言文字渲染整合至任何 .NET 應用程式，全面掌控文件產生與版面配置。

---

**最後更新：** 2026-03-21  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}