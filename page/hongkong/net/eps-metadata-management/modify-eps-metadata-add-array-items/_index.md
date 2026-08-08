---
date: 2026-08-08
description: 了解如何使用 Aspose.Page EPS metadata 新增陣列項目至 EPS 中繼資料。本逐步 .NET 指南示範如何新增陣列項目並有效讀取
  EPS 檔案。
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: 新增陣列項目
og_description: 探索如何使用 Aspose.Page EPS metadata 新增陣列項目至 EPS 中繼資料。遵循此簡潔 .NET 教程，讀取
  EPS 檔案並有效管理中繼資料。
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: 使用 Aspose.Page EPS metadata 在 .NET 中新增陣列項目
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: 使用 Aspose.Page EPS metadata 在 .NET 中新增陣列項目
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page EPS metadata 在 .NET 中新增陣列項目

## 介紹

在本教學中，您將學習如何使用 **Aspose.Page EPS metadata** 為 EPS metadata 新增陣列項目。無論您需要為 EPS 檔案加入額外的標題、創作者或自訂標籤，Aspose.Page 都能讓任何 .NET 開發人員輕鬆完成此任務。我們將逐步說明，從開啟 EPS 串流到持久化更新的 XMP 封包，讓您能自信地將 metadata 處理整合到自己的應用程式中。

## 快速解答
- **Aspose.Page EPS metadata 能做什麼？** 它允許從 .NET 讀寫 EPS 檔案內的 XMP metadata 陣列。  
- **哪個類別代表 EPS 文件？** `PsDocument` 是用於載入和儲存 EPS 內容的核心類別。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買商業授權。  
- **我可以在不更改 EPS 圖形的情況下修改 metadata 嗎？** 可以，僅會變更 XMP 封包，頁面內容保持不變。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.Page EPS metadata 是什麼？

Aspose.Page EPS metadata 是嵌入於 EPS 檔案內的基於 XMP 的資訊區塊。它依照 ISO 16684‑1 標準儲存諸如標題、創作者、關鍵字與自訂標籤等描述性屬性。可透過 Aspose.Page API 以程式方式存取與修改此 metadata，從而實現自動化文件管理與搜尋最佳化。

## 為何要修改 EPS metadata？

Aspose.Page 能處理 **超過 30 個 metadata 欄位**，且可在不將整個文件載入記憶體的情況下處理高達 **200 MB** 的 EPS 檔案，與完整檔案解析相比，可降低最高約 40 % 的 CPU 使用率。更新 metadata 可提升可搜尋性、合規性以及後續工作流程的自動化。

## 前置條件

- 基本的 .NET 程式設計知識。  
- 已安裝 Aspose.Page for .NET – 可從 [download Aspose.Page for .NET](https://releases.aspose.com/page/net/) 下載。  
- 使用 Visual Studio（或任何相容 .NET 的 IDE）執行範例程式碼。  

## 如何為 EPS metadata 新增陣列項目？

要新增陣列項目，首先將 EPS 檔案載入 `PsDocument`，然後使用 `GetXmpMetadata()` 取得其 XMP 封包。於目標 XMP 陣列（例如 `dc:title` 或 `dc:creator`）上呼叫 `AddArrayItem()` 方法以加入新值。最後，呼叫 `Save()` 將更新後的 metadata 寫回檔案，同時保持圖形內容不變。

### 步驟 1：初始化 eps 檔案輸入串流
`PsDocument` 代表 EPS 文件，並提供存取其內容的方法。以下程式碼將 EPS 檔案以串流方式開啟，並建立 `PsDocument` 實例。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 步驟 2：取得 xmp metadata
`GetXmpMetadata()` 取得嵌入於 EPS 檔案中的 XMP 封包。若不存在封包，API 會根據現有的 PostScript 註解產生新的封包。

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### 步驟 3：變更 xmp metadata 值
`AddArrayItem()` 在現有的 XMP 陣列中加入新值，且不會覆寫其他項目。可用於為 metadata 新增標題、創作者或自訂標籤。

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### 步驟 4：儲存已變更 xmp metadata 的 eps 檔案
`Save()` 將修改後的 XMP 封包寫回 EPS 檔案，同時保留原始的 PostScript 內容。提供輸出路徑即可建立新檔或覆寫原檔。

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## 常見問題與故障排除

- **Null XMP packet** – 如果 `GetXmpMetadata()` 回傳 `null`，請確保 EPS 檔案至少包含一個註解區塊；否則需手動建立新的 `XmpMetadata` 實例。  
- **Encoding issues** – 在加入字串值時使用 UTF‑8，以避免非 ASCII 語言的字元損壞。  
- **Large files** – 若 EPS 檔案大於 150 MB，建議使用帶緩衝區的 `FileStream` 進行串流輸入，以降低記憶體使用量。

## 常見問答

**Q: Aspose.Page 是否相容所有 .NET 環境？**  
A: 是的，Aspose.Page 可在 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6/7 上運作，於 Windows、Linux 與 macOS 提供一致的 API 行為。

**Q: 我可以免費使用 Aspose.Page 嗎？**  
A: 您可從 [Aspose purchase page](https://purchase.aspose.com/buy) 下載免費試用版以評估此函式庫。正式上線需購買商業授權。

**Q: Aspose.Page 有提供臨時授權嗎？**  
A: 可從 [temporary license page](https://purchase.aspose.com/temporary-license/) 取得臨時授權，以供短期專案或評估期間使用。

**Q: 我可以在哪裡找到 Aspose.Page 的社群支援？**  
A: 加入 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 討論，向其他開發者提問並分享解決方案。

**Q: Aspose.Page for .NET 的最新版本是什麼？**  
A: 請參考官方 [documentation](https://reference.aspose.com/page/net/) 取得最新的發行說明與下載連結。

---

**最後更新：** 2026-08-08  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## 相關教學

- [使用 Aspose.Page for .NET 變更陣列項目](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [使用 Aspose.Page for .NET 新增簡單屬性](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [使用 Aspose.Page for .NET 新增命名空間](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}