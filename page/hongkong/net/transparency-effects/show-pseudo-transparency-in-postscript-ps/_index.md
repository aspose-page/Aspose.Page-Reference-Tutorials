---
date: 2026-03-29
description: 學習如何使用 C# 的線性漸層筆刷在 PostScript 中創建偽透明效果，搭配 Aspose.Page for .NET。
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: C# 線性漸層筆刷於 PS 中的偽透明
url: /zh-hant/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 用於 PostScript (PS) 偽透明的 Linear Gradient Brush C#

## 介紹

如果您需要在 PostScript (PS) 檔案中加入細微的透視效果，**linear gradient brush C#** 是完美的工具。Aspose.Page for .NET 可輕鬆繪製具有不透明與半透明漸層填充的矩形，為您的文件帶來現代化、分層的外觀。在本教學中，我們將逐步說明如何使用 C# 的 linear gradient brush 來建立偽透明效果。

## 快速解答
- **提供 linear gradient brush 的函式庫是什麼？** Aspose.Page for .NET
- **哪個圖形類別會建立漸層？** `LinearGradientBrush`
- **我可以針對每種顏色控制不透明度嗎？** 可以，使用 `Color.FromArgb(alpha, …)`
- **生產環境需要授權嗎？** 需要有效的 Aspose.Page 授權
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+

## 什麼是 linear gradient brush C#？

`LinearGradientBrush` 是一個 GDI+ 物件，可在直線上繪製兩種顏色之間的平滑過渡。當您為每種顏色指定 alpha 通道（0‑255）時，即可建立半透明漸層——這正是我們在 PostScript 中實現偽透明所需的。

## 為何在偽透明中使用 linear gradient brush C#？

- **細緻的不透明度控制：** 調整每個顏色的 alpha 以達到所需的透視程度。  
- **裝置無關的渲染：** 此筆刷在螢幕、PDF、EPS 以及 PS 輸出上皆表現相同。  
- **簡易 API：** 幾行 C# 程式碼即可產生專業級的視覺效果。

## 前置條件

在深入程式碼之前，請確保您已具備：

- 已安裝 Aspose.Page for .NET。您可從 [Aspose.Page documentation](https://reference.aspose.com/page/net/) 下載。  
- 一個可寫入的資料夾，用於儲存產生的 PostScript 文件。

既然您已備妥必要工具，讓我們開始建立偽透明的矩形吧。

## 匯入命名空間

在開始之前，匯入包含我們將使用之類別的命名空間：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟 1：建立 PostScript 文件的輸出串流

我們先建立一個檔案串流以保存產生的 PS 檔案，然後初始化 `PsDocument`。

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 2：建立具有 **不透明** 漸層填充的矩形

此處我們建立一個 `LinearGradientBrush`，其顏色完全不透明（alpha = 255）。此矩形將作為背景層。

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## 步驟 3：建立具有 **半透明** 漸層填充的矩形

現在我們使用 **linear gradient brush C#**，其 alpha 值低於 255（例如 150 與 50）。這使矩形部分透視，達成偽透明效果。

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## 步驟 4：關閉頁面並儲存文件

最後，我們完成頁面並將 PS 檔寫入磁碟。

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

遵循這四個步驟，即可無縫混合不透明與半透明矩形，於任何 PostScript 輸出中產生逼真的偽透明效果。

## 常見問題與解決方案

| 問題 | 為何會發生 | 解決方案 |
|------|------------|----------|
| 顏色顯示為完全不透明 | Alpha 值誤設為 255 | 使用 `Color.FromArgb(alpha, …)` 並將 `alpha` < 255 |
| 漸層拉伸不正確 | 轉換矩陣錯誤 | 確認矩陣參數與矩形尺寸相符 |
| 輸出檔案為空 | 串流未關閉或未呼叫 `Save()` | 確保在 `using` 區塊內執行 `document.ClosePage()` 與 `document.Save()` |

## 常見問答

**Q: Aspose.Page 是否相容於所有 .NET 版本？**  
A: Aspose.Page for .NET 相容於多個 .NET 框架版本，確保彈性與易於整合。

**Q: 我可以將偽透明應用於除矩形外的其他形狀嗎？**  
A: 可以，透過相應調整 `GraphicsPath`，相同原理適用於任何形狀。

**Q: 我可以在哪裡找到更多範例與文件？**  
A: 請參考 [Aspose.Page documentation](https://reference.aspose.com/page/net/) 以取得完整範例與詳細 API 參考。

**Q: Aspose.Page 有提供免費試用嗎？**  
A: 有，您可從 [this link](https://releases.aspose.com/) 取得 Aspose.Page 的免費試用。

**Q: 我要如何取得 Aspose.Page 的臨時授權？**  
A: 請前往 [this link](https://purchase.aspose.com/temporary-license/) 取得 Aspose.Page 的臨時授權。

---

**最後更新：** 2026-03-29  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}