---
date: 2026-03-26
description: 學習如何在 .NET 中建立 PostScript 文件，並使用 Aspose.Page 加入透明圖像。本分步指南涵蓋先決條件、程式碼與技巧。
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: 使用 .NET 及透明圖片建立 PostScript 文件 (Aspose.Page)
url: /zh-hant/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用透明圖像建立 PostScript 文件 .NET（Aspose.Page）

## 簡介

在本教學中，您將學習 **如何建立 PostScript 文件 .NET**，並使用 Aspose.Page for .NET 嵌入透明 PNG。加入透明圖像可讓您打造更豐富、分層的圖形——非常適合在 PS 檔案中加入浮水印、覆蓋層或 UI 模型。我們將逐步說明，從環境設定到渲染不透明與透明圖像的完整流程。

## 快速回答
- **Aspose.Page 的功能是什麼？** 它提供完整的 API，能在 .NET 中產生、編輯與渲染 PostScript (PS) 與 XPS 文件。  
- **可以加入透明 PNG 嗎？** 可以——使用 `DrawTransparentImage` 來控制不透明度。  
- **支援哪些 .NET 版本？** 支援所有近期的 .NET Framework、.NET Core 以及 .NET 5/6 版本。  
- **需要授權嗎？** 免費試用可用於評估；正式上線需購買授權。  
- **實作大約需要多久？** 基本範例約 10‑15 分鐘即可完成。

## 先決條件

在開始之前，請確保您已擁有：

- **Aspose.Page for .NET** – 從 [download link](https://releases.aspose.com/page/net/) 下載。  
- 用於存放 PS 文件與欲嵌入圖像的資料夾。  
- 一個透明 PNG（例如 `mask1.png`），將作為透明圖層使用。

## 匯入命名空間

首先，匯入我們需要的類別所在的命名空間。這樣即可存取 PS 文件模型、圖形工具以及基本的 .NET 繪圖類型。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟 1：設定文件目錄

定義來源圖像與輸出 PS 檔案的路徑。請將佔位符替換為您機器上的實際路徑。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## 步驟 2：建立 PostScript 文件的輸出串流

我們會將產生的 PS 內容寫入檔案串流。此串流稍後會傳遞給 `PsDocument` 建構子。

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## 步驟 3：設定儲存選項與背景顏色

設定 `PsSaveOptions` 以定義檔案的儲存方式。當您希望在透明元素後面有實心畫布時，設定背景顏色會很有幫助。

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## 步驟 4：建立新的 1 頁 PS 文件

使用上述的串流與選項建立文件。`false` 參數告訴 Aspose.Page 不要自動關閉串流。

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 5：寫入 Graphics Save 與 Translate

在繪製之前，我們先保存當前的圖形狀態，並平移原點，使圖像能出現在頁面上期望的位置。

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## 如何在 PostScript 文件中加入透明圖像

### 步驟 6：加入不透明的 RGB 圖像

首先將相同的 PNG 以普通不透明圖像加入。此步驟用來展示稍後套用透明度時的視覺差異。

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### 步驟 7：加入透明圖像

現在使用 `DrawTransparentImage` 以指定的不透明度值繪製 PNG。第三個參數（`255`）代表完全不透明；數值越低透明度越高。這裡就是 **設定圖像透明度 .NET** 的地方。

> **專業提示：** 若要讓圖像呈現 50 % 透明，請傳入 `128` 而非 `255`。

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

## 步驟 8：寫入 Graphics Restore 並關閉頁面

繪製完成後，恢復先前的圖形狀態並關閉頁面，以完成內容的定稿。

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## 步驟 9：儲存文件

最後，將 PS 檔案寫入磁碟。

```csharp
document.Save();
```

透過上述步驟，您已 **建立 PostScript 文件 .NET**，其中同時包含不透明與透明圖像，展示了如何使用 Aspose.Page **在 C# 中繪製透明圖像**。

## 為何使用 Aspose.Page 來實作透明效果？

- **完整控制** 圖形狀態、矩陣與不透明度等級。  
- **無外部相依**——所有功能皆在純 .NET 程式碼內執行。  
- **跨平台** 支援，可在 Windows、Linux 或 macOS 上產生 PS 檔案。

## 常見問題與疑難排解

| 問題 | 解決方案 |
|------|----------|
| 即使使用 `DrawTransparentImage` 圖像仍顯示為完全不透明 | 確認第三個參數（alpha 值）小於 `255`。 |
| PS 檔案顯示空白頁面 | 檢查是否已設定背景顏色，且串流路徑正確。 |
| 出現 “File not found” 例外 | 再次確認 `dataDir` 路徑，以及 `mask1.png` 是否存在於該資料夾。 |

## 常見問答

**Q: 除了 PNG，還能使用其他圖像格式來做透明嗎？**  
A: 可以——Aspose.Page 支援 PNG、GIF 與 TIFF 的透明渲染。

**Q: Aspose.Page 是否相容最新的 .NET 框架？**  
A: 完全相容。此函式庫會定期更新，支援 .NET 6、.NET 7 以及更新版本。

**Q: 能否對已有的 PS 文件套用透明效果？**  
A: 能。使用 `PsDocument` 開啟文件，新增頁面或修改既有頁面，然後使用相同的 `DrawTransparentImage` 方法即可。

**Q: 與一般圖形函式庫相比，Aspose.Page 有何優勢？**  
A: 它是專為 PS/XPS 設計的，提供對向量圖形、字型與圖像處理的精確控制，且不需要完整的渲染引擎。

**Q: 透明度的設定有上限嗎？**  
A: 沒有。您可以指定任意 alpha 值，範圍從 `0`（完全透明）到 `255`（完全不透明）。

## 結論

我們示範了如何 **建立 PostScript 文件 .NET**，並使用 Aspose.Page 同時嵌入不透明與透明圖像。此技巧可開啟更高階的文件版面配置、浮水印與分層圖形的可能性，全部以 C# 程式碼自動產生。

---

**最後更新：** 2026-03-26  
**測試環境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}