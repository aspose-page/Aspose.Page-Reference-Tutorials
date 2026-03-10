---
date: 2026-02-25
description: 學習如何使用 C# 線性漸層畫刷為 PS 檔案添加漸層，並使用 Aspose.Page for .NET 以漸層填充矩形。
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# 線性漸層筆刷 – 使用 Aspose.Page 為 PostScript (PS) 添加垂直漸層
url: /zh-hant/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 2026-02-25  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

Then closing shortcodes.

Make sure to keep all shortcodes unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# 線性漸層筆刷 – 使用 Aspose.Page 為 PostScript (PS) 新增垂直漸層

## 介紹

在文件操作與產生的領域中，**Aspose.Page for .NET** 是開發人員的強大工具。在本指南中，您將學會如何透過 **C# 線性漸層筆刷** 來 **為 PS 檔案新增漸層**，並 **以漸層填滿矩形**。完成本教學後，您將清楚了解所需程式碼的每一步，以及為何此技巧能在 PostScript 輸出中產生平滑的垂直漸層。

## 快速解答
- **C# 線性漸層筆刷的作用是什麼？** 它會在形狀上產生多種顏色之間的平滑過渡。
- **我可以在任何 .NET 版本上使用嗎？** 可以，Aspose.Page 支援 .NET Framework 4.5 以上以及 .NET Core/5 以上。
- **正式環境需要授權嗎？** 非評估版需要商業授權。
- **漸層真的會是垂直的嗎？** 筆刷會旋轉 90°，確保垂直方向的漸層。
- **輸出檔案儲存在哪裡？** 儲存在您於 `dataDir` 指定的路徑（例如 `VerticalGradient_outPS.ps`）。

## 什麼是 C# 線性漸層筆刷？

**C# 線性漸層筆刷** 是一個 GDI+ 物件 (`LinearGradientBrush`)，可在定義的點之間繪製線性顏色過渡。結合 Aspose.Page 的繪圖 API，您可以直接在 PostScript (PS) 文件中呈現精緻的漸層效果。

## 為什麼在 PostScript 中使用線性漸層筆刷？

- **高品質輸出：** 漸層在印表機層級渲染，保留細節。
- **完整控制：** 可自訂顏色點、旋轉與縮放。
- **可重用程式碼：** 相同的筆刷邏輯同樣適用於 PDF、SVG 及其他 Aspose.Page 支援的格式。

## 前置條件

在開始教學之前，請確保您已具備以下條件：

- Aspose.Page for .NET：確保已安裝 Aspose.Page 函式庫。您可以在[此處](https://reference.aspose.com/page/net/)找到相關資源與文件。
- 開發環境：設定好適合的 .NET 開發環境，包含 IDE。
- 基本了解：熟悉 .NET 開發基礎，包括串流、圖形路徑與顏色操作。

## 匯入命名空間

在您的 C# 專案中，於程式碼檔案開頭加入必要的命名空間：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟 1：設定文件目錄

先指定文件目錄的路徑，這是 PS 文件將被儲存的位置。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：為 PostScript 文件建立輸出串流

使用 `FileStream` 類別產生 PostScript 文件的輸出串流。

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## 步驟 3：建立儲存選項與 PS 文件

建立 A4 大小的儲存選項，並初始化一個 1 頁的 PS 文件。

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 4：定義矩形尺寸

指定將套用垂直漸層的矩形之尺寸與位置。

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## 步驟 5：建立圖形路徑

根據先前定義的矩形建立圖形路徑。

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## 步驟 6：定義插值顏色

建立一個包含插值顏色與位置的陣列，以供漸層使用。

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## 步驟 7：建立線性漸層筆刷

以矩形作為邊界，設定起始與結束顏色，建立線性漸層筆刷。

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## 步驟 8：設定筆刷變換

為筆刷設定變換，確保 X 與 Y 的縮放分量分別對應矩形的寬度與高度。

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## 步驟 9：設定繪圖並填滿矩形

為文件設定繪圖，並使用先前定義的路徑 **以漸層填滿矩形**。

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## 步驟 10：關閉目前頁面並儲存文件

關閉當前頁面，並儲存 PostScript 文件。

```csharp
document.ClosePage();
document.Save();
```

恭喜！您已成功使用 **C# 線性漸層筆刷** 搭配 Aspose.Page for .NET **為 PostScript 文件新增垂直漸層**。可嘗試不同參數與顏色，為文件創造各種視覺效果。

## 常見問題與解決方案

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| 漸層呈現水平 | 未套用筆刷旋轉 | 確認在指派 `brush.Transform` 前已呼叫 `brushTransform.Rotate(90);` |
| 顏色看起來淡化 | 輸出串流解析度過低 | 使用較高解析度的 `PsSaveOptions` 或增大文件尺寸 |
| 輸出檔案為空 | 串流未刷新 | 確認 `document.Save();` 在 `using` 區塊外被呼叫 |

## 常見問答

**Q1：我可以在同一文件的不同區域套用多個漸層嗎？**  
A：可以。只要為每個區域重複上述步驟，並使用各自的尺寸與顏色配置即可。

**Q2：如何將此程式碼整合到現有的 .NET 專案中？**  
A：將程式碼複製貼上至專案檔案，並確保已參考 Aspose.Page 函式庫。

**Q3：Aspose.Page for .NET 還支援其他漸層類型嗎？**  
A：Aspose.Page 支援多種漸層，包括徑向漸層與路徑漸層。詳情請參閱文件說明。

**Q4：我可以在商業專案中使用 Aspose.Page 嗎？**  
A：可以。請前往[此處](https://purchase.aspose.com/buy)了解授權方案。

**Q5：有沒有 Aspose.Page 的社群論壇可以求助？**  
A：當然有！前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 與其他開發者交流並取得協助。

**最後更新：** 2026-02-25  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}