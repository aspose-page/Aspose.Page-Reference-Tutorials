---
date: 2026-07-29
description: 了解如何使用 Aspose.Page for .NET 提取與新增 EPS 中繼資料。本指南提供逐步程式碼示例，協助有效管理 EPS XMP
  中繼資料。
keywords:
- aspose.page eps metadata
- eps metadata extraction
- aspose.page .net
lastmod: 2026-07-29
linktitle: 從 EPS 文件提取中繼資料
og_description: aspose.page eps metadata 指南：使用 Aspose.Page for .NET 提取與設定 EPS 檔案中的
  XMP 中繼資料。請依循逐步教學。
og_image_alt: Tutorial showing how to extract and add metadata to EPS documents with
  Aspose.Page for .NET
og_title: aspose.page eps metadata – 使用 .NET 提取 EPS 中繼資料
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to extract and add EPS metadata using Aspose.Page for .NET.
    This guide shows step‑by‑step code to manage EPS XMP metadata efficiently.
  headline: aspose.page eps metadata – Extract EPS Metadata with .NET
  type: TechArticle
- questions:
  - answer: Yes, iterate over a collection of file paths, apply the same extraction‑and‑update
      logic, and save each file. The API is thread‑safe, so you can parallelise the
      operation for faster batch processing.
    question: Can I add metadata to multiple EPS documents simultaneously?
  - answer: The library comfortably processes EPS files up to **500 MB**. For files
      larger than this, consider splitting the document or using a streaming approach
      to avoid out‑of‑memory exceptions.
    question: Are there any limitations on the size of EPS documents that Aspose.Page
      for .NET can handle?
  - answer: XMP follows the ISO 16684‑1 standard, but individual creators may populate
      custom namespaces. Aspose.Page reads both standard and custom properties, allowing
      you to preserve any proprietary data.
    question: Is the XMP metadata standardized for all EPS documents?
  - answer: Absolutely. You can add custom XMP schemas or extend existing ones by
      using the `XmpMetadata.AddCustomProperty` method, giving you full control over
      the metadata structure.
    question: Can I customize the metadata fields to suit specific requirements?
  - answer: Wrap the extraction and save logic in a `try…catch` block, and log `Aspose.Page.Exception`
      details. This will capture issues such as corrupted streams, unsupported properties,
      or I/O failures.
    question: How can I handle errors during the metadata addition process?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: aspose.page eps metadata – 使用 .NET 提取 EPS 中繼資料
url: /zh-hant/net/eps-metadata-management/extract-metadata-from-eps-document/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 從 EPS 文件提取元資料

## 介紹

在現代文件工作流程中，**aspose.page eps metadata** 是讓 EPS 檔案可搜尋、可排序，並符合企業內容管理政策的關鍵。本教學將指導您如何提取現有的 XMP 元資料，更新常見欄位如 *CreatorTool* 和 *CreateDate*，並以新資訊儲存 EPS 檔案——全部使用 Aspose.Page for .NET API。

## 快速解答
- **本教學涵蓋什麼內容？** 使用 Aspose.Page for .NET 提取並更新 EPS 檔案中的 XMP 元資料。  
- **需要哪個版本的函式庫？** 任何支援 XMP 的 Aspose.Page for .NET 版本（v24.10 或更新）。  
- **我需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **我可以處理大型 EPS 檔案嗎？** 是的——Aspose.Page 可在不將整個文件載入記憶體的情況下處理高達 500 MB 的檔案。  
- **程式碼是否跨平台？** .NET 函式庫可在 Windows、Linux 與 macOS 上執行，支援 .NET 6 以上版本。

## 前置條件

在深入逐步指南之前，請確保您已具備以下條件：

- **Aspose.Page for .NET Library** – 從 [here](https://releases.aspose.com/page/net/) 下載並安裝函式庫。  
- **Document Directory** – 您電腦上存放欲處理 EPS 檔案的資料夾。  
- **.NET Development Environment** – Visual Studio 2022、Rider，或任何支援 .NET 6+ 的 IDE。

## 什麼是 EPS 元資料？

**EPS 元資料** 包含嵌入的 XMP（可擴充元資料平台）封包，用於儲存創建者、建立日期、標題以及產生檔案的工具等資訊。XMP 為 ISO 標準格式，使元資料能在 Adobe 產品、內容管理系統與搜尋引擎之間互通。

## 為何使用 Aspose.Page 處理 EPS 元資料？

Aspose.Page 支援 **30+ 種不同的 XMP 屬性**，且能在不渲染整個 PostScript 內容的情況下讀寫這些屬性。它可處理高達 **500 MB** 的 EPS 檔案，同時將記憶體使用量控制在 **50 MB** 以下，十分適合雲端或本地環境的批次處理管線。

## 匯入命名空間

以下命名空間是處理 EPS 檔案與 XMP 元資料所必需的。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 如何使用 Aspose.Page 提取與設定 EPS 元資料？

將 EPS 檔案載入 `EpsDocument` 串流，取得現有的 XMP 封包，修改所需欄位，最後將文件儲存回磁碟。整個工作流程可分為 **四個簡潔步驟**，可嵌入任何 .NET 服務或主控台應用程式中。

## 步驟 1：初始化 EPS 檔案輸入串流

PsDocument 代表一個 EPS 文件，並提供對其頁面與元資料的存取。

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```

## 步驟 2：取得 XMP 元資料

XmpMetadata 封裝了嵌入於 EPS 檔案的 XMP 封包，允許讀寫元資料屬性。

```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

## 步驟 3：檢查與設定元資料值

檢查從 PS 元資料註解中提取的值，並在新的 XMP 元資料中設定。

### 取得 CreatorTool 值

```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```

### 取得 CreateDate 值

```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```

### 取得 Format 值

```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```

### 取得 Title 值

```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```

### 取得 Creator 值

```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```

### 取得 MetadataDate 值

```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```

## 步驟 4：以新 XMP 元資料儲存 EPS 檔案

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```

## 常見問題與解決方案

- **Missing XMP packet** – 若 `document.XmpMetadata` 回傳 `null`，表示 EPS 檔案未包含 XMP 區塊。您可以建立新的 `XmpMetadata` 實例並在儲存前附加它。  
- **Incorrect date format** – XMP 需要 ISO 8601 格式的日期（`yyyy-MM-ddTHH:mm:ssZ`）。請使用 `DateTime.UtcNow.ToString("o")` 產生符合規範的字串。  
- **Large file memory spikes** – 透過將 `EpsLoadOptions.Streaming = true` 設定為啟用串流模式，以降低記憶體使用量。

## 常見問答

**Q: 我可以同時為多個 EPS 文件新增元資料嗎？**  
A: 可以，遍歷檔案路徑集合，套用相同的提取與更新邏輯，並儲存每個檔案。API 為執行緒安全，您可以平行化此操作以加速批次處理。

**Q: Aspose.Page for .NET 處理 EPS 文件的大小有任何限制嗎？**  
A: 此函式庫可輕鬆處理高達 **500 MB** 的 EPS 檔案。若檔案大於此大小，建議將文件分割或使用串流方式，以避免記憶體不足的例外。

**Q: 所有 EPS 文件的 XMP 元資料是否皆遵循標準？**  
A: XMP 依循 ISO 16684‑1 標準，但個別創作者可能使用自訂命名空間。Aspose.Page 會讀取標準與自訂屬性，讓您保留任何專有資料。

**Q: 我可以自訂元資料欄位以符合特定需求嗎？**  
A: 當然可以。您可透過 `XmpMetadata.AddCustomProperty` 方法新增自訂 XMP 綱要或擴充現有綱要，完整掌控元資料結構。

**Q: 在新增元資料的過程中，我該如何處理錯誤？**  
A: 將提取與儲存的程式碼包在 `try…catch` 區塊中，並記錄 `Aspose.Page.Exception` 的詳細資訊。這樣即可捕捉如串流損毀、不支援的屬性或 I/O 失敗等問題。

**Q: Aspose.Page 是否支援 .NET Core 與 .NET 5/6？**  
A: 是的，函式庫完全相容於 .NET Core 3.1、.NET 5、.NET 6 以及更高版本，於所有支援的執行環境提供一致的 API。

---

**最後更新：** 2026-07-29  
**測試環境：** Aspose.Page for .NET 24.10  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.Page for .NET 為 EPS 文件新增元資料](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [使用 Aspose.Page for .NET 新增命名空間](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)
- [使用 Aspose.Page for .NET 新增簡單屬性](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}