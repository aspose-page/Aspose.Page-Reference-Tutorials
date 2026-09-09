---
date: 2026-09-09
description: 了解如何使用 Aspose.Page 在 Java PostScript 中建立 radial gradient。本分步指南將向您展示如何加入
  color stops gradient、設定 radii，並快速產生 PS file。
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: 精通 Java 中的 radial gradients
og_description: 了解如何使用 Aspose.Page 在 Java PostScript 中建立 radial gradient。本指南說明如何加入
  color stops gradient、設定 radii，並在數分鐘內產生 PS file。
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: 如何在 Java PostScript 中建立 radial gradient
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: 如何在 Java PostScript 中建立 radial gradient
url: /zh-hant/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用 Aspose.Page 建立徑向漸層

## 介紹
如果您需要在 PostScript 檔案中 **建立徑向漸層**，您來對地方了。在本教學中，我們將逐步說明如何產生包含平滑徑向漸層的 PostScript 文件，使用 **Aspose.Page for Java**。完成後，您將了解 API、看到完整可執行的範例，並知道如何為任何設計情境調整顏色、位置與半徑。

## 快速回答
- **什麼函式庫可在 PostScript 中建立徑向漸層？** Aspose.Page for Java。  
- **實作需要多長時間？** 基本範例大約需要 10‑15 分鐘。  
- **執行程式碼是否需要授權？** 免費試用可用於開發；正式環境需購買商業授權。  
- **支援哪個 Java 版本？** Java 8 或以上。  
- **我可以變更漸層形狀嗎？** 可以 – 在 `RadialGradientPaint` 建構子中調整半徑與中心點。

## 如何在 Java 中建立徑向漸層

載入您的 Java 專案、匯入所需類別，並依照以下步驟說明操作。核心做法是實例化 `RadialGradientPaint` 並將其套用於在 `PsDocument` 上繪製的矩形。此兩物件方式會為您處理所有低階 PostScript 指令。

## 什麼是徑向漸層？
`RadialGradientPaint` 是 Java AWT 的類別，定義從中心點向外的圓形顏色過渡。它能平滑混合多個顏色停點，非常適合聚光燈、柔和背景或任何從焦點向外輻射的效果。

## 為什麼使用 Aspose.Page 來製作徑向漸層？
Aspose.Page 為您提供完整的程式化控制 PostScript 輸出，同時處理低階 PS 語法的繁重工作。它支援 **50+ 輸入與輸出格式**，可在不將整個檔案載入記憶體的情況下渲染上百頁文件，且可在任何支援 Java 8+ 的作業系統上執行。這些量化的能力使其成為企業級圖形產生的可靠選擇。

## 前置條件
- **Java Development Kit (JDK) 8+** – 使用 `java -version` 確認。  
- **Aspose.Page for Java** – 從官方 [Aspose.Page 下載頁面](https://releases.aspose.com/page/java/) 下載最新 JAR。  
- **您選擇的 IDE** – Eclipse、IntelliJ IDEA，或具備 Java 擴充功能的 VS Code。  
- **可寫入的資料夾** – 用於儲存產生的 `.ps` 檔案。

## 匯入套件
首先匯入我們需要的類別。`java.awt` 套件提供漸層畫筆物件，而 `com.aspose.eps` 包含 PostScript 文件處理類別。

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟說明

### 步驟 1：建立矩形並開啟 PS 文件
`PsDocument` 是 Aspose.Page 的類別，代表一個 PostScript 文件，提供繪製形狀、文字與影像的方法。我們先建立輸出串流、設定頁面大小（預設 A4），再定義一個將容納漸層的矩形。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Pro tip:** 調整矩形的座標 (`200, 100, 200, 200`) 即可將漸層放置在頁面的任意位置。

### 步驟 2：定義顏色與比例
徑向漸層由 *顏色停點*（顏色）與 *比例*（這些停點的相對位置）組成。此處我們建立六種顏色及其對應的比例陣列。

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Why this matters:** 透過調整 `fractions`，您可以控制顏色過渡的速度，從而實現細膩或戲劇性的效果。

### 步驟 3：建立徑向漸層畫筆
`RadialGradientPaint` 是描述徑向顏色漸層的核心類別，包含中心點、半徑、焦點、比例、顏色、循環方式與色彩空間。現在使用上述陣列建立 `RadialGradientPaint` 物件。

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Note:** 若不需要額外的縮放或旋轉，`transform` 可以為 `null`。如需斜切漸層，請自行嘗試 `AffineTransform`。

### 步驟 4：設定畫筆並填滿矩形
畫筆準備好後，我們告訴 `PsDocument` 使用它，然後填滿先前定義的矩形。

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

此時 PostScript 頁面已包含一個平滑填滿徑向漸層的矩形。

### 步驟 5：關閉並儲存文件
最後，關閉當前頁面並將檔案寫入磁碟。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

開啟 `RadialGradient1_outPS.ps`，使用任何 PostScript 檢視器（例如 Ghostscript），您將看到漸層如同定義般精確呈現。

## 常見問題與解決方案
| 症狀 | 可能原因 | 解決方法 |
|---------|--------------|-----|
| 漸層顯示為單一顏色 | `fractions` 陣列未以 `0.0f` 開頭或未以 `1.0f` 結尾 | 確保第一個 fraction 為 `0.0f`，最後一個為 `1.0f`。 |
| 顏色看起來黯淡 | 使用了錯誤的 `ColorSpaceType` | 改用 `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` 以獲得更鮮豔的輸出。 |
| 未產生輸出檔案 | `FileOutputStream` 路徑無效或不可寫入 | 確認 `dataDir` 存在且應用程式具有寫入權限。 |

## 常見問答

**Q: 我可以在商業專案中使用 Aspose.Page for Java 嗎？**  
A: 可以。正式環境需要商業授權。您可於 [Aspose 授權頁面](https://purchase.aspose.com/buy) 購買。

**Q: 我在哪裡可以找到官方 API 參考文件？**  
A: 完整文件可在 [Aspose.Page Java API 參考](https://reference.aspose.com/page/java/) 取得。

**Q: 是否提供免費試用供測試？**  
A: 當然。可從 [Aspose.Page 下載頁面](https://releases.aspose.com/) 下載試用版。

**Q: 如何取得評估用的臨時授權？**  
A: 可於 [臨時授權申請頁面](https://purchase.aspose.com/temporary-license/) 索取臨時授權。

**Q: 我可以在哪裡取得社群支援？**  
A: 加入 Aspose.Page 社群論壇： [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39)。

## 結論
您現在已掌握 **如何在 Java PostScript 文件中建立徑向漸層**，只要調整矩形大小、顏色停點與漸層半徑，即可創造無限的視覺效果——從細膩的背景填充到醒目的聚光燈圖形。歡迎嘗試不同的 `AffineTransform` 值以旋轉或斜切漸層，並將此技巧與文字、影像結合，產生更豐富的 PDF 或 EPS 輸出。

---

**最後更新：** 2026-09-09  
**測試環境：** Aspose.Page for Java latest (as of writing)  
**作者：** Aspose

## 相關教學

- [使用漸層填充形狀：Java PostScript 徑向範例](/page/java/postscript-gradient-addition/radial2/)
- [在 Java 中建立 PostScript 漸層 – 新增垂直漸層](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page 透明度教學 – 在 Java PostScript 中加入透明度](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}