---
date: 2026-02-28
description: 了解如何使用 Aspose.Page for .NET 向 PostScript 文件添加圖像。本指南亦說明在需要時如何將位圖插入 PS
  以及從 PS 中提取圖像。
linktitle: Add Image to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 向 PostScript (PS) 文件添加圖像
url: /zh-hant/net/image-management/add-image-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 為 PostScript (PS) 文件新增圖像

## 如何為 PostScript (PS) 文件新增圖像

在本教學中，您將學習 **如何新增圖像** 到 PostScript (PS) 文件，使用功能強大的 Aspose.Page for .NET 函式庫。無論您是要製作可列印的傳單、技術圖紙，或是自訂報告，直接將圖形嵌入 PS 檔案都能顯著提升視覺品質。我們會逐步說明每個步驟、解釋每行程式碼的意義，並提供您未來專案可重複使用的技巧。

## 快速答覆
- **需要的函式庫是什麼？** Aspose.Page for .NET（最新版本）
- **可以將 bitmap 插入 ps 嗎？** 可以 – 使用 `DrawImage` 搭配 `Bitmap` 物件
- **實作大約需要多久？** 基本圖像通常在 10 分鐘以內完成
- **需要授權嗎？** 試用版可用於評估；正式環境需購買商業授權
- **之後可以從 ps 中提取圖像嗎？** 當然可以 – Aspose.Page 也提供提取 API

## 前置條件

在開始撰寫程式碼之前，請先確保已具備以下前置條件：

- Aspose.Page for .NET 函式庫：從 [here](https://releases.aspose.com/page/net/) 下載並安裝 Aspose.Page for .NET 函式庫。
- 文件目錄：在系統上建立一個目錄，用於儲存文件與圖像檔案。

## 匯入命名空間

首先在專案中匯入必要的命名空間。這些命名空間可讓您在 .NET 應用程式中使用 Aspose.Page 功能：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步驟 1：設定文件目錄

確保您有專屬的文件目錄。將下方程式碼片段中的 `"Your Document Directory"` 替換為您的文件目錄路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 步驟 2：建立 PS 文件的輸出串流

為 PostScript 文件設定輸出串流。此串流將用於儲存已修改的文件。

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## 步驟 3：建立儲存選項

為 PS 文件建立儲存選項，指定所需的設定，例如頁面大小。

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## 步驟 4：建立 PS 文件

初始化一個 1 頁的 PS 文件，並為圖形操作做準備。

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## 步驟 5：將 Bitmap 插入 PS 文件

從圖像檔案載入 `Bitmap` 物件並套用變換。這就是 **如何新增圖像** 的核心 – 我們將 bitmap 繪製到 PS 畫布上。

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

> **專業提示：** 調整 `Translate`、`Scale` 與 `Rotate` 的數值，以將圖像精確定位與縮放到所需位置。

## 步驟 6：完成圖形操作

結束圖形操作並關閉目前頁面。

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## 步驟 7：儲存文件

儲存已修改的 PS 文件。

```csharp
document.Save();
```

## 如何從 PS 文件提取圖像

若之後需要取得圖形，Aspose.Page 提供如 `PsDocument.ExtractImages` 的提取方法。雖然本教學著重於插入，但同一函式庫亦可 **從 ps 提取圖像** 以供重用或分析。

## 常見問題與解決方案

| 問題 | 為何發生 | 解決方案 |
|------|----------|----------|
| 圖像顯示失真 | 縮放矩陣不正確 | 再次檢查 `Scale` 值；若要保持原始大小，請使用均勻縮放（例如 `Scale(1,1)`） |
| 輸出檔案為空 | 串流未刷新 | 確認在 `using` 區塊內呼叫 `document.Save()` |
| 不支援的圖像格式 | Bitmap 無法載入檔案 | 將圖像轉換為支援的格式，如 JPEG、PNG、BMP 或 GIF |

## 結論

恭喜！您已成功學會使用 Aspose.Page for .NET **將圖像新增至 PostScript 文件**。現在您已具備插入圖形的堅實基礎，亦了解如何在需要時 **從 ps 提取圖像** 與 **將 bitmap 插入 ps**。歡迎嘗試多張圖像、不同的變換，甚至自訂繪圖指令，以建立豐富且可列印的內容。

## 常見問答

### Q1：可以使用 Aspose.Page 在單一 PS 文件中加入多張圖像嗎？

A1：可以。只需在文件中重複圖像新增的步驟即可。

### Q2：Aspose.Page for .NET 支援哪些圖像格式？

A2：Aspose.Page for .NET 支援多種圖像格式，包括 JPEG、PNG、BMP 與 GIF。

### Q3：可加入的圖像大小是否有限制？

A3：大小限制取決於 PS 文件的規格與系統資源。Aspose.Page 能處理各種尺寸的圖像。

### Q4：我可以對圖像套用額外效果，如濾鏡或覆蓋層嗎？

A4：可以，Aspose.Page 允許在將圖像加入文件前套用各種變換與效果。

### Q5：如何從 PS 文件中提取圖像？

A5：Aspose.Page for .NET 提供從 PS 文件提取圖像的方法。請參考文件以取得詳細資訊。

---

**最後更新：** 2026-02-28  
**測試環境：** Aspose.Page for .NET（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}