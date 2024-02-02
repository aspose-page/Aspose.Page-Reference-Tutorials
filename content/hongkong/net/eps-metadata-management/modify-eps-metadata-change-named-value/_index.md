---
title: 使用 Aspose.Page for .NET 變更命名值
linktitle: 更改命名值
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page for .NET 變更 EPS 檔案中的命名值。輕鬆自訂 XMP 元資料以進行客製化文件處理。
type: docs
weight: 16
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## 介紹

在文件處理領域，Aspose.Page for .NET 作為操作 EPS 檔案的強大工具脫穎而出。它提供的關鍵功能之一是能夠更改 XMP 元資料中的命名值。本教學將引導您完成使用 Aspose.Page for .NET 變更命名值的過程，使您能夠根據您的特定需求自訂 EPS 檔案。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Page for .NET：確保您已安裝 Aspose.Page for .NET 程式庫。如果沒有的話可以下載[這裡](https://releases.aspose.com/page/net/).

- 文件目錄：為 EPS 檔案指定一個目錄，您可以在其中執行命名值變更。

## 導入命名空間

在您的.NET專案中，您需要匯入必要的命名空間來存取Aspose.Page提供的功能。將以下命名空間加入您的程式碼：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

現在，我們將程式碼分解為多個步驟以便全面理解：

## 第1步：初始化EPS檔輸入流

```csharp
//開始時間：1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
//結束：1
```

在此步驟中，我們為要修改的 EPS 檔案設定輸入流。確保將“您的文件目錄”替換為文件目錄的實際路徑。

## 第 2 步：取得 XMP 元數據

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

從 EPS 檔案中檢索現有的 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，則會使用 PS 元資料註釋中的值產生一個新檔案。

## 步驟 3：更改 XMP 元資料值

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

在這裡，我們示範如何更改「xmpTPg:MaxPageSize」結構中的兩個命名值。您可以根據您的特定要求進行自訂。

## 步驟 4：使用更改的 XMP 元資料儲存 EPS 文件

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

將修改後的 EPS 檔案儲存到輸出流。該檔案現在將反映對 XMP 元資料所做的更改。

## 結論

透過本教學課程，您了解如何利用 Aspose.Page for .NET 來變更 EPS 檔案中 XMP 元資料內的命名值。此功能為自訂和定製文件以滿足特定要求開闢了無限可能。

## 常見問題解答

### Q1：我可以將 Aspose.Page for .NET 與其他文件格式一起使用嗎？

A1：是的，Aspose.Page支援各種文件格式，包括EPS、XPS和PDF。

### Q2：Aspose.Page for .NET 有試用版嗎？

 A2：是的，您可以免費試用[這裡](https://releases.aspose.com/).

### Q3：在哪裡可以找到更多有關 Aspose.Page for .NET 的文件？

 A3：參考文檔[這裡](https://reference.aspose.com/page/net/).

### Q4：如何取得 Aspose.Page for .NET 的臨時授權？

 A4：您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### 問題 5：Aspose.Page for .NET 使用者可以使用哪些支援選項？

 A5：造訪社群論壇[這裡](https://forum.aspose.com/c/page/39)以尋求支持和討論。