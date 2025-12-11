---
date: 2025-12-07
description: 學習如何縮放矩形、平移形狀，並在 Java 中使用 Aspose.Page 應用仿射變換以建立 PostScript 文件。
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page 縮放矩形並套用變換
url: /zh-hant/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Page 中縮放矩形並套用變換

## 簡介
歡迎閱讀本完整指南，了解如何利用 **Aspose.Page for Java** 的強大功能執行各種頁面變換。在本教學中，您將學會 **如何縮放矩形**、平移形狀、旋轉物件，以及在建立 **PostScript 文件** 時 **套用仿射變換** 的技巧。這些功能讓您能在不必處理底層渲染程式碼的情況下，開發出豐富且圖形密集的 Java 應用程式。

## 快速解答
- **如何在 Java 中使用 Aspose.Page 縮放矩形？** 在繪製圖形前使用 `document.scale()` 方法。  
- **我可以在不影響其他圖形的情況下移動（平移）形狀嗎？** 可以——先儲存圖形狀態，呼叫 `document.translate(x, y)`，繪製後再還原狀態。  
- **哪個類別負責建立 PostScript 檔案？** `PsDocument` 搭配 `PsSaveOptions`。  
- **商業部署是否需要授權？** 商業使用必須擁有有效的 Aspose.Page 授權。  
- **支援哪個 Java 版本？** Aspose.Page 支援 Java 8 及以上版本。

## 先決條件
在開始逐步教學之前，請確保已具備以下條件：

- 具備基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page for Java 套件。您可從 [Aspose.Page for Java 文件](https://reference.aspose.com/page/java/) 下載。  
- 在您的機器上已設定好 Java 整合開發環境 (IDE)。

## 匯入套件
在您的 Java 專案中，匯入使用 Aspose.Page for Java 所需的套件：

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 在 Aspose.Page 中什麼是「如何縮放矩形」？
縮放矩形會沿 X 與 Y 軸改變其大小，同時保持形狀不變。Aspose.Page 提供 `scale(float sx, float sy)` 方法，對目前的圖形狀態套用 **仿射變換**。這正是 **如何縮放矩形** 關鍵字背後的核心技術。

## 如何在 Aspose.Page 中平移形狀
平移會將形狀移至新位置而不改變其尺寸。這正是 **如何平移形狀** 的本質。透過儲存圖形狀態、套用 `translate(dx, dy)`、繪製，最後還原狀態，即可避免影響其他物件。

## 範例 1：無變換
第一個範例繪製一個未套用任何變換的簡單矩形，作為後續範例比較的基準。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## 範例 2：平移
此範例示範 **如何平移形狀**：在繪製第二個矩形之前，將圖形上下文向右平移 250 單位。

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 範例 3：縮放
此範例回應主要問題 **如何縮放矩形**。我們將矩形的寬度縮小至原始的 50%，高度縮小至 75%。

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 如何在 Java 中旋轉形狀（rotate shape java）
旋轉是另一種常見的仿射操作。雖然此處省略了旋轉的程式碼片段，但其模式與前述相同：儲存圖形狀態、呼叫 `document.rotate(angle)`、繪製形狀，最後還原。此方式示範了 **rotate shape java** 與 **如何旋轉矩形** 的實作。

## 為什麼使用 Aspose.Page 進行這些變換？
- **裝置無關**：一次編寫，即可產生 PostScript 或 XPS，無需平台特定程式碼。  
- **精細控制**：直接存取圖形狀態，讓您自由組合平移、縮放、剪切與旋轉。  
- **效能優異**：低開銷 API，適合大量文件的批次處理。

## 常見使用情境
- 產生帶有動態條碼與商標的可列印發票。  
- 建立需要精確縮放與定位的技術圖表。  
- 自動化產出多頁 PostScript 格式的報告。

## 結論
在本教學中，我們探討了使用 Aspose.Page for Java 於 Java 頁面操作的各種變換，重點包括 **如何縮放矩形**、**如何平移形狀** 以及其他仿射操作。透過這些範例，您可以為 Java 應用程式加入進階的頁面操作功能，並 **建立符合專業出版標準的 PostScript 文件**。

## 常見問題

### 我可以將 Aspose.Page for Java 用於其他文件格式嗎？
Aspose.Page 主要聚焦於 PostScript 與 XPS 格式的頁面操作。

### 我在哪裡可以找到更多 Aspose.Page for Java 的範例和文件？
請造訪 [Aspose.Page for Java 文件](https://reference.aspose.com/page/java/) 取得完整資訊。

### 是否有 Aspose.Page for Java 的免費試用？
是的，您可在此取得免費試用 [here](https://releases.aspose.com/)。

### 我如何取得 Aspose.Page for Java 的臨時授權？
請在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

### 我可以在哪裡尋求社群支援或提問關於 Aspose.Page for Java？
請前往 [Aspose.Page for Java 論壇](https://forum.aspose.com/c/page/39) 參與社群討論。

## 常見問答

**Q: `translate` 與 `scale` 有何不同？**  
A: `translate` 會移動座標系的原點，而 `scale` 則會沿 X 與/或 Y 軸改變繪製物件的大小。

**Q: 我可以在單一圖形狀態中結合多個變換嗎？**  
A: 可以——依序呼叫 `translate`、`scale`、`rotate` 或 `shear`，再進行繪製，即可產生組合的仿射變換。

**Q: 繪製完形狀後，我該如何重設變換？**  
A: 使用 `document.writeGraphicsRestore()` 以還原先前儲存的圖形狀態。

**Q: 能否將矩形繞其中心旋轉？**  
A: 完全可以。先將矩形平移至原點，套用 `rotate(angle)`，再平移回原位置後繪製。

**Q: Aspose.Page 是否支援抗鋸齒以產生更平滑的圖形？**  
A: 支援——在 `PsSaveOptions` 中設定相應的渲染選項即可啟用抗鋸齒。

---

**最後更新：** 2025-12-07  
**測試環境：** Aspose.Page for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}