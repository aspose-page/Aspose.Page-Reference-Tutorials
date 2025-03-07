---
title: 使用 Aspose.Page for .NET 調整 EPS 影像大小
linktitle: 調整 EPS 影像的大小
second_title: Aspose.Page .NET API
description: 探索使用 Aspose.Page 在 .NET 中調整 EPS 影像大小的無縫過程。輕鬆實現點、英吋、毫米和百分比的精度。
weight: 11
url: /zh-hant/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 調整 EPS 影像大小

## 介紹

您是否希望使用 Aspose.Page for .NET 無縫調整 EPS 影像的大小？本教學是您輕鬆操作各種單位（例如點、英吋、毫米和百分比）的 EPS 影像尺寸的綜合指南。 Aspose.Page for .NET 提供了一組強大的工具，在本教程中，我們將逐步引導您完成該過程。

## 先決條件

在深入研究調整大小魔法之前，請確保滿足以下先決條件：

-  Aspose.Page for .NET 函式庫：確保您已安裝 Aspose.Page for .NET 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/page/net/).

- 文件目錄：建立一個目錄，用於儲存輸入 EPS 檔案和輸出調整大小的檔案。

現在您已完成所有設置，讓我們繼續匯入必要的命名空間並深入研究逐步指南。

## 導入命名空間

在您的 .NET 專案中，首先匯入必要的命名空間以使用 Aspose.Page。在文件的開頭加入以下程式碼：

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

## 第 1 步：以磅為單位調整大小

讓我們先以磅為單位調整 EPS 影像的大小。點是印刷業的標準計量單位。

```csharp
public static void ResizeInPoints()
{
    //您的文件目錄
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

## 第 2 步：以英吋為單位調整大小

現在，讓我們以英吋為單位調整 EPS 影像的大小，英吋是圖形設計中使用的常用單位。

```csharp
public static void ResizeInInches()
{
    //您的文件目錄
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

## 第 3 步：以毫米為單位調整大小

現在，讓我們以毫米為單位調整 EPS 圖像的大小，這是設計和列印中另一個廣泛使用的單位。

```csharp
public static void ResizeInMillimeters()
{
    //您的文件目錄
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

## 第 4 步：以百分比調整大小

最後，讓我們使用百分比調整 EPS 影像的大小，從而提供一種靈活的方法來調整影像大小。

```csharp
public static void ResizeInPercents()
{
    //您的文件目錄
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

請隨意將這些方法整合到您的專案中，您將輕鬆調整 EPS 圖像的大小。嘗試不同的單位以獲得所需的尺寸。

## 結論

恭喜！您已經掌握了使用 Aspose.Page for .NET 調整 EPS 影像大小的技巧。這個強大的函式庫為操作向量圖形開啟了一個充滿可能性的世界。無論您是為印刷媒體還是數位媒體進行設計，Aspose.Page 都能幫助您實現精確且客製化的結果。

## 常見問題解答

### Q1：我可以同時調整多個 EPS 影像的大小嗎？

A1：是的，您可以循環遍歷 EPS 檔案的集合，並相應地套用調整大小方法。

### Q2：Aspose.Page 是否相容於其他影像格式？

A2：Aspose.Page 主要關注 PostScript 和 EPS 格式。對於其他圖像格式，請考慮使用 Aspose.Imaging。

### Q3：商業項目有什麼許可注意事項嗎？

 A3：是的，請確保您擁有有效的許可證。訪問[這裡](https://purchase.aspose.com/buy)了解許可詳細資訊。

### Q4：我可以在購買前試用Aspose.Page嗎？

 A4：當然！您可以獲得免費試用[這裡](https://releases.aspose.com/).

### Q5：我可以在哪裡尋求更多協助或討論問題？

 A5：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)與社區聯繫並獲得協助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
