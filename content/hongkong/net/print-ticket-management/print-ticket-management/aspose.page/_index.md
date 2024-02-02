---
title: 使用 Aspose.Page for .NET 編輯現有的列印票證
linktitle: 編輯現有的列印票證
second_title: Aspose.Page .NET API
description: 了解使用 Aspose.Page for .NET 在 XPS 文件中編輯列印票據。開發人員的分步指南。輕鬆增強文件列印控制。
type: docs
weight: 11
url: /zh-hant/net/print-ticket-management/print-ticket-management/aspose.page/
---
## 介紹

歡迎閱讀這份關於使用 Aspose.Page for .NET 編輯現有列印票證的綜合指南！ Aspose.Page 是一個功能強大的程式庫，可讓開發人員輕鬆處理 XPS 文件。在本教程中，我們將透過實際範例引導您完成編輯列印票證的過程，分解每個步驟以獲得無縫的學習體驗。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

- C# 程式設計基礎知識。
- Visual Studio 安裝在您的電腦上。
- 下載 Aspose.Page for .NET 程式庫並在您的專案中引用。

如果您尚未安裝 Aspose.Page for .NET，可以下載它[這裡](https://releases.aspose.com/page/net/).

## 導入命名空間

首先，將必要的命名空間匯入到您的 C# 專案中。這可確保您可以存取 Aspose.Page 功能。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

現在，讓我們將您提供的範例程式碼分解為多個步驟。

## 步驟1：設定文檔目錄

```csharp
//文檔目錄的路徑。
string dir = "Your Document Directory";
```

在這裡，替換`"Your Document Directory"`與 XPS 文件所在的實際路徑。

## 步驟 2： 開啟帶有列印票據的 XPS 文檔

```csharp
//起始時間：3
XpsDocument xDocs = new XpsDocument(dir + "input3.xps");
JobPrintTicket pt = xDocs.JobPrintTicket;
//結束：3
```

此步驟涉及開啟 XPS 文件並取得其 JobPrintTicket。

## 步驟 3：從作業列印單中刪除參數

```csharp
//起始時間：4
pt.Remove(
	"ns0000:PageDevmodeSnapshot",
	"ns0000:JobInterleaving",
	"ns0000:JobImageType");
//結束：4
```

使用以下命令從 JobPrintTicket 中刪除不需要的參數`Remove`方法。

## 步驟 4：向作業列印單新增參數

```csharp
//起始時間：5
pt.Add(
	new JobCopiesAllDocuments(2),
	new PageMediaSize(PageMediaSize.PageMediaSizeOption.ISOA4));
//結束：5
```

使用以下命令將所需參數新增至 JobPrintTicket`Add`方法。

## 步驟 5：儲存帶有變更的作業列印票券的文檔

```csharp
//起始時間：6
xDocs.Save(dir + "output3.xps");
//結束：6
```

使用更新的 JobPrintTicket 儲存修改後的 XPS 文件。

重複這些步驟，即可使用 Aspose.Page for .NET 輕鬆編輯列印票據！

## 結論

恭喜！您已成功學習如何使用 Aspose.Page for .NET 編輯現有的列印票證。這個功能強大的程式庫提供了處理 XPS 文件的靈活性和簡單性，使其成為開發人員的寶貴工具。

## 經常問的問題

### Q1：我可以將 Aspose.Page for .NET 與其他文件格式一起使用嗎？

A1：是的，Aspose.Page for .NET 主要專注於 XPS 文檔，但 Aspose 為不同格式提供了各種函式庫。查看他們的文檔以獲取更多詳細資訊。

### Q2：Aspose.Page for .NET 與 .NET Core 相容嗎？

A2：是的，Aspose.Page for .NET 與 .NET Core 相容，為您的開發環境提供靈活性。

### Q3：我如何獲得與 Aspose.Page 相關的支援或提出問題？

 A3：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)獲得社區支持並與其他開發人員聯繫。

### 問題 4：Aspose.Page for .NET 是否有免費試用版？

 A4：是的，您可以獲得免費試用[這裡](https://releases.aspose.com/).

### Q5：如何取得 Aspose.Page for .NET 的臨時授權？

A5：參觀[這個連結](https://purchase.aspose.com/temporary-license/)獲得臨時許可證。