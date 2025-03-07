---
title: 使用 Aspose.Page 將帶有 Unicode 字串的文字新增至 PostScript (PS)
linktitle: 將帶有 Unicode 字串的文字新增至 PostScript (PS)
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page for .NET 將 Unicode 文字新增至 PostScript 檔案。輕鬆增強文件操作。
weight: 11
url: /zh-hant/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 將帶有 Unicode 字串的文字新增至 PostScript (PS)

## 介紹

在文件操作領域，Aspose.Page for .NET 作為一個強大的程式庫脫穎而出，使開發人員能夠創建、編輯和轉換各種文件格式。其強大的功能之一是能夠使用 Unicode 字串將文字新增至 PostScript (PS) 檔案。在本教程中，我們將探索完成此任務的逐步指南，為使用 Aspose.Page 的開發人員提供無縫體驗。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- C# 程式語言的應用知識。
- 安裝了 .NET 函式庫的 Aspose.Page。您可以從[.NET 文件的 Aspose.Page](https://reference.aspose.com/page/net/).
- 設定了必要配置的開發環境。

## 導入命名空間

在您的 C# 程式碼中，匯入使用 Aspose.Page for .NET 功能所需的命名空間：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 第 1 步：設定文件目錄和字型資料夾

```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## 步驟 2：為 PostScript 文件建立輸出流

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    //建立 A4 尺寸的儲存選項
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    //....（可以在此處設定其他選項）
    
    //建立新的 1 頁 PS 文檔
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ……（進一步的步驟將在下面解釋）
    
    //儲存文件
    document.Save();
}
```

## 步驟 3：新增帶有自訂字體的 Unicode 文字

```csharp
string str = "試してみます.";  //統一碼文本
int fontSize = 48;

//使用自訂字體填充文本
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## 第四步：關閉目前頁面

```csharp
document.ClosePage();
```

## 第 5 步：完成並儲存文檔

```csharp
document.Save();
```

## 結論

在本教學中，我們示範了使用 Aspose.Page for .NET 將 Unicode 文字新增至 PostScript 文件的過程。利用其強大的功能，開發人員可以增強其文件操作工作流程，確保靈活性和精確性。

## 常見問題解答

### Q1：我可以將 Aspose.Page for .NET 與其他程式語言一起使用嗎？

A1：Aspose.Page 主要是為.NET 設計的，但也有其他適用於Java 的版本。

### 問題 2：如何取得 Aspose.Page for .NET 的臨時授權？

 A2：參觀[臨時執照](https://purchase.aspose.com/temporary-license/)以獲得臨時許可證。

### Q3：有 Aspose.Page 討論的社群論壇嗎？

 A3：是的，請訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持。

### Q4：Aspose.Page for .NET 可以使用哪些格式？

A4：Aspose.Page支援多種格式，包括XPS、PS、EPS、PDF等。

### Q5：我可以自訂添加文字的外觀嗎？

A5：是的，您可以在Aspose.Page中自訂文字的字體、大小、顏色和其他屬性。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
