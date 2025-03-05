---
title: 使用 Aspose.Page for .NET 將矩形新增至 PostScript (PS)
linktitle: 將矩形新增至 PostScript (PS)
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page 增強 .NET 中的文件建立。了解逐步為 PostScript (PS) 檔案新增矩形。
type: docs
weight: 12
url: /zh-hant/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## 介紹

如果您希望增強 .NET 中的文件建立能力，Aspose.Page 提供了處理 PostScript 文件的強大解決方案。在本教學中，我們將引導您完成使用 Aspose.Page for .NET 將矩形新增至 PostScript 文件的過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Page for .NET 函式庫：從下列位置下載並安裝 Aspose.Page for .NET 函式庫：[這裡](https://releases.aspose.com/page/net/).

- 開發環境：確保您的電腦上設定了 .NET 開發環境。

## 導入命名空間

在開始編碼之前，請確保導入必要的命名空間以存取所需的類別和方法：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

現在，讓我們將範例分解為多個步驟：

## 第 1 步：設定您的文件目錄

```csharp
//開始時間：1
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
```

在此步驟中，將「您的文件目錄」替換為您要儲存 PostScript 文件的路徑。

## 步驟 2：為 PostScript 文件建立輸出流

```csharp
//為 PostScript 文件建立輸出流
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

在這裡，我們為 PostScript 文件建立一個輸出流並指定檔案名稱（「AddRectangle_outPS.ps」）。根據您的喜好調整檔案名稱和位置。

## 步驟 3：設定儲存選項並建立 PS 文檔

```csharp
//建立 A4 尺寸的儲存選項
PsSaveOptions options = new PsSaveOptions();

//建立新的 1 頁 PS 文檔
PsDocument document = new PsDocument(outPsStream, options, false);
```

設定儲存選項，指定所需的頁面尺寸（本例為 A4）。然後，建立一個新的單頁 PostScript 文件。

## 第四步：新增矩形並填充

```csharp
//從第一個矩形建立圖形路徑
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//訂漆
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//填滿矩形
document.Fill(path);
```

在這裡，我們建立一個表示第一個矩形的圖形路徑，設定繪畫顏色（在本例中為橘色），並填滿矩形。

## 步驟5：新增另一個矩形和描邊

```csharp
//從第二個矩形建立圖形路徑
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//設定行程
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//描邊（輪廓）矩形
document.Draw(path);
```

與上一步類似，我們為第二個矩形建立圖形路徑，設定描邊顏色（紅色，厚度為3），並勾勒出矩形的輪廓。

## 步驟 6：關閉頁面並儲存文檔

```csharp
//關閉目前頁面
document.ClosePage();

//儲存文件
document.Save();
```

最後，關閉目前頁面並儲存整個文件。

## 結論

恭喜！您已使用 Aspose.Page for .NET 成功將矩形新增至 PostScript 文件。本教學涵蓋了從設定開發環境到儲存最終文件的基本步驟。

## 常見問題解答

### Q1：我可以自訂矩形的顏色嗎？

A1: 是的，您可以透過調整參數中的參數來自訂顏色`SolidBrush`和`Pen`類。

### Q2：Aspose.Page 是否相容於其他文件格式？

A2：是的，Aspose.Page支援各種文件格式，包括XPS和PostScript。

### Q3：如何在文件中新增文字？

 A3：您可以使用`TextFragment`Aspose.Page 中的類別將文字新增至文件中。

### Q4：在哪裡可以找到更多範例和文件？

 A4：瀏覽文檔[這裡](https://reference.aspose.com/page/net/)並參觀[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持。

### Q5：我可以在購買前試用Aspose.Page嗎？

 A5：是的，您可以獲得免費試用版[這裡](https://releases.aspose.com/)，並且為了延長使用，請考慮[臨時執照](https://purchase.aspose.com/temporary-license/).
