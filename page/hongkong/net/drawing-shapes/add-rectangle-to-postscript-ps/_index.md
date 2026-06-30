---
date: 2026-06-30
description: 了解如何使用 Aspose.Page for .NET 建立 PostScript 文件 .NET 並新增矩形。一步一步的指南，附有程式碼範例。
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: 將矩形新增至 PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: 建立 PostScript 文件 .NET – 新增矩形 Aspose.Page
url: /zh-hant/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 在 PostScript (PS) 中加入矩形

## 介紹

Aspose.Page for .NET 是一套可程式化建立與操作 PostScript、EPS 與 XPS 檔案的函式庫。如果您正尋找 **create postscript document .net**，本教學將示範如何使用 Aspose.Page 在 PostScript 文件中加入矩形，為更豐富的圖形產生奠定堅實基礎。

## 快速回答
- **需要什麼函式庫？** Aspose.Page for .NET.  
- **可以從頭開始建立 PostScript 文件嗎？** 可以 – API 允許您以程式方式建立 PS 檔案。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式環境需購買授權。  
- **實作需要多久？** 基本圖形通常在 10 分鐘內完成。

## 什麼是使用 .NET 建立 PostScript 文件？
在 .NET 中建立 PostScript 文件是指以程式方式產生 `.ps` 檔案，該檔案描述頁面內容——文字、圖形或形狀——使用 Aspose.Page API。此方式非常適合伺服器端圖形產生、自動化報表建立，或任何需要精確控制輸出格式的情境。

## 為什麼使用 Aspose.Page for .NET？
Aspose.Page 支援 **30+ 圖形基元**，且可產生高達 **500 MB** 的檔案而不必將整個文件載入記憶體，於 Windows、Linux 與 macOS 上提供高效能渲染。它讓您完整掌控形狀、顏色與筆觸，同時免除撰寫低階 PostScript 程式碼的需求。

- **完整的圖形控制** – 繪製形狀、設定顏色與筆觸，無需處理低階 PS 語法。  
- **跨平台** – 可在 Windows、Linux 與 macOS 執行環境上運作。  
- **無外部相依性** – 函式庫內部自行處理所有 PS 產生。  
- **豐富的文件與範例** – 可快速上手。

## 前置條件

- **Aspose.Page for .NET 函式庫** – 從 [here](https://releases.aspose.com/page/net/) 下載並安裝。  
- **開發環境** – Visual Studio、VS Code 或任何相容 .NET 的 IDE。

## 匯入命名空間

`Aspose.Page` 命名空間提供您需要的核心類別，如 `Document`、`Page`、`SolidBrush` 與 `Pen`。在開始編寫程式碼前先匯入它。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

現在讓我們將範例分解為清晰的編號步驟。

## 步驟 1：設定文件目錄

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您希望儲存產生的 PS 檔案的資料夾路徑。

## 步驟 2：為 PostScript 文件建立輸出串流

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

此串流指向 **AddRectangle_outPS.ps**。如需可自行重新命名檔案或變更儲存位置。

## 步驟 3：設定儲存選項並建立 PS 文件

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

此處告訴 Aspose.Page 使用 A4 頁面尺寸，並建立單頁文件。

## 步驟 4：加入填色矩形

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

我們在 (250, 100) 定義一個寬 150、高 100 的矩形，設定橙色筆刷，並填滿形狀。

## 步驟 5：加入外框矩形

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

第二個矩形位於頁面較低處，這次使用紅色 3 點筆觸。

## 步驟 6：關閉頁面並儲存文件

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

關閉頁面即完成繪圖，`Save()` 會將 PS 檔寫入磁碟。

## 如何使用 .NET 建立 PostScript 文件？
`Document` 是 Aspose.Page 中代表 PostScript 檔案的主要類別。`SaveOptions` 指定頁面大小與輸出格式等設定。載入 `Document` 物件後，為 A4 頁面配置 `SaveOptions`，使用 `SolidBrush` 或 `Pen` 繪製形狀，最後呼叫 `document.Save()`——整個工作流程僅需數行程式碼，且可在任何支援的 .NET 執行環境上執行。此模式讓您在不觸碰原始 PS 語法的情況下，產生完全符合規範的 PostScript 檔案。

## 如何產生 PostScript 檔案
使用 Aspose.Page 的 `SaveOptions` 類別將輸出格式指定為 PostScript (`SaveFormat.PS`)。函式庫會直接將內容串流至檔案或記憶體串流，讓您在不大量佔用記憶體的前提下，高效產生大型文件。

## 常見問題與技巧

- **檔案路徑不正確** – 確認 `dataDir` 以路徑分隔符 (`\\` 或 `/`) 結尾，或使用 `Path.Combine`。  
- **缺少授權** – 在正式環境中，於建立文件前套用 Aspose 授權，以避免評估水印。  
- **顏色可見性** – 若矩形呈現空白，請確認筆刷或筆的顏色與頁面背景形成對比。

## 常見問與答

**問：** 我可以自訂矩形的顏色嗎？  
**答：** 當然可以。將 `SolidBrush` 與 `Pen` 建構式中的 `Color.Orange` 或 `Color.Red` 改成任意 `System.Drawing.Color` 即可。

**問：** Aspose.Page 是否相容其他文件格式？  
**答：** 是的。除了 PostScript，Aspose.Page 亦支援 XPS 與 EPS 產生。

**問：** 如何在同一文件加入文字？  
**答：** 使用 `TextFragment` 類別於指定座標放置文字，然後呼叫 `document.Draw(textFragment)`。

**問：** 在哪裡可以找到更多範例與完整 API 參考？  
**答：** 參考文件 [here](https://reference.aspose.com/page/net/) 並加入 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 社群。

**問：** 我可以在購買前試用 Aspose.Page 嗎？  
**答：** 可以，於 [here](https://releases.aspose.com/) 下載免費試用。若需延長評估，可考慮 [temporary license](https://purchase.aspose.com/temporary-license/)。

---

**最後更新：** 2026-06-30  
**測試環境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.Page for .NET 建立 PostScript 文件](/page/net/document-creation/create-postscript-document/)
- [使用 Aspose.Page 在 PostScript (PS) 文件加入影像](/page/net/image-management/add-image-to-postscript-ps-document/)
- [使用 Aspose.Page 在 PostScript (PS) 文件加入文字](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}