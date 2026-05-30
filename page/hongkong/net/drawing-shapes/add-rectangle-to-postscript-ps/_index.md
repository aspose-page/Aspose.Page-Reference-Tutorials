---
date: 2026-01-18
description: 學習如何使用 Aspose.Page for .NET 建立 PostScript 文件並加入矩形。一步一步的教學，附有程式碼範例。
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: 使用 .NET 建立 PostScript 文件 – 使用 Aspose.Page 新增矩形
url: /zh-hant/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 為 PostScript (PS) 新增矩形

## Introduction

如果您想 **create postscript document .net**，Aspose.Page 提供了一個強大的解決方案來處理 PostScript 檔案。於本教學中，我們將指導您如何使用 Aspose.Page for .NET 在 PostScript 文件中新增矩形，為更豐富的圖形生成奠定堅實基礎。

## Quick Answers
- **我需要哪個函式庫？** Aspose.Page for .NET.
- **我可以從頭開始建立 PostScript 文件嗎？** 可以 – API 允許您以程式方式建立 PS 檔案。
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7.
- **開發時需要授權嗎？** 免費試用可用於測試；正式環境需購買授權。
- **實作大約需要多久？** 基本圖形通常在 10 分鐘內完成。

## What is creating a postscript document .net?
在 .NET 中建立 PostScript 文件是指使用 Aspose.Page API 以程式方式產生描述頁面內容（文字、圖形或形狀）的 .ps 檔案。此方式非常適合伺服器端圖形產生、自動化報告產生，或任何需要精確控制輸出格式的情境。

## Why use Aspose.Page for .NET?
- **完整的圖形控制** – 繪製形狀、設定顏色、套用筆畫，無需處理低階 PS 語法。
- **跨平台** – 可在 Windows、Linux、macOS 執行環境上運作。
- **無外部相依性** – 函式庫在內部處理所有 PS 產生。
- **豐富的文件與範例** – 快速上手。

## Prerequisites

- **Aspose.Page for .NET Library** – 從 [here](https://releases.aspose.com/page/net/) 下載並安裝。
- **開發環境** – Visual Studio、VS Code 或任何相容 .NET 的 IDE。

## Import Namespaces

Before you start coding, import the namespaces that expose the required classes:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Now let’s break the example into clear, numbered steps.

## Step 1: Set up Your Document Directory

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為您希望儲存產生的 PS 檔案的資料夾路徑。

## Step 2: Create Output Stream for the PostScript Document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

此串流指向 **AddRectangle_outPS.ps**。您可以自行重新命名檔案或依需求變更儲存位置。

## Step 3: Set Save Options and Create the PS Document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

在此我們告訴 Aspose.Page 使用 A4 頁面尺寸，並建立單頁文件。

## Step 4: Add a Filled Rectangle

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

我們在 (250, 100) 定義一個寬 150、高 100 的矩形，設定橙色筆刷，並填滿形狀。

## Step 5: Add an Outlined Rectangle

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

第二個矩形位於頁面較低處，這次使用紅色 3 點寬的筆畫。

## Step 6: Close the Page and Save the Document

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

關閉頁面即完成繪圖，`Save()` 會將 PS 檔寫入磁碟。

## Common Issues & Tips

- **檔案路徑不正確** – 確認 `dataDir` 以路徑分隔符 (`\\` 或 `/`) 結尾，或使用 `Path.Combine`。
- **缺少授權** – 在正式環境中，於建立文件前套用 Aspose 授權，以避免評估水印。
- **顏色可見性** – 若矩形顯示為空白，請確認筆刷或筆的顏色與頁面背景形成對比。

## Frequently Asked Questions

**Q:** 我可以自訂矩形的顏色嗎？  
**A:** 當然可以。將 `SolidBrush` 與 `Pen` 建構式中的 `Color.Orange` 或 `Color.Red` 改成您想要的任何 `System.Drawing.Color` 即可。

**Q:** Aspose.Page 是否相容其他文件格式？  
**A:** 是的。除了 PostScript，Aspose.Page 亦支援 XPS 與 EPS 的產生。

**Q:** 我該如何在同一文件中加入文字？  
**A:** 使用 `TextFragment` 類別在指定座標放置文字，然後呼叫 `document.Draw(textFragment)`。

**Q:** 我在哪裡可以找到更多範例與完整 API 參考？  
**A:** 前往文件 [here](https://reference.aspose.com/page/net/) 探索，並加入 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 社群。

**Q:** 我可以在購買前試用 Aspose.Page 嗎？  
**A:** 可以，從 [here](https://releases.aspose.com/) 下載免費試用版。若需延長評估，可考慮申請 [temporary license](https://purchase.aspose.com/temporary-license/)。

---

**最後更新：** 2026-01-18  
**測試版本：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}