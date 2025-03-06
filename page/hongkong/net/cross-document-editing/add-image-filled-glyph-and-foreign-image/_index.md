---
title: 使用 Aspose.Page .NET 新增圖像填滿字形和外部圖像
linktitle: 新增影像填充字形和外部影像
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page 釋放 .NET 中文件處理的強大功能。輕鬆新增影像填滿的字形。增強視覺效果並簡化您的工作流程。
weight: 11
url: /zh-hant/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page .NET 新增圖像填滿字形和外部圖像

## 介紹

在 .NET 開發領域，Aspose.Page 作為處理文件處理任務的強大工具包脫穎而出。本教學將引導您完成使用 Aspose.Page for .NET 新增影像填滿字形和合併外部影像的過程。讀完本指南後，您將對如何增強文件處理能力有深入的了解。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Page for .NET：確保您已安裝 Aspose.Page 程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/page/net/).

- 開發環境：使用 Visual Studio 或任何其他首選 IDE 設定工作 .NET 開發環境。

- 文檔目錄：建立一個用於儲存文檔的目錄。在程式碼範例中，這將被稱為“您的文檔目錄”。

## 導入命名空間

在您的 .NET 應用程式中，首先匯入必要的命名空間以存取 Aspose.Page 提供的類別和方法：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 步驟 1：建立第一個 XPS 文檔

首先使用 Aspose.Page 建立第一個 XPS 文件。本文檔將作為新增影像填充字形的基礎。

```csharp
//開始時間：1
//文檔目錄的路徑。
string dataDir = "Your Document Directory";

//建立第一個 XPS 文檔
XpsDocument doc1 = new XpsDocument();
```

## 步驟 2：將字形新增至第一個文檔

將字形新增至第一個文檔，指定字體、大小、樣式和位置。

```csharp
//將字形新增至第一個文檔
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 步驟 3： 使用圖像畫筆填滿字形

使用資料目錄中的圖像，用圖像畫筆填滿字形。

```csharp
//使用圖像畫筆填充字形
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## 步驟 4：建立第二個 XPS 文檔

現在，建立第二個 XPS 文檔，該文檔將合併第一個文檔中的字形。

```csharp
//建立第二個 XPS 文檔
XpsDocument doc2 = new XpsDocument();
```

## 步驟 5：使用第一個文件中的字型新增字形

使用第一個文件中的字型將字形新增到第二個文件。

```csharp
//將第一個文件中的字體的字形新增到第二個文件中
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## 第 6 步：從第一個文件的填充中建立圖像畫筆

從第一個文件的填充中建立圖像畫筆，並使用它來填充第二個文件中的字形。

```csharp
//從第一個文件的填充創建圖像畫筆並在第二個文檔中填充字形
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## 步驟7：儲存文檔

保存第一個和第二個 XPS 文件。

```csharp
//保存第一個 XPS 文檔
doc1.Save(dataDir + "out1.xps");

//儲存第二個 XPS 文檔
doc2.Save(dataDir + "out2.xps");
//結束：1
```

## 結論

恭喜！您已使用 Aspose.Page for .NET 成功新增了映像填充字形並合併了外部影像。本教學為增強文件處理能力奠定了基礎，為富有創意和視覺吸引力的文件開闢了新的可能性。

## 常見問題解答

### Q1：我可以使用不同的影像格式來填入字形嗎？

A1：是的，Aspose.Page支援各種圖像格式。確保與所選影像格式的相容性。

### Q2：如何進一步自訂字形的外觀？

A2：探索 Aspose.Page 文件以取得微調字形外觀的其他屬性和方法。

### Q3：Aspose.Page 適合處理大型文件集嗎？

A3：Aspose.Page 旨在有效地處理小型和大型文件集。

### Q4：我可以對各個字形套用不同的樣式嗎？

A4：是的，您可以單獨為每個字形自訂樣式，提供高度的靈活性。

### Q5：與其他文件處理工具相比，使用Aspose.Page有什麼好處？

A5：Aspose.Page 提供了全面的功能、出色的性能和豐富的文檔，使其成為許多開發人員的首選。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
