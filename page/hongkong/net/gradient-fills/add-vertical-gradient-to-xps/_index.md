---
date: 2026-02-25
description: 學習如何使用 Aspose.Page for .NET 建立 XPS 文件並套用線性漸層。請參考我們的逐步指南來儲存 XPS 檔案。
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 建立帶有垂直漸層的 XPS 文件
url: /zh-hant/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 為 XPS 添加垂直漸層

## 介紹

在本教學中，你將 **建立 XPS 文件**，其中包含平滑的垂直漸層。加入漸層是讓 XPS 檔案看起來更專業的常見方法——非常適合報告、手冊或任何可列印的圖形。我們會一步一步說明，從專案設定到儲存最終的 XPS 檔案，讓你能快速為任何路徑套用線性漸層。

## 快速回答
- **本教學涵蓋什麼內容？** 為 XPS 文件中的路徑加入垂直線性漸層。  
- **需要哪個函式庫？** Aspose.Page for .NET。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **實作需要多久？** 基本範例約 10‑15 分鐘即可完成。  
- **可以將結果儲存為 XPS 檔案嗎？** 可以，`Save` 方法會將檔案寫入磁碟。

## 什麼是 XPS 中的垂直漸層？

垂直漸層是指顏色從形狀的上方平滑過渡到下方的顏色變化。在 XPS 中，這透過 **線性漸層筆刷** 來實現，需設定起點與終點，並提供一組漸層停點以控制特定位置的顏色。

## 為什麼使用 Aspose.Page 來建立帶漸層的 XPS 文件？

- **完整 .NET 整合** – 支援 .NET Framework、.NET Core 以及 .NET 5/6+。  
- **無外部相依** – 所有渲染皆由函式庫內部處理。  
- **高保真度** – 漸層會依照 XPS 規範精確呈現。  
- **易於維護** – 物件模型清晰，涵蓋路徑、筆刷與顏色等。

## 前置需求

- Aspose.Page for .NET 函式庫：確保已在開發環境中安裝 Aspose.Page for .NET 函式庫。你可以在此下載 [here](https://releases.aspose.com/page/net/)。  
- 開發環境：使用你慣用的 IDE（如 Visual Studio）建立 .NET 開發環境。

現在所有前置工作已就緒，讓我們進入程式碼部分。

## 匯入命名空間

在 .NET 應用程式中，加入必要的命名空間以存取 Aspose.Page 類別與方法。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 步驟 1：設定文件目錄

定義產生的 XPS 檔案要儲存的資料夾路徑。

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 步驟 2：建立新 XPS 文件

建立一個全新的 XPS 文件，之後我們會在其中加入填滿漸層的路徑。

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## 步驟 3：定義漸層停點

漸層停點決定顏色以及它們在漸層線上的位置。此處建立五個停點，以產生平滑的垂直過渡。

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## 步驟 4：建立帶漸層的路徑

我們繪製一個矩形形狀的路徑，並套用 **線性漸層筆刷**，其垂直方向從點 (10, 110) 延伸至點 (10, 200)。筆刷會使用先前定義的漸層停點。

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## 步驟 5：儲存產生的 XPS 文件

最後，將 XPS 文件寫入磁碟。此 **儲存 XPS 檔案** 步驟會在你指定的資料夾中產生 `AddVerticalGradient_outXPS.xps`。

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**小技巧：** 開啟 Windows XPS Viewer 或任何第三方檢視器，確認漸層如預期般顯示。

## 常見問題與除錯

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 漸層顯示為單一顏色 | 漸層停點未加入筆刷 | 確認已執行 `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);`。 |
| 儲存時找不到檔案 | `dataDir` 指向不存在的資料夾 | 先建立該資料夾或改用絕對路徑。 |
| 顏色與預期不同 | 顏色值使用 ARGB 順序，需確認通道順序 | 正確使用 `CreateColor(alpha, red, green, blue)`。 |

## 常見問答

**Q: Aspose.Page 與 Visual Studio 2019 相容嗎？**  
A: 相容，請確保已安裝正確版本的函式庫。

**Q: 可以在商業專案中使用 Aspose.Page 嗎？**  
A: 可以，請前往 [here](https://purchase.aspose.com/buy) 了解授權方案。

**Q: 有免費試用版嗎？**  
A: 有，請在此取得免費試用版 [here](https://releases.aspose.com/)。  

**Q: 哪裡可以找到 Aspose.Page 的文件說明？**  
A: 文件說明位於 [here](https://reference.aspose.com/page/net/)。  

**Q: 如何取得支援或提問？**  
A: 前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 取得社群支援。

## 結論

現在你已了解如何使用 Aspose.Page for .NET **建立 XPS 文件**、**套用線性漸層**，以及 **儲存 XPS 檔案**。此方法讓你在 XPS 輸出中完整掌控視覺樣式，使可列印文件更具吸引力。

---  

**最後更新：** 2026-02-25  
**測試環境：** Aspose.Page for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}