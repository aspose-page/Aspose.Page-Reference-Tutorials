---
title: 使用 Aspose.Page for .NET 將水平漸層加入 XPS
linktitle: 在 XPS 中加入水平漸變
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page for .NET 將令人驚嘆的水平漸層新增至 XPS 文件中。毫不費力地提升視覺吸引力。
weight: 13
url: /zh-hant/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 將水平漸層加入 XPS

## 介紹

在本教程中，我們將探索如何使用 Aspose.Page for .NET 新增水平漸層來增強 XPS 文件。 Aspose.Page for .NET 是一個功能強大的程式庫，可在.NET 應用程式中無縫處理 XPS（XML 紙張規格）文件。新增漸層可以為您的文件帶來視覺吸引力，本指南將逐步引導您完成流程。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

1.  Aspose.Page for .NET 函式庫：確保您的開發環境中安裝了 Aspose.Page for .NET 函式庫。您可以從[Aspose.Page for .NET 文檔](https://reference.aspose.com/page/net/).

2. 開發環境：設定適當的開發環境，包括Visual Studio等程式碼編輯器。

## 導入命名空間

首先將必要的命名空間匯入到您的專案中。這些命名空間對於使用 Aspose.Page for .NET 至關重要：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

現在，讓我們將提供的範例分解為多個步驟。

## 步驟1：設定文檔目錄路徑

```csharp
//起始時間：3
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
//結束：3
```

## 第 2 步：建立新的 XPS 文檔

```csharp
//起始時間：4
//建立新的 XPS 文檔
XpsDocument doc = new XpsDocument();
//結束：4
```

## 第 3 步：初始化梯度停止點

```csharp
//起始時間：5
//初始化 XpsGradientStop 列表
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
//結束：5
```

## 第 4 步：建立新路徑

```csharp
//起始時間：6
//透過以縮寫形式定義幾何圖形來建立新路徑
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
//結束：6
```

## 第 5 步：儲存產生的 XPS 文檔

```csharp
//起始時間：7
//儲存產生的 XPS 文檔
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
//結束：7
```

現在，您已使用 Aspose.Page for .NET 成功地在 XPS 文件中新增了水平漸層。

## 結論

使用漸層增強 XPS 文件不僅可以提高其視覺吸引力，還可以提供更具吸引力的使用者體驗。 Aspose.Page for .NET 簡化了這個過程，讓您輕鬆獲得專業的結果。

## 常見問題解答

### Q1：在哪裡可以找到 Aspose.Page for .NET 文件？

 A1：你可以找到文檔[這裡](https://reference.aspose.com/page/net/).

### Q2：如何下載 Aspose.Page for .NET？

A2：您可以從以下位置下載該庫：[Aspose.Page for .NET 下載頁面](https://releases.aspose.com/page/net/).

### Q3：哪裡可以購買 Aspose.Page for .NET？

 A3：您可以從以下位置購買 Aspose.Page for .NET[購買頁面](https://purchase.aspose.com/buy).

### Q4：有免費試用嗎？

 A4：是的，您可以從以下位置獲得免費試用[這裡](https://releases.aspose.com/).

### Q5：如何取得 Aspose.Page for .NET 的臨時授權？

 A5：您可以從以下地址獲得臨時許可證：[這個連結](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
