---
title: 使用 Aspose.Page 新增數組項
linktitle: 新增數組項
second_title: Aspose.Page .NET API
description: 探索如何使用 Aspose.Page for .NET 在 EPS 檔案中新增陣列項目。請按照我們的逐步指南進行無縫文件操作。
weight: 11
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 新增數組項

## 介紹

在 .NET 文件操作和處理領域，Aspose.Page 是一個脫穎而出的強大工具。在其眾多功能中，處理 EPS 檔案中的陣列項目是常見要求。在本教程中，我們將探索在 .NET 環境中使用 Aspose.Page 新增陣列項目的逐步過程。無論您是經驗豐富的開發人員還是新手，本指南都將清晰且準確地引導您完成整個過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- 對 .NET 程式設計有基本的了解。
-  Aspose.Page for .NET 已安裝。如果沒有，您可以從以下位置下載[這裡](https://releases.aspose.com/page/net/).
- 程式碼編輯器，例如 Visual Studio，與範例一起使用。

## 導入命名空間

在您的 .NET 專案中，請確保匯入必要的命名空間以利用 Aspose.Page 功能。在程式碼開頭新增以下行：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這些命名空間提供對 EPS 檔案操作所需的基本類別和方法的存取。

## 步驟1：初始化EPS檔輸入流

```csharp
//起始時間：3
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
//初始化EPS檔輸入流
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//從流建立 PsDocument 實例
PsDocument document = new PsDocument(psStream);            
//結束：3
```

在這裡，我們為 EPS 檔案設定初始輸入流並創建`PsDocument`實例。

## 第 2 步：取得 XMP 元數據

```csharp
//起始時間：4
//取得 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，我們會得到一個新文件，其中填充了 PS 元資料註釋中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.GetXmpMetadata();
//結束：4
```

從 EPS 檔案中檢索 XMP 元資料。如果 EPS 檔案缺少 XMP 元數據，則會使用 PS 元資料註釋中的值建立一個新檔案。

## 步驟 3：更改 XMP 元資料值

```csharp
//起始時間：5
//更改 XMP 元資料值

//再增加一個標題。預設情況下它將添加到數組的末尾。
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

//再增加一位創作者。它將透過索引 (0) 添加到數組中。
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
//結束：5
```

透過向陣列新增標題和建立者來修改 XMP 元資料。

## 步驟 4：使用更改後的 XMP 元資料儲存 EPS 文件

```csharp
//起始時間：6
//使用更改的 XMP 元資料儲存 EPS 文件

//建立輸出流
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    //儲存 EPS 文件
    document.Save(outPsStream);
}
//結束：6
```

最後，使用更新的 XMP 元資料儲存 EPS 檔案。對數組項所做的更改將反映在輸出檔中。

## 結論

在 .NET 中使用 Aspose.Page 新增陣列項目是一個簡單的過程，如本教學所示。透過正確的先決條件和逐步指南，開發人員可以無縫操作 EPS 文件，確保其文件符合特定的元資料要求。

## 常見問題解答

### Q1：Aspose.Page 是否相容於所有.NET 環境？

A1：是的，Aspose.Page 旨在與所有 .NET 環境無縫協作，提供跨平台的一致功能。

### Q2：我可以免費使用Aspose.Page嗎？

 A2：Aspose.Page提供免費試用版，讓使用者可以探索其功能。要繼續使用，必須從以下位置購買許可證[這裡](https://purchase.aspose.com/buy).

### Q3：Aspose.Page 是否有臨時授權？

 A3：是的，臨時許可證可以從[這裡](https://purchase.aspose.com/temporary-license/)以滿足短期專案的需要。

### Q4：在哪裡可以找到 Aspose.Page 的社群支援？

A4：如需社區討論和支持，請訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39).

### Q5：Aspose.Page for .NET 的最新版本是什麼？

 A5：若要存取最新版本的 Aspose.Page for .NET，請參閱[文件](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
