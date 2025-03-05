---
title: 使用 Aspose.Page 將帶有 Unicode 字串的文字新增至 XPS 文檔
linktitle: 將帶有 Unicode 字串的文字新增到 XPS 文件中
second_title: Aspose.Page .NET API
description: 透過我們在 XPS 文件中新增 Unicode 文字的逐步指南，探索 Aspose.Page for .NET 的強大功能。
type: docs
weight: 12
url: /zh-hant/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## 介紹

在不斷發展的 .NET 開發領域，Aspose.Page 作為處理 XPS 文件的強大工具脫穎而出。在其眾多功能中，為 XPS 文件添加帶有 Unicode 字串的文字的能力是一項很有價值的功能。本逐步指南將引導您完成整個過程，確保您有效地利用此功能。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- 對 .NET 開發有基本了解。
- Visual Studio 安裝在您的電腦上。
-  .NET 函式庫的 Aspose.Page。您可以從以下位置下載：[這裡](https://releases.aspose.com/page/net/).

## 導入命名空間

首先，確保將必要的命名空間匯入到您的專案中。這將提供使用 Aspose.Page 所需的類別和功能。以下是基本的命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 第 1 步：設定文檔

首先，建立一個新的 XPS 文檔，您將在其中新增 Unicode 文字。請按照下面的程式碼片段操作：

```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
//建立新的 XPS 文檔
XpsDocument doc = new XpsDocument();
```

## 步驟 2： 新增 Unicode 文字

現在，讓我們將 Unicode 文字新增到 XPS 文件中。此範例使用 Arial 字體，將字體大小設為 20，並將文字定位在座標 (400f, 200f) 處。本例中的 Unicode 字串是「TEN.rof SPX.esopsA」。請看下面的程式碼片段：

```csharp
//新增文字
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## 第 3 步：儲存文檔

新增 Unicode 文字後，儲存產生的 XPS 文件。這是最後一步：

```csharp
//儲存產生的 XPS 文檔
doc.Save(dataDir + "AddTextRTL_out.xps");
```

恭喜！您已使用 Aspose.Page for .NET 成功將 Unicode 文字新增至 XPS 文件。

## 結論

在本教程中，我們探索了使用 Aspose.Page for .NET 將 Unicode 文字新增至 XPS 文件的過程。此功能為在 .NET 環境中建立多樣化的動態文件打開了大門。

## 常見問題解答

### Q1：Aspose.Page 與最新的.NET 框架相容嗎？

A1：是的，Aspose.Page 會定期更新，以確保與最新的 .NET 框架相容。

### Q2：新增文字時可以自訂字體樣式和大小嗎？

A2：當然！提供的範例程式碼可讓您輕鬆自訂字體樣式、大小和其他屬性。

### Q3：在哪裡可以找到 Aspose.Page 的附加文件？

 A3：可以參考文檔[這裡](https://reference.aspose.com/page/net/)獲取全面的資訊和範例。

### Q4：有沒有免費的資源可以開始使用Aspose.Page？

 A4：是的，您可以探索[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持和討論。

### Q5：購買前有試用版嗎？

 A5：當然！您可以存取免費試用版[這裡](https://releases.aspose.com/)在購買之前。