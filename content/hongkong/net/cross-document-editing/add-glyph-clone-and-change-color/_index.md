---
title: 使用 Aspose.Page for .NET 新增字形複製並更改顏色
linktitle: 添加字形克隆並更改顏色
second_title: Aspose.Page .NET API
description: 在這個綜合教學中探索 Aspose.Page for .NET 的強大功能。了解如何輕鬆地在 XPS 文件中新增字形複製並更改顏色。
type: docs
weight: 10
url: /zh-hant/net/cross-document-editing/add-glyph-clone-and-change-color/
---
## 介紹

歡迎閱讀本逐步指南，以了解如何使用 Aspose.Page for .NET 在 XPS 文件中新增字形複製和變更顏色。 Aspose.Page for .NET 是一個功能強大的程式庫，可讓您無縫處理 XPS 檔案。在本教程中，我們將重點關注添加字形克隆並更改其顏色的過程，以增強文件的視覺吸引力。

## 先決條件

在深入學習本教程之前，請確保您符合以下先決條件：

- 對 C# 程式語言有基本的了解。
- 安裝 Visual Studio 或任何其他首選的 C# 開發環境。
-  .NET 函式庫的 Aspose.Page。你可以下載它[這裡](https://releases.aspose.com/page/net/).
- 熟悉 XPS 文件格式。

## 導入命名空間

首先，在您的 C# 專案中包含必要的命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 第 1 步：設定您的文件目錄

首先設定儲存文檔的目錄：

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：建立第一個 XPS 文檔

現在，讓我們建立第一個 XPS 文件：

```csharp
XpsDocument doc1 = new XpsDocument();
```

## 步驟 3：將字形新增至第一個文檔

使用指定的參數將字形新增至第一個文件：

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 步驟 4：用顏色填滿第一個文件中的字形

用純色填滿第一個文件中的字形，例如綠色：

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

## 步驟 5：建立第二個 XPS 文檔

現在，建立第二個 XPS 文件：

```csharp
XpsDocument doc2 = new XpsDocument();
```

## 步驟 6：新增從第一個文件複製的字形

從第一個文檔複製字形並將其新增至第二個文件：

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

## 步驟 7：用另一種顏色填滿第二個文件中的字形

將第二個文件中克隆字形的顏色變更為紅色，例如：

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

## 步驟 8：儲存第一個 XPS 文檔

儲存第一個 XPS 文件：

```csharp
doc1.Save(dataDir + "out1.xps");
```

## 步驟 9：儲存第二個 XPS 文檔

儲存第二個 XPS 文件：

```csharp
doc2.Save(dataDir + "out2.xps");
```

恭喜！您已使用 Aspose.Page for .NET 在 XPS 文件中成功新增字形複製並變更顏色。

## 結論

在本教學中，我們探討如何利用 Aspose.Page for .NET 來增強 XPS 文件的視覺元素。透過新增字形複製和調整顏色，您可以根據您的特定需求建立具有視覺吸引力的動態文件。

## 常見問題解答

### Q1：我可以將 Aspose.Page for .NET 與其他文件格式一起使用嗎？

A1：Aspose.Page for .NET 專為處理 XPS 文件而設計。如果您需要操作其他格式，您可以探索為這些格式自訂的其他 Aspose 庫。

### Q2：Aspose.Page for .NET 是否有臨時授權？

 A2：是的，您可以獲得臨時許可證用於測試目的。訪問[這裡](https://purchase.aspose.com/temporary-license/)了解更多。

### Q3：對於任何問題，我如何獲得支持或尋求協助？

 A3：歡迎您來參觀[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)與社區聯繫並尋求協助。

### Q4：免費試用版有限制嗎？

A4：免費試用版有一些限制，建議使用前查看文件以了解詳細資訊。

### Q5：在哪裡可以找到 Aspose.Page for .NET 的綜合文件？

 A5：可以參考文檔[這裡](https://reference.aspose.com/page/net/)取得詳細資訊和範例。