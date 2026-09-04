---
date: 2026-06-30
description: 了解如何使用 Aspose.Page for .NET 在幾個簡易步驟中建立 XPS 文件 .NET 並新增 Image Filled Glyph
  或 Foreign Image。
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: 新增 Image Filled Glyph 與 Foreign Image
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: 建立 XPS 文件 .NET – 使用 Aspose.Page 新增 Image Filled Glyph 與 Foreign Image
url: /zh-hant/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 XPS 文件 .NET – 使用 Aspose.Page 新增影像填充字形與外部影像

## 介紹

在 .NET 開發中，**create XPS document .NET** 任務相當常見，尤其在需要高品質、與解析度無關的圖形時。Aspose.Page for .NET 讓這變得簡單，並且可以使用影像填充的字形或從其他 XPS 文件中提取影像來豐富 XPS 檔案。完成本教學後，您將會知道如何建立兩個 XPS 文件、使用影像填充字形，並在文件之間重複使用這些影像——非常適合產生發票、證書或任何視覺豐富的輸出。

## 快速答覆
- **Aspose.Page 支援什麼？** 超過 25 種影像格式，且能在不完整載入記憶體的情況下處理高達 500 MB 的 XPS 檔案。  
- **加入影像填充字形需要多少行程式碼？** 僅兩行：建立 `ImageBrush` 並指派給 `Glyph`。  
- **正式環境需要授權嗎？** 需要，商業授權會移除評估水印。  
- **相容的 .NET 版本有哪些？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **可以重複使用另一個 XPS 的字型嗎？** 當然可以——您可以將第一個文件的字型集合匯入到第二個文件中。

## 如何使用 Aspose.Page .NET 建立 XPS 文件？

載入 Aspose.Page 程式庫，實例化 `XpsDocument`、新增頁面，然後呼叫 `Save`——這就是三行簡潔語句完成的完整工作流程。API 會自動處理頁面大小、DPI 與資源管理，您不必自行處理低階 XPS 結構。此方法可從單頁傳單擴展至數百頁的目錄。

## 前置條件

- **Aspose.Page for .NET** – 從 [here](https://releases.aspose.com/page/net/) 下載。  
- **.NET IDE** – Visual Studio、Rider，或安裝 C# 擴充功能的 VS Code。  
- **文件資料夾** – 在程式碼範例中，我們將其稱為 **Your Document Directory**。

## 匯入命名空間

`Aspose.Page.XPS` 命名空間提供核心 XPS 文件類別，而 `Aspose.Page.XPS.XpsModel` 包含字形與筆刷等模型元素。請在檔案頂部匯入它們：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 什麼是影像填充字形？

字形是一種向量形狀，可使用純色、漸層或影像筆刷來繪製。當您套用 `ImageBrush` 時，字形的內部會以提供的影像繪製，從而在不將整頁光柵化的情況下實現複雜的視覺效果。

## 步驟 1：建立第一個 XPS 文件

`XpsDocument` 代表一個 XPS 套件，是建立與儲存 XPS 檔案的入口點。首先建立將容納影像填充字形的第一個 XPS 文件。

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## 步驟 2：將字形加入第一個文件

`XpsGlyphs` 定義一組可放置於頁面的字形（文字字元）。將字形加入第一個文件，並指定字型、大小、樣式與位置。

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 步驟 3：使用影像筆刷填充字形

`ImageBrush` 以影像繪製區域，允許圖案或圖片填滿形狀。使用來自資料目錄的影像，以影像筆刷填充字形。

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## 步驟 4：建立第二個 XPS 文件

`XpsDocument` 用於建立可包含頁面、資源與內容的新 XPS 檔案。現在，建立將納入第一個文件字形的第二個 XPS 文件。

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## 步驟 5：使用第一個文件的字型加入字形

`Font` 代表在 XPS 文件中用來呈現文字的字型。將字形加入第二個文件，使用從第一個文件提取的字型。透過共用字型集合，可降低檔案大小並確保視覺一致性。

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## 步驟 6：從第一個文件的填充建立影像筆刷

`ImageBrush` 可以從現有的填充建立，以在多個文件間重複使用相同的影像。從第一個文件的填充建立影像筆刷，並用於第二個文件的字形填充。此「外部影像」技術讓您在不複製來源檔案的情況下重複使用圖稿。

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## 步驟 7：儲存文件

`Save` 將 XPS 套件寫入檔案，並嵌入所有資源。將第一與第二個 XPS 文件儲存至輸出資料夾。`Save` 方法寫入 XPS 套件，嵌入所有資源並保留影像填充字形。

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## 常見問題與解決方案

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **影像未顯示在字形內** | `ImageBrush` 使用了錯誤的 URI，或影像尺寸超過字形範圍。 | 確認影像路徑，必要時設定 `ImageBrush.Stretch = Stretch.Uniform`。 |
| **第二個文件缺少字型** | 字型資源未從第一個 XPS 匯出。 | 在加入字形前使用 `firstDoc.Fonts.SaveTo(secondDoc.Fonts)`。 |
| **大型檔案效能下降** | 為每個字形載入大型影像至記憶體。 | 重複使用單一 `ImageBrush` 實例於所有字形，或在使用前將影像降採樣。 |

## 常見問答

### Q1：我可以使用不同的影像格式來填充字形嗎？

A1：可以，Aspose.Page 支援 PNG、JPEG、BMP、GIF、TIFF 等等——總計超過 25 種格式。

### Q2：我該如何進一步自訂字形的外觀？

A2：可探索 `Glyph.Stroke`、`Glyph.FillOpacity`、`Glyph.Transform` 等屬性，以調整輪廓、透明度與旋轉。

### Q3：Aspose.Page 適合處理大量文件集嗎？

A3：絕對適合。此函式庫使用串流處理數百頁的 XPS 檔案，即使是 500 頁的文件，記憶體使用量也維持在 100 MB 以下。

### Q4：我可以對單一字形套用不同樣式嗎？

A4：可以，每個 `Glyph` 實例都有自己的 `Fill`、`Stroke` 與 `Transform` 屬性，允許對單一字形進行樣式設定。

### Q5：使用 Aspose.Page 相較於其他 XPS 工具有哪些好處？

A5：Aspose.Page 支援 25 種以上的影像格式，能在不完整載入記憶體的情況下處理高達 500 MB 的檔案，並提供 100 % .NET 原生 API——免除 COM 互操作或外部工具的需求。

---

**最後更新：** 2026-06-30  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [建立 XPS 文件 – Aspose.Page for .NET](/page/net/document-creation/)
- [將影像新增至 XPS 文件 – Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [新增字形複本並變更顏色 – Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}