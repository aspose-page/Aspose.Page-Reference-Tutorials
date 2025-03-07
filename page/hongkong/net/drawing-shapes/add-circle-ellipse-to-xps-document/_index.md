---
title: 使用 Aspose.Page for .NET 將圓橢圓加入 XPS 文檔
linktitle: 將圓橢圓加入 XPS 文檔
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 透過充滿活力的徑向漸層增強 XPS 文件。按照我們的逐步指南獲得令人驚嘆的視覺效果。
weight: 11
url: /zh-hant/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 將圓橢圓加入 XPS 文檔

## 介紹

建立具有視覺吸引力的 XPS 文件是各種應用程式中的常見要求。 Aspose.Page for .NET 提供了一組強大的功能來有效地操作 XPS 文件。在本教程中，我們將重點介紹使用 Aspose.Page for .NET 將圓形橢圓添加到 XPS 文件中。請按照以下步驟使用充滿活力的徑向漸層增強您的 XPS 文件。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- 為 .NET 程式庫安裝了 Aspose.Page。您可以從以下位置下載：[這裡](https://releases.aspose.com/page/net/).
- 開發環境，最好是 Visual Studio 或任何其他 .NET 開發工具。
- C# 程式設計基礎知識。

## 導入命名空間

首先，在 C# 程式碼中包含必要的命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

現在，讓我們將範例分解為多個步驟：

## 第 1 步：設定文檔

```csharp
//開始時間：1
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
//建立新的 XPS 文檔
XpsDocument doc = new XpsDocument();
```

在這裡，我們使用 Aspose.Page for .NET 初始化一個新的 XPS 文件。

## 步驟 2：定義徑向漸層橢圓

```csharp
//左下角徑向漸層描邊橢圓
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

此步驟涉及定義具有各種色標的徑向漸層橢圓。

## 步驟3：設定徑向漸層畫筆

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

在這裡，我們將橢圓的筆劃設定為徑向漸變畫筆，並為其提供必要的參數。

## 第四步：調整描邊粗細

```csharp
path.StrokeThickness = 12f;
```

此步驟涉及調整筆劃的粗細以獲得更好的視覺化效果。

## 第 5 步：儲存產生的 XPS 文檔

```csharp
//儲存產生的 XPS 文檔
doc.Save(dataDir + "AddEllipse_outXPS.xps");
//結束：1
```

最後，將修改後的XPS文件儲存到所需位置。

## 結論

恭喜！您已使用 Aspose.Page for .NET 成功將具有徑向漸層的圓形橢圓新增至 XPS 文件中。嘗試不同的參數和顏色，以在文件中實現所需的視覺效果。

## 常見問題解答

### Q1：我可以將 Aspose.Page for .NET 與其他文件格式一起使用嗎？

A1：Aspose.Page for .NET 專門處理 XPS 文件操作。對於其他格式，請考慮使用相關的 Aspose 庫。

### Q2：臨時許可證是否可用於測試目的？

 A2：是的，您可以透過造訪獲得臨時許可證進行測試[這個連結](https://purchase.aspose.com/temporary-license/).

### Q3：我可以在哪裡找到更多幫助和討論？

 A3：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持和討論。

### Q4: 有範本文件可供參考嗎？

 A4：探索[文件](https://reference.aspose.com/page/net/)取得全面的範例和指南。

### Q5：我可以購買 Aspose.Page for .NET 嗎？

 A5：是的，您可以購買圖書館[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
