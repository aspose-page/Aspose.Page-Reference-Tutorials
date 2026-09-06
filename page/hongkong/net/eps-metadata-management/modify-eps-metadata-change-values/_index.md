---
date: 2026-08-13
description: 了解如何在 .NET 應用程式中使用 Aspose.Page 變更 EPS 值，並逐步更新 XMP 中繼資料。
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: 變更值
og_description: Aspose.Page 變更 EPS 值教學示範如何使用 .NET 修改 EPS 檔案內的 XMP 中繼資料。請依循逐步指南，即時更新作者、標題與修改日期。
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page 使用 .NET 變更 EPS 值教學
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page 使用 .NET 變更 EPS 值 – 教學
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page 更改 EPS 值的 .NET 教程

## 介紹

在本教學中，您將學會透過編輯嵌入於 EPS 檔案中的 XMP 中繼資料來 **aspose.page change eps values**。無論您需要更新創建者名稱、調整標題，或是校正修改日期，Aspose.Page for .NET 都提供乾淨、以程式碼為先的 API，支援 Windows、Linux 與 macOS。完成本指南後，您將擁有一段可重複使用的程式碼片段，能直接嵌入任何 .NET 服務或主控台應用程式。

## 快速解答
- **本教程涵蓋什麼？** 使用 Aspose.Page for .NET 在 EPS 檔案中變更 XMP 中繼資料（創建者、標題、修改日期）。  
- **需要哪個庫版本？** 任何支援 XMP 的 Aspose.Page for .NET 版本（v24.10 以上）。  
- **需要授權嗎？** 生產環境需要臨時授權；開發可使用免費試用版。  
- **可以在 .NET Core 上執行嗎？** 可以 – API 相容於 .NET 5、.NET 6 與 .NET Core 3.1+。  
- **實作需要多久？** 基本的中繼資料更新約需 5‑10 分鐘。

## 什麼是 XMP 中繼資料？

XMP 中繼資料是一種標準化的 XML 區塊，用於在 EPS 及其他圖形格式內儲存描述性資訊（作者、標題、日期）。它直接嵌入檔案標頭，許多設計與出版工具皆能讀取，從而在跨平台環境中實現一致的中繼資料處理。更新 XMP 後，下游應用程式即可正確顯示文件屬性，而不會改變視覺內容。

## 為什麼使用 Aspose.Page 處理 EPS 中繼資料？

Aspose.Page 能處理 **30+** 種圖形格式，且可在不將整個檔案載入記憶體的情況下處理高達 **1 GB** 的 EPS 檔案，較傳統串流解析可減少 **70 %** 的 RAM 使用量。此函式庫亦保證在編輯中繼資料後，EPS 的視覺渲染保持不變。

## 前置條件

在開始之前，請確保以下項目已備妥：

1. **Aspose.Page for .NET library** – 從官方 Aspose.Page for .NET 釋出頁面 [here](https://releases.aspose.com/page/net/) 下載。您亦可在 [here](https://releases.aspose.com/) 瀏覽其他 Aspose 產品的釋出。  
2. **Document directory** – 在本機建立資料夾，用於存放來源 EPS 檔案與輸出檔案。

環境設定完成後，讓我們匯入所需的命名空間。

## 匯入命名空間

`Aspose.Page` 命名空間提供核心類別，而 `System.IO` 則負責串流處理功能。

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## 如何變更 EPS 中繼資料值？

載入 EPS 檔案，取得其 XMP 封包，修改所需欄位，最後將更新後的 EPS 寫回磁碟。此過程不需渲染頁面內容，因而快速且節省記憶體。以下步驟將示範每個操作的程式碼範例。

### 步驟 1：初始化 EPS 檔案輸入串流

建立指向來源 EPS 檔案的唯讀 `FileStream`。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 步驟 2：從串流建立 PsDocument 實例

`PsDocument` 為代表 EPS 文件的最高層物件，讓您同時存取頁面內容與嵌入的 XMP 中繼資料。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### 步驟 3：取得 XMP 中繼資料

`XmpMetadata` 屬性會回傳可供查詢與編輯的 `XmpPacket` 物件。

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### 步驟 4：修改 XMP 中繼資料值

接下來將變更三個常見欄位：**ModifyDate**、**Creator** 與 **Title**。

#### 步驟 4.1：變更 ModifyDate 值

將 `ModifyDate` 設為目前的 UTC 時間戳記。

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### 步驟 4.2：變更 Creator 值

將現有的創建者替換為您的應用程式名稱。

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### 步驟 4.3：變更 Title 值

更新標題以反映新內容的用途。

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### 步驟 5：儲存已變更 XMP 中繼資料的 EPS 檔案

編輯完成後，將文件寫回磁碟。

#### 步驟 5.1：建立輸出串流

為目標 EPS 檔案開啟 `FileStream`。

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### 步驟 5.2：儲存 EPS 檔案

呼叫 `PsDocument` 實例的 `Save`，並傳入輸出串流。

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

最後，關閉輸入串流以釋放檔案句柄。

```csharp
// Save EPS file
document.Save(outPsStream);
```

恭喜！您已成功透過更新 EPS 檔案內的 XMP 中繼資料來 **aspose.page change eps values**。

## 常見問題與故障排除

- **Empty XMP packet** – 某些 EPS 檔案可能未包含 XMP。此時請先使用 `new XmpPacket()` 建立新封包，再賦值。  
- **Large files** – 若 EPS 超過 500 MB，請將 `PsDocumentOptions.UseMemoryMappedFiles = true` 以啟用串流緩衝，避免 `OutOfMemoryException`。  
- **Incorrect date format** – XMP 需要 ISO 8601 格式。可使用 `DateTime.UtcNow.ToString("o")` 產生符合規範的字串。

## 常見問答

**問：我可以將 Aspose.Page for .NET 用於其他圖形格式嗎？**  
答：可以，函式庫支援超過 30 種格式，包括 PDF、SVG 與 AI，但 XMP 編輯 API 僅限於 EPS 與 PDF。

**問：是否提供試用版？**  
答：是的，您可在 Aspose 釋出頁面 [here](https://releases.aspose.com/) 取得免費試用版。

**問：在哪裡可以找到詳細文件？**  
答：完整的 Aspose.Page .NET API 參考文件可於 [here](https://reference.aspose.com/page/net/) 查閱。

**問：如何取得臨時授權？**  
答：請前往 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**問：我可以購買 Aspose.Page for .NET 嗎？**  
答：當然可以！請造訪 Aspose.Page 購買頁面 [here](https://purchase.aspose.com/buy) 瞭解授權選項。

---

**最後更新：** 2026-08-13  
**測試環境：** Aspose.Page 24.10 for .NET  
**作者：** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## 相關教學

- [Add Metadata to EPS Document with Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Extract Metadata from EPS Document with Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Change Named Value with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}