---
date: 2026-02-25
description: 使用 Aspose.Page for .NET，為 PostScript 文件增添線性漸層矩形。請跟隨我們的逐步指南，學習漸層填充文字與文字輪廓漸層。
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 為 PostScript (PS) 添加線性漸層矩形
url: /zh-hant/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 為 PostScript (PS) 新增線性漸層矩形

## 介紹

歡迎閱讀本完整教學，教您如何使用 Aspose.Page for .NET 在 PostScript (PS) 文件中加入 **線性漸層矩形**。Aspose.Page 是功能強大的函式庫，可讓您建立、修改與轉換各種格式的文件，今天我們將重點說明如何在 PS 檔案中加入吸睛的漸層效果。

### 快速回答
- **線性漸層矩形的作用是什麼？** 它會以平滑的顏色過渡填滿矩形區域，從一側漸變到另一側。  
- **哪個 API 處理漸層填色文字？** `LinearGradientBrush` 搭配 `SetPaint` 與 `FillAndStrokeText`。  
- **可以使用漸層描邊文字嗎？** 可以——使用 `SetStroke` 並傳入漸層筆刷，再呼叫 `OutlineText`。  
- **正式環境需要授權嗎？** 商業授權的 Aspose.Page 必須購買，才能在非評估模式下使用。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 前置作業

在開始之前，請確保您已具備以下項目：

- Aspose.Page for .NET 函式庫：請確定已在專案中引用此函式庫。您可以從 [Aspose.Page for .NET 文件](https://reference.aspose.com/page/net/) 下載。  
- 文件目錄：在磁碟上建立一個資料夾，用來儲存產生的 PS 檔，並在程式碼中將 **“Your Document Directory”** 替換為該路徑。

## 匯入命名空間

首先，匯入可讓您存取繪圖與 PS 專屬類別的命名空間：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 什麼是線性漸層矩形？

**線性漸層矩形** 指的是內部以線性漸層方式上色的矩形形狀——顏色沿著直線平滑過渡，通常是從左至右（水平）或從上至下（垂直）。在 Aspose.Page 中，您可以透過結合定義矩形的 `GraphicsPath` 與描述顏色過渡的 `LinearGradientBrush` 來實現。

## 為什麼要使用漸層填色文字與描邊文字漸層？

- **視覺吸引力：** 漸層填色文字能為報表、發票或行銷素材增添深度與現代感。  
- **品牌一致性：** 使用精確的 ARGB 值匹配企業色彩。  
- **彈性高：** 同一支筆刷可重複用於圖形填色、文字填色與描邊漸層，減少程式碼重複。

## 第一步：設定文件

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## 第二步：定義漸層矩形與顏色

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## 第三步：設定筆刷的變換

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## 第四步：設定 Paint 並填滿矩形

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## 如何套用漸層填色文字

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## 使用描邊文字漸層

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## 第七步：關閉目前頁面並儲存文件

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

恭喜！您已成功在 PostScript 文件中加入 **線性漸層矩形**，並使用相同的筆刷完成 **漸層填色文字** 與 **描邊文字漸層**。

## 常見使用情境與技巧

- **報表標題：** 使用漸層填滿大型文字區塊，以突顯章節標題。  
- **品牌標誌：** 以漸層填色圖形重建標誌形狀，確保品牌一致性。  
- **專業小技巧：** 重複使用同一個 `LinearGradientBrush` 實例進行多次繪圖呼叫，讓顏色在不同圖形與文字之間保持完美對齊。

## 常見問題

### Q1：我可以將漸層套用到矩形以外的形狀嗎？
**A：** 可以，您可以將漸層套用到任何由 `GraphicsPath` 定義的形狀。只需在呼叫 `document.Fill(path)` 前加入圓形、多邊形或自訂路徑即可。

### Q2：我要如何變更漸層顏色？
**A：** 在建立 `LinearGradientBrush` 時，修改 `Color.FromArgb` 的參數值。第一個顏色為起始色，第二個顏色為結束色。

### Q3：Aspose.Page 是否支援其他文件格式？
**A：** 當然支援。Aspose.Page 支援 XPS、PS、PDF 以及其他多種向量格式。完整支援清單請參考官方文件。

### Q4：我可以在商業專案中使用 Aspose.Page 嗎？
**A：** 可以，提供商業授權。詳情請參閱購買頁面：[here](https://purchase.aspose.com/buy)。

### Q5：在哪裡可以取得社群支援？
**A：** 加入 Aspose.Page 社群論壇：[Aspose.Page Forum](https://forum.aspose.com/c/page/39)。

---

**最後更新：** 2026-02-25  
**測試環境：** Aspose.Page 24.10 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}