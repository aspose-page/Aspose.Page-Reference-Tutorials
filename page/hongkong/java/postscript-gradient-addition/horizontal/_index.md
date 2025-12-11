---
date: 2025-12-07
description: 學習如何在 Java PostScript 中使用 Linear Gradient Paint Java 為 Aspose.Page for
  Java 添加水平漸層。
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: 在 Java PostScript 中使用 Linear Gradient Paint 添加漸層
url: /zh-hant/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Linear Gradient Paint Java 在 Java PostScript 中添加漸層

## 介紹
在本完整教學中，您將學會如何透過 **Linear Gradient Paint Java** 在 PostScript 文件中建立美觀的水平漸層。Aspose.Page for Java 讓處理 PostScript、PDF 以及其他向量格式變得簡單，而 `LinearGradientPaint` 類別則提供對顏色過渡的細緻控制。完成本指南後，您即可在形狀 **以及** 文字上渲染漸層，為文件增添專業且吸睛的效果。

## 快速解答
- **需要的函式庫是什麼？** Aspose.Page for Java（支援 Linear Gradient Paint Java）。  
- **實作需要多長時間？** 基本漸層大約 10‑15 分鐘即可完成。  
- **需要授權嗎？** 生產環境必須使用臨時或正式授權。  
- **支援哪個 JDK 版本？** Java 8 或更新版本。  
- **我可以在形狀和文字上同時使用漸層嗎？** 可以 – 您可以使用相同的漸層填滿形狀或填充/描邊文字。

## 前置條件
在開始撰寫程式碼之前，請先確保具備以下項目：

- 已在機器上安裝 Java Development Kit (JDK)。  
- Aspose.Page for Java 函式庫。您可從 [Aspose.Page Java 文件](https://reference.aspose.com/page/java/) 下載。

## 匯入套件
在 Java 專案中匯入必要的套件。這些匯入讓您能使用圖形基元、漸層處理以及 Aspose.Page API。

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
首先設定輸出串流、文件，以及用來放置漸層的矩形。

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
在此建立 **Linear Gradient Paint Java** 物件，定義水平的顏色過渡。`AffineTransform` 會將漸層縮放至符合矩形的寬高。

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

## 步驟 3：填滿矩形
使用剛才定義的漸層來填滿矩形。

```java
// Fill the rectangle
document.fill(rectangle);
```

## 步驟 4：以漸層填滿文字
您也可以將相同的漸層套用於文字，產生醒目的視覺效果。

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## 步驟 5：以漸層描邊文字
最後，使用漸層作為描邊顏色來勾勒文字。

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|-------|----------------|-----|
| 漸層看起來被拉伸 | `AffineTransform` 縮放設定不正確 | 確保變換的寬度與高度與矩形尺寸相符（範例中為 200 × 100）。 |
| 顏色看起來淡化 | Alpha 值設定過低 | 提高 alpha 成分（`new Color(r,g,b,alpha)` 中的第四個值）。 |
| 文字不可見 | 在繪製文字前未設定 Paint | 在任何 `fillAndStrokeText` 或 `outlineText` 呼叫之前，先執行 `document.setPaint(paint)` **。** |

## 常見問答
### 我可以在商業專案中使用 Aspose.Page for Java 嗎？
是的，Aspose.Page for Java 可用於商業專案。授權細節請參閱 [Aspose.Purchase](https://purchase.aspose.com/buy)。

### 有提供免費試用嗎？
是的，您可在此取得 Aspose.Page for Java 的免費試用版 [here](https://releases.aspose.com/)。

### 我可以在哪裡找到更多文件與支援？
請造訪 [Aspose.Page Java 文件](https://reference.aspose.com/page/java/) 以取得完整資源。社群支援請參考 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39)。

### 如何取得臨時授權？
您可從 [Aspose.Purchase](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Aspose.Page for Java 的系統需求是什麼？
請參考 [文件](https://reference.aspose.com/page/java/) 了解詳細系統需求。

---

**最後更新：** 2025-12-07  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}