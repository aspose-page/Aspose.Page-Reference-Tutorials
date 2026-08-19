---
date: 2026-02-28
description: 學習如何使用 Aspose.Page for .NET 在 .NET 中建立 XPS 文件並加入圖片。請依循此逐步指南，享受順暢的開發體驗。
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: 建立 XPS 文件 .NET – 使用 Aspose.Page 添加圖片
url: /zh-hant/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 為 XPS 文件添加圖片

在本教學中，您將學習如何 **create XPS document .NET** 並使用功能強大的 Aspose.Page 函式庫嵌入圖片。無論是產生報告、發票或自訂圖形，為 XPS 檔案添加視覺元素都是 .NET 開發人員的常見需求。

## 介紹

在 .NET 開發領域，將圖片嵌入 XPS 文件是常見需求。Aspose.Page for .NET 簡化了此過程，提供強大的工具組，讓您輕鬆操作與增強 XPS 文件。本教學將指導您使用 Aspose.Page for .NET 將圖片添加至 XPS 文件的步驟。

## 快速解答
- **本教學涵蓋什麼內容？** 使用 Aspose.Page for .NET 在 XPS 文件中添加圖片。  
- **目標的主要關鍵字是？** *create xps document .net*  
- **需要授權嗎？** 提供免費試用版；正式使用時需購買授權。  
- **支援哪些 .NET 版本？** 支援 .NET Framework 4.5 以上、.NET Core 3.1 以上、以及 .NET 5/6/7。  
- **實作需要多長時間？** 基本的圖片插入大約需要 5‑10 分鐘。

## 什麼是 “create XPS document .NET”？

在 .NET 中建立 XPS 文件是指以程式方式產生 XML Paper Specification（XPS）檔案——一種固定版面的文件格式——使用 C# 或 VB.NET。Aspose.Page 提供流暢的 API，抽象底層細節，讓您專注於文字、圖形與圖片等內容。

## 為何使用 Aspose.Page 添加圖片？

- **完整控制** 可對圖片的位置、縮放與裁剪進行完整控制。  
- **無外部相依性** — 函式庫在內部處理圖片解碼。  
- **跨平台** 支援 Windows 與 Linux 環境。  
- **高保真** 渲染效果可在最終 XPS 檔案中保留圖片品質。

## 前置條件

在開始本教學之前，請確保已具備以下前置條件：

1. Aspose.Page for .NET 函式庫：從 [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/) 下載並安裝函式庫。  
2. 開發環境：建立 .NET 開發環境，例如 Visual Studio。  
3. 範例圖片：準備一張要加入 XPS 文件的範例圖片檔案（例如 "QL_logo_color.tif"）。

## 匯入命名空間

首先在 .NET 專案中匯入必要的命名空間。這些命名空間對於使用 Aspose.Page for .NET 提供的功能至關重要。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Aspose.Page 在 XPS 文件中添加圖片

以下我們將逐步說明完成 **create XPS document .NET** 並嵌入圖片的每個步驟。

### 步驟 1：設定文件目錄

首先指定文件目錄的路徑。此步驟確保專案能正確定位與儲存檔案。

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### 步驟 2：建立 XPS 文件

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### 步驟 3：將圖片加入 XPS 文件

現在，將圖片加入 XPS 文件。本範例使用名為 "QL_logo_color.tif" 的範例圖片。

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### 步驟 4：儲存產生的 XPS 文件

將加入圖片的 XPS 文件儲存下來。

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

現在您已成功使用 Aspose.Page for .NET 為 XPS 文件添加圖片！

## 常見問題與解決方案

- **找不到檔案錯誤** – 確認 `dataDir` 指向正確的資料夾，且圖片檔名完全相符，包括 Linux 上的大小寫敏感性。  
- **圖片變形** – 調整 `CreateMatrix` 的縮放係數或 `RectangleF` 參數，以控制尺寸與長寬比。  
- **不支援的圖片格式** – Aspose.Page 支援常見的點陣圖格式（PNG、JPEG、TIFF）。在使用 `CreateImageBrush` 前，請先將不支援的格式轉換。

## 常見問答

### Q1：Aspose.Page for .NET 是否相容於最新的 .NET 框架版本？

A1：Aspose.Page for .NET 設計上相容於多種 .NET 框架版本，包括最新的發行版。請參考 [documentation](https://reference.aspose.com/page/net/) 取得詳細資訊。

### Q2：我可以在 Windows 與 Linux 環境中使用 Aspose.Page for .NET 嗎？

A2：是的，Aspose.Page for .NET 為平台無關設計，適用於 Windows 與 Linux 環境。

### Q3：Aspose.Page for .NET 有哪些授權方案？

A3：是的，您可在 [此處](https://purchase.aspose.com/buy) 探索授權方案並進行購買。

### Q4：Aspose.Page for .NET 是否提供免費試用？

A4：是的，您可透過 [free trial](https://releases.aspose.com/) 免費試用 Aspose.Page for .NET。

### Q5：我可以在哪裡尋求協助或與 Aspose.Page for .NET 社群互動？

A5：請前往 [Aspose.Page for .NET forum](https://forum.aspose.com/c/page/39) 與社群交流並取得支援。

## 結論

在本教學中，我們探討了如何利用 Aspose.Page for .NET 無縫地將圖片加入 XPS 文件。此步驟式指南確保整合流程順暢，提升您的 .NET 開發能力，並協助您打造具視覺豐富度的 **create XPS document .NET** 解決方案。

---

**最後更新：** 2026-02-28  
**測試環境：** Aspose.Page for .NET 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}