---
date: 2026-01-12
description: 學習如何使用 Aspose.Page for .NET 儲存 PostScript 檔案並建立 PostScript 文件，並套用多重轉換以產生動態圖形。
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 轉換（.NET）保存 PostScript 檔案
url: /zh-hant/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 儲存 PostScript 檔案與 Aspose.Page 變換（.NET）

## 介紹

在本教學中，您將了解如何在使用 Aspose.Page for .NET 時 **儲存 PostScript 檔案**。我們將逐步示範建立 PostScript 文件、套用平移、縮放、旋轉與斜切等多種變換，最後儲存結果。完成後，您將能熟練以程式方式製作動態圖形，並清楚知道在圖形狀態中何處放置每個變換。

## 快速解答
- **我可以建立什麼？** 一個具備完整功能且已套用變換的 PostScript 文件。  
- **需要哪個函式庫？** Aspose.Page for .NET（可從官方網站下載）。  
- **如何儲存檔案？** 在設定圖形狀態後使用 `PsDocument.Save()`。  
- **可以套用多個變換嗎？** 可以——使用 `Transform` 或連續呼叫來結合它們。  
- **需要授權嗎？** 開發階段可使用免費試用版，正式上線則需商業授權。

## 「儲存 PostScript 檔案」操作是什麼？

儲存 PostScript 檔案即是將您在記憶體中建立的繪圖指令寫入磁碟上的 `.ps` 檔案。之後可由任何 PostScript 直譯器、印表機或檢視器進行渲染。

## 為什麼使用 Aspose.Page for .NET 來建立 PostScript 文件？

Aspose.Page 提供高階、與裝置無關的 API，抽象化低階的 PostScript 語法。您將獲得：

- 強型別的 C# 物件，用於路徑、筆刷與變換。  
- 自動處理圖形狀態堆疊（save/restore）。  
- 完整支援複雜的變換矩陣，無需手動計算。  

## 前置條件

在開始之前，請確保您已具備以下項目：

- **Aspose.Page for .NET** 函式庫已整合至您的專案。請從[下載連結](https://releases.aspose.com/page/net/)取得。  
- 一個可寫入的資料夾，用於儲存產生的 `.ps` 檔案。請在程式碼中將佔位路徑替換為實際目錄。

## 匯入命名空間

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

現在讓我們一步一步探索每個變換。

## 無變換

### 步驟 1：建立輸出串流

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

此程式碼片段會建立一個包含單一橙色矩形的 **PostScript 文件**，並在未套用任何變換的情況下 **儲存 PostScript 檔案**。

## 平移

### 步驟 1：儲存圖形狀態

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

儲存圖形狀態可讓您在移動物件後回復至原始狀態。

### 步驟 2：平移圖形狀態

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

此平移會將此呼叫之後繪製的所有內容向右移動 250 單位。

### 步驟 3：以平移變換填滿矩形

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

現在藍色矩形會出現在橙色矩形右側 250 點的位置。

### 步驟 4：還原圖形狀態

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

還原會將座標系統回復至原始位置，因而後續的繪圖不會受到平移的影響。

## 縮放

> *您可以遵循相同的模式——儲存狀態、套用 `Scale`、繪製，然後還原。*  
> **技巧提示：** 使用非均勻縮放 (`Scale(sx, sy)`) 只在單一方向上拉伸物件。

## 旋轉

> *使用 `Rotate(angle)` 以原點或自訂樞紐點進行旋轉。*  
> **技巧提示：** 在旋轉前先使用 `Translate`，即可繞特定點旋轉。

## 斜切

> *斜切變換 (`Shear(shx, shy)`) 會使形狀傾斜，適用於斜體效果。*

## 複雜變換

> *在進階情境下，建立自訂的 `Matrix` 並傳遞給 `Transform(matrix)`。*  
> 這就是在單一步驟中 **套用多個變換** 的地方。

## 結論

您已學會如何使用 Aspose.Page for .NET **儲存 PostScript 檔案**、**建立 PostScript 文件**，以及 **套用多重變換**。嘗試不同的變換順序、將它們結合，觀察圖形的變化。

## 常見問題

**Q: 如何將多個變換套用到單一物件上？**  
A: 使用 `Transform` 方法，搭配自訂的 `Matrix`，依需求的順序結合平移、縮放、旋轉或斜切。

**Q: 我可以在儲存文件前預覽變換效果嗎？**  
A: 可以——將 `PsDocument` 渲染成影像，或使用 PostScript 檢視器在呼叫 `Save()` 前檢查輸出。

**Q: 是否能對文件中的特定元素套用變換？**  
A: 當然可以。在繪製該元素前先儲存圖形狀態，套用所需變換，繪製後再還原狀態。

**Q: 在處理複雜變換時有性能考量嗎？**  
A: 複雜的矩陣會增加 CPU 負擔。盡量保持變換簡單，且在繪製大量相似物件時重複使用已儲存的狀態。

**Q: 我如何取得支援或協助 Aspose.Page 相關的問題？**  
A: 前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39)尋求社群協助，或直接聯絡 Aspose 支援。

---

**最後更新：** 2026-01-12  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}