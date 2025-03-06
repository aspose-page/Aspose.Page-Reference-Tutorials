---
title: 使用 Aspose.Page for .NET 將垂直漸層加入 XPS
linktitle: 在 XPS 上添加垂直漸變
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page for .NET 透過垂直漸層增強 XPS 文件。請按照我們的逐步指南進行無縫整合。
weight: 15
url: /zh-hant/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 將垂直漸層加入 XPS

## 介紹

歡迎閱讀本逐步教學，了解如何使用 Aspose.Page for .NET 將垂直漸層新增至 XPS 文件。 Aspose.Page 是一個功能強大的 API，可讓您在 .NET 應用程式中使用 XPS（XML 紙張規格）檔案。在本教程中，我們將引導您完成建立新 XPS 文件、在路徑上新增垂直漸層以及儲存結果的過程。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Page for .NET 函式庫：確保您的開發環境中安裝了 Aspose.Page for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/page/net/).

- 開發環境：使用您首選的 IDE（例如 Visual Studio）設定 .NET 開發環境。

現在，讓我們開始使用 Aspose.Page for .NET 在 XPS 文件中新增垂直漸層。

## 導入命名空間

在您的 .NET 應用程式中，包含存取 Aspose.Page 類別和方法所需的命名空間。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 第 1 步：設定您的文件目錄

在開始之前，設定要儲存產生的 XPS 文件的文件目錄的路徑。

```csharp
//起始時間：3
string dataDir = "Your Document Directory";
//結束：3
```

## 第 2 步：建立新的 XPS 文檔

使用以下程式碼初始化一個新的 XPS 文件：

```csharp
//起始時間：4
XpsDocument doc = new XpsDocument();
//結束：4
```

## 第 3 步：定義漸變停止點

建立漸變停止點列表，指定每個停止點的顏色和位置。在此範例中，我們定義了具有五個停止點的垂直漸變。

```csharp
//起始時間：5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
//結束：5
```

## 第四步：建立漸變路徑

透過指定其幾何形狀來定義路徑並向其應用線性漸變畫筆。

```csharp
//起始時間：6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
//結束：6
```

## 第 5 步：儲存產生的 XPS 文檔

將修改後的 XPS 文件儲存到指定目錄。

```csharp
//起始時間：7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
//結束：7
```

恭喜！您已使用 Aspose.Page for .NET 成功地在 XPS 文件中新增垂直漸層。

## 結論

在本教學中，我們探討如何利用 Aspose.Page for .NET 透過垂直漸層增強 XPS 文件。 Aspose.Page 簡化了複雜的任務，為開發人員提供了在 .NET 應用程式中操作 XPS 檔案的無縫方式。

## 常見問題解答

### Q1：Aspose.Page 與 Visual Studio 2019 相容嗎？

A1：是的，Aspose.Page 與 Visual Studio 2019 相容。確保您安裝了正確版本的程式庫。

### Q2：我可以將Aspose.Page用於商業項目嗎？

 A2：是的，Aspose.Page可以用於商業項目。訪問[這裡](https://purchase.aspose.com/buy)探索許可證選項。

### Q3：有免費試用嗎？

A3：是的，您可以免費試用Aspose.Page[這裡](https://releases.aspose.com/).

### Q4：哪裡可以找到Aspose.Page文件？

 A4：文檔可用[這裡](https://reference.aspose.com/page/net/).

### Q5：我如何獲得支持或提出問題？

 A5：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
