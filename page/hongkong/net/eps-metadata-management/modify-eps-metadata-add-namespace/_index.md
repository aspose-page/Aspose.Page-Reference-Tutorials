---
date: 2026-08-08
description: 了解如何使用 Aspose.Page for .NET 初始化 Aspose.Page 文件、加入 XML 命名空間，以及在 EPS 檔案中修改
  XMP 中繼資料。
keywords:
- initialize aspose page document
- c# add xml namespace
- open eps file stream
- how to add xmp namespace
lastmod: 2026-08-08
linktitle: 新增命名空間
og_description: 使用 Aspose.Page for .NET 初始化 Aspose.Page 文件、加入 XML 命名空間，並編輯 EPS 檔案中的
  XMP 中繼資料。遵循簡潔的步驟與程式碼片段。
og_image_alt: Guide showing how to add namespace to EPS metadata using Aspose.Page
  for .NET
og_title: 在 .NET 中初始化 Aspose.Page 文件並新增命名空間
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to initialize Aspose.Page document, add an XML namespace,
    and modify XMP metadata in EPS files using Aspose.Page for .NET.
  headline: Initialize Aspose.Page document and add namespace in .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for .NET works with .NET Framework 4.5+, .NET Core 3.1+,
      and .NET 5/6+.
    question: Is Aspose.Page compatible with all versions of .NET?
  - answer: Absolutely. Retrieve the `XmpMetadata` object and read its properties
      without invoking `SetProperty` or `AddNamespace`.
    question: Can I extract metadata without modifying it?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support or assistance?
  - answer: Yes, you can explore a free trial of Aspose.Page on the [Aspose.Page free
      trial](https://releases.aspose.com/) page.
    question: Is there a free trial available for Aspose.Page?
  - answer: Obtain a temporary license on the [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)
      page for testing purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- Aspose.Page
- c# document processing
title: 在 .NET 中初始化 Aspose.Page 文件並新增命名空間
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 初始化 Aspose.Page 文件並在 .NET 中新增命名空間

## 介紹

在現代 .NET 開發中，**initialize aspose page document** 通常是需要以程式方式處理 EPS 檔案的第一步。Aspose.Page for .NET 為您提供完整的 XMP 中繼資料控制，讓您可以新增自訂 XML 命名空間、編輯現有屬性，並將變更儲存回檔案。本教學將逐步說明每個細節——從匯入正確的命名空間到持久化已修改的 EPS 檔案——讓您能自信地將中繼資料管理整合到工作流程中。

## 快速解答
- **第一行程式碼是什麼？** 建立 `new Document("yourfile.eps")` 以載入 EPS 檔案。
- **哪個方法可以新增命名空間？** 使用 `XmpMetadata.AddNamespace(prefix, uri)`。
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買授權。
- **可以串流大型 EPS 檔案嗎？** 可以——使用 `FileStream` 開啟檔案，避免一次將整個檔案載入記憶體。
- **此方式相容於 .NET 6+ 嗎？** 完全相容；Aspose.Page 支援 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 6+。

## 什麼是初始化 Aspose.Page 文件？

`Document` 類別代表已載入記憶體的 EPS 檔案。使用 `new Document("file.eps")` 載入檔案後，您即可直接存取其頁面、圖形與 XMP 中繼資料，並可讀取或修改文件的任何部分。此類別同時提供操作 XMP 中繼資料與頁面內容的方法。

## 為何要在 EPS 中加入 XML 命名空間？

加入自訂 XML 命名空間可擴充中繼資料結構，讓您在標準 XMP 欄位之外儲存專屬資訊。Aspose.Page 支援 **50+** 個 XMP 屬性，且可處理 **200+** 頁的檔案而不需將整個文件全部載入 RAM，這意味著更快的處理速度與更低的記憶體使用量。

## 前置條件

1. **Aspose.Page for .NET 套件** – 從 [Aspose.Page documentation](https://reference.aspose.com/page/net/) 下載。  
2. **.NET 開發環境** – Visual Studio 2022、Rider，或任何支援 .NET 6+ 的 IDE。

在開始之前，請確保已在專案中參考此套件（透過 NuGet 或直接加入 DLL）。

## 匯入命名空間

使用 Aspose.Page 前，必須匯入提供 `Document` 與 XMP 類別的核心命名空間。

您需要：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.XMP;
using System.IO;
```

這些匯入讓您能存取 `Document`、`XmpMetadata` 以及串流處理相關類別，以完成以下步驟。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 步驟 1：初始化您的專案

在要放置程式碼的來源檔案中開啟，先建立 `Document` 類別的實例，以 **initialize aspose page document** 供後續操作使用。`Document` 類別代表 EPS 文件，並提供對其內容與中繼資料的存取。

```csharp
var epsDocument = new Document("sample.eps");
```

此行程式碼將 EPS 檔案載入 `epsDocument` 物件，使後續的 API 呼叫皆可執行。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## 步驟 2：開啟 EPS 檔案串流

`FileStream` 類別提供讀寫檔案的串流，能避免將整個 EPS 檔案一次載入記憶體。

```csharp
using (FileStream fs = new FileStream("sample.eps", FileMode.Open, FileAccess.ReadWrite))
{
    // Stream is ready for XMP operations
}
```

在生產環境工作負載中，建議使用 `open eps file stream` 模式。

```csharp
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## 步驟 3：取得 XMP 中繼資料

`XmpMetadata` 類別封裝 EPS 文件的 XMP 中繼資料。

```csharp
XmpMetadata xmp = epsDocument.XmpMetadata;
```

現在您已擁有可操作的 `xmp` 物件，內含所有目前的中繼資料項目。

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步驟 4：變更 XMP 中繼資料

`AddNamespace` 方法可註冊帶有前置詞與 URI 的新 XML 命名空間，`SetProperty` 方法則為中繼資料屬性指派值。

```csharp
// Define a new namespace
string prefix = "myNs";
string uri = "http://mycompany.com/metadata";

// Register the namespace with the XMP metadata object
xmp.AddNamespace(prefix, uri);

// Add a custom property under the new namespace
xmp.SetProperty($"{prefix}:Author", "John Doe");
```

`AddNamespace` 呼叫會註冊前置詞，而 `SetProperty` 會使用該前置詞儲存對應的值。

```csharp
// Add new XML namespace "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Add new string property in the new namespace.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

## 步驟 5：儲存 EPS 檔案

`Save` 方法將文件與其中繼資料寫回檔案系統。

```csharp
epsDocument.Save("sample-updated.eps");
```

完成此步驟後，EPS 檔案即包含新加入的命名空間與屬性。

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

## 常見問題與疑難排解

- **命名空間已存在** – 若 `AddNamespace` 拋出錯誤，表示前置詞已被註冊。請改用其他前置詞，或使用 `xmp.GetNamespaceUri(prefix)` 取得已存在的 URI。
- **檔案被其他程序鎖定** – 在呼叫 `Save` 前，確保 `FileStream` 已在 `using` 區塊中正確釋放。
- **中繼資料未持久化** – 確認 EPS 檔案實際支援 XMP（大多數現代 EPS 都支援）。舊版檔案可能需要重新產生。

## 常見問答

**Q: Aspose.Page 是否相容所有 .NET 版本？**  
A: 是，Aspose.Page for .NET 支援 .NET Framework 4.5+、.NET Core 3.1+，以及 .NET 5/6+。

**Q: 我可以在不修改的情況下擷取中繼資料嗎？**  
A: 當然可以。取得 `XmpMetadata` 物件後，只讀取其屬性而不呼叫 `SetProperty` 或 `AddNamespace` 即可。

**Q: 我可以在哪裡取得更多支援或協助？**  
A: 前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 取得社群支援與討論。

**Q: 是否提供 Aspose.Page 的免費試用？**  
A: 有，您可於 [Aspose.Page free trial](https://releases.aspose.com/) 頁面探索免費試用版。

**Q: 如何取得 Aspose.Page 的臨時授權？**  
A: 可在 [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/) 頁面取得測試用的臨時授權。

---

**最後更新：** 2026-08-08  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Add Metadata to EPS Document with Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Add Simple Properties with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Extract Metadata from EPS Document with Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}