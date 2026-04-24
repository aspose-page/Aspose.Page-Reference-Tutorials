---
date: 2026-01-05
description: 學習如何使用 Aspose.Page for .NET 剪裁 XPS 文件。此一步一步的指南將向您展示如何有效地建立、操作及儲存 XPS
  檔案。
linktitle: Clipping XPS
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page for .NET 剪裁 XPS
url: /zh-hant/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for .NET 裁剪 XPS

## 簡介

歡迎閱讀本完整教學，說明如何使用 Aspose.Page for .NET **裁剪 XPS**！在本指南中，我們將帶領您了解使用此函式庫建立、操作與儲存 XPS 文件的整個流程。XPS（XML Paper Specification）是一種標準化且開放的文件格式，而 Aspose.Page for .NET 為您的 .NET 應用程式提供強大的 XPS 文件處理工具。

## 快速答案
- **什麼是裁剪 XPS？** 為 XPS 畫布元素套用幾何遮罩（clip），以限制可見區域。  
- **哪個函式庫最適合？** Aspose.Page for .NET 提供完整功能的 API，用於 XPS 建立與裁剪。  
- **先決條件？** Visual Studio、.NET 執行環境，以及 Aspose.Page for .NET 函式庫。  
- **實作需要多久？** 基本裁剪情境大約需要 10‑15 分鐘。  
- **可以在正式環境使用嗎？** 可以，只要擁有有效的 Aspose 授權（提供試用版）。

## 什麼是「裁剪 XPS」？

在 XPS 中，裁剪是透過定義 **clip geometry**（例如圓形或矩形）並將其指派給畫布來實現的。任何繪製在該幾何圖形之外的內容都不會被渲染，讓您能夠建立如遮罩影像、自訂形狀或聚焦內容區域等精緻的頁面版面配置。

## 為什麼使用 Aspose.Page for .NET 來裁剪 XPS？

- **完整控制** 畫布變換、路徑幾何與筆刷。  
- **無外部相依性** – 所有功能皆在您的 .NET 應用程式內執行。  
- **跨平台** 支援 .NET Framework、.NET Core 以及 .NET 5/6+。  
- **高效能** 輕量化 API，可產生符合規範的 XPS 檔案。

## 先決條件

在開始之前，請確保您已具備以下項目：

- 已在電腦上安裝 Visual Studio。  
- 已將 Aspose.Page for .NET 函式庫加入專案。您可於 [此處](https://releases.aspose.com/page/net/) 下載。  
- 具備 C# 程式語言的基礎知識。

## 匯入命名空間

若要使用 Aspose.Page for .NET 功能，您需要在專案中匯入所需的命名空間。請依照以下步驟操作：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

現在，讓我們將您提供的範例程式碼分解為多個步驟。

## 步驟 1：設定文件目錄路徑。

```csharp
string dataDir = "Your Document Directory";
```

請將「Your Document Directory」替換為實際的文件目錄路徑。

## 步驟 2：建立新的 XPS 文件。

```csharp
XpsDocument doc = new XpsDocument();
```

此程式碼會建立一個您即將使用的 XPS 文件。

## 步驟 3：建立主畫布。

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

此步驟會建立主畫布，供所有頁面元素共用。

## 步驟 4：設定主畫布的左側與上側偏移。

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

依需求調整左側與上側的偏移量。

## 步驟 5：建立矩形路徑幾何。

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

此程式碼會為矩形建立路徑幾何。

## 步驟 6：為矩形建立填色。

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

定義矩形的填充顏色。

## 步驟 7：將另一個帶有裁剪的畫布加入主畫布。

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

此步驟會將另一個畫布加入主畫布。

## 步驟 8：建立圓形幾何作為裁剪。

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

此程式碼會建立圓形裁剪幾何，並套用至第二個畫布。

## 步驟 9：在第二個畫布中建立矩形並填充。

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

此步驟會在第二個畫布中建立矩形並填入顏色。

## 步驟 10：將帶有描邊矩形的第二個畫布加入主畫布。

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

此程式碼會將另一個畫布加入主畫布。

## 步驟 11：在第三個畫布中建立矩形並套用描邊。

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

此步驟會在第三個畫布中建立矩形並套用描邊。

## 步驟 12：儲存最終的 XPS 文件。

```csharp
doc.Save(dataDir + "output2.xps");
```

此程式碼會將 XPS 文件儲存至指定目錄。

## 常見問題與解決方案
- **路徑無效** – 確認 `dataDir` 以反斜線 (`\\`) 結尾，或使用 `Path.Combine`。  
- **裁剪未套用** – 檢查裁剪幾何字串是否格式正確；缺少空格可能導致裁剪被忽略。  
- **授權例外** – 在非評估版建置中，於建立文件前加入有效的 Aspose 授權，以避免執行時例外。

## 常見問答

### Q1：我可以將 Aspose.Page for .NET 與其他文件格式一起使用嗎？

A1：Aspose.Page for .NET 主要針對 XPS 文件，但 Aspose 亦提供其他函式庫以支援各種文件格式。

### Q2：Aspose.Page for .NET 適合初學者使用嗎？

A2：是的，Aspose.Page for .NET 設計友善，初學者只要參考完整文件即可快速掌握其功能。

### Q3：我可以在哪裡找到更多範例與資源？

A3：請前往[文件說明](https://reference.aspose.com/page/net/)與[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)取得豐富的資源與範例。

### Q4：如何取得 Aspose.Page for .NET 的臨時授權？

A4：您可於[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

### Q5：是否提供 Aspose.Page for .NET 的免費試用？

A5：是的，您可於[此處](https://releases.aspose.com/)體驗免費試用版。

## 其他常見問答

**Q: 我可以在單一畫布上結合多個裁剪幾何嗎？**  
A: 可以，您可以將包含多個子路徑的複雜 `PathGeometry` 指派給 `Clip` 屬性，以實現分層遮罩。

**Q: 裁剪會影響 PDF 轉換嗎？**  
A: 當您使用 Aspose.PDF 將 XPS 轉換為 PDF 時，裁剪幾何會被保留，視覺結果保持相同。

**Q: XPS 能否對裁剪進行動畫化？**  
A: XPS 本身不支援動畫；不過，您可以產生一系列具有不同裁剪形狀的 XPS 頁面，以模擬動態效果。

---

**最後更新：** 2026-01-05  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}