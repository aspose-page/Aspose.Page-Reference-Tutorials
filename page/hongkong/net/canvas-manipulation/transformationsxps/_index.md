---
date: 2026-01-05
description: 了解如何使用 Aspose.Page for .NET 輕鬆轉換 XPS 文件。跟隨我們的逐步指南，實現無縫轉換。
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page for .NET 轉換 XPS
url: /zh-hant/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for .NET 轉換 XPS

## 介紹

歡迎來到 Aspose.Page for .NET 的世界，這是一個功能強大的函式庫，可讓您輕鬆對 XPS 文件執行各種轉換。**在本教學中，您將學會如何使用 Aspose.Page for .NET 轉換 XPS 文件**，無論您是資深開發者還是剛入門。我們會一步步示範，說明每個轉換背後的原因，並提供實務技巧，讓您能在真實專案中運用。

## 快速回答
- **可以做到什麼？** 程式化建立、平移、縮放與旋轉 XPS 畫布元素。  
- **需要哪個函式庫？** Aspose.Page for .NET（最新版本）。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援平台？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **實作時間大約？** 基本轉換約需 10‑15 分鐘。

## 什麼是「how to transform xps」？
「how to transform xps」指的是以程式方式修改 XPS（XML Paper Specification）文件內元素的版面、大小與方向。使用 Aspose.Page，您可以對畫布套用矩陣轉換，精細控制位置、縮放與旋轉，而不必手動編輯 XPS XML。

## 為什麼使用 Aspose.Page 進行 XPS 轉換？
- **完整 .NET 整合** – 可無縫搭配 Visual Studio、Rider 等 IDE。  
- **無外部相依** – API 為您處理所有底層 XPS 細節。  
- **豐富的轉換支援** – 平移、縮放、旋轉，且可在一次呼叫中結合多種轉換。  
- **效能優化** – 適合即時產生報表、發票或任何可列印圖形。

## 前置作業

在開始之前，請確保您已具備：

- **Aspose.Page for .NET 函式庫** – 從官方文件下載並安裝：[Aspose.Page for .NET 文件](https://reference.aspose.com/page/net/)。  
- **開發環境** – Visual Studio、Visual Studio Code 或任何相容 .NET 的 IDE。  
- **文件目錄** – 您機器上用來讀寫 XPS 檔案的資料夾。請將程式碼中的佔位路徑替換為實際路徑。

準備就緒後，讓我們深入程式碼。

## 匯入命名空間

首先，匯入提供 Aspose.Page 類別的命名空間：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 如何轉換 XPS – 步驟說明

### 步驟 1：建立新 XPS 文件

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*說明*：我們先定義存放來源與輸出檔案的資料夾，然後實例化一個空的 `XpsDocument`。此物件將作為後續所有轉換的畫布。

### 步驟 2：建立主畫布

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*為什麼重要*：主畫布充當所有其他畫布的容器。透過微小的偏移，可避免內容在頁面邊緣被裁切。

### 步驟 3：建立矩形路徑幾何

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*提示*：路徑字串遵循標準 XPS 路徑語法（`M` 移動、`L` 直線、`Z` 關閉）。調整座標即可改變矩形大小。

### 步驟 4：為矩形加入填色

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*專業技巧*：使用 `CreateColor` 並傳入 RGB 值，以符合您的品牌調色盤。

### 步驟 5：新增不含轉換的畫布

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

此範例在頁面上放置一個未套用額外轉換的矩形，可作為基準元素。

### 步驟 6：新增含平移轉換的畫布

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*發生了什麼*？第一個矩陣將矩形向下平移 200 單位，接著的 `Translate` 呼叫再向右平移 500 單位，示範多重平移的串接方式。

### 步驟 7：新增含雙倍縮放的畫布

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*為什麼要縮放*？縮放 2 倍會使矩形的寬高各翻倍，讓您在不重新定義幾何形狀的情況下建立更大的圖形。

### 步驟 8：新增含繞點旋轉的畫布

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*關鍵洞見*：`RotateAround` 讓畫布繞自訂點（此處為 (100, 50)）旋轉，提供對旋轉錨點的精細控制。

### 步驟 9：儲存最終 XPS 文件

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

所有轉換完成後，文件會寫入 `output1.xps`。使用任意 XPS 檢視器開啟，即可看到堆疊的矩形及其各自的平移、縮放與旋轉效果。

## 常見問題與除錯

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 輸出檔案為空白 | `dataDir` 指向不存在的資料夾 | 確認資料夾已建立，或改用絕對路徑 |
| 矩形位置不如預期 | 矩陣值錯誤 | 再次檢查 `Translate`、`Scale`、`RotateAround` 的呼叫順序 |
| 顏色顯示異常 | RGB 值超出 0‑255 範圍 | 使用每個通道的有效位元組值 |

## 常見問答

**Q: Aspose.Page for .NET 是否相容所有 .NET 開發環境？**  
A: 是的，無縫支援 Visual Studio、Visual Studio Code、Rider 以及任何支援 .NET 的 IDE。

**Q: 我可以在哪裡找到更多範例與詳細 API 文件？**  
A: 請造訪官方文件：[Aspose.Page for .NET 文件](https://reference.aspose.com/page/net/)。

**Q: 我可以在購買授權前先試用 Aspose.Page 嗎？**  
A: 當然可以。免費試用版請前往：[Aspose.Page 免費試用](https://releases.aspose.com/)。

**Q: 如何取得測試用的臨時授權？**  
A: 可於臨時授權頁面申請：[臨時授權](https://purchase.aspose.com/temporary-license/)。

**Q: 完整授權該向哪裡購買？**  
A: 直接於 Aspose 商店購買：[Aspose.Page 購買頁面](https://purchase.aspose.com/buy)。

---

**最後更新：** 2026-01-05  
**測試環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}