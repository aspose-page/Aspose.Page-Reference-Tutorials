---
date: 2026-03-19
description: 學習如何使用 Aspose.Page for .NET 透過建立自訂列印票證來新增票證，並以細緻的控制自訂列印體驗。
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 如何新增票證：使用 Aspose.Page for .NET 建立自訂列印票證
url: /zh-hant/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何新增票證：使用 Aspose.Page for .NET 建立自訂列印票證

## 介紹

如果您需要在 .NET 應用程式中 **如何新增票證** 的功能，Aspose.Page 為您提供直接從程式碼產生自訂列印票證的能力。在本教學中，我們將逐步說明整個流程——設定環境、建立 XPS 文件、附加自訂工作列印票證，並儲存結果。完成後，您即可自信地在任何列印工作流程中加入票證支援。

## 快速回答
- **「新增票證」是什麼意思？** 它指的是嵌入自訂列印票證（XPS 中的中繼資料），用以控制印表機設定。  
- **需要哪個程式庫？** Aspose.Page for .NET。  
- **需要授權嗎？** 評估期間可使用臨時授權；正式環境必須使用正式授權。  
- **可以在 .NET Core 使用嗎？** 可以，Aspose.Page 同時支援 .NET Framework 與 .NET Core。  
- **實作需要多長時間？** 基本票證通常在 15 分鐘內完成。

## 什麼是自訂列印票證？
自訂列印票證是一種基於 XML 的印表機偏好設定描述（例如分頁、份數、色彩管理等），會隨 XPS 文件一起傳遞。開發者可透過程式碼指定文件的列印方式，省去客戶端手動設定的步驟。

## 為什麼要使用 Aspose.Page 加入票證支援？
- **精細控制：** 可在程式碼中設定分頁、份數、紙張類型等。  
- **跨平台一致性：** 同一張票證可在任何支援 XPS 中繼資料的印表機上使用。  
- **無縫整合：** 直接與現有 .NET 專案結合，無需額外服務。

## 前置條件

在開始之前，請確保您已具備：

- 基本的 C# 與 .NET 開發能力。  
- 已安裝 Visual Studio（任意近期版本）。  
- 已將 Aspose.Page for .NET 程式庫加入專案。

如果尚未加入程式庫，您可以從 [Aspose.Page for .NET 文件說明](https://reference.aspose.com/page/net/) 下載。欲取得社群協助，請造訪 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39)。

## 匯入命名空間

先引入提供 XPS 與中繼資料類別的命名空間。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

接下來，我們將一步步拆解實作細節。

## 步驟 1：設定文件目錄

定義產生的 XPS 檔案要儲存的位置。

```csharp
string dir = "Your Document Directory";
```

## 步驟 2：建立新 XPS 文件

建立一個全新的 XPS 文件，用來容納頁面與票證。

```csharp
XpsDocument xDocs = new XpsDocument();
```

## 步驟 3：加入自訂工作列印票證

將自訂工作列印票證附加到文件上。這是 **如何新增票證** 功能的核心——在此您可以指定分頁、份數、渲染意圖、色彩管理以及其他所需設定。

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **專業提示：** 請將佔位的 snapshot 字串替換為符合您印表機能力的 Base64 編碼 DEVMODE 結構。

## 步驟 4：儲存文件

將包含嵌入票證的 XPS 文件寫入磁碟。

```csharp
xDocs.Save(dir + "output1.xps");
```

當您在支援 XPS 中繼資料的檢視器中開啟 *output1.xps* 時，印表機會自動套用票證中定義的設定。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 票證未套用 | 檢視器忽略 XPS 中繼資料 | 使用支援 XPS 列印票證的印表機驅動程式或 Microsoft XPS Viewer 等檢視器。 |
| Base64 snapshot 無效 | DEVMODE 資料損毀 | 使用 `GetPrinter` API 從印表機驅動程式重新產生 snapshot。 |
| 權限不足 | 無法寫入 `dir` | 確認應用程式具備足夠的檔案系統存取權限。 |

## 常見問答

**Q: Aspose.Page for .NET 可以與其他 .NET 框架一起使用嗎？**  
A: 可以，Aspose.Page 支援 .NET Framework、.NET Core、.NET 5/6 以及更新版本。

**Q: 如何取得 Aspose.Page 的臨時授權？**  
A: 前往 [此連結](https://purchase.aspose.com/temporary-license/) 取得 Aspose.Page 的臨時授權。

**Q: 有沒有 Aspose.Page 的社群論壇可以取得支援？**  
A: 當然有，您可以在 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 找到相關討論與協助。

**Q: 自訂列印票證支援哪些紙張類型？**  
A: Aspose.Page 支援多種紙張類型，包括普通紙、光面紙以及自訂紙張定義。

**Q: 有沒有 Aspose.Page for .NET 的範例專案？**  
A: 請參考 [文件說明](https://reference.aspose.com/page/net/) 中的範例專案與程式碼片段，快速啟動開發。

## 結論

我們已說明如何使用 Aspose.Page for .NET 為 XPS 文件加入 **如何新增票證** 支援。依照上述步驟，您可以將豐富的列印指令直接嵌入檔案，從 .NET 應用程式完整掌控列印工作流程。歡迎自行嘗試更多票證設定，以符合您的特定列印環境。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-19  
**測試環境：** Aspose.Page for .NET（最新穩定版）  
**作者：** Aspose  

---