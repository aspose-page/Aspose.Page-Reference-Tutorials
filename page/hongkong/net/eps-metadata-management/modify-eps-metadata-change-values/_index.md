---
title: 使用 Aspose.Page for .NET 變更值
linktitle: 改變值
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 掌握 EPS 檔案操作。輕鬆變更 XMP 元資料值。
type: docs
weight: 17
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-change-values/
---
## 介紹

在文件處理的動態世界中，Aspose.Page for .NET 作為一款強大的工具脫穎而出，為開發人員提供了輕鬆操作 EPS 檔案的能力。在本教程中，我們將深入研究使用 Aspose.Page for .NET 更改 EPS 檔案中的值的過程。無論您是經驗豐富的開發人員還是好奇的初學者，本逐步指南都將為您提供有效修改 EPS 檔案中的 XMP 元資料所需的技能。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

### 1..NET 函式庫的 Aspose.Page

確保您的開發環境中安裝了 Aspose.Page for .NET 程式庫。如果沒有的話可以下載[這裡](https://releases.aspose.com/page/net/).

### 2. 文檔目錄

為您的文件設定一個目錄。這將是您的 EPS 檔案的儲存位置。

現在我們已經解決了先決條件，讓我們繼續接下來的關鍵步驟。

## 導入命名空間

在任何 .NET 專案中，導入必要的命名空間以利用 Aspose.Page 的功能至關重要。您可以這樣做：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 步驟1：初始化EPS檔輸入流

```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
//初始化EPS檔輸入流
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## 步驟 2：從流程建立 PsDocument 實例

```csharp
//從流建立 PsDocument 實例
PsDocument document = new PsDocument(psStream);
```

現在我們已經做好準備，讓我們繼續本教程的核心內容 - 更改 EPS 檔案中的 XMP 元資料值。

## 步驟 3：取得 XMP 元數據

```csharp
//取得 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，我們會取得一個新文件，其中填入了 PS 元資料註釋中的數值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步驟 4：修改 XMP 元資料值

現在，讓我們更改 XMP 元資料中的一些鍵值：

### 步驟4.1：更改ModifyDate值

```csharp
//更改修改日期值
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### 步驟4.2：更改創作者價值

```csharp
//改變創造者價值
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### 步驟 4.3：更改標題值

```csharp
//更改標題值
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

完成這些變更後，讓我們繼續最後一步 - 儲存修改後的 EPS 檔案。

## 步驟 5：使用更改的 XMP 元資料儲存 EPS 文件

### 步驟5.1：建立輸出流

```csharp
//建立輸出流
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### 步驟5.2：儲存EPS文件

```csharp
//儲存 EPS 文件
document.Save(outPsStream);
```

最後，關閉輸入流：

```csharp
finally
{
    psStream.Close();
}
```

恭喜！您已使用 Aspose.Page for .NET 成功修改了 EPS 檔案中的 XMP 元資料值。

## 結論

在本教程中，我們探索了使用 Aspose.Page for .NET 更改 EPS 檔案中的值的無縫過程。作為開發人員，您現在可以使用一個強大的工具來進行高效的文件操作。

## 常見問題解答

### Q1：我可以將 Aspose.Page for .NET 與其他檔案格式一起使用嗎？

A1：Aspose.Page 主要專注於 EPS 檔案操作。其他格式，請探索 Aspose 的各種產品。

### Q2：有試用版嗎？

 A2：是的，您可以免費試用 Aspose.Page for .NET[這裡](https://releases.aspose.com/).

### Q3：哪裡可以找到詳細的文件？

 A3：可以找到全面的文檔[這裡](https://reference.aspose.com/page/net/).

### Q4：如何取得臨時駕照？

 A4：您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### Q5：我可以購買 Aspose.Page for .NET 嗎？

 A5：當然！造訪購買頁面[這裡](https://purchase.aspose.com/buy)用於許可選項。