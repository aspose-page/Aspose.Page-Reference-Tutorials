---
title: 使用 Aspose.Page for .NET 將 XPS 轉換為 PDF
linktitle: 將 XPS 轉換為 PDF
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page 在 .NET 中輕鬆將 XPS 轉換為 PDF。下載庫、瀏覽文件並獲得免費試用。
type: docs
weight: 11
url: /zh-hant/net/document-conversion/convert-xps-to-pdf/
---
## 介紹

在本教學中，我們將深入研究使用強大的 Aspose.Page for .NET 函式庫將 XPS（XML 紙張規格）文件轉換為 PDF（便攜式文件格式）的過程。 Aspose.Page for .NET 提供了一組強大的功能來處理 XPS 文件，使開發人員能夠透過各種自訂選項將其無縫轉換為 PDF 格式。

## 先決條件

在我們開始此轉換之旅之前，請確保您具備以下先決條件：

-  Aspose.Page for .NET 函式庫：確保您的開發環境中安裝了 Aspose.Page for .NET 函式庫。您可以從[Aspose.Page 文檔](https://reference.aspose.com/page/net/).

- 開發環境：使用 Visual Studio 或任何其他相容的 IDE 設定 .NET 開發環境。

- XPS 文件：準備要轉換為 PDF 的 XPS 文件。這可能是儲存在指定目錄中的範例 XPS 檔案。

## 導入命名空間

在深入研究程式碼之前，讓我們導入必要的命名空間，以使 Aspose.Page for .NET 功能可以在我們的程式碼中存取：

```csharp
using Aspose.Page.XPS;
```

## 步驟1：初始化文檔目錄

```csharp
string dataDir = "Your Document Directory";
```

將「您的文件目錄」替換為包含 XPS 文件的目錄的路徑。

## 步驟 2：初始化 PDF 和 XPS 串流

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

開啟輸出 PDF 檔案和輸入 XPS 檔案的流。確保您設定了適當的文件路徑。

## 第 3 步：載入 XPS 文檔

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

使用 Aspose.Page for .NET 程式庫載入 XPS 文件。

## 步驟 4：初始化 PDF 儲存選項

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

設定 PDF 儲存選項，包括 JPEG 品質等級、影像壓縮、文字壓縮和要包含的特定頁碼等參數。

## 第5步：建立PDF渲染設備

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

使用 Aspose.Page for .NET 函式庫建立 PDF 格式的渲染裝置。

## 第 6 步：將文件儲存為 PDF

```csharp
document.Save(device, options);
```

使用指定的渲染設備和選項將 XPS 文件儲存為 PDF。

## 結論

恭喜！您已使用 Aspose.Page for .NET 成功將 XPS 文件轉換為 PDF。這個多功能庫為開發人員提供了強大的工具集，可以輕鬆處理各種文件格式。

## 常見問題解答

### 問題 1：我可以使用 Aspose.Page for .NET 將多個 XPS 檔案轉換為單一 PDF 嗎？

A1：是的，您可以循環瀏覽多個 XPS 文件，並按照相同的步驟將它們合併為單一 PDF。

### Q2：Aspose.Page for .NET 是否支援其他輸出格式？

A2：是的，Aspose.Page for .NET 支援各種輸出格式，包括 TIFF、JPEG、PNG 等。

### Q3：如何自訂轉換後的PDF文件的外觀？

A3：您可以調整選項物件參數，例如影像壓縮和文字壓縮，以獲得所需的外觀。

### Q4：Aspose.Page for .NET 有試用版嗎？

 A4：是的，您可以透過取得免費試用版來探索 Aspose.Page for .NET 的功能[這裡](https://releases.aspose.com/).

### 問題 5：在哪裡可以獲得 Aspose.Page for .NET 的社群支援？

 A5：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)供社區討論和支持。