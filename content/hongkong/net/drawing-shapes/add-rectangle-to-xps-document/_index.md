---
title: 使用 Aspose.Page for .NET 將矩形新增至 XPS 文檔
linktitle: 將矩形新增至 XPS 文件
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 增強文件建立。在此逐步教學中了解如何為 XPS 文件新增矩形。
type: docs
weight: 13
url: /zh-hant/net/drawing-shapes/add-rectangle-to-xps-document/
---
## 介紹

Aspose.Page for .NET 是一個功能強大的函式庫，提供了在 .NET 應用程式中處理 XPS（XML 紙張規格）文件的各種功能。在本教程中，我們將重點介紹使用 Aspose.Page for .NET 將矩形新增至 XPS 文件。請按照此逐步指南來增強您的文件建立流程。

## 先決條件

在開始學習本教程之前，請確保您具備以下先決條件：

1.  Aspose.Page for .NET 函式庫：確保您的開發環境中安裝了 Aspose.Page for .NET 函式庫。你可以下載它[這裡](https://releases.aspose.com/page/net/).

2. 文檔目錄：設定要儲存 XPS 文件的目錄。

## 導入命名空間

在您的 .NET 應用程式中，包含使用 Aspose.Page 功能所需的命名空間。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 步驟1：設定文檔目錄

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

## 第三步：新增一個矩形

```csharp
//起始時間：5
//左下角的 CMYK（藍色）純色描邊矩形
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
//結束：5
```

## 步驟 4：儲存文檔

```csharp
//起始時間：6
//儲存產生的 XPS 文檔
doc.Save(dataDir + "AddRectangleXPS_out.xps");
//結束：6
```

恭喜！您已使用 Aspose.Page for .NET 成功將矩形新增至 XPS 文件。

## 結論

Aspose.Page for .NET 簡化了文件操作任務，使開發人員能夠輕鬆建立和修改 XPS 文件。本逐步指南示範如何為 XPS 文件添加矩形，為進一步探索奠定了堅實的基礎。

## 常見問題解答

### Q1：Aspose.Page 是否與所有.NET 應用程式相容？

A1：是的，Aspose.Page 旨在與所有 .NET 應用程式無縫協作。

### Q2：在哪裡可以找到 Aspose.Page for .NET 的文件？

 A2：文檔可用[這裡](https://reference.aspose.com/page/net/).

### Q3：我可以在購買前免費試用 Aspose.Page for .NET 嗎？

 A3：是的，您可以獲得免費試用[這裡](https://releases.aspose.com/).

### Q4：如何取得 Aspose.Page for .NET 的臨時授權？

A4：參觀[這個連結](https://purchase.aspose.com/temporary-license/)獲得臨時許可證。

### Q5：我可以在哪裡尋求社群支援或提出與 Aspose.Page for .NET 相關的問題？

 A5：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持。