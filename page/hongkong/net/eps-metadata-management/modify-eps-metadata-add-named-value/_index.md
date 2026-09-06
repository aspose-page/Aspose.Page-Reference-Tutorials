---
date: 2026-08-08
description: 使用 Aspose.Page for .NET 建立含 XMP 中繼資料的 EPS，並新增命名值。逐步指南，附有程式碼佔位符。
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: 新增命名值
og_description: 使用 Aspose.Page 在 .NET 中建立含 XMP 中繼資料的 EPS。本指南示範如何快速且可靠地為 EPS 檔案新增命名值。
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: 使用 Aspose.Page 建立含 XMP 的 EPS – 新增命名值
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: 使用 Aspose.Page 建立含 XMP 的 EPS – 新增命名值
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立含 XMP 的 EPS – 使用 Aspose.Page 新增命名值

## 介紹

在本教學中，您將學習如何使用 .NET 的 Aspose.Page 函式庫 **建立含 XMP 的 EPS** 中繼資料，並注入命名值。無論您是建立批次處理管線，或是需要以自訂 XMP 標籤豐富 EPS 檔案，下列步驟將從專案設定到保存已修改檔案，完整說明整個流程。Aspose.Page 能處理最多 **500 頁** 的 EPS 文件，且無需將整個檔案載入記憶體，適合高容量情境。

## 快速解答
- **主要目標是什麼？** 在現有 EPS 檔案中新增命名的 XMP 值。  
- **需要哪個函式庫？** Aspose.Page for .NET。  
- **需要授權嗎？** 生產環境需要商業授權；亦提供免費試用版。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **實作需要多長時間？** 基本案例大約需要 10–15 分鐘。

## 如何在 .NET 中建立含 XMP 中繼資料的 EPS？

載入目標 EPS 檔案，取得（或建立）其 XMP 中繼資料物件，加入所需的命名值，最後將文件儲存回磁碟。此工作流程僅需少量方法呼叫，且在所有支援的 EPS 版本中皆能一致運作。此方法亦會保留現有頁面內容與其他 XMP 結構，讓您可安全地連續執行多次中繼資料更新。

## 前置條件

在開始之前，請確保您已具備以下條件：

- 具備 C# 及 .NET 專案結構的基礎知識。  
- Visual Studio 2022（或任何相容的 IDE）。  
- Aspose.Page for .NET 函式庫。若尚未取得，請從 **Aspose.Page for .NET 下載頁面**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)) 下載。

## 匯入命名空間

以下命名空間提供對 Aspose.Page EPS 處理、裝置輸出與 XMP 中繼資料類別的存取。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 步驟 1：初始化 EPS 檔案輸入串流

為來源 EPS 檔案建立 `FileStream`，並實例化 `PsDocument` 物件以操作該文件。

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 步驟 2：取得 XMP 中繼資料

從文件中取得 `XmpMetadata` 物件；此物件代表嵌入的 XMP 封包。

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步驟 3：變更 XMP 中繼資料值

使用 `XmpMetadata` 的 `AddNamedValue` 方法，將新命名值插入指定的 XMP 結構中。

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## 步驟 4：儲存已變更 XMP 中繼資料的 EPS 檔案

將修改後的文件寫入新的 `FileStream` 以完成儲存。

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## 為何使用 Aspose.Page 處理 EPS 中繼資料？

Aspose.Page 支援超過 **50 種 XMP 架構**，且可處理最多 **500 頁** 的 EPS 檔案，同時在一般文件中將記憶體使用量控制在 **30 MB** 以下。此函式庫不依賴外部工具或原生程式碼，確保在 Windows、Linux 與 macOS 環境中皆有一致的行為。

## 常見問題與疑難排解

- **缺少 XMP 封包：** 若 `GetXmpMetadata()` 回傳 `null`，表示 EPS 檔案未包含 XMP 區塊。函式庫會自動建立，但請確認檔案未損毀。  
- **命名空間衝突：** 新增自訂命名值時，請使用唯一的命名空間 URI，以避免與現有架構衝突。  
- **大型檔案：** 若 EPS 檔案大於 200 MB，建議以串流方式輸出，以避免過度記憶體消耗。

## 常見問答

**問：Aspose.Page 是否相容於不同的 EPS 檔案版本？**  
答：Aspose.Page 支援 EPS 3.0 至 3.3 版本，確保與舊版與新版檔案皆具廣泛相容性。

**問：我可以在商業專案中使用 Aspose.Page 嗎？**  
答：可以，生產環境需要商業授權。您可於 **[Aspose.Page 授權購買頁面](https://purchase.aspose.com/buy)** 購買授權。

**問：是否提供免費試用？**  
答：有，您可從 **[Aspose.Page 免費試用下載頁面](https://releases.aspose.com/)** 下載完整功能的試用版。

**問：如何取得支援或加入社群？**  
答：請前往 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 提問與分享經驗。

**問：什麼是暫時授權，該如何取得？**  
答：暫時授權允許您在短期內評估產品。您可於 **[暫時授權申請頁面](https://purchase.aspose.com/temporary-license/)** 申請。

---

**最後更新：** 2026-08-08  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Page for .NET 為 EPS 文件新增中繼資料](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [使用 Aspose.Page for .NET 變更命名值](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [使用 Aspose.Page for .NET 從 EPS 文件擷取中繼資料](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}