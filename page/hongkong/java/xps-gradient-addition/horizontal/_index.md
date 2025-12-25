---
date: 2025-12-25
description: 學習如何在 Java 中使用 Aspose.Page 為 XPS 文件添加漸層，以及如何自訂漸層停點以產生驚艷的水平效果。
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java XPS 中添加漸層 – 水平漸層
url: /zh-hant/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java XPS 中加入漸層 – 水平漸層

## 介紹
歡迎閱讀本步驟教學，了解 **如何在 XPS 文件中加入漸層**，本教學將示範如何加入水平漸層、說明其對視覺精緻度的重要性，並教您 **自訂漸層停點** 以精確控制顏色。Aspose.Page for Java 讓操作 XPS（XML Paper Specification）文件變得簡單，您可以專注於設計，而不必處理底層檔案細節。

## 快速答覆
- **需要哪個函式庫？** Aspose.Page for Java  
- **支援哪個 Java 版本？** 任意 Java 8+ 執行環境  
- **需要授權嗎？** 開發可使用免費試用版；正式上線需購買商業授權  
- **可以變更漸層方向嗎？** 可以，只要修改線性筆刷的起點/終點即可  
- **可以加入多個漸層嗎？** 當然可以，對不同筆刷重複路徑建立步驟即可  

## 什麼是 XPS 中的水平漸層？
水平漸層是指顏色從左至右平滑過渡於形狀之上。在 XPS 中，它以線性漸層筆刷（Linear Gradient Brush）表示，會在定義好的 **漸層停點** 之間插值。此視覺效果常用於橫幅、按鈕與背景填充。

## 為什麼選擇 Aspose.Page for Java？
- **完整的 XPS 支援** – 可建立、編輯與渲染，無需第三方工具。  
- **簡易 API** – `XpsDocument`、`XpsPath`、`XpsGradientBrush` 等高階物件隱藏了 XML 複雜度。  
- **效能佳** – 為大型文件與批次處理進行最佳化。  

## 前置作業
開始之前，請確保您已具備以下環境：

1. **Java 開發環境** – 從 [java.com](https://www.java.com) 下載並安裝最新 JDK。  
2. **Aspose.Page for Java 函式庫** – 從 [Aspose.Page for Java 文件](https://reference.aspose.com/page/java/) 下載 JAR 檔。  

## 匯入套件
先匯入所需的類別，這些匯入讓您可以存取文件建立、漸層處理與基本幾何功能。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## 步驟 1：初始化 XPS 文件
建立一個全新的 `XpsDocument` 實例，並指定要儲存結果的資料夾路徑。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## 步驟 2：建立水平漸層
定義一組 **漸層停點**，用來控制每個過渡點的顏色與位置。以下範例會建立一個充滿活力的彩虹式漸層。

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### 如何自訂漸層停點
- **顏色** – 使用 `doc.createColor(alpha, red, green, blue)` 設定任意 ARGB 值。  
- **位置** – 第二個參數（`float`，介於 `0` 與 `1` 之間）決定停點在漸層線上的相對位置。調整此數值即可將顏色向左或向右平移。

## 步驟 3：將漸層套用至路徑
建立矩形路徑，必要時加入變換，並以線性漸層筆刷填充。筆刷使用兩個點（`(10,0)` 到 `(228,0)`）產生水平效果。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**小技巧：** 多條路徑共用同一個 `stops` 清單可提升效能，但在加入新停點前務必先呼叫 `clear()`。

## 步驟 4：儲存文件
將 XPS 檔寫入磁碟。之後您即可使用任何 XPS 檢視器開啟，觀察水平漸層的呈現效果。

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 漸層顯示為單色 | 未加入漸層停點或筆刷未設定 | 確認 `path.setFill(...)` 使用 `LinearGradientBrush`，且已透過 `getGradientStops().addAll(stops)` 加入停點。 |
| 顏色顯得暗淡 | Alpha 值（第一個參數）設定不正確 | 除非需要透明，否則請使用 `255` 以取得完全不透明的顏色。 |
| 路徑尺寸不正確 | 變換矩陣參數錯誤 | 調整矩陣參數（`scaleX, skewY, skewX, scaleY, translateX, translateY`）。 |

## 常見問答

**Q: 可以在同一個 XPS 文件中使用多個漸層嗎？**  
A: 可以，您可以為每條路徑套用不同的漸層筆刷，以建立複雜的分層設計。

**Q: Aspose.Page 是否相容最新的 Java 版本？**  
A: Aspose.Page for Java 會定期更新，支援 Java 8 以及更新的版本。

**Q: Aspose.Page 還提供其他類型的漸層嗎？**  
A: 除了線性漸層，Aspose.Page 亦支援徑向漸層（Radial Gradient），可實現圓形顏色過渡。

**Q: 能否自訂漸層停點的顏色與位置？**  
A: 當然可以！您可以完全控制每個停點的 ARGB 顏色與相對位置（0‑1 範圍）。

**Q: 有沒有 Aspose.Page 的社群論壇可以求助？**  
A: 有，您可以前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 與社群交流並取得協助。

---

**最後更新：** 2025-12-25  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}