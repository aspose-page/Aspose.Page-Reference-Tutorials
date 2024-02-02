---
title: 使用 Aspose.Page 將文字新增至 PostScript (PS) 文檔
linktitle: 將文字新增至 PostScript (PS) 文檔
second_title: Aspose.Page .NET API
description: 透過學習使用 Aspose.Page 將文字新增至 PostScript (PS) 文件來增強您的 .NET 開發技能。探索逐步範例並釋放文件操作的力量。
type: docs
weight: 10
url: /zh-hant/net/text-manipulation/add-text-to-postscript-ps-document/
---
## 介紹

在 .NET 開發的動態世界中，操作和增強 PostScript (PS) 文件是一項常見要求。 Aspose.Page for .NET 提供了一組強大的工具，可以輕鬆地將文字新增至您的 PS 文件。本教學將引導您完成整個過程，確保您可以將此功能無縫整合到您的專案中。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

-  Aspose.Page for .NET：確保您已將 Aspose.Page 庫整合到您的 .NET 專案中。您可以從[Aspose.Page .NET 文檔](https://reference.aspose.com/page/net/).

- 文檔目錄：設定儲存文檔的目錄。在範例中這將被稱為“您的文檔目錄”。

- 字體資料夾：建立一個資料夾來儲存自訂字體，在範例中稱為「您的文件目錄」。

## 導入命名空間

在開始之前，請確保在您的專案中包含必要的命名空間：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

現在，讓我們將該範例分解為多個步驟。

## 步驟1：為PS文檔建立輸出流

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟2：用系統字體填滿文本

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## 第 3 步：使用自訂字體填充文本

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## 步驟 4：使用系統字體勾勒文字輪廓

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## 第 5 步：使用自訂字體勾勒文字輪廓

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## 第 6 步：關閉並儲存

```csharp
document.ClosePage();
document.Save();
}
```

## 結論

恭喜！您已成功學習如何使用 Aspose.Page for .NET 將文字新增至 PostScript (PS) 文件。請隨意探索更多功能並增強您的文件操作能力。

## 常見問題解答

### Q1：我可以將 Aspose.Page 與其他 .NET 函式庫一起使用嗎？

A1：是的，Aspose.Page 與其他 .NET 程式庫無縫集成，為文件操作提供了多功能環境。

### Q2：自訂字體對於此過程至關重要嗎？

A2：雖然您可以使用系統字體，但合併自訂字體可以提供更大的靈活性和設計選擇。

### Q3：Aspose.Page適合大規模文件處理嗎？

A3：當然！ Aspose.Page 旨在高效、可靠地處理大規模文件。

### Q4：PS文檔中的文字位置可以修改嗎？

A4：當然！調整提供的範例中的座標以變更新增文字的位置。

### Q5：我可以在哪裡尋求 Aspose.Page 相關查詢的協助？

 A5：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)與社區聯繫並尋求專家建議。