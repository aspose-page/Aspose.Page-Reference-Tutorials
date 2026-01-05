---
date: 2026-01-05
description: 學習如何在 PostScript 中使用 Aspose.Page for .NET 添加裁剪路徑——一步一步的指南，涵蓋設定畫筆與繪製虛線矩形的技巧。
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 為 PS 添加裁剪路徑
url: /zh-hant/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 .NET 使用 Aspose.Page 為 PS 添加裁剪路徑

## 簡介

在本完整教學中，您將學習如何使用 Aspose.Page for .NET **添加裁剪路徑** 到 PostScript (PS) 文件。我們將逐步說明每個步驟，展示如何 **設定畫筆**，以及如何 **繪製虛線矩形** 圍繞被裁剪的內容。完成後，您將擁有一個完整功能的 PS 檔案，示範以形狀進行裁剪，使您的圖形更具動態與專業感。

## 快速解答
- **「add clipping path」的作用是什麼？** 它會將繪圖操作限制在指定的形狀內，隱藏形狀外的所有內容。  
- **哪個函式庫在 .NET 中處理裁剪？** Aspose.Page for .NET 提供豐富的 PS/EPS 操作 API。  
- **我需要授權嗎？** 免費試用可用於開發；正式上線需購買商業授權。  
- **我可以更改畫筆顏色嗎？** 可以，使用 `SetPaint` 搭配任意 `SolidBrush` 或漸層。  
- **可以繪製虛線矩形嗎？** 當然可以 – 建立帶有 `DashStyle.Dash` 的 `Pen` 並使用 `Draw`。  

## PostScript 中的裁剪路徑是什麼？

裁剪路徑定義了後續繪圖指令的可見區域。路徑外的任何繪圖都會被忽略，讓您在不改變原始內容的情況下，建立複雜的遮罩圖形。

## 為何使用 Aspose.Page 進行裁剪？

- **無外部相依性** – 純 .NET 函式庫。  
- **完整控制** 圖形狀態（save/restore、translate、rotate）。  
- **豐富的繪圖基元**，如 `SetPaint`、`Clip`、`Draw`，可自訂筆刷與畫筆。  

## 前置條件

- 具備基本的 C# 程式設計知識。  
- 已安裝 Aspose.Page for .NET 函式庫 – 可從 [here](https://releases.aspose.com/page/net/) 下載。  
- Visual Studio 或其他您偏好的 .NET IDE。  

## 匯入命名空間

首先，匯入圖形操作所需的命名空間：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

現在讓我們將範例分解為清晰的編號步驟。

### 步驟 1：設定文件目錄

定義來源與輸出檔案所在的資料夾。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### 步驟 2：建立 PostScript 文件的輸出串流

建立可寫入的串流，以儲存產生的 PS 檔案。

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### 步驟 3：建立儲存選項

以預設設定實例化 `PsSaveOptions`。如有需要，可稍後自訂。

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### 步驟 4：建立新的 1 頁 PS 文件

初始化代表您的 PS 檔案的 `PsDocument` 物件。

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步驟 5：從矩形建立圖形路徑

我們將使用矩形作為基礎形狀，之後再進行裁剪。

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### 步驟 6：以形狀進行裁剪

此處我們使用圓形 **添加裁剪路徑**，將 **畫筆設定** 為藍色，並在裁剪區域內填滿矩形。

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### 步驟 7：位移上層圖形狀態並繪製虛線矩形

在還原先前狀態後，我們再次移動圖形游標，**繪製虛線矩形**，並套用藍色筆畫。

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### 步驟 8：關閉並儲存文件

完成頁面並將 PS 檔寫入磁碟。

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

您已成功 **添加裁剪路徑**、設定自訂畫筆，並使用 Aspose.Page for .NET 在圖形周圍繪製虛線矩形。

## 常見問題與解決方案

- **裁剪未顯示：** 確保在平移前呼叫 `WriteGraphicsSave()`，在填充後呼叫 `WriteGraphicsRestore()`。  
- **顏色不正確：** 確認在 `Clip` 後、`Fill` 前呼叫 `SetPaint`。  
- **虛線顯示為實線：** 確保在 `SetStroke` 前將 `Pen` 的 `DashStyle` 設為 `DashStyle.Dash`。  

## 常見問答

### Q1：我可以在其他程式語言中使用 Aspose.Page for .NET 嗎？

A：Aspose.Page 主要設計給 .NET 應用程式使用。但 Aspose 亦提供其他程式語言的類似函式庫。

### Q2：在哪裡可以找到 Aspose.Page for .NET 的其他範例與文件？

A：您可於 [Aspose.Page documentation](https://reference.aspose.com/page/net/) 探索更多範例與詳細文件。

### Q3：是否提供 Aspose.Page for .NET 的免費試用？

A：是的，您可在 [here](https://releases.aspose.com/) 取得 Aspose.Page for .NET 的免費試用。

### Q4：如何取得 Aspose.Page for .NET 的臨時授權？

A：您可於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q5：在哪裡可以取得支援或討論 Aspose.Page 相關問題？

A：請前往 [Aspose.Page forums](https://forum.aspose.com/c/page/39) 取得社群支援與討論。

---

**最後更新：** 2026-01-05  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}