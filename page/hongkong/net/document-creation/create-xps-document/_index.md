---
date: 2026-01-12
description: 學習如何使用 Aspose.Page for .NET 建立 XPS 文件 — 一步一步的指南，生成高品質的電子文件。
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 建立 XPS 文件
url: /zh-hant/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 建立 XPS 文件

## 簡介

歡迎閱讀我們的逐步教學，**教您如何建立 XPS 文件**，使用 Aspose.Page for .NET。在本教學中，我們將探討產生 XPS 檔案的流程，XPS 是廣泛使用的電子文件格式。無論您是資深開發者或是剛開始使用 Aspose.Page，本指南都旨在協助您以清晰的範例與詳細說明，順利建立 XPS 文件。

## 快速解答
- **需要哪個函式庫？** Aspose.Page for .NET  
- **可以在 .NET Core 上執行嗎？** 可以，函式庫完整支援 .NET Core 以及 .NET 5/6  
- **需要多少行程式碼？** 不到 20 行即可產生基本的 XPS 檔案  
- **測試需要授權嗎？** 提供免費試用版；正式環境需購買授權  
- **輸出格式為何？** XPS（XML Paper Specification）  

## 如何使用 Aspose.Page for .NET 建立 XPS 文件

以下將提供您在開始編寫程式碼前需要的所有資訊，接著以簡潔的編號步驟說明整個流程。

## 先決條件

在深入教學之前，請先確保您已具備以下條件：

1. Aspose.Page for .NET 函式庫：從 [download link](https://releases.aspose.com/page/net/) 下載並安裝 Aspose.Page 函式庫。  
2. 您的文件目錄：選擇或建立一個目錄，用於儲存產生的 XPS 檔案。

現在，讓我們開始教學！

## 匯入命名空間

為了在 .NET 中使用 Aspose.Page，您需要將必要的命名空間匯入專案。請依照以下步驟操作：

### 步驟 1：新增 Aspose.Page 參考

在您的專案中，加入對 Aspose.Page for .NET 函式庫的參考。所需的 DLL 可在下載的套件內找到。

### 步驟 2：匯入命名空間

在程式碼檔案中加入下列命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

現在，我們已完成先決條件的設定與必要命名空間的匯入，接下來將建立 XPS 文件的流程分成多個步驟說明。

## 步驟 1：設定文件目錄

```csharp
string dir = "Your Document Directory";
```

請將 `"Your Document Directory"` 替換為您實際想要儲存 XPS 檔案的路徑。

## 步驟 2：建立 XPS 文件

```csharp
XpsDocument xDocs = new XpsDocument();
```

使用 `XpsDocument` 類別初始化一個新的 XPS 文件。

## 步驟 3：向文件新增字形

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

透過 `AddGlyphs` 方法將字形（文字）加入文件。您可以依需求自訂字型、大小、樣式與位置。

## 步驟 4：設定字形填充顏色

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

為已加入的字形指定填充顏色。本範例使用黑色，您亦可自行選擇其他顏色。

## 步驟 5：儲存結果

```csharp
xDocs.Save(dir + "output.xps");
```

最後，將 XPS 文件儲存至先前指定的目錄，並使用您想要的檔名。產生的 XPS 檔案將包含「Hello World!」文字。

恭喜！您已成功使用 Aspose.Page for .NET 建立 XPS 文件。

## 常見提示與注意事項

- **目錄路徑** – 使用 `Path.Combine(dir, "output.xps")` 可避免不同作業系統間的路徑分隔符問題。  
- **字型可用性** – 您指定的字型必須已安裝於執行程式的機器上，否則 Aspose 會自動替換為預設字型。  
- **多頁面** – 若要建立多頁面的 XPS 檔案，可實例化額外的 `XpsPage` 物件，並在每頁加入內容後再儲存。

## 結論

在本教學中，我們示範了如何使用 Aspose.Page for .NET 產生 XPS 文件。此功能強大的函式庫讓您輕鬆生成電子文件。您可以嘗試不同的字型、樣式與內容，將 XPS 檔案客製化以符合特定需求。

## 常見問題

### Q1: 可以在 XPS 文件中使用自訂字型嗎？

A1: 可以，您可以在加入字形時指定字型族與大小。

### Q2: Aspose.Page 是否相容於 .NET Core？

A2: 相容，Aspose.Page 支援 .NET Core，讓您能在跨平台應用程式中使用。

### Q3: 如何在 XPS 文件中加入圖片？

A3: Aspose.Page 提供加入圖片的方法，請參考官方文件取得詳細範例。

### Q4: 能否建立多頁面的 XPS 文件？

A4: 當然可以！您可以使用 Aspose.Page 函式庫在同一個 XPS 文件中加入多個頁面。

### Q5: 有提供試用版嗎？

A5: 有，您可以下載 [free trial](https://releases.aspose.com/) 來體驗 Aspose.Page 的功能。

---

**最後更新：** 2026-01-12  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}