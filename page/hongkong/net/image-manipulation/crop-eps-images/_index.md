---
date: 2026-03-16
description: 學習如何在 .NET 中使用 Aspose.Page 裁剪 EPS 圖像並調整 EPS 圖像檔案大小。跟隨本分步指南，輕鬆裁剪 EPS 並調整
  EPS 圖像大小。
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page for .NET 裁剪 EPS 圖像
url: /zh-hant/net/image-manipulation/crop-eps-images/
weight: 10
---

：** Aspose"

Now produce final content with all shortcodes preserved.

Let's craft.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for .NET 裁剪 EPS 圖像

## 介紹

如果您需要了解 **如何在 .NET 應用程式中裁剪 EPS** 圖像，您來對地方了。在本教學中，我們將示範如何使用功能強大的 Aspose.Page for .NET 函式庫對 EPS 檔案進行裁剪與調整大小。無論您是在完善報表工具，或是為 Web 服務準備圖形，掌握此技巧都能為您節省時間，並取得像素完美的結果。

## 快速回答
- **哪個函式庫負責 EPS 裁剪？** Aspose.Page for .NET  
- **主要方法？** `doc.CropEps(outputStream, newBoundingBox)`  
- **可以同時調整 EPS 大小嗎？** 可以 – 使用 `ResizeEps` 並以英吋、毫米或百分比為單位。  
- **前置條件？** .NET（Framework 4.5+ / .NET Core 3.1+）、已安裝 Aspose.Page、以及 EPS 檔案。  
- **典型實作時間？** 基本的裁剪與調整大小工作流程約需 10 分鐘。

## 前置條件

在進入程式碼之前，請確保您已具備：

- .NET 開發的基本知識。  
- 已安裝 Aspose.Page for .NET 函式庫。若尚未安裝，可從 [此處](https://releases.aspose.com/page/net/) 下載。  
- 一個範例 EPS 圖像（在程式碼中將 `"input.eps"` 替換為您的實際檔案名稱）。

## 匯入命名空間

讓我們先匯入可存取 EPS 處理類別的命名空間。

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## 如何裁剪 EPS 圖像 – 步驟指南

### 步驟 1：初始化 `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

我們從輸入的 EPS 串流建立 `PsDocument` 實例。此物件在記憶體中代表 EPS 檔案，並提供裁剪與調整大小的方法。

### 步驟 2：提取原始邊界框

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

邊界框會告訴您 EPS 畫布目前的尺寸。了解這些數值有助於您定義安全的裁剪矩形。

### 步驟 3：建立輸出串流

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

我們開啟一個可寫入的串流，用於儲存裁剪後的 EPS。使用 `using` 區塊可確保串流在結束時正確關閉。

### 步驟 4：定義新邊界框

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

將數字替換為您想保留的座標。請確保新值位於原始邊界框內，否則操作會失敗。

### 步驟 5：裁剪並儲存 EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

這一行程式碼即完成裁剪，並將結果寫入 `output_crop.eps`。此方法會在記憶體中修改文件，若有需要，您可以在之後串接其他操作。

## 調整 EPS 圖像大小

裁剪完成後，您常會想要改變 EPS 的顯示或列印尺寸。Aspose.Page 支援三種測量單位。

### 以英吋調整大小

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### 以毫米調整大小

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### 以百分比調整大小

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

每一次呼叫都會覆寫先前的輸出，若需要為每種尺寸產生獨立檔案，請務必建立新的串流。

## 常見問題與疑難排解

| 症狀 | 可能原因 | 解決方法 |
|---------|--------------|-----|
| **Bounding box values out of range** | 新的邊界框超出原始尺寸 | 核對 `initialBoundingBox` 的值，並選擇位於該範圍內的座標。 |
| **Output file is empty** | 輸出串流未刷新或未關閉 | 確保 `using` 區塊結束前已完成寫入，或呼叫 `outputEpsStream.Flush()`。 |
| **Unexpected scaling** | 單位混用（例如英吋與毫米） | 始終使用與尺寸值相符的 `Units` 列舉。 |

## 常見問答

### Q1：我可以在 .NET 中使用 Aspose.Page 處理其他圖像格式嗎？

A1：Aspose.Page 主要聚焦於 EPS 圖像，但 Aspose 提供多種函式庫支援不同格式。請參閱其文件以取得特定格式的資訊。

### Q2：如何取得 Aspose.Page for .NET 的臨時授權？

A2：前往 [此連結](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

### Q3：使用 Aspose.Page for .NET 處理的圖像尺寸有什麼限制嗎？

A3：Aspose.Page 設計能處理各種尺寸的圖像。然而，處理效能會依圖像的複雜度而異。

### Q4：是否有 Aspose.Page 的社群論壇？

A5：有，您可以在 [此處](https://forum.aspose.com/c/page/39) 與 Aspose.Page 社群互動。

### Q5：在哪裡可以找到 Aspose.Page for .NET 的詳細文件？

A5：請參考文件 [此處](https://reference.aspose.com/page/net/)。

---

**最後更新：** 2026-03-16  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}