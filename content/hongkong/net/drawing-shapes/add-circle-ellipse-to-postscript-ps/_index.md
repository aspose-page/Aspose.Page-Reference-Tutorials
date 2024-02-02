---
title: 使用 Aspose.Page 將圓橢圓加到 PostScript (PS)
linktitle: 將圓橢圓加到 PostScript (PS)
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page for .NET 輕鬆地將圓形橢圓新增至 PostScript (PS) 文件。請按照我們的逐步指南進行無縫整合。
type: docs
weight: 10
url: /zh-hant/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## 介紹

歡迎來到這個關於使用 Aspose.Page for .NET 將圓橢圓加入 PostScript (PS) 文件的綜合教學。 Aspose.Page 是一個功能強大的程式庫，可讓開發人員無縫地使用 PostScript 和其他文件格式。在本指南中，我們將引導您輕鬆完成將圓形橢圓合併到 PS 文件中的過程。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

1.  Aspose.Page for .NET 函式庫：從下列位置下載並安裝 Aspose.Page for .NET 函式庫：[這裡](https://releases.aspose.com/page/net/).

2. 開發環境：確保您的電腦上設定了有效的 .NET 開發環境。

現在，讓我們開始使用逐步指南。

## 導入命名空間

第一步，您需要匯入必要的命名空間，以使 Aspose.Page 功能在您的程式碼中可用。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

現在，讓我們將提供的範例分解為多個步驟，以引導您完成在 PostScript 文件中新增圓形橢圓的過程。

## 步驟1：設定文檔目錄

```csharp
//開始時間：1
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
```

確保將“您的文件目錄”替換為文件目錄的實際路徑。

## 步驟 2：為 PostScript 文件建立輸出流

```csharp
//為 PostScript 文件建立輸出流
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

這裡創建了一個FileStream來寫入PostScript文檔，並設定文件模式來建立一個新文件。

## 步驟3：建立保存選項和PS文檔

```csharp
//建立 A4 尺寸的儲存選項
PsSaveOptions options = new PsSaveOptions();

//建立新的 1 頁 PS 文檔
PsDocument document = new PsDocument(outPsStream, options, false);
```

此步驟涉及建立 A4 尺寸的儲存選項並初始化新的 1 頁 PS 文件。

## 步驟 4：為第一個橢圓建立圖形路徑

```csharp
//從第一個橢圓建立圖形路徑
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

為第一個橢圓建立圖形路徑，指定其位置和尺寸。

## 步驟5：設定油漆並填充橢圓

```csharp
//訂漆
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//填充橢圓
document.Fill(path);
```

在這裡，繪製已設置，並且第一個橢圓形以指定的顏色填充。

## 步驟6：為第二個橢圓建立圖形路徑

```csharp
//從第二個橢圓建立圖形路徑
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

同樣，為第二個橢圓建立圖形路徑，定義其位置和尺寸。

## 步驟7：設定描邊並繪製橢圓

```csharp
//設定行程
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//描邊（輪廓）橢圓
document.Draw(path);
```

在此步驟中，設定筆劃，並使用指定的顏色和線條粗細勾勒出第二個橢圓的輪廓。

## 步驟 8：關閉目前頁面並儲存文檔

```csharp
//關閉目前頁面
document.ClosePage();

//儲存文件
document.Save();
```

最後，關閉目前頁面，並儲存整個文檔，完成該過程。

## 結論

恭喜！您已成功學習如何使用 Aspose.Page for .NET 將圓形橢圓新增至 PostScript 文件。本教學提供了詳細的逐步指南，可協助您將此功能無縫整合到您的專案中。

## 常見問題解答

### Q1：我可以將 Aspose.Page for .NET 與其他文件格式一起使用嗎？

 A1：Aspose.Page 主要專注於 PostScript，但 Aspose 也為各種文件格式提供了其他函式庫。檢查[Aspose 文檔](https://reference.aspose.com/page/net/)更多細節。

### 問題 2：我可以在哪裡找到更多支持和社區討論？

 A2：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)供社區討論和支持。

### 問題 3：Aspose.Page for .NET 是否有免費試用版？

 A3：是的，您可以訪問[免費試用](https://releases.aspose.com/)探索 Aspose.Page for .NET 的功能。

### Q4：如何取得Aspose.Page的臨時授權？

 A4：取得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)用於測試和評估目的。

### Q5：哪裡可以購買 Aspose.Page for .NET？

 A5：從以下位置購買 Aspose.Page for .NET[購買頁面](https://purchase.aspose.com/buy).