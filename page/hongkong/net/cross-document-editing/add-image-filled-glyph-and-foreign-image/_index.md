---
date: 2026-01-07
description: 學習如何使用 Aspose.Page 在 .NET 中建立 XPS 文件。本指南示範如何加入以圖像填充的字形與外部圖像，以提升文件的視覺效果。
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 於 .NET 建立 XPS 文件 – 圖像填充字形與外部圖像
url: /zh-hant/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 建立 XPS 文件 .NET – 圖像填充字形與外部圖像

## 簡介

## 快速解答
- **本教學涵蓋什麼內容？** 使用 Aspose.Page for .NET 在 XPS 文件中加入圖像填充字形並重複使用它們。  
- **目標的主要關鍵字是？** `create xps document .net`。  
- **先決條件？** .NET 開發環境、Aspose.Page for .NET，以及用於存放 XPS 檔案的資料夾。  
- **實作需要多長時間？** 大約 10‑15 分鐘即可完成可運作的原型。  
- **可以使用其他圖像格式嗎？** 可以 – 任何 .NET `System.Drawing.Image` 支援的格式皆可。  

## 先決條件

在深入程式碼之前，請先確保以下項目已備妥：

- **Aspose.Page for .NET** – 從 [here](https://releases.aspose.com/page/net/) 下載最新版本的程式庫。  
- **開發環境** – Visual Studio 2022（或任何支援 .NET 6+ 的 IDE）。  
- **文件目錄** – 在電腦上建立一個資料夾，用於存放輸入圖像與產生的 XPS 檔案；在程式碼片段中我們會稱之為 **Your Document Directory**。  

## 匯入命名空間

首先匯入處理 XPS 物件與繪圖工具所需的命名空間。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 逐步指南

### 步驟 1：建立第一個 XPS 文件

我們先建立一個空的 XPS 文件，以容納圖像填充的字形。

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### 步驟 2：在第一個文件中加入字形

接著加入一個字形（文字字元），稍後會以圖像筆刷填充它。

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### 步驟 3：以圖像筆刷填充字形

此處我們從資料目錄中的 TIFF 檔案建立 `ImageBrush`，並套用至字形。筆刷設定為平鋪模式，若字形區域大於圖像尺寸，圖像會重複顯示。

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### 步驟 4：建立第二個 XPS 文件

現在建立第二個 XPS 文件，將重複使用第一個文件的字形樣式與圖像筆刷。

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### 步驟 5：使用第一個文件的字型在第二個文件中加入字形

我們在第二個文件中加入字形，重複使用第一個文件的字型物件，以確保兩個文件的視覺一致性。

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### 步驟 6：從第一個文件的填充建立圖像筆刷

我們不再重新載入圖像，而是從 `glyphs1` 複製筆刷並指派給 `glyphs2`。此示範了如何在 **create xps document .net** 工作流程中有效共享資源。

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### 步驟 7：儲存文件

最後，將兩個 XPS 檔案寫入磁碟。現在可使用任何 XPS 檢視器開啟，查看圖像填充字形的效果。

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## 為何在建立 XPS 文件 .NET 時使用圖像填充字形？

- **視覺衝擊** – 將純文字轉換為圖形豐富的元素，且不需將整頁光柵化。  
- **資源重用** – 在多個文件間共享筆刷與字型，降低記憶體佔用。  
- **彈性** – 平鋪、拉伸或旋轉圖像筆刷，以實現自訂圖案或品牌化。  

## 常見問題與技巧

- **檔案路徑錯誤** – 確認 `dataDir` 以符合作業系統的路徑分隔符（`\` 或 `/`）結尾。  
- **不支援的圖像格式** – Aspose.Page 最適合使用 TIFF、PNG 與 JPEG。使用前請先轉換其他格式。  
- **TileMode 未套用** – 在設定 `TileMode` 前，請確認已將物件轉型為 `XpsImageBrush`；否則屬性會被忽略。  

## 常見問答

### Q1：我可以使用不同的圖像格式來填充字形嗎？

**A:** 是的，Aspose.Page 支援 TIFF、PNG、JPEG、BMP 與 GIF。只需在 `CreateImageBrush` 呼叫中提供正確的副檔名即可。

### Q2：我該如何進一步自訂字形的外觀？

**A:** 可探索 `XpsGlyphs` 的其他屬性，如 `Opacity`、`RenderTransform` 與 `Stroke`，以微調呈現效果。

### Q3：Aspose.Page 適合處理大量文件集嗎？

**A:** 絕對可以。此函式庫針對高效能情境進行最佳化，能在批次作業中處理數千個 XPS 檔案。

### Q4：我可以對單一字形套用不同樣式嗎？

**A:** 可以。每個 `XpsGlyphs` 實例皆可擁有自己的填充、描邊與變形，提供細緻的控制。

### Q5：使用 Aspose.Page 相較於其他文件處理工具有何優勢？

**A:** Aspose.Page 提供完整且免授權費的 XPS 建立、操作與轉換 API，並附有豐富文件與 24/7 支援服務。

---

**最後更新：** 2026-01-07  
**測試環境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}