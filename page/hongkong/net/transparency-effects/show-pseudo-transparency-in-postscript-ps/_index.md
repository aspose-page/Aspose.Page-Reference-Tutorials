---
title: 使用 Aspose.Page 在 PostScript (PS) 中顯示偽透明度
linktitle: 在 PostScript (PS) 中顯示偽透明度
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 探索 PostScript 中偽透明的強大功能。請按照我們的分步指南獲取視覺上令人驚嘆的文檔。
weight: 13
url: /zh-hant/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 在 PostScript (PS) 中顯示偽透明度

## 介紹

您是否希望透過合併偽透明度來增強 PostScript (PS) 文件的視覺吸引力？ Aspose.Page for .NET 提供了一個強大的解決方案來輕鬆實現這種效果。在本逐步教學中，我們將引導您完成使用 Aspose.Page 在 PostScript 中顯示偽透明度的過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- Aspose.Page for .NET：確保您已安裝 Aspose.Page for .NET 程式庫。您可以從[Aspose.Page 文檔](https://reference.aspose.com/page/net/).

- 文件目錄：設定一個目錄來儲存您的 PostScript 文件。

現在您的武器庫中已經有了必要的工具，讓我們探索如何使用 Aspose.Page 在 PostScript 中展示偽透明度。

## 導入命名空間

在深入研究範例之前，請確保導入所需的命名空間：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟 1：為 PostScript 文件建立輸出流

```csharp
//開始時間：1
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
//為 PostScript 文件建立輸出流
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//建立 A4 尺寸的儲存選項
	PsSaveOptions options = new PsSaveOptions();

	//建立新的 1 頁 PS 文檔
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 2： 使用不透明漸層填滿建立矩形

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

## 步驟 3： 建立具有半透明漸層填滿的矩形

```csharp
	offsetX = 350;

	//從第一個矩形建立圖形路徑
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//創建線性漸變畫筆顏色，透明度不是255，而是150和50。所以它是半透明的。
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## 步驟 4：關閉目前頁面並儲存文檔

```csharp
	document.ClosePage();
	document.Save();
}
//結束：1
```

透過執行這些步驟，您可以使用 Aspose.Page for .NET 將偽透明度無縫整合到 PostScript 文件中。

## 結論

總之，Aspose.Page for .NET 提供了一個簡單有效的方法來增強 PostScript 文件的視覺元素。上述步驟為合併偽透明度提供了一條清晰的路徑，使您能夠創建視覺上令人驚嘆的輸出。

## 常見問題解答

### Q1：Aspose.Page 是否相容於所有版本的.NET？

A1：Aspose.Page for .NET 與.NET 框架的各個版本相容，確保靈活性和易於整合。

### Q2：除了矩形之外，我可以對其他形狀套用偽透明嗎？

A2：是的，透過相應地調整 GraphicsPath，可以將相同的原理應用於其他形狀。

### Q3：在哪裡可以找到更多範例和文件？

 A3：探索[Aspose.Page 文檔](https://reference.aspose.com/page/net/)取得全面的範例和詳細的文件。

### Q4：Aspose.Page 有免費試用版嗎？

 A4：是的，您可以從以下位置存取 Aspose.Page 的免費試用版：[這個連結](https://releases.aspose.com/).

### Q5：如何取得Aspose.Page的臨時授權？

A5：參觀[這個連結](https://purchase.aspose.com/temporary-license/)取得 Aspose.Page 的臨時許可證。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
