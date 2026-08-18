---
date: 2026-08-18
description: 了解如何使用 Aspose.Page Java 為 Java PostScript 檔案加入交叉陰影圖案。本逐步指南展示完整程式碼與技巧。
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: 在 Java PostScript 中加入交叉陰影圖案
og_description: 了解如何使用 Aspose.Page 在 Java PostScript 中加入交叉陰影圖案。遵循本逐步教學，可快速建立填充交叉陰影的圖形。
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: 如何在 Java PostScript 中加入交叉陰影圖案 – Aspose.Page 指南
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: 如何在 Java PostScript 中加入交叉陰影圖案
url: /zh-hant/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中加入交叉圖案

## 介紹
如果您正在使用 **Aspose.Page Java**，並且想了解 **如何加入交叉圖案** 到您的 PostScript 輸出，交叉圖案是一種快速且彈性的解決方案。在本教學中，我們將逐步說明 **如何加入交叉** 設計到 PostScript 文件，解釋其用途，並提供完整、可直接執行的程式碼範例。完成後，您只需幾行 Java 程式碼即可建立視覺上吸引人的交叉填充形狀與文字。

## 快速回答
- **需要哪個函式庫？** Aspose.Page for Java（“aspose page java” SDK）。  
- **我們要加入哪種視覺效果？** 交叉圖案（例如對角線、交叉陰影）。  
- **執行範例是否需要授權？** 免費試用可用於開發；正式環境需購買授權。  
- **程式碼行數多少？** 約 70 行，分為清晰的步驟。  
- **可以將相同方法套用於 PDF 嗎？** 可以 — Aspose.Page 支援多種輸出格式，包括 PDF。

## 什麼是交叉圖案？
交叉圖案是一種基於向量的填充，由重複的線條或形狀組成，可產生紋理效果。由於其以數學方式定義，圖案在放大縮小時不會失真，適合高解析度列印與單色輸出。

## 為什麼在 Aspose.Page Java 中使用交叉圖案？
Aspose.Page 支援 **10+ 輸出格式**（包括 PostScript、PDF、EPS、SVG 與 XPS），且可在最多 **500 頁** 的文件上渲染交叉填充，而無需將整個檔案載入記憶體。這意味著您能獲得快速的效能、低記憶體佔用，且在所有支援的格式中呈現一致的視覺效果。

## 如何加入交叉圖案 – 概觀
交叉圖案是向量式紋理，可在任何解析度下清晰呈現，且適用於單色印表機。使用 Aspose.Page Java，您可以將這些圖案套用於形狀、路徑，甚至文字，而無需處理低階的 PostScript 指令。

## 前置條件
在開始之前，請確保您已具備：

- **Java 開發環境** – JDK 8 或更高版本，搭配您喜好的 IDE。  
- **Aspose.Page for Java 函式庫** – 從官方 **Aspose.Page for Java 下載頁面** [here](https://releases.aspose.com/page/java/) 下載最新的 JAR。  
- 您也可以在此處[here](https://releases.aspose.com/) 瀏覽其他 Aspose 版本。  
- **寫入權限** – 需要對儲存產生的 PostScript 檔案的資料夾具有寫入權限。

## 匯入套件
以下匯入語句包含標準的 Java AWT 類別，用於圖形基元（如顏色、筆畫與幾何形狀），以及 Aspose.Page 類別，提供文件模型、交叉樣式定義與產生 PostScript 檔案所需的儲存選項。  
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

## `Document` 類別是什麼？
`Document` 類別是 Aspose.Page 的頂層物件，代表記憶體中的單一 PostScript 檔案。所有繪圖操作皆透過此物件執行。

## 如何設定輸出串流？
要寫入輸出，請建立指向目標檔案路徑的 `FileOutputStream`；此串流負責低階位元組寫入。`PsSaveOptions` 用於設定文件的儲存方式，包括頁面大小與壓縮。接著以設定好頁面大小、壓縮與其他 PostScript 專屬設定的 `PsSaveOptions` 物件建立 `Document` 實例。  
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

## 如何保存圖形狀態並平移原點？
保存圖形狀態會捕獲當前的變換矩陣、裁剪區域與繪圖屬性，讓您之後可以還原。保存後，對圖形物件呼叫 `translate(x, y)`，將原點平移至繪製交叉方格網格的便利位置。  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## 如何為每個圖案建立可重複使用的方形？
`Rectangle2D` 代表由位置與尺寸定義的矩形形狀。透過建立與格子尺寸相符的單一實例，您可以在每個交叉填充方格中重複使用，減少物件分配並保持繪圖迴圈的效能。  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## 如何為圖案方格輪廓設定筆刷？
`BasicStroke` 描述向量形狀的輪廓粗細、虛線樣式與端點樣式。使用 2 點的 `BasicStroke` 可為每個交叉填充的格子提供清晰的邊框，確保填充與相鄰格子在視覺上分離。  
```java
BasicStroke stroke = new BasicStroke(2);
```

## 如何遍歷交叉圖案？
`HatchStyle` 是列舉型別，列出所有預定義的交叉圖案，如對角線、交叉與點狀樣式。遍歷 `HatchStyle.values()` 可依序套用每種圖案，使用 `HatchBrush` 填充矩形，然後繪製其輪廓。  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## 繪製完成後如何還原圖形狀態？
在圖形物件上呼叫 `restore()` 會將變換矩陣與繪圖設定還原至先前保存的狀態，避免累積的平移或縮放影響後續的繪製操作。這確保後續內容從原始座標系統開始，並使用預設屬性。  
```java
document.writeGraphicsRestore();
```

## 如何使用交叉圖案填充文字？
`TextFragment` 代表可獨立定位與樣式設定的文字片段。將帶有選定 `HatchStyle` 的 `HatchBrush` 指派給片段的填充，即可使用交叉紋理而非純色來繪製文字字元。  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## 如何以不同的交叉樣式描邊文字？
`HatchBrush` 也可用於描邊。若要繪製輪廓，將片段的筆畫設定為具有不同 `HatchStyle`（例如 70 % 交叉）的 `HatchBrush`，並透過 `setStrokeWidth` 增加筆寬。如此即可以自身的交叉圖案呈現文字邊框，同時保留填充的內部。  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## 如何關閉並儲存文件？
`document.save()` 會將記憶體中的文件寫入指定的輸出串流。完成所有繪圖指令後，呼叫此方法，然後關閉 `FileOutputStream` 以釋放系統資源，確保檔案正確寫入磁碟。  
```java
document.closePage();
document.save();
```

遵循上述步驟，您將得到一個展示完整交叉圖案套用於形狀與文字的 PostScript 檔案——全部由 **aspose page java** 提供支援。

## 常見陷阱與提示
- **檔案路徑錯誤** – 確認 `dataDir` 以正確的檔案分隔符（`/` 或 `\`）結尾。  
- **不支援的顏色** – 某些較舊的 PostScript 直譯器可能無法處理特定色彩空間；建議使用基本的 RGB 以獲得最高相容性。  
- **授權警告** – 未使用有效授權執行範例會在輸出中嵌入浮水印。

## 常見問答

**Q: 我可以在其他 Java 框架中使用 Aspose.Page Java 嗎？**  
A: 可以，該函式庫與框架無關，支援 Spring、Jakarta EE、Android（有限）以及純 Java SE。

**Q: 是否提供 Aspose.Page Java 的試用版？**  
A: 當然。下載免費 30 天試用版 [Aspose trial download page](https://releases.aspose.com/)。

**Q: 如何取得開發用的臨時授權？**  
A: 申請臨時授權 [temporary license request page](https://purchase.aspose.com/temporary-license/)。此授權會移除評估浮水印。

**Q: 我可以在哪裡找到更多教學與社群支援？**  
A: 前往官方論壇 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) 取得更多範例與問答。

**Q: 是否有完整的類別與方法文件？**  
A: 有，完整的 API 參考可在此取得 [Aspose.Page Java API reference](https://reference.aspose.com/page/java/)。

**Q: 我可以將相同的交叉圖案渲染成 PDF 而非 PostScript 嗎？**  
A: 當然。將 `PsSaveOptions` 改為 `PdfSaveOptions`（或等效設定），其餘程式碼保持不變。

**Q: 若產生的檔案為空白該怎麼辦？**  
A: 確認輸出串流指向可寫入的目錄，且在所有繪圖操作完成後已呼叫 `document.save()`。

**最後更新:** 2026-08-18  
**測試環境:** Aspose.Page for Java 24.12 (latest at time of writing)  
**作者:** Aspose

## 相關教學

- [在 PostScript 中建立紋理圖案 – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [如何在 Java PostScript 中使用 Aspose.Page Java 添加漸層：對角線漸層](/page/java/postscript-gradient-addition/diagonal/)
- [如何使用 Aspose.Page Java API 將 PostScript 轉換為 PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}