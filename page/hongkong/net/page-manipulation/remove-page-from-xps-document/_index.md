---
date: 2026-03-19
description: 學習如何使用 Aspose.Page for .NET **移除 XPS 頁面** 文件以及 **刪除指定索引的頁面** — 完整的逐步指南，包含前置條件、程式碼範例與常見問題。
linktitle: Remove Page from XPS Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 從 XPS 文件中移除頁面
url: /zh-hant/net/page-manipulation/remove-page-from-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 從 XPS 文件中移除頁面

## 簡介

如果您需要以程式方式 **remove page xps** 檔案，Aspose.Page for .NET 為您提供一個乾淨且可靠的解決方案。在本教學中，我們將逐步說明如何從 XPS 文件中刪除特定頁面，解釋此操作的重要性，並示範如何將更新後的檔案儲存回磁碟。

## 快速解答
- **“remove page xps” 是什麼意思？** 它指的是從 XPS（XML Paper Specification）文件中刪除單一頁面。  
- **哪個方法可刪除頁面？** 使用 `RemovePageAt(index)`，其中索引為零基礎。  
- **我可以在任何位置刪除頁面嗎？** 可以——您可以 **delete page at index** 0、1、2 等，視需要而定。  
- **使用 Aspose.Page 是否需要授權？** 測試時需要臨時授權，正式環境則需完整授權。  
- **此程式碼是否相容於 .NET 6？** 完全相容——Aspose.Page 支援 .NET Framework、.NET Core 以及 .NET 5/6。

## 什麼是 “remove page xps”？

從 XPS 文件中移除頁面是指將文件中的某一頁取出，同時保留其餘內容、版面配置與中繼資料。當您需要裁剪 PDF、產生自訂報告，或符合文件大小限制時，此操作相當有用。

## 為什麼使用 Aspose.Page for .NET？

- **無外部相依性** – 純 .NET 函式庫。  
- **高保真度** – 保留向量圖形與版面精確度。  
- **跨平台** – 可在 Windows、Linux 與 macOS 上執行。  
- **簡易 API** – 只需呼叫一次方法 (`RemovePageAt`) 即可完成繁重工作。

## 前置條件

在深入程式碼之前，請確保您已具備以下項目：

- **Aspose.Page for .NET** – 從 [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) 下載。  
- 一個 **.NET 開發環境**（Visual Studio、VS Code 或您偏好的任何 IDE）。  
- 一個 **範例 XPS 文件**（例如 `Sample.xps`），放置於您專案可參照的資料夾中。

## 匯入命名空間

在 C# 檔案的頂部加入所需的命名空間，讓編譯器能找到 XPS 類別。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 步驟 1：設定文件目錄

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **小技巧：** 使用 `Path.Combine` 以建立跨平台的路徑。

## 步驟 2：建立新的 XPS 文件

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// ExEnd:4
```

此行程式碼會將現有的 XPS 檔案（`Sample.xps`）載入 `XpsDocument` 物件，準備進行操作。

## 步驟 3：刪除指定索引的頁面

```csharp
// ExStart:5
// Remove the first page (at index 1).
doc.RemovePageAt(1);
// ExEnd:5
```

`RemovePageAt` 方法 **會刪除指定索引的頁面**。請記得索引從 0 開始，因此 `1` 會刪除第二頁。請調整索引以定位您要刪除的頁面。

## 步驟 4：儲存結果 XPS 文件

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "Sample_out.xps");
// ExEnd:6
```

移除後，文件會儲存為 `Sample_out.xps`。您現在可以開啟此檔案，確認不需要的頁面已被移除。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **索引超出範圍** | 嘗試刪除不存在的頁面。 | 在呼叫 `RemovePageAt` 前，使用 `doc.Pages.Count` 檢查頁面總數。 |
| **檔案被鎖定** | XPS 檔案正被其他程式開啟。 | 關閉所有檢視器，或確保檔案未被使用後再執行程式碼。 |
| **授權未套用** | 在正式環境中未使用有效授權即使用函式庫。 | 使用 `License license = new License(); license.SetLicense("Aspose.Page.lic");` 套用臨時或永久授權。 |

## 常見問答

**Q1：我可以一次移除多個頁面嗎？**  
A1：可以，只需重複呼叫 `RemovePageAt`，或對索引列表進行迴圈（記得從最高索引開始刪除，以保持剩餘索引的有效性）。

**Q2：Aspose.Page 是否相容於最新的 .NET 框架？**  
A2：Aspose.Page 會定期更新，以支援最新的 .NET 版本，包括 .NET 6 與 .NET 7。

**Q3：我可以在商業應用中使用 Aspose.Page 嗎？**  
A3：當然可以。授權細節請參閱 [Aspose.Purchase](https://purchase.aspose.com/buy) 頁面。

**Q4：在哪裡可以找到 Aspose.Page 的其他支援與討論？**  
A4：加入 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 社群，取得技巧、範例與除錯協助。

**Q5：測試 Aspose.Page 是否需要臨時授權？**  
A5：需要，您可以取得 [temporary license](https://purchase.aspose.com/temporary-license/) 以在購買前評估函式庫。

**Q6：移除頁面後如何保留文件的中繼資料？**  
A6：`RemovePageAt` 方法會自動保留原始中繼資料。如需修改，請使用 `doc.DocumentProperties` 集合。

## 結論

您現在已學會如何使用 Aspose.Page for .NET **remove page xps** 文件以及 **delete page at index**。這種簡潔的做法讓您能直接在 .NET 應用程式中整合頁面移除邏輯，全面掌控 XPS 文件內容。

---

**最後更新：** 2026-03-19  
**測試環境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}