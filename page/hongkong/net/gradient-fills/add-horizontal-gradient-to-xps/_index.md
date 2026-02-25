---
date: 2026-02-25
description: 學習如何使用 Aspose.Page for .NET 建立具有水平填充的 XPS 漸層，輕鬆提升文件的視覺吸引力。
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 建立 XPS 漸層：水平填充，使用 Aspose.Page for .NET
url: /zh-hant/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

 answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 XPS 漸層 – 使用 Aspose.Page for .NET 為 XPS 添加水平漸層

## 介紹

在本教學中，您將 **建立 XPS 漸層** 填充，使其在頁面上水平延伸。添加水平漸層可以立即讓 XPS 文件看起來更精緻、更具吸引力，特別適用於報告、手冊或任何視覺豐富的輸出。我們將使用 Aspose.Page for .NET，從環境設定到儲存最終 XPS 檔案，完整說明整個流程。

## 快速回答
- **本教學涵蓋什麼內容？** 使用 Aspose.Page for .NET 為 XPS 文件添加水平漸層。  
- **需要哪個函式庫？** Aspose.Page for .NET（任何近期版本）。  
- **需要授權嗎？** 開發階段可使用試用版；正式上線需購買商業授權。  
- **實作需要多長時間？** 基本漸層大約需要 5–10 分鐘。  
- **可以更改漸層方向嗎？** 可以 – 只要修改 `LinearGradientBrush` 的起始與結束點即可。  

## 如何使用 Aspose.Page for .NET 建立 XPS 漸層

以下提供逐步指南，說明每行程式碼的 **原因**（why），而不僅是 **功能**（what）。歡迎在 Visual Studio 或您偏好的 .NET 編輯器中跟隨操作。

## 前置條件

在開始之前，請確保已具備以下前置條件：

1. Aspose.Page for .NET 函式庫：確保已在開發環境中安裝 Aspose.Page for .NET 函式庫。可從 [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) 下載。  
2. 開發環境：建立合適的開發環境，包含如 Visual Studio 等程式碼編輯器。

## 匯入命名空間

首先在專案中匯入必要的命名空間。這些命名空間對於使用 Aspose.Page for .NET 至關重要：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

現在，讓我們將提供的範例分解為多個步驟。

## 步驟 1：設定文件目錄路徑

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 步驟 2：建立新 XPS 文件

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## 步驟 3：初始化漸層停點

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## 步驟 4：建立新路徑

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## 步驟 5：儲存產生的 XPS 文件

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

現在，您已成功使用 Aspose.Page for .NET 為 XPS 文件添加水平漸層。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 漸層顯示為單色 | 漸層停點未正確加入 | 確保在設定畫筆後執行 `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);`。 |
| 儲存的檔案為空 | `dataDir` 指向不存在的資料夾 | 確認資料夾是否存在，或使用絕對路徑。 |
| `PointF` 編譯錯誤 | 缺少 `System.Drawing` 參考 | 加入對 `System.Drawing.Common` 的參考（適用於 .NET Core/5+）。 |

## 常見問答

### Q1：在哪裡可以找到 Aspose.Page for .NET 的文件說明？

A1：您可以在 [此處](https://reference.aspose.com/page/net/) 找到文件說明。

### Q2：如何下載 Aspose.Page for .NET？

A2：您可從 [Aspose.Page for .NET 下載頁面](https://releases.aspose.com/page/net/) 下載函式庫。

### Q3：在哪裡可以購買 Aspose.Page for .NET？

A3：您可在 [購買頁面](https://purchase.aspose.com/buy) 購買。

### Q4：是否提供免費試用？

A4：是的，您可從 [此處](https://releases.aspose.com/) 取得免費試用。

### Q5：如何取得 Aspose.Page for .NET 的臨時授權？

A5：您可透過 [此連結](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

## 常見問題

**Q：我可以在已包含圖像的 XPS 文件中使用此漸層技術嗎？**  
A：當然可以。漸層是套用在路徑圖層上，現有的圖像不會受到影響。

**Q：是否可以改為建立垂直漸層？**  
A：可以。只要將 `LinearGradientBrush` 的起始與結束點的 Y 座標設為不同，X 座標保持不變即可。

**Q：Aspose.Page 是否支援 .NET Core？**  
A：此函式庫完全相容於 .NET Core、.NET 5 以及更高版本。

**Q：如何在多個頁面重複使用相同的漸層？**  
A：先建立一次 `XpsLinearGradientBrush`，將其存入變數，然後在每個頁面的路徑上使用該變數即可。

## 結論

為 XPS 文件加入漸層不僅提升視覺吸引力，亦能提供更具互動性的使用者體驗。使用 Aspose.Page for .NET，您可以快速且可靠地 **建立 XPS 漸層** 填充，為報告、手冊或電子書增添專業光澤。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-02-25  
**測試版本：** Aspose.Page for .NET 24.11  
**作者：** Aspose  

---