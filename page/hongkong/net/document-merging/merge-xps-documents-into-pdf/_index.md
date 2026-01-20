---
date: 2026-01-20
description: 輕鬆在合併 XPS 文件為高品質 PDF 時加入頁碼，使用 Aspose.Page for .NET。請參考我們的逐步指南將 XPS 轉換為
  PDF。
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: 為 PDF 添加頁碼 – 使用 Aspose.Page 合併 XPS 為 PDF
url: /zh-hant/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 PDF 中加入頁碼 – 使用 Aspose.Page 合併 XPS 為 PDF

## Introduction

如果您在合併 XPS 檔案時需要 **在 PDF 中加入頁碼**，Aspose.Page for .NET 能讓整個流程變得輕鬆無憂。在本教學中，我們將示範一個完整、可直接投入生產環境的範例，說明如何將 XPS 文件轉換為高品質 PDF、控制影像壓縮，並自動在最終 PDF 中插入頁碼。完成後，您將擁有一段可重複使用的程式碼片段，隨時可放入任何 C# 專案中。

## Quick Answers
- **Can I add page numbers when merging XPS to PDF?** Yes – the `PdfSaveOptions.PageNumbers` property does exactly that.  
- **Which library handles the conversion?** Aspose.Page for .NET.  
- **Do I need a license for production use?** A valid Aspose.Page license is required; a temporary license is available for testing.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6+.  
- **Is high‑quality image output possible?** Absolutely – set `JpegQualityLevel` to 100 and choose `PdfImageCompression.Jpeg`.

## Prerequisites

在開始教學之前，請先確保已具備以下前置條件：

- Aspose.Page for .NET：請確認已安裝 Aspose.Page 套件，可從 [here](https://releases.aspose.com/page/net/) 下載。  
- 文件檔案：請將 XPS 文件（`input.xps`）放置於指定的目錄中。

## Import Namespaces

在 .NET 專案中，加入使用 Aspose.Page 所需的命名空間：

```csharp
using Aspose.Page.XPS;
```

此步驟確保您能存取文件轉換所需的類別與方法。

## How to add page numbers PDF when merging XPS documents

`PdfSaveOptions.PageNumbers` 集合允許您精確指定哪些頁面（或頁面範圍）會出現在輸出 PDF 中。只要將欲加入的頁碼填入此集合，Aspose.Page 便會自動插入正確的編號。

### Step 1: Initialize Streams

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

此步驟負責為 XPS 與 PDF 檔案設定輸入與輸出串流，請確認路徑與檔名正確無誤。

### Step 2: Load XPS Document

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

在此將 XPS 文件載入 `XpsDocument` 物件，為後續處理做準備。

### Step 3: Initialize Save Options (merge xps to pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

依需求自訂 `PdfSaveOptions` 物件，設定影像壓縮、文字壓縮以及 **頁碼** 的顯示方式。將 `JpegQualityLevel` 設為 100，即可確保 **高品質 PDF 影像**。

### Step 4: Create Rendering Device

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` 為將 XPS 文件渲染成 PDF 格式的核心工具。

### Step 5: Save the Document (c# xps to pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

最後使用渲染裝置與先前設定的選項將文件儲存。輸出的 PDF 會包含選取的頁面，且已自動加入頁碼。

## Why use Aspose.Page for this conversion?

- **Reliability** – Handles complex XPS features without loss of fidelity.  
- **Performance** – Stream‑based processing avoids loading entire files into memory.  
- **Flexibility** – Fine‑grained control over image quality, compression, and page numbering.  
- **Cross‑platform** – Works on Windows, Linux, and macOS with .NET Core.

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **Output PDF is blank** | Verify that the XPS file path is correct and that the file is not corrupted. |
| **Page numbers not appearing** | Ensure `PageNumbers` is set to the correct zero‑based page indices (e.g., `new int[] {1,2,6}`). |
| **Low‑quality images** | Increase `JpegQualityLevel` and choose `PdfImageCompression.Jpeg`. |
| **Large XPS files cause memory pressure** | Process the XPS in smaller chunks or increase the application’s memory limit. |

## Frequently Asked Questions

### Q1: Can I merge multiple XPS files into a single PDF?

A1: Yes, you can. Simply adjust the `PageNumbers` parameter in the `PdfSaveOptions` to include the desired pages from different XPS files, or load each XPS sequentially and call `document.Save` on the same `PdfDevice`.

### Q2: Is a temporary license available for Aspose.Page for .NET?

A2: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing purposes.

### Q3: Are there any limitations on file size when using Aspose.Page for document conversion?

A3: Aspose.Page for .NET does not impose strict limitations on file size, but optimal performance is achieved with reasonably sized files. For very large XPS documents, consider processing them in streams to reduce memory consumption.

### Q4: Can I customize the output PDF further, such as adding watermarks or annotations?

A4: Yes, Aspose.Page for .NET provides extensive features for PDF manipulation. After conversion, you can use the Aspose.PDF library to add watermarks, annotations, or other enhancements.

### Q5: Does Aspose.Page for .NET support cross‑platform development?

A5: Yes, Aspose.Page for .NET is designed to work seamlessly across various platforms, including Windows, Linux, and macOS, when used with .NET Core or .NET 5/6.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}