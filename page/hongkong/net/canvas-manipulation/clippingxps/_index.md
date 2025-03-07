---
title: 使用 Aspose.Page for .NET 剪下 XPS
linktitle: 剪裁XPS
second_title: Aspose.Page .NET API
description: 在本有關剪切 XPS 文件的逐步指南中探索 Aspose.Page for .NET 的強大功能。輕鬆建立、操作和儲存 XPS 檔案。
weight: 11
url: /zh-hant/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 剪下 XPS

## 介紹

歡迎來到這個關於使用 Aspose.Page for .NET 剪切 XPS 的綜合教學！在本指南中，我們將引導您完成使用 Aspose.Page for .NET 建立、操作和儲存 XPS 文件的過程。 XPS（即 XML 紙張規格）是一種標準化的開放式文件格式，Aspose.Page for .NET 提供了強大的工具來在 .NET 應用程式中處理 XPS 文件。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

- Visual Studio 安裝在您的電腦上。
-  Aspose.Page for .NET 函式庫已新增至您的專案中。你可以下載它[這裡](https://releases.aspose.com/page/net/).
- C# 程式語言的基礎知識。

## 導入命名空間

為了使用 Aspose.Page for .NET 功能，您需要將所需的命名空間匯入到您的專案中。按著這些次序：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

現在，讓我們將您提供的範例程式碼分解為多個步驟。

## 第一步：設定文檔目錄路徑。

```csharp
string dataDir = "Your Document Directory";
```

確保將“您的文件目錄”替換為文件目錄的實際路徑。

## 步驟 2：建立一個新的 XPS 文件。

```csharp
XpsDocument doc = new XpsDocument();
```

這將建立一個您將使用的新 XPS 文件。

## 第三步：建立主畫布。

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

此步驟建立主畫布，這對於所有頁面元素都是通用的。

## 步驟 4：在主畫布中設定左側和頂部的偏移量。

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

根據您的要求調整左側和頂部的偏移量。

## 步驟5：建立矩形路徑幾何圖形。

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

這將建立一個矩形的路徑幾何圖形。

## 步驟6：建立矩形填滿。

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

定義矩形的填滿顏色。

## 步驟7：將另一個帶有剪輯的畫布添加到主畫布上。

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

此步驟將另一個畫布添加到主畫布上。

## 步驟8：為剪輯建立一個圓形幾何體。

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

這將創建一個圓形剪輯幾何體並將其應用於第二個畫布。

## 步驟9：在第二個畫布中建立一個矩形並填滿它。

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

此步驟在第二個畫布中建立一個矩形並填滿它。

## 步驟10：將第二個帶有描邊矩形的畫布加入主畫布上。

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

這會在主畫布上添加另一個畫布。

## 步驟11：在第三個畫布中建立一個矩形並對其進行描邊。

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

這將在第三個畫布中建立一個矩形並對其套用描邊。

## 第 12 步：儲存產生的 XPS 文件。

```csharp
doc.Save(dataDir + "output2.xps");
```

這會將 XPS 文件儲存到指定目錄。

## 結論

恭喜！您已成功學習如何使用 Aspose.Page for .NET 剪輯 XPS。本指南詳細介紹了過程中涉及的步驟。

## 常見問題解答

### Q1：我可以將 Aspose.Page for .NET 與其他文件格式一起使用嗎？

A1：Aspose.Page for .NET 主要專注於 XPS 文檔，但 Aspose 為各種文檔格式提供了其他程式庫。

### Q2：Aspose.Page for .NET 適合初學者嗎？

A2：是的，Aspose.Page for .NET 的設計是使用者友善的，初學者可以透過適當的文件快速掌握其功能。

### Q3：在哪裡可以找到更多範例和資源？

 A3：訪問[文件](https://reference.aspose.com/page/net/)和[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)獲取廣泛的資源和範例。

### Q4：如何取得 Aspose.Page for .NET 的臨時授權？

 A4：您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### Q5：Aspose.Page for .NET 有免費試用版嗎？

 A5：是的，您可以探索免費試用[這裡](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
