---
title: 使用 Aspose.Page for .NET 建立 XPS 文檔
linktitle: 建立 XPS 文檔
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 探索 XPS 文件所建立的世界。按照我們的逐步指南輕鬆產生電子文檔。
weight: 10
url: /zh-hant/net/document-creation/create-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 建立 XPS 文檔

## 介紹

歡迎閱讀我們有關使用 Aspose.Page for .NET 建立 XPS 文件的逐步指南。在本教學中，我們將探討產生 XPS 檔案的過程，XPS 檔案是一種廣泛使用的電子文檔格式。無論您是經驗豐富的開發人員還是剛開始使用 Aspose.Page，本指南都經過量身定制，可透過清晰的範例和詳細的說明幫助您無縫建立 XPS 文件。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

1.  Aspose.Page for .NET Library：從下列位置下載並安裝 Aspose.Page 函式庫：[下載連結](https://releases.aspose.com/page/net/).

2. 您的文件目錄：在系統上選擇或建立一個用於儲存輸出 XPS 檔案的目錄。

現在，讓我們進入教程吧！

## 導入命名空間

為了使用 Aspose.Page for .NET，您需要將必要的命名空間匯入到您的專案中。按著這些次序：

### 步驟1：新增對Aspose.Page的引用

在您的專案中，新增對 Aspose.Page for .NET 程式庫的參考。您可以在下載的套件中找到所需的DLL。

### 第 2 步：導入命名空間

在您的程式碼檔案中包含以下命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

現在我們已經設定了先決條件並導入了必要的命名空間，讓我們將建立 XPS 文件的過程分解為多個步驟。

## 步驟1：設定文檔目錄

```csharp
string dir = "Your Document Directory";
```

確保更換`"Your Document Directory"`與要儲存輸出 XPS 檔案的實際路徑。

## 第 2 步：建立 XPS 文檔

```csharp
XpsDocument xDocs = new XpsDocument();
```

使用以下命令初始化新的 XPS 文檔`XpsDocument`班級。

## 步驟 3：將字形新增至文件中

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

使用`AddGlyphs`在文件中新增字形（文字）的方法。根據需要自訂字體、大小、樣式和位置。

## 步驟 4： 設定字形填滿顏色

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

指定新增的字形的填滿顏色。在此範例中，我們使用黑色，但您可以選擇任何顏色。

## 第 5 步：儲存結果

```csharp
xDocs.Save(dir + "output.xps");
```

最後，使用所需的檔案名稱將 XPS 文件儲存到指定目錄。產生的 XPS 文件將包含“Hello World!”文字.

恭喜！您已使用 Aspose.Page for .NET 成功建立了 XPS 文件。

## 結論

在本教程中，我們演練了使用 Aspose.Page for .NET 建立 XPS 文件的過程。這個功能強大的庫提供了一種輕鬆生成電子文檔的無縫方式。嘗試不同的字體、樣式和內容，根據您的特定需求自訂 XPS 檔案。

## 常見問題解答

### 問題 1：我可以在 XPS 文件中使用自訂字體嗎？

A1：是的，您可以在為 XPS 文件新增字形時指定字型系列和大小。

### Q2：Aspose.Page 與.NET Core 相容嗎？

A2：是的，Aspose.Page 支援.NET Core，讓您在跨平台應用程式中使用它。

### 問題 3：如何將影像新增至 XPS 文件？

A3：Aspose.Page 提供了將影像新增至 XPS 文件的方法。請參閱文件以了解詳細範例。

### 問題 4：我可以建立多頁 XPS 文件嗎？

A4：當然！您可以使用 Aspose.Page 庫將多個頁面新增至 XPS 文件。

### Q5：有試用版嗎？

 A5：是的，您可以透過下載Aspose.Page來探索Aspose.Page的功能[免費試用](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
