---
date: 2026-01-25
description: 學習如何使用 Aspose.Page for .NET 在 EPS 檔案中設定陣列項目。一步一步的指南，協助高效操作 XMP 中繼資料。
linktitle: Change Array Items
second_title: Aspose.Page .NET API
title: aspose.page 設定陣列項目 – 使用 Aspose.Page for .NET 更改陣列項目
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 更改陣列項目

## 簡介

歡迎閱讀本完整指南，內容涵蓋使用 Aspose.Page for .NET 的 **aspose.page set array item**！Aspose.Page 是一個功能強大的函式庫，讓開發人員能處理各種文件格式，包括 EPS 檔案。在本教學中，我們將重點放在操作 EPS 檔案內的 XMP 中繼資料，特別是如何有效地更改陣列項目。

## 快速答覆
- **“aspose.page set array item” 的功能是什麼？** 它會 陣列內 Framework 4 **實作需要多長時間？** 基本更新通常在 10 分鐘以內完成。

## 什麼是 **aspose.page set array item**？

`SetArrayItem` 方法屬於 `XmpMetadata` 類別。它允許您在 XMP 陣列屬性（例如 `dc:title[0]`）的指定索需要在不重新建立整個文件的情況下校正或更新中繼資料時，這非常重要。

## 為什麼使用 **aspose.page set array item**？

- **精確度：** 只變更目標中繼資料項目，其他保持不變。  
- **合規性：** 讓 EPS 檔案符合 XMP 標準，以提升可搜尋性與存檔效果。  
- **自動化：** 非常適合大量文件集合的批次處理。  

## 先決條件

在深入教學之前，請確保您具備以下先決條件：

1. Aspose.Page for .NET 函式庫：確保已安裝 Aspose.Page for .NET 函式庫。您可從 [here](https://releases.aspose.com/page/net/) 下載。  
2. 開發環境：設定您偏好的開發環境，無論是 Visual Studio 或其他支援 .NET 開發的 IDE。

## 匯入命名空間

在 .NET 應用程式中，您需要匯入必要的命名空間以存取 Aspose.Page 功能。請在程式碼開頭加入以下命名空間：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 逐步指南

### 步驟 1：初始化 EPS 檔案輸入串流

```csharp
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

在此步驟中，我們開啟 EPS 檔案，並建立一個代表記憶體中文件的 `PsDocument` 實例。

### 步驟 2：取得 XMP 中繼資料

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

從 EPS 檔案中取得 XMP 中繼資料。若檔案未包含 XMP 中繼資料，則會根據 PS 中繼資料註解建立新的 XMP。

### 步驟 3：變更 XMP 中繼資料值

```csharp
xmp.SetArrayItem("dc:title", 0, new XmpValue("NewTitle"));
xmp.SetArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

此處，我們使用 **aspose.page set array item** 取代 `dc:title` 與 `dc:creator` 陣列的第一個元素（`index 0`）為新值。

### 步驟 4：以變更後的 XMP 中繼資料儲存 EPS 檔案

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

建立輸出串流，並以修改後的 XMP 中繼資料儲存 EPS 檔案。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| 輸出檔案未出現變更 | 來源 EPS 缺少 XMP 中繼資料，導致 `GetXmpMetadata()` 建立了沒有預期結構的新物件。 | 在設定項目之前呼叫 `xmp.AddArrayProperty("dc:title")`，或確保來源檔案已包含所需的陣列。 |
| `SetArrayItem` 拋出 *IndexOutOfRangeException* | 指定的索引在陣列中不存在。 | 使用 `xmp.GetArraySize("dc:title")` 檢查長度，或使用 `xmp.AppendArrayItem` 新增項目。 |
| 儲存時檔案被鎖定 | 輸入串流仍未關閉。 | 將輸入串流放在 `using` 區塊中，或在儲存前關閉它。 |

## 結論

恭喜！您已成功學會如何在 EPS 檔案中使用 Aspose.Page for .NET 進行 **aspose.page set array item**。此功能對於自訂與管理文件中的中繼資料至關重要，特別是當您需要保持大型集合的一致性與可搜尋性時。

## 常見問答

### Q1：我可以將 Aspose.Page for .NET 與其他文件格式一起使用嗎？

A1：Aspose.Page 主要處理 EPS 檔案，但 Aspose 針對不同文件格式提供了其他函式庫。

### Q2：我可以在哪裡找到更多文件說明？

A2：請參考位於 [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) 的文件說明。

### Q3：是否提供免費試用版？

A3：是的，您可從 [here](https://releases.aspose.com/) 取得免費試用版。

### Q4：如何取得臨時授權？

A4：可從 [this link](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q5：我可以在哪裡取得支援或與社群聯繫？

A5：請前往 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 獲得社群支援與討論。

**Additional FAQ**

**Q：我可以在一次呼叫中更新多個陣列項目嗎？**  
A：不能，`SetArrayItem` 每次只能處理一個索引。如需修改多個項目，請迴圈處理陣列。

**Q：此方法會保留現有的命名空間嗎？**  
A：會，Aspose.Page 在修改陣列項目時會保留所有現有的 XMP 命名空間。

**Q：是否可以新增陣列元素而非取代？**  
A：使用 `xmp.AppendArrayItem("dc:subject", new XmpValue("NewSubject"))` 以新增條目。

---

**最後更新：** 2026-01-25  
**測試環境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}