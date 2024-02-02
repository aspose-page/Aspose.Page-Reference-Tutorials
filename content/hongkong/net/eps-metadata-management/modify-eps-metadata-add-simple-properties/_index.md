---
title: 使用 Aspose.Page for .NET 新增簡單屬性
linktitle: 新增簡單屬性
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 增強 EPS 檔案。輕鬆為自訂文檔元資料新增簡單屬性。
type: docs
weight: 14
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## 介紹

在文件操作和增強領域，Aspose.Page for .NET 成為一個強大的工具，為開發人員提供了在 EPS 檔案中無縫新增和修改 XMP 元資料的能力。本教學將引導您完成使用 Aspose.Page for .NET 將簡單屬性新增至 EPS 檔案的過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

1.  Aspose.Page for .NET：確保您的開發環境中安裝了 Aspose.Page for .NET。如果沒有的話可以下載[這裡](https://releases.aspose.com/page/net/).

2. 文檔目錄：設定一個目錄來儲存您的 EPS 檔案。更新`dataDir`提供的程式碼片段中的變數以及文檔目錄的路徑。

## 導入命名空間

首先，導入必要的命名空間以啟用與 Aspose.Page for .NET 的通訊。在程式碼檔案的開頭新增以下行：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 第1步：初始化EPS檔輸入流

```csharp
//開始時間：1
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
//初始化EPS檔輸入流
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//從流建立 PsDocument 實例
PsDocument document = new PsDocument(psStream);
```

## 第 2 步：取得 XMP 元數據

```csharp
//取得 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，我們會得到一個新文件，其中填入 PS 元資料註釋中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步驟 3：更改 XMP 元資料值

```csharp
//更改 XMP 元資料值
DateTime now = DateTime.UtcNow;

//新增整數屬性
xmp.Add("xmp:Intg1", new XmpValue(111));

//新增日期時間屬性
xmp.Add("xmp:Date1", new XmpValue(now));

//新增雙精度屬性
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//添加字串屬性
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## 步驟 4：使用更改的 XMP 元資料儲存 EPS 文件

```csharp
//使用更改的 XMP 元資料儲存 EPS 文件

//建立輸出流
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    //儲存 EPS 文件
    document.Save(outPsStream);
}
```

## 第5步：關閉文件流

```csharp
finally
{
    psStream.Close();
}
```

透過執行這些步驟，您可以使用 Aspose.Page for .NET 輕鬆地將簡單的屬性合併到 EPS 檔案中。

## 結論

總之，Aspose.Page for .NET 對於尋求使用自訂 XMP 元資料增強 EPS 檔案的開發人員來說是一項寶貴的資產。透過新增簡單的屬性，您可以自訂和豐富文件以滿足特定要求，從而開啟文件操作的無限可能。

## 常見問題解答

### Q1：Aspose.Page for .NET 是否與所有 EPS 檔案相容？

A1：Aspose.Page for .NET 支援多種 EPS 檔案。但是，相容性可能會根據各個文件的複雜性和結構而有所不同。

### 問題 2：我可以使用 Aspose.Page for .NET 修改現有的 XMP 元資料嗎？

A2：當然！如本教學所示，您可以輕鬆變更現有的 XMP 元資料值或新增值以滿足您的需求。

### Q3：我可以新增的屬性類型有限制嗎？

A3：Aspose.Page for .NET 支援各種屬性資料類型，包括整數、日期、雙精確度數和字串。您可以靈活地為元資料選擇適當的類型。

### Q4：如何獲得 Aspose.Page for .NET 的技術支援？

 A4： 如需技術協助，請訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)或探索[文件](https://reference.aspose.com/page/net/)進行全面指導。

### Q5：Aspose.Page for .NET 有免費試用版嗎？

 A5：是的，您可以免費試用[這裡](https://releases.aspose.com/).