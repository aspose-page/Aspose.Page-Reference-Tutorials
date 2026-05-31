---
date: 2026-01-23
description: 學習如何使用 Aspose.Page for .NET 透過新增命名值來編輯 EPS 檔案。本分步指南協助開發人員操作 EPS 中繼資料。
linktitle: Add Named Value
second_title: Aspose.Page .NET API
title: 如何編輯 EPS 檔案 – 使用 Aspose.Page 新增具名值
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何編輯 EPS 檔案 – 使用 Aspose.Page 新增具名值

## 如何編輯 EPS 檔案 – 介紹

在本教學 **如何編輯 EPS** 檔案中，我們將示範如何使用 .NET 的 Aspose.Page 函式庫向 EPS 文件新增具名值。無論您是要建立批次處理工具，或是需要即時豐富 EPS 中的中繼資料，以下步驟都會提供清晰、實作導向的指引。

## 快速解答
- **Aspose.Page 能做什麼？** 它讓您能讀取、修改與寫入 EPS 檔案，包含 XMP 中繼資料。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **需要授權嗎？** 提供免費試用版，但正式使用需購買商業授權。  
- **實作需要多久？** 基本的具名值情境通常在 10 分鐘以內完成。  
- **大型 EPS 檔案安全嗎？** 是的 – Aspose.Page 以串流方式處理資料，保持低記憶體使用量。

## 前置條件

在深入教學之前，請確保已具備以下前置條件：

- 具備 C# 程式語言的基礎知識。  
- 已安裝如 Visual Studio 等整合開發環境 (IDE)。  
- Aspose.Page for .NET 函式庫。若尚未安裝，可從 [here](https://releases.aspose.com/page/net/) 下載。

## 匯入命名空間

首先，將必要的命名空間匯入您的 C# 程式碼中。這些命名空間對於存取 Aspose.Page 所提供的功能至關重要：

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

第一步是為 EPS 檔案初始化輸入串流。將 `"Your Document Directory"` 替換為您的文件目錄路徑：

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 步驟 2：取得 XMP 中繼資料

從 EPS 檔案取得 XMP 中繼資料。若 EPS 檔案沒有 XMP 中繼資料，系統會建立新的，並以 PS 中繼資料註解的值填入：

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步驟 3：變更 XMP 中繼資料值

現在，我們對 XMP 中繼資料進行變更。在此範例中，我們將在 `"xmpTPg:MaxPageSize"` 結構中加入具名值：

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## 步驟 4：以變更後的 XMP 中繼資料儲存 EPS 檔案

使用更新後的 XMP 中繼資料儲存 EPS 檔案。建立輸出串流並儲存已修改的 EPS 檔案：

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## 結論

恭喜！您已成功使用 .NET 中的 Aspose.Page 為 EPS 檔案新增具名值。本教學示範了編輯 **EPS** 中繼資料的簡易性，讓您能以程式方式豐富文件內容。

## 常見問題

### Q1：Aspose.Page 是否相容於不同的 EPS 檔案版本？

A1：Aspose.Page 支援多種 EPS 檔案版本，確保與廣泛文件的相容性。

### Q2：我可以在商業專案中使用 Aspose.Page 嗎？

A2：可以，Aspose.Page 附有商業授權，您可於 [here](https://purchase.aspose.com/buy) 購買。

### Q3：Aspose.Page 是否提供免費試用？

A3：可以，您可在 [here](https://releases.aspose.com/) 取得免費試用版。

### Q4：如何取得支援或與 Aspose 社群聯繫？

A4：請前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 取得支援並與社群互動。

### Q5：什麼是臨時授權？該如何取得？

A5：若您需要測試或評估用的臨時授權，可於 [here](https://purchase.aspose.com/temporary-license/) 取得。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-23  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose