---
date: 2026-07-19
description: 了解如何在 .NET 中建立 XPS 文件，並使用 Aspose.Page for .NET 以簡明的逐步指南新增矩形。
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: 在 XPS 文件中新增矩形
og_description: 快速建立 XPS 文件 .NET。本教學示範如何使用 Aspose.Page for .NET 為 XPS 檔案新增矩形，提供清晰的程式碼與技巧。
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: 建立 XPS 文件 .NET – 使用 Aspose.Page 新增矩形
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: 建立 XPS 文件 .NET – 使用 Aspose.Page 新增矩形
url: /zh-hant/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 XPS 文件 .NET – 使用 Aspose.Page 新增矩形

## 介紹

在本教學中，您將學習如何 **建立 XPS 文件 .NET** 並使用 Aspose.Page for .NET 在其中繪製矩形。無論您是在構建報表引擎、可列印的發票，或是自訂圖形層，程式化產生 XPS 檔案的能力都能讓您完整掌控版面配置與精確度。依照以下步驟操作，即可在數分鐘內取得可直接使用的 XPS 檔案。

## 快速解答
- **主要目標是什麼？** 建立 XPS 文件 .NET 並新增矩形形狀。  
- **需要哪個函式庫？** Aspose.Page for .NET（可從官方網站下載）。  
- **測試是否需要授權？** 免費試用版可用於開發；正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.6+、.NET Core 3.1+、.NET 5/6/7。  
- **實作需要多久？** 基本矩形大約 5‑10 分鐘即可完成。

## Aspose.Page for .NET 是什麼？
Aspose.Page for .NET 是一套高效能、完全受管理的 API，讓開發人員能以程式方式建立、編輯與轉譯 XPS（XML Paper Specification）文件，且不需依賴外部元件。它提供豐富的物件模型，可繪製圖形、文字與影像，並支援色彩管理、壓縮與 PDF 轉換等進階功能，適用於各種文件產生情境。

## 為何使用 Aspose.Page 來建立 XPS 文件 .NET？
Aspose.Page 支援 **30 多項 XPS 功能**——包括向量圖形、文字版面配置與色彩管理，且可產生最高 **500 MB** 的檔案而無需將整個文件載入記憶體。此量化能力確保即使在大規模列印工作時亦能保持流暢效能。

## 前置條件

在開始本教學之前，請確保已具備以下前置條件：

1. Aspose.Page for .NET 函式庫：確保已在開發環境中安裝 Aspose.Page for .NET 函式庫。您可於 [此處](https://releases.aspose.com/page/net/) 下載。  
2. 文件目錄：設定一個用於儲存 XPS 文件的資料夾。

## 匯入命名空間

在您的 .NET 應用程式中，加入必要的命名空間以使用 Aspose.Page 功能。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 如何在 .NET 中為 XPS 文件新增矩形？

載入 XPS 文件，建立 `Graphics` 物件，定義具有所需尺寸的 `RectangleF`，然後呼叫 `DrawRectangle`。此流程可於單行程式碼中繪製矩形，且會自動處理 DPI 縮放。對於一般 A4 大小的頁面，200 × 100 pt 的矩形會置中顯示，無需額外計算。

### 步驟 1：設定文件目錄

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### 步驟 2：建立新 XPS 文件

`XpsDocument` 類別代表您正在建立的 XPS 檔案，並提供加入頁面、圖形及其他資源的方法。

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### 步驟 3：新增矩形

`XpsPath` 定義 XPS 文件中的可繪製路徑物件，讓您設定幾何形狀、筆畫、填色及其他視覺屬性。

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### 步驟 4：儲存文件

`Save` 方法將構建好的 XPS 文件寫入磁碟上指定的檔案路徑。

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

恭喜！您已成功使用 Aspose.Page for .NET 為 XPS 文件新增矩形。

## 常見問題與技巧

- **缺少字型：** 確保您引用的字型已安裝於伺服器上；否則 Aspose.Page 會使用預設字型取代，可能會影響版面配置。  
- **大型文件：** 產生超過 200 MB 的檔案時，建議呼叫 `document.SaveOptions.Compress = true` 以降低記憶體使用量。  
- **座標系統：** XPS 使用點（1/72 英吋）。若使用螢幕尺寸，請記得將像素轉換為點。

## 常見問答

**Q: Aspose.Page 是否相容於所有 .NET 應用程式？**  
A: 是，Aspose.Page 可無縫運作於桌面、Web 與雲端 .NET 應用程式。

**Q: 在哪裡可以找到 Aspose.Page for .NET 的文件？**  
A: 完整的 API 參考可於 [此處](https://reference.aspose.com/page/net/) 取得。

**Q: 購買前可以免費試用 Aspose.Page for .NET 嗎？**  
A: 可以，您可於 [此處](https://releases.aspose.com/) 取得免費試用。

**Q: 如何取得 Aspose.Page for .NET 的臨時授權？**  
A: 請前往 [此連結](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 在哪裡可以尋求社群支援或提問有關 Aspose.Page for .NET 的問題？**  
A: 請造訪 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得社群支援。

---

**最後更新：** 2026-07-19  
**測試環境：** Aspose.Page for .NET 24.9  
**作者：** Aspose

## 相關教學

- [建立 XPS 文件（使用 Aspose.Page for .NET）](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – 繪製圖形](/page/net/drawing-shapes/)
- [為 XPS 文件新增文字（使用 Aspose.Page for .NET）](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}