---
title: 使用 Aspose.Page for .NET 裁切 EPS 影像
linktitle: 裁切 EPS 影像
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page 探索 .NET 中 EPS 影像處理的無縫世界。輕鬆裁剪圖像並調整圖像大小，以獲得令人驚嘆的結果。
type: docs
weight: 10
url: /zh-hant/net/image-manipulation/crop-eps-images/
---
## 介紹

您是否正在為在 .NET 應用程式中操作 EPS 圖像而苦苦掙扎？別再猶豫了！在本教學中，我們將引導您完成使用強大的 Aspose.Page for .NET 函式庫裁切 EPS 影像的過程。無論您是經驗豐富的開發人員還是新手，本逐步指南都將幫助您輕鬆實現精確的影像裁切。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- .NET 開發的實用知識。
- 安裝了 .NET 函式庫的 Aspose.Page。如果沒有的話可以下載[這裡](https://releases.aspose.com/page/net/).
- 範例 EPS 圖像（將程式碼中的“input.eps”替換為您的實際檔案）。

## 導入命名空間

讓我們先導入必要的命名空間，以使我們的程式碼順利運行。 

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

現在，讓我們將教程分解為多個步驟。

## 第1步：初始化PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

初始化一個`PsDocument`具有輸入 EPS 流的物件。

## 步驟2：提取邊界框

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

檢索 EPS 影像的初始邊界框。

## 第 3 步：建立輸出流

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

為裁剪後的 EPS 影像建立輸出流。

## 第 4 步：定義新邊界框

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

定義一個新的裁切邊界框。確保新值位於初始邊界框內。

## 第 5 步：裁剪並儲存

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

使用新的邊界框裁剪 EPS 影像並將其儲存到輸出流。

針對不同的調整大小場景重複這些步驟。

## 調整 EPS 影像的大小

### 以英吋為單位調整大小

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

調整 EPS 影像的大小並以指定尺寸（以英吋為單位）儲存。

### 以毫米為單位調整大小

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

調整 EPS 影像的大小並以指定尺寸（以毫米為單位）儲存。

### 以百分比調整大小

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

調整 EPS 影像的大小並以指定的百分比尺寸儲存。

## 結論

恭喜！您已成功學習如何使用 Aspose.Page for .NET 裁剪 EPS 影像並調整其大小。現在，增強您的影像處理能力並將您的 .NET 應用程式提升到新的水平。

## 常見問題解答

### Q1：我可以將 Aspose.Page for .NET 與其他影像格式一起使用嗎？

A1：Aspose.Page 主要關注 EPS 影像，但 Aspose 提供了針對不同格式的各種函式庫。檢查他們的文件以了解特定格式。

### Q2：如何取得 Aspose.Page for .NET 的臨時授權？

 A2：參觀[這個連結](https://purchase.aspose.com/temporary-license/)獲得臨時測試許可證。

### 問題 3：使用 Aspose.Page for .NET 處理的圖片大小是否有任何限制？

A3：Aspose.Page 旨在處理各種尺寸的圖像。但是，性能可能會根據影像的複雜性而有所不同。

### Q4：有 Aspose.Page 討論的社群論壇嗎？

 A4：是的，您可以參與 Aspose.Page 社區[這裡](https://forum.aspose.com/c/page/39).

### Q5：在哪裡可以找到 Aspose.Page for .NET 的詳細文件？

 A5：參考文檔[這裡](https://reference.aspose.com/page/net/).