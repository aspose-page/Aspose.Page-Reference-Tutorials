---
date: 2026-04-03
description: 學習如何在 .NET 中使用 Aspose.Page 添加透明矩形並套用 Grid Visual Brush，以製作驚艷的 XPS 文件。
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: 套用格線視覺筆刷
second_title: Aspose.Page .NET API
title: 使用 Grid Visual Brush 添加透明矩形 (.NET)
url: /zh-hant/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Grid Visual Brush (.NET) 新增透明矩形

## 介紹

如果您想在 XPS 文件中 **新增透明矩形**，同時套用時尚的 Grid Visual Brush，您來對地方了。在本教學中，我們將逐步說明使用 Aspose.Page for .NET 所需的完整步驟，讓您能夠建立視覺豐富、脫穎而出的文件。完成後，您將擁有一個完整且可執行的範例，展示這兩種技術於單一、易於跟隨的工作流程中。

## 快速解答
- **透明矩形的作用是什麼？** 它會加入半透明的覆蓋層，讓背景內容得以顯示。  
- **哪個 API 用於建立筆刷？** `XpsDocument.CreateVisualBrush` 會建立 Grid Visual Brush。  
- **我需要授權嗎？** 免費試用版可用於測試；正式環境需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **實作需要多長時間？** 基本範例大約需要 10‑15 分鐘。

## XPS 中的透明矩形是什麼？
透明矩形只是填色包含小於 1.0 的 alpha 透明度的形狀，讓底層圖形得以部分可見。這非常適合在不完全遮蔽背景的情況下突顯區段。

## 為什麼使用 Grid Visual Brush？
Grid Visual Brush 允許您將小型向量圖形平鋪於較大區域，產生格線、斜紋或自訂紋理等圖案。將其與透明矩形結合，可產生輕量且與解析度無關的分層視覺效果。

## 前置條件

在深入程式碼之前，請確保您已具備：

- **Aspose.Page for .NET** – 您可於 [here](https://releases.aspose.com/page/net/) 下載。  
- .NET 開發環境（Visual Studio、VS Code 或您偏好的任何 IDE）。  
- 用於儲存產生之 XPS 檔案的資料夾。

## 匯入命名空間

在您的 C# 檔案中，匯入所需的命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

現在讓我們將解決方案分解為清晰的編號步驟。

## 步驟 1：初始化 XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

我們先建立 `XpsDocument` 實例，它將容納所有後續的繪圖操作。

## 步驟 2：建立洋紅色格線幾何圖形

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

此幾何圖形定義了視覺筆刷將填充的格線輪廓。

## 步驟 3：設計洋紅色格線 VisualBrush

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

此處繪製一個小型洋紅色圖塊，將在格線上重複。

## 步驟 4：將 VisualBrush 套用至格線

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

`CreateVisualBrush` 呼叫將洋紅色圖塊與格線幾何圖形關聯，並啟用平鋪。

## 步驟 5：將格線加入 Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

我們將平鋪的格線放置於 Canvas，並套用平移變換，使其出現在指定位置。

## 步驟 6：新增透明矩形

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

在此步驟中，我們 **新增透明矩形**（紅色形狀，`Opacity = 0.7f`）。調整透明度值即可控制矩形的透視程度。

## 步驟 7：儲存文件

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

XPS 檔案會寫入您先前指定的資料夾。

## 常見使用情境

- **報告強調：** 在圖表或表格上覆蓋半透明矩形以突顯重點。  
- **浮水印效果：** 結合平鋪格線與透明覆蓋層，實現細膩的品牌標示。  
- **互動式 PDF/XPS：** 將圖案作為表單欄位的背景，同時保持介面可讀性。

## 疑難排解技巧

- **透明度未顯示？** 確認您的檢視器支援 XPS 透明度；某些舊版檢視器可能會忽略 `Opacity` 屬性。  
- **圖塊尺寸不正確？** 檢查來源矩形 (`new RectangleF(0f, 0f, 10f, 10f)`) 是否與向量圖塊的尺寸相符。  
- **檔案未儲存？** 再次確認 `dataDir` 指向一個已存在且可寫入的目錄。

## 常見問題

**Q：我可以在 Web 與桌面應用程式中同時使用 Aspose.Page for .NET 嗎？**  
A：可以，該函式庫支援所有 .NET 應用程式類型。

**Q：購買前是否有試用版可供使用？**  
A：當然，您可於 [here](https://releases.aspose.com/) 取得免費試用版。

**Q：我可以在哪裡找到額外的支援或社群討論？**  
A：請前往 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 取得社群與 Aspose 工程師的協助。

**Q：如何取得評估用的臨時授權？**  
A：您可於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q：還有什麼其他 Aspose.Page for .NET 的文件可供參考？**  
A：請於 [here](https://reference.aspose.com/page/net/) 瀏覽完整文件。

---

**最後更新：** 2026-04-03  
**測試版本：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}