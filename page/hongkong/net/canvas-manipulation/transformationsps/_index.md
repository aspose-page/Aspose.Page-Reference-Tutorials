---
title: 使用 Aspose.Page for .NET 轉換 PS
linktitle: 變形PS
second_title: Aspose.Page .NET API
description: 透過這份關於 PostScript 轉換的綜合指南釋放 Aspose.Page for .NET 的潛力。輕鬆建立動態圖形。
type: docs
weight: 12
url: /zh-hant/net/canvas-manipulation/transformationsps/
---
## 介紹

歡迎來到 Aspose.Page for .NET 的世界，您可以釋放 PostScript 文件轉換的力量。本教學將引導您完成各種變換，例如平移、縮放、旋轉、剪切和複雜變換，使您能夠創建視覺上令人驚嘆的動態圖形。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Page for .NET 函式庫：確保您已將 Aspose.Page for .NET 函式庫整合到您的專案中。您可以從[下載連結](https://releases.aspose.com/page/net/).

- 文件目錄：為您的文件設定一個目錄，並將程式碼中的佔位符替換為實際路徑。

## 導入命名空間

在您的 .NET 專案中，匯入使用 Aspose.Page 所需的命名空間：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

現在，讓我們以逐步指南的形式將每個範例分解為多個步驟。


## 無轉換

### 第 1 步：建立輸出流

```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";

//為 PostScript 文件建立輸出流
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    //建立具有預設值的儲存選項
    PsSaveOptions options = new PsSaveOptions();

    //建立新的 1 頁 PS 文檔
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    //從矩形建立圖形路徑
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    //將繪畫設定為上層圖形狀態
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    //填滿處於上層圖形狀態且不進行任何變換的第一個矩形
    document.Fill(path);

    //關閉目前頁面
    document.ClosePage();

    //儲存文件
    document.Save();
}
```

此程式碼建立一個沒有轉換的 PostScript 文檔，以橘色填滿矩形。

## 翻譯

### 第1步：儲存圖形狀態

```csharp
//保存圖形狀態以在變換後返回該狀態
document.WriteGraphicsSave();
```

此步驟保存目前的圖形狀態，以便我們在轉換後返回它。

### 第 2 步：轉換圖形狀態

```csharp
//將目前圖形狀態向右移動 250
document.Translate(250, 0);
```

透過新增平移組件來平移目前圖形狀態，然後將目前圖形狀態下的繪製設為藍色。

### 第三步：用平移變換填滿矩形

```csharp
//將繪畫設定為目前圖形狀態
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

//填滿目前圖形狀態下的第二個矩形（具有平移變換）
document.Fill(path);
```

此步驟填入目前圖形狀態下的第二個矩形，其中現在包括平移變換。

### 第四步：恢復圖形狀態

```csharp
//將圖形狀態恢復到上一個（上）級別
document.WriteGraphicsRestore();
```

填滿矩形後，將圖形狀態恢復到先前的水平。

繼續針對每種變換類型（包括縮放、旋轉、剪切和複雜變換）的逐步指南。

## 結論

恭喜！您已成功掌握 Aspose.Page for .NET 的變革功能。現在，嘗試不同的組合併在 PostScript 文件轉換中釋放您的創造力。

## 常見問題解答

### Q1：如何對單一物件套用多個變換？

A1：若要套用多個轉換，請使用`Transform`具有自訂變換矩陣的方法。

### Q2：我可以在儲存文件之前預覽轉換嗎？

A2：是的，您可以透過渲染文件並在適當的檢視器中預覽來視覺化轉換。

### 問題 3：是否可以對文件中的特定元素套用轉換？

A3：是的，您可以隔離文件中特定圖形元素的轉換。

### Q4：處理複雜的轉換時是否有效能上的考量？

A4：複雜的轉換可能會影響效能，因此請最佳化程式碼以提高效率。

### Q5：我如何獲得 Aspose.Page 相關查詢的支援或尋求協助？

 A5：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持和討論。