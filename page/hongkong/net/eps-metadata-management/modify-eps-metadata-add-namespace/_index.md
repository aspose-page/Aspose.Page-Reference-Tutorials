---
date: 2026-01-23
description: 學習如何使用 Aspose.Page for .NET 為 EPS 檔案新增命名空間。本指南逐步說明如何新增命名空間、修改 XMP 中繼資料，並簡化您的
  .NET 工作流程。
linktitle: Add Namespace
second_title: Aspose.Page .NET API
title: 如何在 Aspose.Page for .NET 中加入命名空間
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for .NET 新增 Namespace

## Introduction

在現代 .NET 開發中，**如何新增 namespace** 到 EPS 檔案是一項常見需求，尤其在需要豐富 XMP 中繼資料時。Aspose.Page for .NET 讓此工作變得簡單，您可以在程式碼編輯器內註冊自訂 XML 命名空間並儲存額外屬性。本教學將逐步說明如何新增 namespace、為何重要，以及如何儲存更新後的 EPS 檔案——全部以清晰、口語化的方式呈現。

## Quick Answers
- **「新增 namespace」是什麼意思？** 它會註冊一個自訂的 XML 前置詞，讓您可以在新的 XMP 屬性中使用。  
- **需要哪個函式庫？** Aspose.Page for .NET（從官方文件下載）。  
- **需要授權嗎？** 生產環境必須使用臨時或正式授權；亦提供免費試用版。  
- **可以在 .NET Core / .NET 6+ 上執行嗎？** 可以，函式庫支援所有近期的 .NET 版本。  
- **實作需要多久？** 只要引用函式庫，通常在 10 分鐘以內完成。

## What is Adding a Namespace?

新增 namespace 意味著建立一個唯一的識別碼（URI），將相關的中繼資料欄位以共同的前置詞分組。這樣可讓您的中繼資料保持有序，並避免與既有標準發生衝突。

## Why Use Aspose.Page for Namespace Management?
- **完整控制** XMP 中繼資料，無需手動解析 XML。  
- **跨平台** 支援 .NET Framework、.NET Core 以及 .NET 5/6+。  
- **零相依** —— API 會自行處理串流管理與檔案儲存。

## Prerequisites

1. **Aspose.Page for .NET** – 從 [Aspose.Page 文件](https://reference.aspose.com/page/net/) 下載並安裝。  
2. **.NET 開發環境** – Visual Studio、VS Code 或任何您偏好的 IDE。  

既然已說明基礎，接下來讓我們深入程式碼。

## Import Namespaces

首先，將所需的 Aspose.Page 命名空間匯入作用域：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Step 1: Initialize Your Project

設定包含 EPS 檔案的資料夾路徑：

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Open EPS File

使用 `FileStream` 開啟 EPS 檔案，並建立 `PsDocument` 實例：

```csharp
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## Step 3: Get XMP Metadata

取得現有的 XMP 中繼資料（若不存在則建立新檔案）：

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.
XmpMetadata xmp = document.GetXmpMetadata();
```

## Step 4: Change XMP Metadata

以下示範 **如何新增 namespace** 的實作。註冊新的 namespace URI，並加入使用該前置詞的屬性：

```csharp
// Add new XML namespace "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Add new string property in the new namespace.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

*小技巧：* 請選擇簡短且具意義的前置詞（例如 `tmp`），以及全域唯一的 URI，以避免與其他中繼資料標準衝突。

## Step 5:寫回磁碟：

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

執行程式後，檔案 `add_namespace_output.eps` 會包含您剛註冊的自訂命名空間中的新屬性 `tmp:newKey`。

## Common Issues and Solutions

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **Namespace 未出現** | 忘記在加入屬性前呼叫 `RegisterNamespaceUri`。 |存取錯誤** | EPS 檔案正被其他程式開啟。 | 關閉可能鎖定檔案的應用程式，或改用不同的輸出路徑。 |
| **儲存後中繼資料遺失** | 使用了過時 更新至最新的 Asp擷取 檔案的 XMP 中繼資料。

### Q3：我可以在哪裡取得更多支援或協助？

A3：前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得社群支援與討論。

### Q4：Aspose.Page 有提供免費試用嗎？

A4：有的，您可在此處 [免費試用 Aspose.Page](https://releases.aspose.com/)。

### Q5：如何取得 Aspose.Page 的臨時授權？

A5：可於此處 [取得臨時授權](https://purchase.aspose.com/temporary-license/) 以供測試使用。

## Frequently Asked Questions

**Q: 可以在同一次執行中新增多個 namespace 嗎？**  
A: 可以，只要在加入屬性之前，為每個需要的前置詞呼叫 `RegisterNamespaceUri`。

**Q: 函式庫是否支援屬性值的 Unicode 字元？**  
A: 支援。XMP 值以 UTF‑8 儲存，您可以安全使用國際字符。

**Q: 如何驗證 namespace 是否正確加入？**  
A: 開啟產生的 EPS 檔案於 XMP 檢視器，或使用 `document.GetXmpMetadata().ToString()` 觀察原始 XML。

**Q: 新增 namespace 會顯著增加檔案大小嗎？**  
A: 只會略微增加——XMP 中繼資料本身很輕量，新增的 XML 通常只有幾個位元組。

## Conclusion

您現在已了解 **如何新增 namespace** 到 EPS 檔案，使用 Aspose.Page for .NET 從專案設定到變更儲存的完整流程。此功能為您開啟了更豐富的自訂中繼資料之門，可供下游應用程式、數位資產管理系統或任何依賴 XMP 的工作流程使用。歡迎自行嘗試其他屬性、不同的 namespace，並將此模式整合至更大型的文件處理管線中。

---

**Last Updated:** 2026 Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}