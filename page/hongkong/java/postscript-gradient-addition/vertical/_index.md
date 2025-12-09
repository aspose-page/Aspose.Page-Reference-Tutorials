---
date: 2025-12-09
description: 學習如何在 Java 中使用 Aspose.Page 建立 PostScript 漸層。此一步一步的指南會教您如何輕鬆地在 PostScript
  文件中加入垂直漸層。
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: 在 Java 中建立 PostScript 漸層 – 加入垂直漸層
url: /zh-hant/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中建立 PostScript 漸層 – 新增垂直漸層

## Introduction
在本完整教學中，您將學習如何使用 Aspose.Page for Java **在 Java 中建立 PostScript 漸層**。新增垂直漸層可以讓您的文件更具活力與專業感，只需幾行程式碼即可呈現驚豔的視覺效果。我們會逐步帶您走過每個步驟，說明每個環節的重要性，並提供實用技巧以避免常見陷阱。  
在本指南中，我們將 **一步一步建立 postscript 漸層 java**。

## Quick Answers
- **需要的函式庫是什麼？** Aspose.Page for Java  
- **我可以自訂顏色嗎？** 可以，任何 `java.awt.Color` 都可使用  
- **支援旋轉嗎？** 可以，您可以使用 `AffineTransform` 旋轉漸層  
- **產生的輸出格式為何？** 標準的 PostScript (.ps) 檔案  
- **正式環境需要授權嗎？** 需要，必須購買商業授權  

## Prerequisites
在深入教學之前，請確保已具備以下前置條件：
- 已在電腦上安裝 Java Development Kit (JDK)。  
- Aspose.Page for Java 函式庫。您可於 [此處](https://releases.aspose.com/page/java/) 下載。

## Import Packages
在您的 Java 專案中，匯入必要的套件以開始使用：

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

現在，讓我們將在 Java PostScript 中新增垂直漸層的過程分解為多個步驟。

## 如何在 Java 中建立 PostScript 漸層
以下是逐步指南，說明如何使用 Aspose.Page API **在 Java 中建立 PostScript 漸層**。

### 步驟 1：設定文件目錄
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步驟 2：為 PostScript 文件建立輸出串流
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### 步驟 3：使用 A4 大小建立儲存選項
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### 步驟 4：建立新的 PS 文件
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步驟 5：建立矩形
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### 步驟 6：設定漸層的顏色與比例
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### 步驟 7：建立漸層變換
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### 步驟 8：建立垂直線性漸層 Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### 步驟 9：設定 Paint 並填滿矩形
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### 步驟 10：關閉當前頁面並儲存文件
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

恭喜！您已成功使用 Aspose.Page for Java 為 Java PostScript 文件新增垂直漸層。

## 為什麼在 PostScript 中使用垂直漸層？
垂直漸層能為頁面增添深度與視覺趣味，同時不會大幅增加檔案大小。它特別適用於：
- 報告的頁首與頁尾  
- 圖表或示意圖的背景填充  
- 技術文件中段落的突顯  

## 常見問題與解決方案
- **漸層看起來平坦：** 確認 `AffineTransform` 的縮放比例與矩形尺寸相符。  
- **顏色顯得淡薄：** 確認使用正確的 `ColorSpaceType`（SRGB），且比例陣列的順序為 0.0 到 1.0。  
- **檔案未產生：** 檢查輸出目錄 (`dataDir`) 是否存在，且應用程式具有寫入權限。  

## 常見問答
### 我可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？
可以，Aspose.Page for Java 設計上能與其他 Java 函式庫無縫整合。

### 是否提供 Aspose.Page for Java 的免費試用？
可以，您可於 [此處](https://releases.aspose.com/) 取得免費試用。

### 我可以在哪裡找到更多文件？
詳細文件可於 [此處](https://reference.aspose.com/page/java/) 取得。

### 我要如何購買 Aspose.Page for Java？
您可於 [此處](https://purchase.aspose.com/buy) 購買 Aspose.Page for Java。

### 是否有 Aspose.Page 討論論壇？
可以，您可於 [此處](https://forum.aspose.com/c/page/39) 加入社群論壇。

## Additional Frequently Asked Questions

**Q: 我可以建立其他方向的漸層（水平、對角線）嗎？**  
A: 當然可以。調整 `LinearGradientPaint` 的起點與終點，並在 `AffineTransform` 中修改旋轉角度。

**Q: 這也適用於 PDF 輸出嗎？**  
A: 相同的漸層邏輯可在儲存為 PDF 時使用 `PdfSaveOptions` 取代 `PsSaveOptions` 來套用。

**Q: 我要如何動態變更漸層大小？**  
A: 在執行時計算矩形尺寸，並將這些值傳遞給 `Rectangle2D` 與 `AffineTransform` 的建構子。

---

**最後更新：** 2025-12-09  
**測試環境：** Aspose.Page for Java 24.11（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}