---
date: 2026-02-07
description: 學習如何使用 Aspose.Page for Java 縮放矩形、平移形狀，以及套用仿射變換以建立 PostScript 文件。
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page for Java 縮放矩形
url: /zh-hant/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for Java 縮放矩形

## 簡介
歡迎閱讀本完整指南，了解如何利用 **Aspose.Page for Java** 的強大功能執行各種頁面變換。在本教學中，您將學會 **如何縮放矩形**、平移形狀、旋轉物件，以及在建立 **PostScript 文件** 時 **套用仿射變換** 的技巧。這些功能讓您能在 Java 中開發圖形密集的應用程式，而不必處理底層的渲染程式碼。

## 快速答案
- **如何在 Java 中使用 Aspose.Page 縮放矩形？** 在繪製形狀之前使用 `document.scale()` 方法。  
- **我可以移動（平移）形狀而不影響其他圖形嗎？** 可以——先保存圖形狀態，呼叫 `document.translate(x, y)`，繪製，然後恢復狀態。  
- **哪個類別用於建立 PostScript 檔案？** `PsDocument` 搭配 `PsSaveOptions`。  
- **生產環境是否需要授權？** 商業部署需要有效的 Aspose.Page 授權。  
- **支援哪個 Java 版本？** Aspose.Page 支援 Java 8 及以上版本。

## 先決條件
在深入逐步說明之前，請確保您已具備以下條件：

- 具備 Java 程式設計的基本知識。  
- 已安裝 Aspose.Page for Java 程式庫。可從 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) 下載。  
- 在電腦上已設定 Java 整合開發環境 (IDE)。  

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

## 什麼是 Aspose.Page 中的「如何縮放矩形」？
縮放矩形會沿 X 與 Y 軸改變其大小，同時保持形狀不變。Aspose.Page 提供 `scale(float sx, float sy)` 方法，將 **仿射變換** 套用到目前的圖形狀態。這正是 **how to scale rectangle** 關鍵字背後的核心技術。

## 如何使用 Aspose.Page 平移形狀
平移會將形狀移至新位置而不改變其尺寸。這正是 **how to translate shape** 的本質。透過保存圖形狀態、套用 `translate(dx, dy)`、繪製，最後恢復狀態，即可避免影響其他物件。

## 範例 1：無變換
第一個範例繪製一個未套用任何變換的簡單矩形。此範例作為後續範例比較的基準。

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
此處示範 **how to translate shape**，在繪製第二個矩形之前將圖形上下文向右平移 250 單位。

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
此範例回應主要問題 **how to scale rectangle**。我們將矩形的寬度縮小至原始的 50%，高度縮小至 75%。

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

## 如何在 Java 中旋轉形狀 (rotate shape java)
旋轉是另一種常見的仿射操作。雖然旋轉的程式碼片段為簡潔起見未列出，但其模式相同：保存圖形狀態，呼叫 `document.rotate(angle)`，繪製形狀，然後恢復。此範例說明 **rotate shape java** 與 **how to rotate rectangle** 的實作方式。

## 為何重要 – 真實世界的好處
- **裝置無關的輸出** – 只寫一次即可產生 PostScript 或 XPS，無需平台特定的調整。  
- **細緻的控制** – 結合平移、縮放、剪切與旋轉，以滿足精確的版面需求。  
- **效能導向** – 低開銷 API，適合大量文件的批次處理。  

## 常見使用情境
- 產生可列印的發票 – 例如，提供精確放置標誌與條碼的 **printable invoice java** 解決方案。  
- 建立需要精確縮放與定位的技術圖表。  
- 自動化產生 PostScript 格式的多頁報告。  

## 常見問題與解決方案
- **變換未重設** – 必須將 `document.writeGraphicsSave()` 與 `document.writeGraphicsRestore()` 成對使用，以避免不必要的影響。  
- **顏色異常** – 確保在每次變換後設定繪圖顏色；恢復後圖形狀態不會保留先前的顏色設定。  
- **檔案過大** – 使用 `PsSaveOptions` 開啟壓縮或在嵌入點陣圖時降低影像解析度。  

## 常見問答

### 我可以將 Aspose.Page for Java 用於其他文件格式嗎？
Aspose.Page 主要專注於 PostScript 與 XPS 格式的頁面操作。

### 哪裡可以找到更多 Aspose.Page for Java 的範例與文件？
請前往 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) 獲取完整資訊。

### 是否提供 Aspose.Page for Java 的免費試用？
是的，您可在此處取得免費試用 [here](https://releases.aspose.com/).

### 如何取得 Aspose.Page for Java 的臨時授權？
請在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/).

### 哪裡可以尋求社群支援或提問關於 Aspose.Page for Java 的問題？
請前往 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) 參與社群討論。

## 常見問題

**Q: `translate` 與 `scale` 有何不同？**  
A: `translate` 移動座標系統的原點，而 `scale` 則沿 X 和/或 Y 軸改變繪製物件的大小。

**Q: 我可以在單一圖形狀態中結合多個變換嗎？**  
A: 可以——在繪製之前依序呼叫 `translate`、`scale`、`rotate` 或 `shear`，即可產生組合的仿射變換。

**Q: 繪製形狀後如何重設變換？**  
A: 使用 `document.writeGraphicsRestore()` 以回復先前保存的圖形狀態。

**Q: 能否繞矩形中心旋轉？**  
A: 完全可以。先將矩形平移至原點，套用 `rotate(angle)`，再平移回原位置後繪製。

**Q: Aspose.Page 是否支援抗鋸齒以獲得更平滑的圖形？**  
A: 支援——在 `PsSaveOptions` 中設定相應的渲染選項即可啟用抗鋸齒。

---

**最後更新：** 2026-02-07  
**測試版本：** Aspose.Page for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}