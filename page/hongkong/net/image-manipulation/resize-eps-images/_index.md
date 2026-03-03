---
date: 2026-03-03
description: 學習如何在 .NET 中使用 Aspose.Page 調整 EPS 圖像大小 – 一個逐步指南，說明如何使用點、英吋、毫米或百分比來調整
  EPS 大小。
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 調整 EPS 圖像大小
url: /zh-hant/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for .NET 調整 EPS 圖片大小

## 簡介

您是否在尋找 **如何調整 EPS** 圖片大小的無縫解決方案，並使用 Aspose.Page for .NET？本教學提供完整指南，教您如何以點、英吋、公釐與百分比等單位輕鬆調整 EPS 圖片尺寸。Aspose.Page for .NET 提供強大的工具組合，本文將一步步帶您完成整個流程。

## 快速解答
- **哪個函式庫負責 EPS 調整大小？** Aspose.Page for .NET  
- **支援哪些單位？** 點 (Points)、英吋 (Inches)、公釐 (Millimeters) 與百分比 (Percents)  
- **生產環境需要授權嗎？** 需要 – 必須購買商業授權  
- **可以一次調整多個檔案嗎？** 當然可以，只要在迴圈中處理檔案即可  
- **支援 .NET Core 嗎？** 支援，API 可在 .NET Framework 與 .NET Core 上執行  

## 什麼是 EPS 調整大小？
Encapsulated PostScript (EPS) 是一種向量圖形格式，常用於印刷與設計工作流程。調整 EPS 檔案的大小會改變其邊界框 (bounding box)，但不會將圖形點陣化，從而在任何比例下都能保持清晰度。

## 為什麼要調整 EPS 圖片大小？
- **維持列印品質：** 向量縮放可保持邊緣銳利。  
- **符合版面需求：** 調整尺寸以匹配頁面或畫布大小。  
- **自動化批次作業：** 程式化地在數秒內調整數十個檔案。  

## 先決條件

在開始調整大小的魔法之前，請先確保已具備以下條件：

- Aspose.Page for .NET 函式庫：請確定已安裝 Aspose.Page for .NET 函式庫。您可從 [here](https://releases.aspose.com/page/net/) 下載。

- 文件目錄：建立一個目錄，用於存放輸入的 EPS 檔案以及輸出的調整後檔案。

現在所有前置作業已完成，讓我們繼續匯入必要的命名空間，並深入步驟說明。

## 匯入命名空間

在您的 .NET 專案中，先匯入使用 Aspose.Page 所需的命名空間。於檔案開頭加入以下程式碼：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## 如何以點 (Points) 調整 EPS 大小

點是印刷業的標準測量單位。以下範例將原始寬度與高度各放大兩倍。

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## 如何以英吋 (Inches) 調整 EPS 大小

英吋是平面設計師在準備列印素材時常用的單位。

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## 如何以公釐 (Millimeters) 調整 EPS 大小

公釐在使用公制系統的地區相當普遍。

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## 如何以百分比調整 EPS 大小

以百分比為基礎的調整方式，可讓您依原始尺寸比例進行縮放。

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

歡迎將這些方法整合至您的專案中，您將能輕鬆調整 EPS 圖片大小。可自行嘗試不同單位，以達到理想的尺寸。

## 常見問題與解決方案
- **找不到檔案：** 請確認 `dataDir` 指向正確的資料夾，且 `input.eps` 確實存在。  
- **尺寸異常：** 記得 `Units.Percents` 需要傳入類似 150 這樣的數值，代表原始大小的 150%。  
- **授權例外：** 若出現授權錯誤，請在建立 `PsDocument` 前載入有效的 Aspose.Page 授權檔案。

## 結論

恭喜您！已掌握 **如何調整 EPS** 圖片大小的技巧，並成功運用 Aspose.Page for .NET。這套功能強大的函式庫為向量圖形的操作開啟無限可能。無論是列印還是數位媒體設計，Aspose.Page 都能協助您達成精確且客製化的成果。

## 常見問答

### Q1：我可以同時調整多個 EPS 圖片的大小嗎？

A1：可以，您只需在迴圈中遍歷 EPS 檔案集合，依序套用調整大小的方法即可。

### Q2：Aspose.Page 是否相容其他影像格式？

A2：Aspose.Page 主要聚焦於 PostScript 與 EPS 格式。若需處理其他影像格式，建議使用 Aspose.Imaging。

### Q3：商業專案的授權有何注意事項？

A3：需要購買有效授權。請前往 [here](https://purchase.aspose.com/buy) 了解授權細節。

### Q4：我可以在購買前先試用 Aspose.Page 嗎？

A4：當然可以！您可在 [here](https://releases.aspose.com/) 取得免費試用版。

### Q5：若需要額外協助或討論問題，該去哪裡？

A5：請造訪 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 與社群互動，獲得協助。

## 常見問題

**Q: 這段程式碼能在 .NET Core 6 上執行嗎？**  
A: 能。此 API 相容於 .NET Framework 4.5+、.NET Core 3.1+、.NET 5+ 與 .NET 6+。

**Q: 如何保留原始的色彩描述檔？**  
A: `ResizeEps` 方法不會更改色彩資料，只會調整邊界框。

**Q: 能否在不將整個檔案載入記憶體的情況下調整 EPS？**  
A: 如範例所示使用串流 (stream) 可降低記憶體使用量，文件會即時處理。

**Q: 可以串接多個調整大小的操作嗎？**  
A: 可以。只要在同一個 `PsDocument` 實例上依序呼叫 `ResizeEps` 即可。

**Q: EPS 內嵌的影像會發生什麼變化？**  
A: 內嵌影像會隨向量內容等比例縮放，仍能保持品質。

---

**最後更新：** 2026-03-03  
**測試環境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}