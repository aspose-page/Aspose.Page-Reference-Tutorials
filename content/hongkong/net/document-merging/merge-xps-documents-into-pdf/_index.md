---
title: 使用 Aspose.Page for .NET 將 XPS 文件合併為 PDF
linktitle: 將 XPS 文件合併為 PDF
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 輕鬆將 XPS 文件合併為高品質 PDF。請按照我們的逐步指南獲得流暢的文件轉換體驗。
type: docs
weight: 11
url: /zh-hant/net/document-merging/merge-xps-documents-into-pdf/
---
## 介紹

在不斷發展的文件處理領域，Aspose.Page for .NET 成為將 XPS 文件無縫合併為 PDF 格式的強大工具。本教學將引導您完成整個過程，分解每個步驟，以確保順利有效地執行。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Page for .NET：確保您已安裝 Aspose.Page 程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/page/net/).

- 文檔文件：具有 XPS 文檔 (`input.xps`）在您指定的目錄中準備好。

## 導入命名空間

在您的 .NET 專案中，包含使用 Aspose.Page 所需的命名空間：

```csharp
using Aspose.Page.XPS;
```

此步驟可確保您有權存取文件轉換所需的類別和方法。

## 第 1 步：初始化流

```csharp
//起始時間：3
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
//初始化 PDF 輸出流
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
//初始化XPS輸入流
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // …
}
//結束：3
```

此步驟涉及設定 XPS 和 PDF 檔案的輸入和輸出流。確保使用正確的路徑和檔案名稱。

## 第 2 步：載入 XPS 文檔

```csharp
//起始時間：4
//從流程載入 XPS 文檔
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
//或直接從文件載入 XPS 文件。則不需要 xpsStream。
//XpsDocument 文件 = new XpsDocument(inputFileName, new XpsLoadOptions());
//結束：4
```

在這裡，我們將 XPS 文件載入到`XpsDocument`對象，為進一步處理做好準備。

## 第 3 步：初始化保存選項

```csharp
//起始時間：5
//使用必要的參數初始化選項物件。
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
//結束：5
```

客製化`PdfSaveOptions`根據您的喜好指定對象，指定圖像壓縮、文字壓縮和頁碼等參數。

## 第四步：建立渲染設備

```csharp
//起始時間：6
//建立PDF格式的渲染設備
PdfDevice device = new PdfDevice(pdfStream);
//結束：6
```

這`PdfDevice`是負責將XPS文件渲染為PDF格式的工具。

## 第 5 步：儲存文檔

```csharp
//起始時間：7
document.Save(device, options);
//結束：7
```

最後，使用渲染設備和指定選項儲存文件。

## 結論

恭喜！您已使用 Aspose.Page for .NET 成功將 XPS 文件合併為 PDF。這個無縫過程確保了文件品質和格式的保留。

## 常見問題解答

### 問題 1：我可以將多個 XPS 檔案合併為一個 PDF 嗎？

 A1: 是的，可以。只需調整`PageNumbers`中的參數`PdfSaveOptions`以包含不同 XPS 檔案中的所需頁面。

### Q2：Aspose.Page for .NET 是否有臨時授權？

 A2：是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)用於測試目的。

### Q3：使用Aspose.Page進行文件轉換時，檔案大小有限制嗎？

A3：Aspose.Page for .NET 對檔案大小沒有嚴格的限制，但透過合理的檔案大小可以獲得最佳效能。

### Q4：我可以進一步自訂輸出的 PDF，例如新增浮水印或註解嗎？

A4：是的，Aspose.Page for .NET 提供了廣泛的 PDF 操作功能。檢查進階自訂選項的文件。

### Q5：Aspose.Page for .NET支援跨平台開發嗎？

A5：是的，Aspose.Page for .NET 旨在跨各種平台無縫運作。