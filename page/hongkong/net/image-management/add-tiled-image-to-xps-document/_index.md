---
date: 2026-03-03
description: 學習如何使用 Aspose.Page for .NET 在 XPS 文件中平鋪圖像。本分步指南示範如何高效平鋪圖像並提升視覺吸引力。
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page 向 XPS 文件添加平鋪圖像
url: /zh-hant/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 在 XPS 文件中添加平鋪圖像

## 簡介

如果你想了解 **如何使用 Aspose** 為 XPS 檔案增添更豐富的視覺風格，你來對地方了。在本教學中，我們將逐步說明如何使用 Aspose.Page for .NET 在 XPS 文件中 **平鋪圖像**。完成後，你將擁有一段可重複使用的程式碼片段，能直接嵌入任何 .NET 專案，即時產生平鋪圖像圖形。

## 快速解答
- **需要的程式庫是什麼？** Aspose.Page for .NET  
- **哪個方法會建立平鋪筆刷？** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **我可以控制不透明度嗎？** 是 – 設定 `path.Fill.Opacity` (例如 0.5f)  
- **測試是否需要授權？** A temporary license works for evaluation; a full license is required for production.  
- **支援哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6!

## 什麼是 Aspose.Page 以及為什麼要平鋪圖像？

Aspose.Page 是一套功能強大的 API，讓開發者在不依賴 Microsoft Office 的情況下，產生、編輯與轉譯 XPS、PDF 以及其他以頁面為基礎的格式。平鋪圖像——在形狀上重複位圖——可協助你以圖案、浮水印或背景紋理填滿大面積，同時保持檔案大小低。

## 如何使用 Aspose.Page 在 XPS 文件中平鋪圖像

以下提供完整、可直接執行的範例。每一步都先以簡易說明文字說明 **為什麼** 需要這行程式碼，之後才呈現對應的程式碼區塊。

### 先決條件

- **Aspose.Page for .NET** – 從官方網站[此處](https://reference.aspose.com/page/net/)下載並參考該程式庫。  
- **開發環境** – Visual Studio（任何版本）或您偏好的其他 .NET IDE。

### 匯入命名空間

首先，將所需的命名空間匯入，以便編譯器知道 XPS 類別的所在位置。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### 步驟 1：定義文件目錄

指定產生的 XPS 檔案與來源圖像的存放位置。請將佔位符替換為你機器上的實際資料夾路徑。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### 步驟 2：建立新的 XPS 文件

實例化一個空的 XPS 文件，用來容納平鋪圖形。

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 步驟 3：加入平鋪圖像

在此我們建立一個矩形路徑，使用 `ImageBrush` 填充，並將筆刷設定為平鋪模式。`TileMode` 屬性告訴引擎在水平與垂直方向上重複圖像。視需求調整矩形座標或來源圖像。

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### 步驟 4：儲存產生的 XPS 文件

最後，將文件寫入磁碟。輸出檔案可使用任何 XPS 檢視器開啟，或進一步以 Aspose.Page 處理。

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## 常見問題與技巧

- **路徑錯誤** – 確保 `dataDir` 以斜線結尾，或使用 `Path.Combine` 以避免缺少分隔符的問題。  
- **圖像尺寸不匹配** – 原始圖像應足夠大以覆蓋平鋪區域；否則圖案可能會被拉伸。  
- **不透明度未顯示** – 某些檢視器會忽略 XPS 的不透明度；請使用完整支援 XPS 呈現的檢視器測試（例如 Windows 的 XPS Viewer）。

## 常見問答

### Q1：Aspose.Page 是否相容於所有 .NET 開發環境？

A：是，Aspose.Page 可在 Visual Studio、Rider、VS Code 以及任何支援 .NET 的 IDE 中使用。

### Q2：我可以調整平鋪圖像的不透明度嗎？

A：當然可以。範例中設定 `path.Fill.Opacity = 0.5f;`——您可以將浮點值調整為 0（透明）到 1（不透明）之間的任意值。

### Q3：Aspose.Page for .NET 還有其他平鋪模式嗎？

A：是。除了 `XpsTileMode.Tile`，您還可以使用 `FlipX`、`FlipY` 和 `FlipXY` 來建立鏡像圖案。

### Q4：如何處理 Aspose.Page 的臨時授權？

A：請參閱 Aspose 網站上的[臨時授權](https://purchase.aspose.com/temporary-license/)頁面，了解取得與套用試用授權的詳細資訊。

### Q5：我可以在哪裡尋求協助或加入 Aspose.Page 社群？

A：前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 提問、分享程式碼片段，並向其他開發者學習。

### Q6：我可以使用此方法製作浮水印效果嗎？

A：可以。降低不透明度並選擇半透明圖像，平鋪筆刷即可完美作為重複的浮水印。

## 結論

你現在已掌握 **如何使用 Aspose** 在 XPS 文件中加入平鋪圖像、控制其不透明度，並將結果儲存以供後續使用。此技巧非常適合背景圖案、浮水印，或任何需要重複圖形而不致於增加檔案大小的情境。歡迎自行嘗試不同形狀、圖像與平鋪模式，以符合專案需求。

---

**最後更新：** 2026-03-03  
**測試環境：** Aspose.Page for .NET (latest release)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}