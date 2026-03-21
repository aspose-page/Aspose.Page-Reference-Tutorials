---
date: 2026-03-21
description: 了解如何使用 Aspose.Page for .NET 在 XPS 文件中加入 Unicode 文字。本指南示範如何使用 C# 建立 XPS
  文件，並透過 Aspose.Page 添加 Unicode 字串。
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page 向 XPS 文件添加 Unicode 文本
url: /zh-hant/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 在 XPS 文件中加入 Unicode 文字

## Introduction

如果您需要在 XPS 檔案中加入 Unicode 文字，您來對地方了。在本教學中，我們將逐步說明如何使用 Aspose.Page for .NET 以 C# 方式建立 XPS 文件，並示範使用 Unicode 字串的 aspose page add text 功能。完成後，您將擁有一個能正確顯示從右至左 (RTL) Unicode 文字的完整 XPS 文件。

## Quick Answers
- **本教學涵蓋什麼內容？** 使用 Aspose.Page for .NET 在 XPS 文件中加入 Unicode 文字。  
- **使用的程式語言為？** C#（相容於 .NET Framework 與 .NET Core）。  
- **需要授權嗎？** 開發階段可使用免費試用版，正式上線需購買商業授權。  
- **可以變更字型或大小嗎？** 可以——範例使用 Arial 20 pt，任何已安裝的字型皆可使用。  
- **是否支援 RTL？** 設定 `BidiLevel = 1` 即可為 Unicode 字串啟用從右至左的呈現。

## What is “how to add unicode” in XPS?

在 XPS 中加入 Unicode 文字指的是將任何語言的字元——阿拉伯文、希伯來文、中文等——插入 XPS 文件。Aspose.Page 的 `XpsGlyphs` 類別負責低階字形定位，而 `BidiLevel` 屬性則控制 RTL 文字的方向。

## Why use Aspose.Page to add text?

- **完整的 .NET 整合** – 支援 .NET Framework、.NET Core、.NET 5/6+。  
- **無外部相依性** – 純受管理程式碼，無需 COM interop。  
- **豐富的排版支援** – 字型、樣式、顏色與雙向文字。  
- **高效能** – 快速建立與儲存 XPS 檔案，適合伺服器端產生。

## Prerequisites

- 具備 C# 與 .NET 開發的基本知識。  
- Visual Studio（任一較新版）。  
- Aspose.Page for .NET 函式庫 – 可從 [here](https://releases.aspose.com/page/net/) 下載。

## Import Namespaces

首先，匯入可讓您存取 XPS 模型與繪圖工具的命名空間。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set up the Document – create XPS document C#

建立一個全新的 XPS 文件，以容納 Unicode 文字。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Step 2: Add Unicode Text – aspose page add text

現在加入實際的 Unicode 字串。此範例使用 Arial 字型、20 點大小，並將文字放置於 (400 f, 200 f)。將 `BidiLevel` 設為 1 可讓渲染器將字串視為從右至左。

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Step 3: Save the Document

最後，將 XPS 檔案寫入磁碟。

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Congratulations! You have successfully **how to add unicode** text to an XPS document using Aspose.Page for .NET.

## Common Issues and Solutions

| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| 文字顯示亂碼 | 字型不支援該 Unicode 範圍 | 使用包含所需字形的字型（例如 Arial Unicode MS）。 |
| RTL 文字仍為左至右 | 未設定或 `BidiLevel` 為 0 | 確認對 RTL 文字設定 `glyphs.BidiLevel = 1;`。 |
| 檔案未儲存 | `dataDir` 路徑無效 | 檢查目錄是否存在且應用程式具備寫入權限。 |

## Frequently Asked Questions

**Q: Aspose.Page 是否相容於最新的 .NET 框架？**  
A: 是，Aspose.Page 會定期更新，以支援 .NET Framework、.NET Core 與 .NET 5/6+。

**Q: 加入文字時可以自訂字型樣式與大小嗎？**  
A: 當然可以！`AddGlyphs` 方法允許您指定任意字型系列、大小與 `FontStyle`。

**Q: 哪裡可以找到 Aspose.Page 的其他文件？**  
A: 您可前往文件 [here](https://reference.aspose.com/page/net/) 取得完整的 API 說明。

**Q: 有免費資源可以用來入門 Aspose.Page 嗎？**  
A: 有，您可以在 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 社群論壇中探索技巧、範例與同儕支援。

**Q: 購買前可以先試用嗎？**  
A: 當然！可從 [here](https://releases.aspose.com/) 下載免費試用版以評估此函式庫。

---

**最後更新：** 2026-03-21  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}