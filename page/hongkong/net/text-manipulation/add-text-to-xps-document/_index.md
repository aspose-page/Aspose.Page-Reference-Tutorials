---
date: 2026-03-21
description: 學習如何在 .NET 中使用 Aspose.Page for .NET 建立 XPS 文件並加入文字。針對 .NET 開發者的逐步指南。
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: 使用 .NET 建立 XPS 文件，並以 Aspose.Page 添加文字
url: /zh-hant/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 建立 XPS 文件 .NET 並加入文字

在現代 .NET 開發中，能夠以程式方式 **create XPS document .NET** 檔案是一項寶貴的技能，尤其在需要產生可列印的報告、發票或自訂圖形時。本教學將帶領您使用 Aspose.Page 於 XPS 文件中 **aspose.page add text**，讓您在 .NET 應用程式內即可完整掌控版面配置與樣式。

## 快速解答
- **本教學涵蓋什麼內容？** 使用 Aspose.Page for .NET 在新建立的 XPS 文件中加入文字。  
- **需要多久時間？** 基本實作大約需要 5‑10 分鐘。  
- **先決條件是什麼？** .NET 開發環境與 Aspose.Page 函式庫。  
- **需要授權嗎？** 是，正式使用時需要有效的 Aspose.Page 授權。  
- **能在 .NET Core / .NET 6+ 上執行嗎？** 當然可以 – Aspose.Page 支援所有近期的 .NET 版本。

## 什麼是 create xps document .net？

在 .NET 中建立 XPS 文件即是產生一種固定版面的檔案，能在不同裝置與印表機上保留內容的精確外觀。XPS（XML Paper Specification）是微軟的開放頁面描述標準，類似 PDF，但完全基於 XML。

## 為什麼使用 Aspose.Page 加入文字？

Aspose.Page 提供高階、物件導向的 API，抽象化低階的 XPS 標記。您可以在不直接處理原始 XML 的情況下加入文字、圖形與形狀，使開發過程更快速且降低錯誤風險。

## 前置條件

- Aspose.Page for .NET：確保已安裝 Aspose.Page 函式庫。您可從 [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) 下載。
- 開發環境：設定您的 .NET 開發環境。若尚未完成，請依照 [documentation](https://reference.aspose.com/page/net/) 中提供的安裝說明操作。
- 文件目錄：建立一個用來存放文件的資料夾。將提供的程式碼片段中的 "Your Document Directory" 替換為實際路徑。

現在我們已說明基礎，讓我們深入程式碼。

## 匯入命名空間

首先，匯入必要的命名空間以啟動專案：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 步驟 1：建立 XPS 文件 .NET

建立一個全新的 XPS 文件，作為我們文字的畫布。

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## 步驟 2：建立文字筆刷

定義一個實色筆刷以決定文字顏色。此處使用黑色。

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## 步驟 3：加入字形 (aspose.page add text)

字形是 XPS 文件中字符的低階表示。此呼叫會在指定座標加入文字 “Hello World!”。

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## 步驟 4：儲存產生的 XPS 文件

將文件寫入磁碟，以便之後檢視或列印。

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

依照上述步驟，您已成功 **create XPS document .NET**，並使用 Aspose.Page 加入自訂文字。

## 常見問題與解決方案

| Issue | Reason | Fix |
|-------|--------|-----|
| **File not found** 儲存時 | `dataDir` 指向不存在的資料夾 | 確保資料夾存在，或在儲存前使用 `Directory.CreateDirectory(dataDir)`。 |
| **Text not visible** | 筆刷顏色與背景相同 | 將 `Color.Black` 改為其他對比色。 |
| **Unsupported font** | 系統未安裝該字型 | 使用系統必定存在的字型，或使用 Aspose.Page 的字型嵌入功能嵌入字型。 |

## 常見問答

### Q1：我可以自訂加入文字的字型與大小嗎？

A1：可以，您可以完整控制字型與大小。請依需求調整 `AddGlyphs` 方法中的參數。

### Q2：Aspose.Page 相容於 .NET Core 嗎？

A2：當然！Aspose.Page 支援 .NET Core，確保與最新的 .NET 技術相容。

### Q3：使用 Aspose.Page 有授權需求嗎？

A3：是的，您需要有效的授權。請在[此處](https://purchase.aspose.com/buy)了解授權方案。

### Q4：我該如何取得支援或求助？

A4：前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 與社群互動並取得協助。

### Q5：是否提供免費試用？

A5：當然！您可在[此處](https://releases.aspose.com/)取得免費試用。

**其他問答**

**Q：我可以在同一頁面加入多個文字區塊嗎？**  
A：可以，只要對 `doc.AddGlyphs` 使用不同座標呼叫多次即可。

**Q：Aspose.Page 支援文字旋轉嗎？**  
A：您可以對 `XpsGlyphs` 物件套用變換矩陣，以旋轉或斜切文字。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

---