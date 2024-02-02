---
title: 使用 Aspose.Page 將紋理平鋪模式套用至 PostScript (PS)
linktitle: 將紋理平鋪圖案套用至 PostScript (PS)
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 透過紋理平鋪圖案增強 PostScript (PS) 文件。請按照我們的逐步指南進行創意操作。
type: docs
weight: 10
url: /zh-hant/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## 介紹

歡迎閱讀本逐步教學課程，了解如何使用 Aspose.Page for .NET 將紋理平鋪圖案套用到 PostScript (PS) 文件。 Aspose.Page 是一個功能強大的庫，可讓您使用各種文件格式，在本教學中，我們將探索如何透過添加紋理平鋪圖案來增強您的 PS 文件。

## 先決條件

在我們深入學習本教學之前，請確保您具備以下條件：

- [視覺工作室](https://visualstudio.microsoft.com/)安裝在您的機器上。
- C# 程式設計基礎知識。
- 下載並安裝[Aspose.Page for .NET 函式庫](https://releases.aspose.com/page/net/).
- 紋理圖案的圖像檔案（例如“TestTexture.bmp”）。

## 導入命名空間

在您的 C# 程式碼中，確保導入必要的命名空間：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

讓我們將提供的範例分解為多個步驟來引導您完成整個過程。

## 第 1 步：設定文檔目錄

```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
```

確保將「您的文件目錄」替換為您要儲存 PS 文件的路徑。

## 步驟2：為PS文檔建立輸出流

```csharp
//為 PostScript 文件建立輸出流
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    //建立 A4 尺寸的儲存選項
    PsSaveOptions options = new PsSaveOptions();

    //建立新的 1 頁 PS 文檔
    PsDocument document = new PsDocument(outPsStream, options, false);
```

此步驟設定 PS 文件的輸出流，包括定義文件大小。

## 第 3 步：套用紋理平鋪圖案

```csharp
//從映像檔建立 Bitmap 對象
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    //從圖像創建紋理畫筆
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //在圖案上添加 X 方向的縮放
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    //將此紋理畫筆設定為目前繪畫
    document.SetPaint(brush);
}
```

此步驟涉及從圖像創建紋理畫筆並將其設定為文件的當前繪畫。

## 第四步：建立矩形路徑並填充

```csharp
//建立矩形路徑
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

//填滿矩形
document.Fill(path);
```

在這裡，我們定義一個矩形路徑並用先前設定的紋理畫筆填滿它。

## 步驟5：設定描邊和繪製

```csharp
//取得當前油漆
Brush paint = document.GetPaint();

//設定紅色描邊
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

//描畫矩形
document.Draw(path);
```

此步驟涉及設定描邊屬性並繪製輪廓矩形。

## 步驟6：用紋理圖案填滿和輪廓文本

```csharp
//以紋理圖案填滿文本
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

//帶有紋理圖案的輪廓文本
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

最後，我們使用紋理圖案填充和輪廓文本，增強文件的視覺吸引力。

## 第 7 步：儲存並關閉文檔

```csharp
//關閉目前頁面
document.ClosePage();

//儲存文件
document.Save();
```

確保關閉目前頁面並儲存文件以套用變更。

## 結論

恭喜！您已經成功學習如何使用 Aspose.Page for .NET 將紋理平鋪圖案套用到 PostScript 文件。嘗試不同的圖像和圖案來進一步自訂您的 PS 文件。

## 常見問題解答

### Q1: 我可以使用其他影像格式作為紋理圖案嗎？

A1：是的，Aspose.Page支援各種圖像格式。確保與庫文檔的兼容性。

### Q2：Aspose.Page 與.NET Core 相容嗎？

A2：是的，Aspose.Page 與 .NET Framework 和 .NET Core 相容。

### Q3：如何調整紋理矩形的大小？

 A3：修改尺寸`RectangleF`路徑創建期間的參數。

### Q4：我可以在一個文件中加入多個紋理圖案嗎？

A4：是的，您可以使用不同的圖像和路徑重複此過程。

### Q5：我可以在哪裡找到更多資源和支援？

 A5：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)尋求社區支持並探索[文件](https://reference.aspose.com/page/net/).
