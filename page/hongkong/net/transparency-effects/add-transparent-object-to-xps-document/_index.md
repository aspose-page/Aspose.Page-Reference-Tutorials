---
date: 2026-03-29
description: 學習如何在 XPS 文件中加入透明物件，然後使用 Aspose.Page for .NET 將 XPS 匯出為 PDF。一步一步的指南，附實用技巧。
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: 匯出 XPS 為 PDF – 使用 Aspose.Page 添加透明物件
url: /zh-hant/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 匯出 XPS 為 PDF – 使用 Aspose.Page 新增透明物件

## 介紹

在本教學中，您將學習如何在 XPS 文件中新增透明物件，然後使用 Aspose.Page for .NET **匯出 XPS 為 PDF**。透明度可以讓您的文件看起來更現代，並協助您突顯重要資訊。我們會逐步說明每個步驟，解釋程式碼背後的原理，並示範如何透過將 XPS 檔案轉換為 PDF 來完成工作流程，以便輕鬆分享。

## 快速解答
- **「匯出 XPS 為 PDF」是什麼意思？** 將 XPS 檔案轉換為 PDF 檔案，同時保留版面配置、顏色和透明度。  
- **為什麼要先加入透明度？** 透明物件讓您能建立分層圖形，在最終的 PDF 中呈現出色的效果。  
- **需要授權嗎？** 是的，生產環境必須擁有有效的 Aspose.Page 授權。  
- **可以在 .NET Core 上執行嗎？** 當然可以 – Aspose.Page 支援 .NET Core、.NET 5/6 以及完整的 .NET Framework。  
- **在哪裡可以找到更多範例？** 請參閱下方連結的 Aspose.Page 文件與社群論壇。

## 前置條件

在開始本教學之前，請確保已具備以下前置條件：

- Aspose.Page for .NET：確保已安裝 Aspose.Page .NET 函式庫。您可以從 [Aspose.Page for .NET 文件說明](https://reference.aspose.com/page/net/) 下載。

## 匯入命名空間

要開始使用，請在專案中加入必要的命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

現在，讓我們繼續逐步說明。

## 步驟 1：建立新 XPS 文件

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

此程式碼使用 Aspose.Page for .NET 初始化一個新 XPS 文件。

## 步驟 2：示範透明度

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

這些程式碼建立兩條灰色路徑，作為稍後將新增的透明形狀的背景。

## 步驟 3：建立具有封閉矩形幾何形狀的路徑

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

在此我們建立一個藍色矩形。由於稍後會調整其不透明度，該矩形在最終的 PDF 中會呈現半透明效果。

## 步驟 4：操作路徑與顏色

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

我們複製第一個矩形，將其加入頁面，並將填充顏色改為綠色。此示範了重複使用現有幾何形狀的便利性。

## 步驟 5：複製與變換路徑

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

複製的路徑向下平移 300 單位並塗上紅色，產生堆疊層的效果。

## 步驟 6：重複與修改路徑

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

我們重複使用 `path2` 的幾何資料，將其向右移動，並再次套用藍色填充。

## 步驟 7：管理不透明度

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

將 `Opacity` 屬性設定為 0.8，會使此矩形的透明度為 80%，說明您如何為每個元素微調透明度。

## 步驟 8：儲存 XPS 文件

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

XPS 檔案已儲存，且所有透明物件已套用。  

**匯出為 PDF：** 若要 **匯出 XPS 為 PDF**，只需再次呼叫 `doc.Save`，並使用 `.pdf` 副檔名，例如 `doc.Save(dataDir + "TransparentDocument.pdf");`。結果 PDF 會保留相同的視覺品質，包括不透明度設定。

## 為什麼在加入透明度後要匯出 XPS 為 PDF？

- **通用相容性：** PDF 在各平台上廣受支援，而 XPS 的使用較為有限。  
- **保留視覺效果：** Aspose.Page 在轉換過程中保留透明度、漸層與矩陣變換。  
- **輕鬆分享：** PDF 可在瀏覽器、行動裝置以及許多第三方閱讀器中開啟，無需額外插件。

## 常見使用情境

- **行銷手冊**：分層圖形營造高級感。  
- **技術圖表**：需要突顯區塊而不使版面雜亂。  
- **報告產生**：想要以部分透明度覆蓋浮水印或商標。

## 提示與注意事項

- **專業提示：** 請始終將 `Opacity` 值設定在 0 到 1 之間。超出此範圍的值會被限制，可能產生意外結果。  
- **效能提示：** 重複使用幾何形狀 (`path2.Data`) 可在需要大量相似圖形時降低記憶體使用量。  
- **陷阱：** 在加入透明度後直接儲存為 PDF 通常可直接使用，但若之後使用其他工具編輯 PDF，某些較舊的檢視器可能無法正確呈現不透明度。

## 結論

使用 Aspose.Page for .NET 在 XPS 文件中加入透明物件，提供了一種多功能的方式來提升視覺呈現。當您的 XPS 檔案達到理想效果後，只需一行程式碼即可 **匯出 XPS 為 PDF**，保留所有透明效果，以便廣泛分發。

## 常見問答

### Q1：我可以對 XPS 文件中的任何物件套用透明度嗎？

A1：是的，透明度可套用於 XPS 文件中的各種物件，例如路徑、形狀與影像。

### Q2：如何調整特定元素的不透明度？

A2：您可以設定 Fill 或 Stroke 的 opacity 屬性，以調整特定元素的透明度。

### Q3：Aspose.Page 相容於 .NET Core 嗎？

A3：是的，Aspose.Page 支援 .NET Core，讓跨平台開發成為可能。

### Q4：我可以使用 Aspose.Page 將 XPS 文件匯出為其他格式嗎？

A4：Aspose.Page 提供將 XPS 文件匯出為多種格式的功能，包含 PDF 與影像。

### Q5：在哪裡可以找到額外的支援與社群討論？

A5：欲取得額外支援與社群討論，請前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39)。

### Q6：PDF 轉換會保留我的透明度設定嗎？

A6：絕對會。使用 Aspose.Page 匯出 XPS 為 PDF 時，所有不透明度與混合設定皆會被保留。

### Q7：我可以批次處理多個 XPS 檔案匯出為 PDF 嗎？

A7：可以，您可以遍歷 XPS 檔案集合，對每個檔案呼叫 `doc.Save(...".pdf")`，以自動化批量轉換。

---

**最後更新：** 2026-03-29  
**測試環境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}