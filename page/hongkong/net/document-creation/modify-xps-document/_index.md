---
date: 2026-01-12
description: 學習如何使用 Aspose.Page for .NET 修改 XPS 文件，並了解如何透過簡單的程式碼範例向 XPS 檔案添加文字。
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 修改 XPS 文件
url: /zh-hant/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 修改 XPS 文件

## 介紹

歡迎閱讀我們的逐步指南，說明 **如何修改 xps 文件**，使用 Aspose.Page for .NET。無論您需要插入簽名、加入浮水印，或只是將自訂文字放在頁面上，本教學會在幾分鐘內向您展示 **如何在 XPS 文件中加入文字**。我們會逐行說明程式碼，解釋每一步的原因，並提供避免常見問題的技巧。

### 快速解答
- **本教學涵蓋什麼內容？** 在 XPS 檔案的指定頁面加入簽名文字（「Confirmed」）。  
- **需要哪個函式庫？** Aspose.Page for .NET（最新版本）。  
- **需要授權嗎？** 測試時可使用臨時授權，正式環境需購買正式授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **實作需要多久？** 基本簽名插入大約需要 10 分鐘。

## 什麼是修改 XPS 文件？

XPS（XML Paper Specification）是 Microsoft 的固定版面文件格式，類似 PDF。修改 XPS 文件指的是以程式方式變更其視覺內容——加入文字、影像或圖形——而不需將檔案轉換成其他格式。Aspose.Page 提供完整的物件模型，讓您直接在 .NET 程式碼中編輯 XPS 檔案。

## 為什麼使用 Aspose.Page 來修改 XPS 文件？

* **完整控制** – 低階操作頁面、字形、筆刷與變換。  
* **無外部相依** – 純 .NET 函式庫，無需 Office 或 Adobe 元件。  
* **跨平台** – 可於 Windows、Linux、macOS 上執行，透過 .NET Core。  
* **效能穩健** – 高效處理大型文件，支援進階排版。

## 前置條件

- **Aspose.Page for .NET** – 安裝 NuGet 套件或從官方文件 **[此處](https://reference.aspose.com/page/net/)** 下載函式庫。  
- **輸入 XPS 檔案** – 從 **[Aspose 釋出頁面](https://releases.aspose.com/page/net/)** 取得範例 XPS 文件（例如 `input1.xps`）。  
- **工作目錄** – 在電腦上建立資料夾以存放輸入與輸出檔案，並記下完整路徑；在程式碼中將此路徑指派給 `dir` 變數。  
- **開發環境** – Visual Studio 2019/2022、.NET Framework 4.7.2 以上，或任何 .NET Core/5/6 專案。

現在一切就緒，讓我們深入程式碼。

## 匯入命名空間

在 .NET 專案中，先匯入 Aspose.Page 所需的命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## 步驟 1：開啟 XPS 文件串流

我們會將來源 XPS 檔案以串流方式開啟，並建立代表整個文件的 `XpsDocument` 物件。

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*小技巧：* 將串流包在 `using` 區塊中，可自動釋放檔案句柄。

## 步驟 2：建立簽名文字

接著，我們建立一個實色筆刷，用於繪製簽名字形。

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

您可以將 `Color.BlueViolet` 改成任何符合品牌的 `System.Drawing.Color`。

## 步驟 3：定義頁面並加入簽名

我們會指定哪些頁面需要加入簽名，然後將字形加入每一頁。

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*為什麼使用這些座標？* X 與 Y 值以點 (1/72 英吋) 為單位。請依需求調整，以將文字精確放置在頁面版面上。

## 步驟 4：儲存對 XPS 文件的變更

最後，將修改後的文件寫回磁碟。

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

新檔案 `input1_out.xps` 現在在第 1‑3 頁包含「Confirmed」簽名。

## 常見問題與解決方案

| Issue | Cause | Solution |
|-------|-------|----------|
| **簽名未顯示** | 座標錯誤或未選取頁面 | 確認每頁都有呼叫 `SelectActivePage`，並調整 X/Y 座標。 |
| **`AddGlyphs` 例外** | 伺服器未安裝字型 | 確保指定的字型（如 Arial）可用，或使用 `document.AddFont` 嵌入自訂字型。 |
| **輸出檔案損毀** | 串流未正確關閉 | 對所有串流使用 `using`，必要時呼叫 `document.Dispose()`。 |
| **大型檔案效能下降** | 將整個文件載入記憶體 | 分批處理頁面，或使用具串流功能的 `XpsLoadOptions`（若新版支援）。 |

## 常見問答

**Q: Aspose.Page 是否相容於最新的 .NET 框架？**  
A: 是，Aspose.Page 定期更新以支援 .NET Framework 4.5+、.NET Core 3.1+、.NET 5 與 .NET 6。

**Q: 我可以自訂加入文字的字型與樣式嗎？**  
A: 當然可以。變更 `AddGlyphs` 的參數（字型名稱、大小、`FontStyle`）以符合您的設計。

**Q: XPS 檔案有大小限制嗎？**  
A: Aspose.Page 能處理大型文件，但記憶體使用會隨檔案大小增加。對於極大檔案，建議逐頁處理。

**Q: 如何取得 Aspose.Page 的臨時授權？**  
A: 您可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 我可以在哪裡尋求協助或加入 Aspose 社群？**  
A: 請造訪 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 提問與分享經驗。

## 結論

本教學示範了如何使用 Aspose.Page for .NET 透過加入自訂簽名文字來 **修改 xps 文件**。現在您已具備在 XPS 檔案的特定頁面插入文字、浮水印或註解的基礎。可嘗試不同的字型、顏色與位置，以符合應用程式的品牌需求，並探索更廣泛的 Aspose.Page API，以實作進階的圖形與版面功能。

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.Page 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}