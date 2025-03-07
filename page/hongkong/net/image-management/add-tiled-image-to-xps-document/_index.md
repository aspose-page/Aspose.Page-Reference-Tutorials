---
title: 使用 Aspose.Page for .NET 將平鋪影像新增至 XPS 文檔
linktitle: 將平鋪影像新增至 XPS 文檔
second_title: Aspose.Page .NET API
description: 探索使用 Aspose.Page for .NET 輕鬆地將平鋪影像新增至 XPS 文件。增強視覺吸引力並創建令人驚嘆的文件。
weight: 12
url: /zh-hant/net/image-management/add-tiled-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 將平鋪影像新增至 XPS 文檔

## 介紹

您是否希望透過添加具有視覺吸引力的平鋪影像來增強您的 XPS 文件？ Aspose.Page for .NET 讓開發人員能夠無縫地實現這一目標。在本逐步指南中，我們將引導您完成使用 Aspose.Page for .NET 將平鋪影像新增至 XPS 文件的過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Page for .NET：確保您已安裝 Aspose.Page 程式庫。您可以找到詳細的文檔並下載庫[這裡](https://reference.aspose.com/page/net/).
- 開發環境：設定您首選的 .NET 開發環境，例如 Visual Studio。

## 導入命名空間

首先，將必要的命名空間匯入到您的專案中。這可確保您可以存取使用 Aspose.Page 所需的類別和方法。在程式碼開頭新增以下命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

現在，讓我們將該範例分解為多個步驟。

## 第 1 步：定義文檔目錄

```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
```

確保將「您的文件目錄」替換為您要儲存 XPS 文件的實際路徑。

## 第 2 步：建立新的 XPS 文檔

```csharp
//建立新的 XPS 文檔
XpsDocument doc = new XpsDocument();
```

使用以下命令實例化一個新的 XPS 文檔`XpsDocument`班級。

## 第 3 步：新增平鋪影像

```csharp
//平鋪影像
//ImageBrush 填滿矩形位於右上方下方
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

此步驟將平鋪影像新增至 XPS 文件。根據您的要求調整座標和圖像檔案路徑。

## 步驟 4：儲存產生的 XPS 文檔

```csharp
//儲存產生的 XPS 文檔
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

將修改後的XPS文檔儲存到指定目錄。

## 結論

恭喜！您已成功學習如何使用 Aspose.Page for .NET 將平鋪圖像新增至 XPS 文件。這個簡單而強大的功能使您可以輕鬆增強文件的視覺吸引力。

## 常見問題解答

### Q1：Aspose.Page 是否相容於所有.NET 開發環境？

A1：是的，Aspose.Page 旨在與各種 .NET 開發環境（包括 Visual Studio）無縫協作。

### Q2：我可以調整平鋪影像的不透明度嗎？

A2：當然，如範例所示，您可以使用以下命令設定填滿矩形的不透明度`Opacity`財產。

### Q3：Aspose.Page for .NET 中是否還有其他可用的平鋪模式？

 A3：是的，Aspose.Page提供了不同的平鋪模式。在本教程中，我們使用了`XpsTileMode.Tile`，但您可以探索文件中的其他選項。

### Q4：如何處理 Aspose.Page 的臨時授權？

 A4：請參閱[臨時執照](https://purchase.aspose.com/temporary-license/) Aspose 網站上的頁面提供有關獲取和實施臨時許可證的指導。

### Q5：我可以在哪裡尋求協助或與 Aspose.Page 社群聯繫？

 A5：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)與社區互動、提出問題並尋找解決方案。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
