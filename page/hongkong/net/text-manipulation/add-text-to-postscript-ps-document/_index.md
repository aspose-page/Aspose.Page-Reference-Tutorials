---
date: 2026-03-21
description: 學習如何使用 Aspose.Page for .NET 填寫文字並向 PS 文件加入文字。一步一步的指南，附有程式碼範例。
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page 在 PostScript（PS）文件中填充文字
url: /zh-hant/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 PostScript (PS) 文件中填充文字（使用 Aspose.Page）

## 介紹

如果您需要在 PostScript (PS) 檔案中 **填充文字**，Aspose.Page for .NET 讓這個操作變得簡單。無論是產生報表、發票或自訂圖形，加入與樣式化文字都是核心需求。在本教學中，我們將從環境設定到儲存最終的 PS 文件，完整示範整個流程，讓您能在 .NET 應用程式中自信地為 PS 檔案加入文字。

## 快速回答
- **「fill text」是什麼意思？** 它使用實心筆刷渲染字元，直接在頁面上繪製字形。  
- **我可以使用自訂字型嗎？** 可以 — Aspose.Page 透過 `add custom font ps` 功能支援自訂字型。  
- **如何儲存 PS 文件？** 在關閉頁面後呼叫 `document.Save()`；這會將檔案寫入磁碟 (`save ps document`)。  
- **是否支援「fill and stroke text」？** 當然支援；使用 `FillAndStrokeText` 以同時套用填充與輪廓。  
- **需要哪個 .NET 版本？** 任何 .NET Framework 4.5 以上或 .NET Core/5/6 以上的執行環境。

## 在 PS 文件中「填充文字」是什麼？

填充文字指的是使用實心顏色（或筆刷）繪製字元而不加輪廓。在 PostScript 中，這相當於 `fill` 運算子。Aspose.Page 將其抽象為易於使用的方法，如 `FillText` 和 `FillAndStrokeText`。

## 為什麼使用 Aspose.Page 來加入自訂字型 ps？

- **完整字型支援** – 系統字型與外部 TrueType/OpenType 字型即插即用。  
- **精確定位** – 您可以控制 X/Y 座標、大小與樣式。  
- **豐富樣式** – 結合填充、輪廓與筆刷，可實現如「fill and stroke text」等效果。  
- **跨平台** – 在 Windows、Linux 與 macOS 上皆可使用相同的 API。

## 前置條件

在開始之前，請確保您已具備：

- **Aspose.Page for .NET** – 從 [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/) 下載此函式庫。  
- **Document Directory** – 您機器上用來存放來源與輸出 PS 檔案的資料夾（程式碼中稱為 *Your Document Directory*）。  
- **Fonts Folder** – 包含您計畫使用的任何自訂字型的子資料夾。

## 匯入命名空間

首先匯入所需的命名空間，讓編譯器知道要使用哪些類別：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟指南

### 步驟 1：為 PS 文件建立輸出串流  

我們開啟一個 `FileStream` 以保存產生的 PS 檔案，設定 `PsSaveOptions` 指向自訂字型資料夾，並實例化 `PsDocument`。

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

> **Pro tip:** 保持 `using` 區塊，以確保串流自動關閉，這同時也會完成 PS 檔案的最終寫入 (`save ps document`)。

### 步驟 2：使用系統字型填充文字  

此範例示範使用內建 *Times New Roman* 字型執行基本 **填充文字** 操作。

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### 步驟 3：使用自訂字型填充文字  

若需要特定外觀，請使用 `ExternalFontCache.FetchDrFont` 從字型資料夾載入自訂字型。這滿足 **add custom font ps** 的需求。

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### 步驟 4：使用系統字型描邊（輪廓）文字  

描邊會繪製字形的輪廓。將其與填充結合即可產生「fill and stroke」效果。

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Why this matters:** `FillAndStrokeText` 呼叫示範了如何在單一步驟中 **fill and stroke text**，讓您獲得更豐富的排版控制。

### 步驟 5：使用自訂字型描邊文字  

相同的描邊技術亦適用於任何已載入的自訂字型。

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### 步驟 6：關閉頁面並儲存文件  

完成非常簡單：關閉目前的頁面，然後呼叫 `Save()` 將 PS 檔案寫入磁碟。

```csharp
document.ClosePage();
document.Save();
}
```

> **Result:** 您會在 *Your Document Directory* 中找到 `AddText_outPS.ps`，其中包含使用系統與自訂字型渲染的填充與描邊文字。

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **找不到自訂字型** | 確認字型檔案 (.ttf/.otf) 存在於 `AdditionalFontsFolders` 所指向的資料夾中。 |
| **文字出現在錯誤位置** | 調整傳遞給 `FillText`/`OutlineText` 的 X/Y 座標。請記得 PostScript 使用點 (1/72 英吋) 為單位。 |
| **顏色顯示不同** | 確認使用 `SolidBrush` 或 `Pen` 時的 `Color` 值正確。 |
| **文件未儲存** | 確認 `using` 區塊在無例外情況下完成，且應用程式對目標資料夾具有寫入權限。 |

## 常見問答

**Q: 我可以將 Aspose.Page 與其他 .NET 函式庫一起使用嗎？**  
A: 可以，Aspose.Page 能順暢整合其他 .NET 元件，讓您在同一解決方案中結合 PDF、影像或圖表函式庫。

**Q: 自訂字型在此流程中是否必須？**  
A: 雖然系統字型已足夠使用，但自訂字型能提供完整的設計自由度，且在需要品牌專屬排版時相當有用。

**Q: Aspose.Page 是否適用於大規模文件處理？**  
A: 絕對適用。此函式庫已針對高吞吐量情境進行最佳化，能有效處理成千上萬的 PS 檔案。

**Q: 我可以修改 PS 文件中文字的位置嗎？**  
A: 當然可以，只需變更 `FillText` 或 `OutlineText` 呼叫中的數值 X/Y 即可。

**Q: 我可以在哪裡取得 Aspose.Page 相關問題的協助？**  
A: 前往 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 與社群互動，獲得專業支援。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-21  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose