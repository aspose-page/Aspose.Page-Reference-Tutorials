---
title: 使用 Aspose.Page for .NET 應用網格視覺筆刷
linktitle: 應用網格視覺畫筆
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page 探索 .NET 中文件處理的動態世界。了解如何應用網格視覺畫筆來製作視覺上令人驚嘆的文件。
type: docs
weight: 10
url: /zh-hant/net/visual-brushes/apply-grid-visual-brush/
---
## 介紹

在.NET 開發領域，Aspose.Page 作為處理文件處理任務的強大工具脫穎而出。它提供的一項令人著迷的功能是能夠應用網格視覺畫筆，為您的文件帶來新的維度。本教學將引導您使用 Aspose.Page for .NET 逐步完成洋紅色網格視覺筆刷的實作過程。

## 先決條件

在深入學習本教程之前，請確保您符合以下先決條件：

-  Aspose.Page for .NET：確保您已在 .NET 環境中安裝並設定了該程式庫。你可以下載它[這裡](https://releases.aspose.com/page/net/).

- 開發環境：準備好可用的.NET 開發環境，並對 C# 程式設計有基本的了解。

- 文件目錄：為您的文件建立一個目錄，用於保存已處理的文件。

## 導入命名空間

在您的 C# 程式碼中，您需要匯入必要的命名空間才能有效地利用 Aspose.Page 功能：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

現在，讓我們將該範例分解為多個步驟。

## 第 1 步：初始化 XpsDocument

```csharp
//起始時間：3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
//結束：3
```

在這裡，我們建立一個實例`XpsDocument`處理 XPS 文件。

## 第 2 步：建立洋紅色網格幾何圖形

```csharp
//起始時間：4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
//結束：4
```

此步驟涉及為洋紅色網格建立路徑幾何形狀。

## 第 3 步：設計洋紅色網格 VisualBrush

```csharp
//起始時間：5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
//結束：5
```

在這裡，我們使用向量圖形設計洋紅色網格的視覺效果。

## 第 4 步：將 VisualBrush 應用到網格

```csharp
//起始時間：6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
//結束：6
```

將視覺畫筆應用於網格路徑，確保其正確平鋪。

## 第 5 步：將網格新增至畫布

```csharp
//起始時間：7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
//結束：7
```

將網格新增至畫布，指定所需的任何轉換。

## 步驟6：用紅色矩形增強

```csharp
//開始時間：8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f;
//結束：8
```

透過添加紅色透明矩形來增強視覺吸引力。

## 步驟7：儲存文檔

```csharp
//開始時間：9
doc.Save(dataDir + "AddGrid_out.xps");
//結束：9
```

將產生的 XPS 文件保存在指定目錄中。

## 結論

恭喜！您已使用 Aspose.Page for .NET 成功地將網格視覺筆刷套用到您的文件中。此技術可顯著增強文件的視覺元素，提供動態且引人入勝的使用者體驗。

## 常見問題解答

### Q1：我可以在 Web 和桌面應用程式中使用 Aspose.Page for .NET 嗎？

A1：是的，Aspose.Page for .NET 用途廣泛，可用於各種應用程式類型。

### Q2：購買前有試用版嗎？

 A2：當然，您可以免費試用[這裡](https://releases.aspose.com/).

### 問題 3：我可以在哪裡找到其他支持或社區討論？

 A3：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)進行討論和支持。

### Q4：如何取得 Aspose.Page for .NET 的臨時授權？

 A4：您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### 問題 5：Aspose.Page for .NET 還有哪些其他文件可用？

 A5：探索全面的文檔[這裡](https://reference.aspose.com/page/net/).