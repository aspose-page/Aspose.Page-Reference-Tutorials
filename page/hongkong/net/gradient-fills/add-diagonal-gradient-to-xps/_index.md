---
date: 2026-02-23
description: 學習如何使用 Aspose.Page for .NET 建立斜向漸層 XPS 文件，輕鬆提升您的視覺呈現效果。
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 建立對角漸層 XPS
url: /zh-hant/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 建立對角漸層 XPS

## 簡介

如果您需要製作引人注目的 **create diagonal gradient XPS** 檔案，Aspose.Page for .NET 讓這變得簡單。在本教學中，您將學習如何使用 Aspose.Page API 逐步將對角漸層加入 XPS 文件。完成後，您將擁有一個可重複使用的模式，能套用於任何形狀或配色方案。

## 快速解答
- **API 方法的作用是什麼？** 它會建立一個沿對角線跨越路徑的線性漸層筆刷。  
- **哪個類別代表 XPS 文件？** `XpsDocument`。  
- **執行範例是否需要授權？** 免費試用版可用於開發；正式環境需購買授權。  
- **我可以變更漸層方向嗎？** 可以——調整起始與結束的 `PointF` 值。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 什麼是 **create diagonal gradient xps**？
對角漸層是一種平滑的顏色過渡，從形狀的一個角落延伸至相對的角落。在 XPS 中，透過將 `LinearGradientBrush` 套用至路徑的填充屬性即可實現此效果。Aspose.Page 函式庫抽象化了低階的 XPS 標記，讓您專注於顏色與幾何形狀。

## 為何使用 Aspose.Page 進行對角漸層？
- **高保真度渲染** – 輸出完全符合 XPS 規範。  
- **完整 .NET 整合** – 支援 C#、VB.NET 以及任何 .NET 語言。  
- **無外部相依性** – 全部在程序內處理，無需 COM 或 Office。  
- **可擴展至複雜文件** – 您可以在同一頁面上結合多個漸層、影像與文字。

## 先決條件

1. **Aspose.Page for .NET 函式庫** – 從 [此處](https://releases.aspose.com/page/net/) 下載。  
2. **開發環境** – Visual Studio、Rider，或任何支援 .NET 專案的編輯器。  

現在，讓我們深入程式碼。

## 匯入命名空間

在您的 .NET 專案中，加入 Aspose.Page 函式庫所需的命名空間，以存取相關類別與方法。請在程式碼開頭加入以下命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 步驟 1：設定文件目錄

首先指定文件目錄的路徑。此目錄將用來儲存帶有對角漸層的 XPS 文件。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## 步驟 2：建立新 XPS 文件

使用 Aspose.Page 函式庫初始化新的 `XpsDocument`。

```csharp
XpsDocument doc = new XpsDocument();
```

## 步驟 3：定義漸層顏色

建立 `XpsGradientStop` 物件的清單，每個物件代表對角漸層中的一種顏色。

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## 步驟 4：將對角漸層套用至路徑

建立具有定義幾何形狀的新路徑，並將對角漸層套用於該路徑。視需要調整渲染變換與填充屬性。

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## 步驟 5：儲存產生的 XPS 文件

最後，將修改後的 XPS 文件儲存至指定目錄。

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

您已成功 **created a diagonal gradient XPS** 檔案。隨意嘗試不同的顏色停點、幾何字串或變換矩陣，以產生各種視覺效果。

## 常見問題與解決方案
- **漸層未顯示** – 確認路徑幾何形狀已閉合，且筆刷的起始/結束點位於路徑範圍內。  
- **顏色不正確** – 確保使用 `CreateColor` 並提供正確的 ARGB 值；此方法接受 0‑255 範圍的數值。  
- **檔案未儲存** – 檢查 `dataDir` 是否指向已存在的資料夾，且應用程式具備寫入權限。

## 常見問答

**Q: 我可以在文件的不同部分套用多個漸層嗎？**  
A: 可以，您可以建立多條路徑，並為每條路徑套用不同的漸層。

**Q: 有預設的漸層樣式可用嗎？**  
A: Aspose.Page 支援自訂漸層，讓您完全掌控顏色過渡。

**Q: 我可以將 Aspose.Page for .NET 用於其他文件格式嗎？**  
A: Aspose.Page 主要聚焦於 XPS 文件的操作。

**Q: 如何處理與文件處理相關的錯誤？**  
A: 請參考 [文件說明](https://reference.aspose.com/page/net/) 以獲得錯誤處理的最佳實踐。

**Q: 購買前是否有試用版可供使用？**  
A: 有，您可以透過 [免費試用](https://releases.aspose.com/) 體驗 Aspose.Page for .NET。

**Q: 如何將漸層方向改為垂直或水平？**  
A: 修改 `CreateLinearGradientBrush` 中的 `PointF` 參數，以設定新的起始與結束點。

**Q: 函式庫是否支援漸層的透明度？**  
A: 支援——在使用 `CreateColor` 建立顏色時加入 alpha 值。

## 結論

Aspose.Page for .NET 簡化了在 XPS 文件中加入對角漸層的流程。本指南從環境設定到最終儲存檔案，為您一步步說明。持續嘗試不同的形狀與配色，讓您的 XPS 報告、手冊或發票真正脫穎而出。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-02-23  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose