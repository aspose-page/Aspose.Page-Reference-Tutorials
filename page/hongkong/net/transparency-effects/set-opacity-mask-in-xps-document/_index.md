---
date: 2026-03-26
description: 學習如何在 XPS 文件中使用 Aspose.Page for .NET 設定不透明遮罩並套用多個不透明遮罩。
linktitle: Set Opacity Mask in XPS Document
second_title: Aspose.Page .NET API
title: 在 XPS 文件中使用 Aspose.Page for .NET 設定多個不透明度遮罩
url: /zh-hant/net/transparency-effects/set-opacity-mask-in-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 XPS 文件中設定多重不透明遮罩 – 使用 Aspose.Page for .NET

## 簡介

不透明遮罩讓您可以控制任何視覺元素的透明度，透過 **多重不透明遮罩**，您可以實現複雜的圖層效果，讓 XPS 文件更具特色。本教學將逐步說明 **如何在形狀上設定不透明遮罩**，並示範如何結合多個遮罩以獲得更豐富的視覺效果。完成後，您只需幾行 C# 程式碼，即可為任意 XPS 元素加入一個或多個不透明遮罩。

## 快速解答
- **什麼是不透明遮罩？** 用於定義形狀每個像素透明度的位圖、漸層或純色筆刷。  
- **為什麼要使用多重不透明遮罩？** 疊加遮罩可產生單一遮罩無法達成的複雜透明度圖案。  
- **哪個函式庫支援此功能？** Aspose.Page for .NET 完全支援 XPS 圖形的不透明遮罩。  
- **需要授權嗎？** 開發階段可使用免費試用版，正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 什麼是「多重不透明遮罩」？
多重不透明遮罩指的是同時套用兩個以上遮罩（可依序或層疊）的技術，使每個遮罩皆對最終的透明度圖產生貢獻。此方法可在不需複雜影像編輯的情況下，製作漸層、紋理或圖案化的透明效果。

## 為什麼使用 Aspose.Page for .NET 來設定不透明遮罩？
- **完整的 XPS 功能集** – 所有 XPS 圖形功能皆以乾淨的 .NET API 暴露。  
- **無外部相依性** – 直接操作 XPS 物件，無需額外的影像函式庫。  
- **效能最佳化** – 能有效處理大型文件與高解析度遮罩。

## 先決條件

在開始本教學之前，請確保您已具備以下條件：

- Aspose.Page for .NET：請確認已安裝此函式庫。若尚未安裝，可從 [網站](https://releases.aspose.com/page/net/) 下載。  
- 文件目錄：建立一個目錄，用於儲存您的 XPS 文件。

## 匯入命名空間

在 .NET 專案中，先匯入必要的命名空間：

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## 步驟 1：建立新的 XPS 文件

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

首先使用 Aspose.Page for .NET 建立一個新的 XPS 文件。

## 步驟 2：將 Canvas 加入 XpsDocument 實例

```csharp
// Add Canvas to XpsDocument instance
XpsCanvas canvas = doc.AddCanvas();
```

接著，將 Canvas 加入 XPS 文件。Canvas 會作為各種圖形元素的容器。

## 步驟 3：為矩形加入不透明遮罩

```csharp
// Rectangle with opacity masked by ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

將矩形加入 Canvas，並使用 `OpacityMask` 屬性設定其不透明度。本範例使用影像作為不透明遮罩。您可以重複此步驟，使用不同的筆刷為同一形狀套用 **多重不透明遮罩**，以達成層疊透明效果。

## 步驟 4：儲存產生的 XPS 文件

```csharp
// Save resultant XPS document
doc.Save(dataDir + "OpacityMask_out.xps");
```

最後，將套用不透明遮罩後的 XPS 文件儲存起來。

## 多重不透明遮罩的常見使用情境
- **浮水印** – 結合文字遮罩與圖案遮罩，製作半透明浮水印。  
- **主題圖** – 在點陣圖上覆蓋漸層遮罩，以突顯特定區域。  
- **品牌化** – 使用商標影像遮罩搭配顏色漸層遮罩，打造精緻的品牌元素。

## 故障排除與技巧
- **遮罩對齊** – 確保來源矩形尺寸與目標形狀相同，以免產生拉伸。  
- **TileMode** – 可嘗試 `XpsTileMode.Tile` 或 `XpsTileMode.None` 來控制遮罩的重複方式。  
- **效能** – 在多個元素使用相同遮罩時，請重複利用 `XpsImageBrush` 實例。

## 常見問題

### Q1：我可以將不透明遮罩套用到除矩形之外的其他形狀嗎？

A1：可以，Aspose.Page for .NET 允許您將不透明遮罩套用到各種形狀，包括圓形、多邊形與自訂路徑。

### Q2：不透明遮罩只能使用圖像嗎？

A2：不會，雖然本教學以影像作為不透明遮罩，您同樣可以使用純色、漸層或圖案等其他筆刷。

### Q3：是否有進階選項可微調不透明度？

A3：當然，Aspose.Page for .NET 提供詳細的透明度設定控制，讓您能精確調整透明效果。

### Q4：我可以對單一元素套用多個不透明遮罩嗎？

A4：可以，您可以層疊多個不透明遮罩，以創造複雜的透明效果。

### Q5：Aspose.Page 是否相容於其他文件格式？

A5：Aspose.Page 主要聚焦於 XPS 文件，但 Aspose 亦提供多種產品來處理其他格式。

**其他問題**

**Q：如何在同一形狀上結合兩個不同的遮罩？**  
A：建立兩個 `XpsImageBrush`（或漸層筆刷）物件，將其中一個指派給 `OpacityMask`，然後將該形狀包在 `XpsCanvas` 中，並將第二個遮罩套用於 Canvas 本身。

**Q：API 是否支援動畫式的不透明度變化？**  
A：雖然 XPS 本身不支援動畫，但您可以產生一系列具有不同遮罩透明度的 XPS 頁面，以模擬動畫效果。

**最後更新：** 2026-03-26  
**測試環境：** Aspose.Page for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}