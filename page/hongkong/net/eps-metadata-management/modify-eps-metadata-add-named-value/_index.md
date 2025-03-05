---
title: 使用 Aspose.Page 新增命名值
linktitle: 新增命名值
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page 將命名值新增至 .NET 中的 EPS 檔案。這個綜合教程將逐步引導您完成整個過程。
type: docs
weight: 12
url: /zh-hant/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## 介紹

在使用 .NET 進行文件處理的領域中，Aspose.Page 作為處理 EPS 檔案的強大工具脫穎而出。 Aspose.Page 使開發人員能夠操作 XMP 元數據，從而簡化新增命名值等任務。本教學將引導您逐步完成使用 Aspose.Page 將命名值新增至 EPS 檔案的過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- C# 程式語言的基礎知識。
- 安裝了整合開發環境 (IDE)，例如 Visual Studio。
-  .NET 函式庫的 Aspose.Page。如果沒有安裝，可以從以下位址下載[這裡](https://releases.aspose.com/page/net/).

## 導入命名空間

首先，讓我們將必要的命名空間匯入到您的 C# 程式碼中。這些命名空間對於存取 Aspose.Page 提供的功能至關重要：

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

初始步驟涉及初始化 EPS 檔案的輸入流。代替`"Your Document Directory"`與您的文檔目錄的路徑：

```csharp
//開始時間：1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 第 2 步：取得 XMP 元數據

從 EPS 檔案中檢索 XMP 元資料。如果 EPS 文件缺少 XMP 元數據，則會建立一個新文件，並填入 PS 元資料註釋中的值：

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步驟 3：更改 XMP 元資料值

現在，讓我們更改 XMP 元資料。在此範例中，我們將在「xmpTPg:MaxPageSize」結構中新增一個命名值：

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## 步驟 4：使用更改的 XMP 元資料儲存 EPS 文件

使用更新的 XMP 元資料儲存 EPS 檔案。建立輸出流並儲存修改後的 EPS 檔案：

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## 結論

恭喜！您已成功使用 .NET 中的 Aspose.Page 將命名值新增至 EPS 檔案。本教學將引導您完成基本步驟，以展示 Aspose.Page 在文件操作中的簡單性和有效性。

## 常見問題解答

### Q1: Aspose.Page 是否相容於不同的 EPS 檔案版本？

A1：Aspose.Page支援各種EPS檔案版本，確保與各種文件的兼容性。

### Q2：我可以將Aspose.Page用於商業項目嗎？

 A2：是的，Aspose.Page附有商業許可證，您可以購買它[這裡](https://purchase.aspose.com/buy).

### Q3：Aspose.Page 有免費試用版嗎？

 A3：是的，您可以免費試用 Aspose.Page[這裡](https://releases.aspose.com/).

### 問題 4：我如何獲得支持或與 Aspose 社群建立聯繫？

 A4：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)獲得支持並與社區建立聯繫。

### 問題 5：什麼是臨時許可證？如何取得臨時許可證？

 A5：如果您需要臨時許可證用於測試或評估目的，您可以獲得一個[這裡](https://purchase.aspose.com/temporary-license/).