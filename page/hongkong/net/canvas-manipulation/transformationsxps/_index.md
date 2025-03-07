---
title: 使用 Aspose.Page for .NET 進行 XPS 轉換
linktitle: XPS 變換
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 輕鬆轉換 XPS 文件。請按照我們的逐步指南進行無縫轉換。
weight: 13
url: /zh-hant/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 進行 XPS 轉換

## 介紹

歡迎來到 Aspose.Page for .NET 的世界，這是一個功能強大的程式庫，讓您可以輕鬆地對 XPS 文件執行各種轉換。在本教程中，我們將深入研究使用 Aspose.Page for .NET 轉換 XPS 文件的過程。無論您是經驗豐富的開發人員還是新手，本指南都將引導您完成每個步驟，確保您輕鬆掌握概念。

## 先決條件

在我們開始之前，請確保您已具備以下條件：

-  Aspose.Page for .NET Library：從以下位置下載並安裝該程式庫[Aspose.Page for .NET 文檔](https://reference.aspose.com/page/net/).

- 開發環境：設定相容的開發環境，例如 Visual Studio 或任何其他 .NET 開發工具。

- 您的文件目錄：將程式碼中的佔位符替換為文件目錄的實際路徑。

現在，讓我們進入教程吧！

## 導入命名空間

首先，請確保導入必要的命名空間，以使 Aspose.Page for .NET 功能在程式碼中可用。在腳本的開頭新增以下命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 第 1 步：建立新的 XPS 文檔

```csharp
//開始時間：1
//文檔目錄的路徑。
string dataDir = "Your Document Directory";

//建立新的 XPS 文檔
XpsDocument doc = new XpsDocument();
```

## 第 2 步：建立主畫布

```csharp
//建立主畫布，所有頁面元素通用
XpsCanvas canvas1 = doc.AddCanvas();

//在主畫布中進行左側和頂部偏移
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## 第 3 步：建立矩形路徑幾何圖形

```csharp
//建立矩形路徑幾何體
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## 第 4 步：新增矩形填充

```csharp
//為矩形建立填充
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## 第 5 步：新增不進行任何變換的新畫布

```csharp
//添加新畫布而不對主畫布進行任何轉換
XpsCanvas canvas2 = canvas1.AddCanvas();

//在此畫布中建立矩形並填充它
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## 第 6 步：新增帶有平移變換的新畫布

```csharp
//將具有平移轉換的新畫布新增至主畫布
XpsCanvas canvas3 = canvas1.AddCanvas();

//平移此畫布以將新矩形放置在前一個矩形下方
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

//將此畫布平移到頁面的右側
canvas3.RenderTransform.Translate(500, 0);

//在此畫布中建立矩形並填充它
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## 步驟7：新增具有雙比例變換的新畫布

```csharp
//將具有雙比例變換的新畫布添加到主畫布
XpsCanvas canvas4 = canvas1.AddCanvas();

//平移此畫布以將新矩形放置在前一個矩形下方
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

//縮放此畫布
canvas4.RenderTransform.Scale(2, 2);

//在此畫布中建立矩形並填充它
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## 第 8 步：新增圍繞點變換旋轉的新畫布

```csharp
//將圍繞點變換旋轉的新畫布添加到主畫布
XpsCanvas canvas5 = canvas1.AddCanvas();

//平移此畫布以將新矩形放置在前一個矩形下方
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

//圍繞一點旋轉畫布 45 度
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

//在此畫布中建立矩形並填充它
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## 第 9 步：儲存產生的 XPS 文檔

```csharp
//儲存產生的 XPS 文檔
doc.Save(dataDir + "output1.xps");
//結束：1
```

## 結論

恭喜！您已使用 Aspose.Page for .NET 成功轉換了 XPS 文件。本指南涵蓋了從設定先決條件到執行各種轉換的基本步驟。嘗試這些技術並釋放 Aspose.Page for .NET 在您的專案中的全部潛力。

## 常見問題解答

### Q1：Aspose.Page for .NET 是否相容於所有.NET 開發環境？

A1：是的，Aspose.Page for .NET 旨在與各種 .NET 開發環境（包括 Visual Studio）無縫協作。

### 問題 2：在哪裡可以找到 Aspose.Page for .NET 的其他範例和文件？

 A2：訪問[Aspose.Page for .NET 文檔](https://reference.aspose.com/page/net/)取得全面的文件和範例。

### Q3：我可以在購買前試用 Aspose.Page for .NET 嗎？

 A3：是的，您可以存取免費試用版[Aspose.Page 免費試用](https://releases.aspose.com/).

### Q4：如何取得 Aspose.Page for .NET 的臨時授權？

A4：透過訪問獲得臨時許可證[臨時執照](https://purchase.aspose.com/temporary-license/).

### Q5：哪裡可以購買 Aspose.Page for .NET？

 A5：購買 .NET 版 Aspose.Page，網址為[Aspose.Page 購買](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
