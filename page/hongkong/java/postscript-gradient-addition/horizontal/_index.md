---
date: 2026-09-04
description: 了解如何使用 Aspose.Page for Java 搭配 Linear Gradient Paint Java，在 PostScript
  檔案中建立水平漸層 java。提供逐步程式碼說明、常見陷阱與常見問答。
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: 使用 Aspose 在 PostScript 中建立水平漸層 java
og_description: 使用 Linear Gradient Paint Java 在 PostScript 中建立水平漸層 java。本 Aspose.Page
  教學在 15 分鐘內示範完整步驟、前置條件與除錯技巧。
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: 使用 Aspose 在 PostScript 中建立水平漸層 java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: 使用 Aspose 在 PostScript 中建立水平漸層 java
url: /zh-hant/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用 Linear Gradient Paint 添加水平漸層

## 介紹
在本完整教學中，您將學習如何在 PostScript 文件中使用 Aspose.Page for Java 隨附的 **Linear Gradient Paint Java** 類別來 **建立水平漸層 java**。我們將逐步說明從設定專案到在形狀與文字上繪製漸層的每個步驟，讓您在幾分鐘內即可產生精緻、可列印的圖形。無論您是構建報表引擎、設計自動化工具，或是自訂印表機驅動程式，本指南都會提供您所需的完整程式碼。

## 快速回答
- **需要的程式庫是什麼？** Aspose.Page for Java（包含 Linear Gradient Paint Java）。  
- **實作需要多長時間？** 基本的水平漸層大約需要 10‑15 分鐘。  
- **需要授權嗎？** 生產環境需要臨時或完整授權。  
- **支援哪個 JDK 版本？** Java 8 或更新版本。  
- **可以在形狀與文字上都使用漸層嗎？** 可以 — 同一個 `LinearGradientPaint` 實例可用於填充形狀，也可套用於文字的描邊或填色。

## 什麼是水平漸層以及為何使用它？
水平漸層會將顏色從物件的左邊緣平滑過渡到右邊緣，產生柔和的變化，為圖形增添深度與視覺趣味。它非常適合用於現代 UI 元件、突顯標題，或在 PDF 或 PostScript 報表中作為細微的背景陰影。使用 **Linear Gradient Paint Java** 可精確控制起始與結束顏色、不透明度與縮放，確保在任何裝置或印表機上皆呈現清晰的效果。

## 前置條件
在深入程式碼之前，請確保您具備以下條件：

- 已在機器上安裝 Java Development Kit (JDK)。  
- Aspose.Page for Java 程式庫。您可從 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) 下載。

## 匯入套件
在 Java 專案中開始匯入必要的套件。這些匯入讓您能使用圖形基元、漸層處理以及 Aspose.Page API。

`PsDocument` 類別代表一個可在其上繪製圖形的 PostScript 文件。  

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟 1：建立矩形
首先，設定輸出串流、文件，並建立一個用於放置漸層的矩形。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## 步驟 2：建立水平線性漸層 Paint
`LinearGradientPaint` 是定義線性顏色過渡的核心類別。  
`LinearGradientPaint` 類別代表一個在直線上繪製漸層的 Paint 物件；您可以指定起始與結束點、顏色停點，並可選擇使用 `AffineTransform` 來將其縮放至形狀。

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## 步驟 3：填充矩形
現在使用剛才定義的漸層填充矩形。

```java
// Fill the rectangle
document.fill(rectangle);
```

## 步驟 4：使用漸層填充文字
您也可以將相同的漸層套用於文字，產生引人注目的視覺效果。

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## 步驟 5：使用漸層描邊文字
最後，使用漸層作為描邊顏色為文字描邊。

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|-------|----------------|-----|
| 漸層看起來被拉伸 | `AffineTransform` 縮放不正確 | 確保變換的寬度與高度與矩形的尺寸相符（範例中為 200 × 100）。 |
| 顏色看起來淡化 | Alpha 值設定過低 | 提高 alpha 成分（`new Color(r,g,b,alpha)` 中的第四個值）。 |
| 文字不可見 | 在繪製文字前未設定 Paint | 在任何 `fillAndStrokeText` 或 `outlineText` 呼叫之前，先呼叫 `document.setPaint(paint)` **before**。 |

## 常見問答
**Q:** 我可以在商業專案中使用 Aspose.Page for Java 嗎？  
**A:** 可以，Aspose.Page for Java 可用於商業專案。授權細節請參閱 [Aspose.Purchase](https://purchase.aspose.com/buy) 頁面。

**Q:** 有提供免費試用嗎？  
**A:** 有，您可在 [Aspose.Page for Java free trial](https://releases.aspose.com/) 頁面取得 Aspose.Page for Java 的免費試用。

**Q:** 我可以在哪裡找到更多文件與支援？  
**A:** 請造訪 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) 取得完整資源。社群協助請查看 [Aspose.Page forum](https://forum.aspose.com/c/page/39)。

**Q:** 如何取得臨時授權？  
**A:** 您可從 [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q:** Aspose.Page for Java 的系統需求是什麼？  
**A:** 請參考 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) 了解詳細系統需求。

---

**最後更新：** 2026-09-04  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose

## 相關教學

- [在 Java 中建立 PostScript 漸層 – 添加垂直漸層](/page/java/postscript-gradient-addition/vertical/)
- [如何在 Java PostScript 中使用 Aspose.Page Java 添加漸層：對角線漸層](/page/java/postscript-gradient-addition/diagonal/)
- [建立 PostScript 漸層 – 徑向漸層（Java）](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}