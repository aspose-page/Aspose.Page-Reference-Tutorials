---
date: 2026-02-15
description: 學習如何使用 Aspose.Page Java 為 Java PostScript 檔案添加斜紋圖案。本一步一步的指南展示完整程式碼與提示。
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 如何在 Java PostScript 中使用 Aspose.Page 添加剖面圖案
url: /zh-hant/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中添加 Hatch Pattern

## Introduction
如果您正在使用 **Aspose.Page Java** 並想了解 **如何在 PostScript 輸出中添加 hatch pattern**，hatch pattern 是一種快速且彈性的解決方案。在本教學中，我們將逐步說明 **如何在 PostScript 文件中添加 hatch** 設計，解釋其用途，並提供完整、可直接執行的程式碼範例。完成後，您只需幾行 Java 程式碼，即可建立視覺上吸引人的 hatch 填充形狀與文字。

## Quick Answers
- **需要哪個函式庫？** Aspose.Page for Java（“aspose page java” SDK）。  
- **我們要加入哪種視覺效果？** Hatch patterns（例如斜線、交叉線）。  
- **執行範例是否需要授權？** 開發階段可使用免費試用版；正式環境需購買授權。  
- **程式碼行數大約？** 約 70 行，分為明確的步驟。  
- **此方法能否套用於 PDF？** 可以——Aspose.Page 支援多種輸出格式，包括 PDF。

## How to Add Hatch Pattern – Overview
Hatch patterns 是向量式紋理，可在任何解析度下清晰呈現，且適用於單色印表機。使用 Aspose.Page Java，您可以將這些紋理套用於形狀、路徑，甚至文字，而無需處理低階 PostScript 指令。

## Prerequisites
在開始之前，請確保您已具備：

- **Java 開發環境** – JDK 8 以上及您選擇的 IDE。  
- **Aspose.Page for Java 函式庫** – 從官方網站[此處](https://releases.aspose.com/page/java/)下載最新 JAR。  
- **寫入權限** – 能寫入產生的 PostScript 檔案的資料夾。

## Import Packages
首先，將所需類別匯入專案。這些 import 讓您可以使用繪圖基元、顏色處理以及 Aspose.Page API。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Initial Parameters
建立輸出串流，設定頁面大小（A4），並定義在繪製每個 hatch 填充方格時會重複使用的版面變數。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Step 2: Save Graphics State and Translate
儲存圖形狀態可讓我們稍後返回原始座標系統，而 `translate` 則將原點移至方便的起始位置。

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Step 3: Create Square for Each Pattern
定義一個可重複使用的矩形，作為每個 hatch 填充格子的代表。

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Step 4: Set Up Pen for Pattern Square Outline
`BasicStroke` 設為 2 點，可為每個方格提供清晰的輪廓。

```java
BasicStroke stroke = new BasicStroke(2);
```

## Step 5: Iterate Through Hatch Patterns
遍歷 `HatchStyle` 列舉中的每個值，使用相應的紋理填充每個方格，然後繪製其輪廓。這是 **加入 hatch pattern** 功能的核心。

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Step 6: Restore Graphics State
在完成格子網格的繪製後，返回原始座標系統。

```java
document.writeGraphicsRestore();
```

## Step 7: Fill Text with Hatch Pattern
此範例示範如何使用 hatch 紋理為文字上色。範例將字串 “ABC” 填充為對角交叉圖案。

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Step 8: Outline Text with Hatch Pattern
現在為相同文字描邊，使用 70 % 的 hatch 風格與較粗的筆畫。

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Step 9: Close and Save Document
完成頁面、將檔案寫入磁碟，並釋放資源。

```java
document.closePage();
document.save();
```

依照上述步驟操作，即可得到一個展示完整 hatch pattern 套用於形狀與文字的 PostScript 檔案——全部由 **aspose page java** 提供支援。

## Why Use Hatch Patterns with Aspose.Page Java?
- **視覺區分度** – 即使印表機僅支援單色輸出，hatch 填充仍能清晰呈現。  
- **效能** – 紋理即時產生，避免使用大型影像檔案。  
- **跨格式支援** – 同一段程式碼只需微調，即可輸出 PDF、EPS 或 SVG。

## Common Pitfalls & Tips
- **檔案路徑錯誤** – 確認 `dataDir` 以正確的檔案分隔符（`/` 或 `\`）結尾。  
- **不支援的顏色** – 部分舊版 PostScript 直譯器可能無法處理某些色彩空間；建議使用基本的 RGB 以獲得最高相容性。  
- **授權警告** – 未使用有效授權執行範例會在輸出中嵌入浮水印。

## Conclusion
加入 hatch pattern 可大幅提升技術圖紙、地圖或任何由 Java 產生的圖形之可讀性與美觀度。使用 **Aspose.Page Java**，您可透過簡潔的 API 抽象低階 PostScript 指令，讓您專注於設計而非檔案格式的細節。現在您已了解 **如何在 PostScript 文件中加入 hatch pattern**——可嘗試不同的 `HatchStyle` 值，以打造所需的外觀。

## Frequently Asked Questions

**Q: 我可以將 Aspose.Page Java 與其他 Java 框架一起使用嗎？**  
A: 可以，該函式庫與框架無關，支援 Spring、Jakarta EE、Android（有限支援）以及純 Java SE。

**Q: Aspose.Page Java 有提供試用版嗎？**  
A: 當然有。可於[此處](https://releases.aspose.com/)下載免費 30 天試用版。

**Q: 如何取得開發用的臨時授權？**  
A: 可於[此處](https://purchase.aspose.com/temporary-license/)申請臨時授權，能移除評估浮水印。

**Q: 我在哪裡可以找到更多教學與社群支援？**  
A: 請前往官方論壇 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)取得更多範例與問答。

**Q: 是否有完整的類別與方法文件？**  
A: 有，完整的 API 參考文件可於[此處](https://reference.aspose.com/page/java/)取得。

**Q: 我可以將相同的 hatch pattern 輸出為 PDF 而非 PostScript 嗎？**  
A: 當然可以。只需將 `PsSaveOptions` 改為 `PdfSaveOptions`（或等效設定），其餘程式碼保持不變。

**Q: 若產生的檔案為空白該怎麼辦？**  
A: 請確認輸出串流指向可寫入的目錄，且在所有繪圖操作完成後已呼叫 `document.save()`。

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}