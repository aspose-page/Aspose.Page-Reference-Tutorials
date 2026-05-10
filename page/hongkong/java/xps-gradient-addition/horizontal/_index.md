---
date: 2026-03-13
description: 學習如何在 Java 中使用 Aspose.Page 為 XPS 文件添加漸層，以及如何自訂漸層停點以打造驚艷的水平效果。
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java XPS 中添加漸層 – 水平漸層
url: /zh-hant/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java XPS 中添加漸層 – 水平漸層

## 簡介
歡迎閱讀本步驟教學，內容說明 **如何添加漸層** 到使用 Java 的 XPS 文件。您將學會如何加入水平漸層、為何它能提升視覺質感，以及如何 **自訂漸層停點** 以精確控制顏色。Aspose.Page for Java 讓操作 XPS（XML Paper Specification）文件變得簡單，您只需專注於設計，而不必處理底層檔案細節。

## 快速答覆
- **需要哪個函式庫？** Aspose.Page for Java  
- **支援哪個 Java 版本？** 任意 Java 8+ 執行環境  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權  
- **可以變更漸層方向嗎？** 可以 – 只要調整線性筆刷的起點與終點即可  
- **可以加入多個漸層嗎？** 當然可以 – 針對不同筆刷重複路徑建立步驟即可  

## 什麼是 XPS 中的水平漸層？
水平漸層是指顏色從左至右平滑過渡於形狀之上。在 XPS 中，它以線性漸層筆刷表示，會在定義好的 **gradient stops** 之間插值。此視覺效果常用於橫幅、按鈕與背景填充。

## 為什麼使用 Aspose.Page for Java？
- **完整的 XPS 支援** – 可直接建立、編輯與渲染，無需第三方工具。  
- **簡易 API** – `XpsDocument`、`XpsPath`、`XpsGradientBrush` 等高階物件隱藏了 XML 的複雜度。  
- **效能優化** – 針對大型文件與批次處理進行最佳化。  

## 先決條件
在開始之前，請確保您已具備：

1. **Java 開發環境** – 從 [java.com](https://www.java.com) 下載並安裝最新的 JDK。  
2. **Aspose.Page for Java 函式庫** – 從 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) 下載 JAR 檔。  

## 匯入套件
先匯入所需的類別。這些匯入讓您可以存取文件建立、漸層處理與基本幾何功能。

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
定義一組 **gradient stops**，用來控制每個過渡點的顏色與位置。以下範例會產生一條充滿活力的彩虹式漸層。

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
- **Color** – 使用 `doc.createColor(alpha, red, green, blue)` 設定任意 ARGB 值。  
- **Position** – 第二個參數（`float`，介於 `0` 與 `1` 之間）決定停點在漸層線上的位置。調整此數值即可將顏色向左或向右平移。

## 步驟 3：加入帶漸層的路徑
建立矩形路徑，視需要套用變換，並以線性漸層筆刷填充。筆刷使用兩個點 (`(10,0)` 到 `(228,0)`) 產生水平效果。因為 Y 座標相同，這支筆刷即為 **horizontal gradient brush**。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**專業提示：** 重複使用同一個 `stops` 清單於多條路徑可提升效能，但在加入新停點前務必先呼叫 `clear()`。

## 步驟 4：儲存文件
將 XPS 檔寫入磁碟。之後您即可使用任何 XPS 檢視器開啟，觀察水平漸層的實際效果。

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## 如何套用多重漸層
若想在同一個 XPS 文件中 **套用多個漸層**，只需對每個新圖形重複「建立水平漸層」與「加入帶漸層的路徑」兩個步驟。使用全新的 `XpsGradientStop` 物件清單（或先清除既有清單），再為每個圖形指派擁有獨立起點/終點的 `LinearGradientBrush`。此作法可讓您疊加漸層、打造複雜背景，或在單頁中突顯不同 UI 元件。

## 為什麼這很重要 – 水平漸層刷的好處
- **視覺深度：** 水平漸層刷能在不使用額外圖片的情況下，為介面增添細緻的立體感。  
- **檔案大小效益：** 漸層以向量定義儲存，使 XPS 檔案保持輕量。  
- **可伸縮性：** 由於漸層是向量式的，在高解析度螢幕上亦能保持清晰。  

## 常見問題與解決方案
| Issue | Reason | Fix |
|-------|--------|-----|
| Gradient appears solid | No gradient stops added or brush not set | Ensure `path.setFill(...)` uses a `LinearGradientBrush` and that stops are added via `getGradientStops().addAll(stops)`. |
| Colors look muted | Incorrect alpha value (first parameter) | Use `255` for fully opaque colors unless transparency is desired. |
| Path size is off | Transform matrix values are wrong | Adjust the matrix parameters (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## 常見問答

**Q: 可以在單一 XPS 文件中套用多個漸層嗎？**  
A: 可以，您只要為每條路徑加入各自的漸層筆刷，即可打造複雜的分層設計。

**Q: Aspose.Page 是否相容最新的 Java 版本？**  
A: Aspose.Page for Java 會定期更新，支援 Java 8 以及更新的版本。

**Q: Aspose.Page 還提供其他類型的漸層嗎？**  
A: 除了線性漸層，Aspose.Page 也支援徑向漸層，用於圓形顏色過渡。

**Q: 能否自訂漸層停點的顏色與位置？**  
A: 當然可以！您可以完全掌控每個停點的 ARGB 顏色以及相對位置（0‑1 範圍）。

**Q: 有沒有 Aspose.Page 的社群論壇可以求助？**  
A: 有，您可以前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 與社群互動並取得協助。

---

**最後更新：** 2026-03-13  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}