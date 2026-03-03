---
date: 2026-03-03
description: 學習如何使用 Aspose.Page for .NET 設定自訂頁面大小，並在 PostScript 文件中新增第二個 PS 頁面。
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 在 PS 文件中設定自訂頁面大小
url: /zh-hant/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 向 PostScript (PS) 文件新增頁面

## 簡介

在 .NET 開發中，能夠 **設定自訂頁面尺寸** 並 **新增第二個 PS 頁面** 到 PostScript (PS) 文件，可讓您對產生的列印、報告或圖形的版面配置進行精細控制。Aspose.Page for .NET 以簡潔的物件導向 API 讓此工作變得直觀。在本教學中，您將學習如何建立多頁 PS 檔案、為每個頁面定義自訂尺寸，並儲存結果——只需幾行 C# 程式碼。

## 快速問答
- **我可以設定自訂頁面尺寸嗎？** 可以，只需在開啟頁面時傳入寬度與高度。  
- **如何新增第二個 PS 頁面？** 再次呼叫 `document.OpenPage(width, height)` 即可。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **我需要授權嗎？** 測試時可使用臨時授權；正式環境則需正式授權。  
- **我可以從哪裡下載 Aspose.Page？** 請從下方的官方下載頁面取得。

## 先決條件

在開始本教學之前，請確保您已具備以下先決條件：

- 具備 .NET 開發的實務知識。  
- 機器上已安裝 Visual Studio。  
- Aspose.Page for .NET 函式庫，可從 [此處](https://releases.aspose.com/page/net/) 下載。  
- 您用於測試的文件目錄。

## 匯入命名空間

確保在專案中加入必要的命名空間，以存取 Aspose.Page 提供的功能。範例中已隱含加入命名空間，但仍建議您根據專案結構再次確認並作相應調整。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟 1：設定專案

在 Visual Studio 中建立新的 .NET 專案，並完成必要的設定。請確保已在專案中參考 Aspose.Page 函式庫。

## 設定自訂頁面尺寸並新增第二個 PS 頁面

本節將示範如何為每個頁面 **設定自訂頁面尺寸**，以及如何 **在同一文件中新增第二個 PS 頁面**。

### 步驟 2：初始化文件

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### 步驟 3：新增第一頁（預設尺寸）

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### 步驟 4：以不同（自訂）尺寸新增第二頁

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### 步驟 5：儲存文件

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

請依序執行上述步驟，即可成功 **設定自訂頁面尺寸**，並使用 Aspose.Page for .NET 為 PostScript 文件新增 **第二個 PS 頁面**。

## 為何重要

- **精確版面** – 自訂頁面尺寸可符合印表機規格或打造獨特的手冊格式。  
- **多頁面** – 新增第二頁（或更多）即可產生多頁報告，無需外部合併工具。  
- **跨平台** – 產生的 PS 檔可在任何相容 PostScript 的裝置上呈現，亦可稍後轉換為 PDF。

## 常見問題與除錯

- **路徑錯誤** – 確認 `dataDir` 以路徑分隔符結尾，或使用 `Path.Combine`。  
- **授權問題** – 若未取得有效授權，函式庫可能會加上浮水印或限制頁數。  
- **單位混淆** – 寬度與高度以點 (point) 為單位 (1 point = 1/72 吋)。請依此調整。

## 常見問答

**Q1: Aspose.Page 是否相容於不同的文件格式？**  
A1: Aspose.Page 主要專注於 PostScript 文件的操作。若需處理其他格式，可探索針對特定需求的 Aspose 函式庫。

**Q2: 我可以在 Aspose.Page 中自訂頁面尺寸嗎？**  
A2: 當然可以！如本教學所示，您可依需求為每個頁面指定不同尺寸。

**Q3: 我在哪裡可以找到更多範例與文件說明？**  
A3: 請前往 [documentation](https://reference.aspose.com/page/net/) 取得完整資訊與各式範例。

**Q4: 我要如何取得 Aspose.Page 的臨時授權？**  
A4: 前往 [this link](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

**Q5: 我可以在哪裡尋求社群支援或提問？**  
A5: 加入 [Aspose.Page community forum](https://forum.aspose.com/c/page/39) 與其他開發者交流、分享經驗並取得協助。

---

**最後更新：** 2026-03-03  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}