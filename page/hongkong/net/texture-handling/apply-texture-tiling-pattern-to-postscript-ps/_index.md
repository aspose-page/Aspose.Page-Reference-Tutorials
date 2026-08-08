---
date: 2026-03-26
description: 學習如何使用 Aspose.Page 在 .NET 中建立帶有紋理平鋪圖案的 PostScript 文件。按照我們的逐步指南，為您的 PS
  檔案添加豐富的紋理。
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: 建立具紋理平鋪的 PostScript .NET 文件
url: /zh-hant/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立具紋理平鋪的 PostScript .NET 文件

## 如何在 .NET 中建立具紋理平鋪的 PostScript 文件

在本教學中，你將學會如何 **建立 PostScript 文件 .NET**，並使用 Aspose.Page 函式庫以紋理平鋪圖案為其增色。我們會一步步說明，從專案設定到使用紋理筆刷填充與描邊文字，讓你在數分鐘內產出視覺效果佳的 PS 檔案。

## 快速回答
- **使用哪個函式庫？** Aspose.Page for .NET  
- **可以使用 .NET Core 嗎？** 可以，函式庫支援 .NET Core 以及 .NET 5/6  
- **紋理支援哪些影像格式？** 任何 System.Drawing 支援的格式（BMP、PNG、JPEG 等）  
- **實作需要多久？** 基本範例約 10‑15 分鐘即可完成  
- **需要授權嗎？** 免費試用可用於測試；正式環境需購買授權  

## 前置條件

- 已在電腦上安裝 [Visual Studio](https://visualstudio.microsoft.com/)  
- 具備 C# 程式基礎  
- 下載並安裝 [Aspose.Page for .NET library](https://releases.aspose.com/page/net/)  
- 準備一張作為紋理圖案的影像檔（例如 **TestTexture.bmp**）

## 匯入命名空間

在 C# 檔案中匯入所需的命名空間，讓編譯器能找到我們將使用的型別：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟 1：設定文件目錄

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

將 **Your Document Directory** 替換為你希望儲存產生的 PS 檔案的資料夾路徑。

## 步驟 2：為 PS 文件建立輸出串流

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

此段程式碼會開啟檔案串流、設定頁面大小（預設 A4），並建立一個全新的 **PsDocument** 實例供後續繪圖使用。

## 步驟 3：套用紋理平鋪圖案

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

在此我們載入位圖、以 **TextureBrush** 包裝，必要時水平拉伸，並告訴 **PsDocument** 在之後的繪圖操作中使用此筆刷。

## 步驟 4：建立矩形路徑並填充

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

定義一個簡單的矩形，並以先前設定的紋理筆刷進行填充。

## 步驟 5：設定描邊並繪製

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

取得目前的繪圖筆刷（即紋理筆刷），建立紅色筆刷作為輪廓，然後繪製矩形的邊框。

## 步驟 6：以紋理圖案填充與描邊文字

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

此步驟示範 **填充與描邊文字** 的功能：字元 “ABC” 先以紋理筆刷填滿，再以筆刷描邊，產生醒目的視覺效果。

## 步驟 7：儲存並關閉文件

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

關閉頁面會完成繪圖指令，`Save()` 則會將 PostScript 檔寫入磁碟。

## 常見問題與解決方案

- **紋理被拉伸得不正確** – 調整 `Matrix` 的數值以控制 X/Y 方向的縮放比例。  
- **找不到影像檔** – 確認 `dataDir` 指向正確的資料夾，且檔名大小寫完全相符。  
- **顏色顯示異常** – 記得 PostScript 使用與裝置無關的色彩空間，請確保使用的 `Color` 物件能正確對應。

## 常見問答

**Q:** 可以使用其他影像格式作為紋理圖案嗎？  
**A:** 可以，任何 `System.Drawing.Bitmap` 支援的格式（BMP、PNG、JPEG、GIF 等）皆可使用。

**Q:** Aspose.Page 是否相容 .NET Core？  
**A:** 完全相容。此函式庫可在 .NET Framework、.NET Core 以及 .NET 5/6 上執行。

**Q:** 要如何變更紋理矩形的大小？  
**A:** 在建立矩形的步驟中調整 `RectangleF` 的參數（例如 `new RectangleF(0, 0, 300, 150)`）。

**Q:** 能在同一文件中套用多種紋理圖案嗎？  
**A:** 能。只要建立不同影像的 `TextureBrush`，在繪製下一個圖形或文字前再次呼叫 `SetPaint` 即可。

**Q:** 哪裡可以找到更多範例與 API 參考？  
**A:** 前往 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 取得社群協助，或參考官方的 [documentation](https://reference.aspose.com/page/net/) 瞭解詳細 API 用法。

## 結論

現在你已掌握如何 **建立 PostScript 文件 .NET**，並套用紋理平鋪圖案，包括 **以紋理填充與描邊文字** 的技巧。可自行嘗試不同影像、縮放矩陣與繪圖基元，製作客製化的 PS 檔案，用於報告、傳單或任何圖形密集的輸出需求。

---

**最後更新：** 2026-03-26  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}