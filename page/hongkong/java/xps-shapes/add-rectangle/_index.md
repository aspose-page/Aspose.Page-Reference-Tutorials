---
date: 2026-04-24
description: 學習如何在 Java XPS 中使用 Aspose.Page 設定矩形顏色並新增矩形。本指南涵蓋 Java 新增矩形以及更改矩形筆劃。
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: 在 Java XPS 中新增矩形
second_title: Aspose.Page Java API
title: 在 Java XPS 中設定矩形顏色與新增矩形
url: /zh-hant/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中設定矩形顏色與新增矩形

## 介紹
在本指南中，您將學習如何在 Java XPS 中使用 Aspose.Page 函式庫 **set rectangle color** 與 **add a rectangle**。無論是為報告繪製簡單圖形，或是建立複雜的向量圖形，精通矩形樣式可讓您對 XPS 文件擁有精確的控制。

## 快速解答
- **需要的函式庫是什麼？** Aspose.Page for Java  
- **我可以變更矩形的描邊嗎？** 可以，使用 `setStroke` 與 `setStrokeThickness`  
- **支援 CMYK 色彩描述檔嗎？** 當然可以——如範例所示，您可以載入 ICC 描述檔  
- **正式使用需要授權嗎？** 需要，非評估用途必須購買商業授權  
- **實作需要多久？** 基本矩形通常在 10 分鐘內完成

## 什麼是 **set rectangle color**？
設定矩形顏色是指為形狀定義填充或描邊顏色，最終會在 XPS 文件中呈現。使用 Aspose.Page，您可以使用 RGB、CMYK，甚至自訂的 ICC 色彩描述檔，以達到精確的顏色匹配。

## 為何使用 Aspose.Page 來 **add rectangle java** 與 **change rectangle stroke**？
- **功能完整的 API** – 同時支援實心顏色與漸層。  
- **跨平台** – 可在任何 Java 執行環境上運作，無需原生相依性。  
- **豐富的幾何支援** – 輕鬆建立複雜路徑、套用變換，並管理描邊粗細。

## 前置條件
在深入程式碼之前，請確保您已具備：

- 具備基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page 函式庫。若未安裝，請從 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) 下載。  
- 可正常運作的 Java 開發環境（IDE、JDK 等）。

## 匯入套件
要開始使用，請在 Java 專案中匯入必要的套件。確保已正確將 Aspose.Page 函式庫加入 classpath。以下是一個基本範例：
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

接下來，我們將把上述範例分解為多個步驟，以在 Java XPS 中 **add a rectangle** 並 **set its color**。

## 步驟 1：設定文件目錄
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
將 `"Your Document Directory"` 替換為您希望讀寫 XPS 檔案的絕對路徑。

## 步驟 2：建立新 XPS 文件
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
此行會初始化一個全新的 XPS 文件，用於存放我們的圖形。

## 步驟 3：新增 CMYK 實心顏色描邊矩形
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
此步驟會新增一個 **stroked rectangle**，使用 CMYK 實心顏色。`setStroke` 方法定義矩形的輪廓顏色，而 `setStrokeThickness` 控制線寬——非常適合 **changing rectangle stroke**。

### 小技巧：
如果您偏好使用 RGB 顏色，請將 `createColor` 呼叫改為 `doc.createColor(0, 0, 255)`，即可得到實心藍色填充。

## 步驟 4：儲存產生的 XPS 文件
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
最後，將 XPS 文件寫入磁碟。檔案 `AddRectangle_out.xps` 現在包含了您已設定顏色與描邊的矩形。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|-------|----------|
| **矩形未顯示** | 路徑幾何不正確或描邊粗細設定為 0 | 檢查路徑字串 (`"M 20,10 L 220,10 220,100 20,100 Z"`) 並確保 `setStrokeThickness` 大於 0。 |
| **顏色錯誤** | 使用的 ICC 描述檔與目標色彩空間不符 | 使用 `doc.createColor(r, g, b)` 產生 RGB，或再次檢查 ICC 檔案路徑。 |
| **檔案未儲存** | `dataDir` 指向不存在的資料夾或缺乏寫入權限 | 事先建立該資料夾，或選擇可寫入的位置。 |

## 常見問與答

**Q:** *我可以在同一個 XPS 文件中新增多個矩形嗎？*  
A: 可以。只要對每個需要的矩形重複建立幾何與樣式的步驟即可。

**Q:** *我如何變更矩形的填充顏色而非描邊？*  
A: 使用 `path.setFill(...)` 搭配實心顏色筆刷，方式類似 `setStroke` 的使用。

**Q:** *Aspose.Page 適合用於複雜的 XPS 文件操作嗎？*  
A: 絕對適合。此函式庫支援漸層、變換、嵌入字型等進階功能。

**Q:** *我可以在哪裡找到更多範例與社群支援？*  
A: 請前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 瀏覽更多程式碼範例與同儕協助。

**Q:** *我可以在購買前試用 Aspose.Page 嗎？*  
A: 可以，您可透過 [free trial](https://releases.aspose.com/) 來評估 API 功能。

**最後更新：** 2026-04-24  
**測試環境：** Aspose.Page for Java 24.12  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}