---
date: 2026-02-23
description: 學習如何在 PostScript 檔案中加入漸層、將 PostScript 檔案儲存為 A4 頁面大小，並使用 Aspose.Page for
  .NET 填充矩形漸層。
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: 如何在 PostScript (PS) 中使用 Aspose.Page .NET 添加漸層 – 對角線漸層
url: /zh-hant/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 PostScript (PS) 中加入對角漸層 – 使用 Aspose.Page .NET

## 介紹

在 PostScript (PS) 文件中加入對角漸層可以大幅提升視覺效果，特別是當您需要在技術報告、手冊或圖形密集的應用程式中加入 **how to add gradient** 效果時。本教學將示範如何在 PostScript 檔案中加入漸層、設定 A4 頁面大小，並使用 Aspose.Page for .NET 以平滑的顏色過渡填滿矩形。

## 快速回答
- **需要哪個函式庫？** Aspose.Page for .NET  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6  
- **可以變更漸層方向嗎？** 可以 – 如程式碼所示，旋轉筆刷的變換矩陣即可  
- **如何儲存結果？** 使用 `PsDocument.Save()`，可將 PostScript 檔寫入磁碟  
- **正式環境需要授權嗎？** 需要，商業授權可解鎖全部功能  

## 什麼是 PostScript 中的對角漸層？

對角漸層是一種以角度（通常為 45°）在形狀上進行的線性顏色過渡。在 PostScript 中，透過套用帶有自訂變換矩陣的 `LinearGradientBrush`，將漸層旋轉、縮放與平移，以符合目標矩形。

## 為什麼使用 Aspose.Page 來繪製漸層填色？

Aspose.Page 抽象化了低階的 PostScript 指令，讓您可以使用熟悉的 .NET 圖形物件。您可以輕鬆建立複雜的填色、設定頁面尺寸，並直接 **save PostScript file**，無需手寫原始 PS 語法。

## 前置作業

- **Aspose.Page for .NET Library** – 前往[此處](https://releases.aspose.com/page/net/)下載。  
- **文件目錄** – 用於寫入產生的 `*.ps` 檔案的資料夾。

現在基礎已備妥，讓我們一步步實作。

## 匯入命名空間

首先，匯入可讓您存取 EPS 裝置、繪圖工具與 I/O 類別的命名空間。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟 1：建立 PostScript 文件的輸出串流（Create PostScript Document）

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## 步驟 2：設定 A4 頁面大小（Save Options）

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## 步驟 3：建立新的 1 頁 PS 文件

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 4：定義矩形參數

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## 步驟 5：建立 Graphics Path

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## 步驟 6：建立線性漸層筆刷（Fill Rectangle Gradient）

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## 步驟 7：為筆刷建立變換矩陣

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## 步驟 8：對筆刷套用變換（旋轉、縮放、平移）

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## 步驟 9：將變換套用至筆刷

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## 步驟 10：設定畫筆並填滿矩形

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## 步驟 11：關閉目前頁面

```csharp
	//Close current page
	document.ClosePage();
```

## 步驟 12：儲存文件（Save PostScript File）

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## 如何儲存 PostScript 檔案

`PsDocument.Save()` 會將完整的 PostScript 內容寫入 **步驟 1** 中開啟的串流。`using` 區塊結束後，檔案 `DiagonaGradient_outPS.ps` 會出現在您先前指定的目錄中。

## 常見使用情境

- **技術文件** 需要細膩的背景陰影。  
- **行銷手冊** 中，對角漸層可增添現代感。  
- **自動化報表產生器** 可即時產出可列印的 PS 檔。

## 疑難排解與小技巧

- **顏色不正確** – 請再次確認傳入 `LinearGradientBrush` 的 ARGB 值。  
- **看不到漸層** – 確認變換矩陣正確旋轉與縮放；`Rotate(-45)` 會設定對角角度。  
- **檔案未產生** – 確認 `dataDir` 指向已存在的資料夾，且程式具備寫入權限。

## 常見問答

**Q: Aspose.Page 是否相容所有 .NET 框架？**  
A: Aspose.Page 支援廣泛的 .NET 版本，從 .NET Framework 4.5+ 到 .NET 6+，確保相容性。

**Q: 我可以自訂 Aspose.Page 的漸層顏色嗎？**  
A: 可以，您在建立 `LinearGradientBrush` 時可指定任意 ARGB 顏色，完整掌控起始與結束色調。

**Q: 有提供 Aspose.Page 的試用版嗎？**  
A: 有，您可在[此處](https://releases.aspose.com/)下載試用版以探索功能。

**Q: 如何取得 Aspose.Page 的臨時授權？**  
A: 前往[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權，以在評估期間解鎖更多功能。

**Q: 哪裡可以找到 Aspose.Page 的社群支援？**  
A: 可於[論壇](https://forum.aspose.com/c/page/39)與社群互動，取得協助與討論。

---

**最後更新：** 2026-02-23  
**測試環境：** Aspose.Page for .NET（最新穩定版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}