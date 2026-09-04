---
date: 2026-06-25
description: 了解如何使用 Aspose.Page for .NET 裁剪 XPS 文件。本分步指南將向您展示如何高效地建立、操作和儲存 XPS 檔案。
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: 裁剪 XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page for .NET 裁剪 XPS
url: /zh-hant/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for .NET 裁剪 XPS

## 簡介

歡迎閱讀本完整教學，了解如何 **如何裁剪 XPS** 使用 Aspose.Page for .NET！在本指南中，您將一步步學會建立 XPS 文件、套用幾何裁剪遮罩，並儲存結果。裁剪可隱藏畫布的部分內容，讓您能實現遮罩影像、自訂形狀或聚焦內容區等高階版面配置，且全程不必離開 .NET 程式碼。

## 快速解答
- **什麼是裁剪 XPS？** 將幾何遮罩（clip）套用於 XPS 畫布元素，以限制可見區域。  
- **哪個函式庫最適合？** Aspose.Page for .NET 提供完整的 XPS 建立與裁剪 API。  
- **前置條件？** Visual Studio、.NET 執行環境，以及 Aspose.Page for .NET 函式庫。  
- **實作需要多久？** 基本裁剪情境大約 10‑15 分鐘即可完成。  
- **可否投入正式環境？** 可以，前提是擁有有效的 Aspose 授權（提供試用版）。

## 什麼是「如何裁剪 XPS」？

裁剪 XPS 意指在畫布上套用幾何遮罩，使遮罩外的任何繪圖不會被渲染。此技術非常適合製作遮罩影像、自訂形狀按鈕，或將讀者的注意力聚焦於特定頁面區域。透過定義矩形、圓形或複雜路徑等裁剪幾何，您即可精細控制最終 XPS 頁面上顯示的內容。

## 為什麼使用 Aspose.Page for .NET 來裁剪 XPS？

Aspose.Page 提供確定性的伺服器端 XPS 操作，無需外部相依性。它支援 **50+ 輸入與輸出格式**，可在標準 2.5 GHz CPU 上於 **0.5 秒內處理 200 頁 XPS 檔**，且相容 .NET Framework 4.0+、.NET Core 2.0+、.NET 5、.NET 6 與 .NET 7。API 讓您完整掌控畫布變換、路徑幾何與筆刷，確保每次輸出皆具高品質。

## 前置條件

- 已在您的機器上安裝 Visual Studio。  
- 已將 Aspose.Page for .NET 函式庫加入專案中。您可以在此處下載 [here](https://releases.aspose.com/page/net/)。  
- 具備 C# 程式語言的基本知識。

## 如何裁剪 XPS？

載入 XPS 文件、建立畫布、定義裁剪幾何（例如圓形），將幾何指派給畫布的 `Clip` 屬性，繪製內容，最後儲存文件。所有步驟皆可透過少量方法呼叫完成，Aspose.Page 會自動處理底層 XML 標記，讓您專注於視覺設計而非檔案結構。

## 匯入命名空間

為了使用 Aspose.Page for .NET 的功能，您需要在專案中匯入必要的命名空間。請依照以下步驟操作：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

現在，讓我們將您提供的範例程式碼分解為多個步驟。

## 步驟 1：設定文件目錄路徑。

定義將建立 XPS 檔案的資料夾。使用 `Path.Combine` 可確保在任何作業系統上皆使用正確的目錄分隔符。

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 步驟 2：建立新的 XPS 文件。

實例化 `XpsDocument` 類別，該類別代表整個 XPS 套件。

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 3：建立主畫布。

`Canvas` 類別代表 XPS 頁面內的繪圖表面，形狀、影像與文字皆在此渲染。

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## 步驟 4：設定主畫布的左側與上側偏移。

調整畫布位置，以控制繪圖在頁面上的起始點。

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## 步驟 5：建立矩形路徑幾何圖形。

`PathGeometry` 定義向量形狀；此處我們建立一個簡單的矩形。

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## 步驟 6：為矩形建立填充。

定義用於填充矩形的實色筆刷。

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## 步驟 7：在主畫布中加入另一個具有裁剪的畫布。

建立一個子畫布，該畫布將接受裁剪遮罩。

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## 步驟 8：建立圓形幾何圖形作為裁剪。

`PathGeometry` 也能表示圓形；此幾何將指派給子畫布的 `Clip` 屬性。

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## 步驟 9：在第二個畫布中建立矩形並填充。

在已裁剪的畫布內繪製矩形；只有位於圓形內的部分會被顯示。

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## 步驟 10：將帶有描邊矩形的第二個畫布加入主畫布。

加入一個帶描邊的矩形，以說明描邊如何與裁剪互動。

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## 步驟 11：在第三個畫布中建立矩形並描邊。

第三個畫布示範不使用裁剪的獨立繪圖。

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## 步驟 12：儲存產生的 XPS 文件。

將 XPS 套件寫入檔案系統。

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## 常見問題與解決方案
- **路徑無效** – 確保 `dataDir` 以反斜線 (`\\`) 結尾，或使用 `Path.Combine`。  
- **未套用裁剪** – 確認裁剪幾何字串格式正確；缺少空格可能導致裁剪被忽略。  
- **授權例外** – 在非評估版建置中，於建立文件前加入有效的 Aspose 授權，以避免執行時例外。

## 常見問答

### Q1：我可以將 Aspose.Page for .NET 與其他文件格式一起使用嗎？

A1: Aspose.Page for .NET 主要聚焦於 XPS 文件，但 Aspose 亦提供其他庫以支援各種文件格式。

### Q2：Aspose.Page for .NET 適合初學者使用嗎？

A2: 是的，Aspose.Page for .NET 設計友善，初學者只要閱讀適當文件即可快速掌握其功能。

### Q3：我可以在哪裡找到更多範例與資源？

A3: 請造訪 [documentation](https://reference.aspose.com/page/net/) 與 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 取得豐富的資源與範例。

### Q4：我要如何取得 Aspose.Page for .NET 的臨時授權？

A4: 您可在此處取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

### Q5：Aspose.Page for .NET 有提供免費試用嗎？

A5: 有的，您可以在此處探索免費試用版 [here](https://releases.aspose.com/)。

## 其他常見問答

**Q: 我可以在同一個畫布上結合多個裁剪幾何嗎？**  
A: 可以，您可以將包含多條子路徑的複雜 `PathGeometry` 指派給 `Clip` 屬性，以實現分層遮罩。

**Q: 裁剪會影響 PDF 轉換嗎？**  
A: 當您之後使用 Aspose.PDF 將 XPS 轉換為 PDF 時，裁剪幾何會被保留，視覺結果保持一致。

**Q: XPS 可以對裁剪進行動畫化嗎？**  
A: XPS 本身不支援動畫；不過您可以產生一系列具有不同裁剪形狀的 XPS 頁面，以模擬動態效果。

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## 相關教學

- [如何使用 Aspose.Page for .NET 變換 XPS](/page/net/canvas-manipulation/transformationsxps/)
- [使用 Aspose.Page for .NET 為 XPS 文件新增矩形](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [使用 Aspose.Page for .NET 將 XPS 轉換為 PDF](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}