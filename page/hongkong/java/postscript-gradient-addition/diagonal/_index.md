---
date: 2026-09-04
description: 了解如何在 Java PostScript 中使用 Aspose.Page Java 添加漸層，透過 LinearGradientPaint
  建立對角線色彩過渡，打造生動的文件。
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 如何在 Java PostScript 中使用 Aspose.Page Java 添加漸層：對角線漸層
og_description: 了解如何在 Java PostScript 中使用 Aspose.Page Java 添加漸層。本指南將示範如何僅透過幾個步驟，使用
  LinearGradientPaint 建立對角線漸層。
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: 如何在 Java PostScript 中使用 Aspose.Page Java 添加漸層
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 如何在 Java PostScript 中使用 Aspose.Page Java 添加漸層：對角線漸層
url: /zh-hant/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page Java 在 Java PostScript 中添加對角漸層

## 介紹
如果您想為 PostScript 檔案加入平滑的對角色彩過渡，**Aspose.Page Java** 讓這個過程變得相當簡單。在本教學中，您將一步步學會 **如何添加漸層** 效果，使用 Java 2D 的 `LinearGradientPaint` 類別。完成後，您將擁有一段可直接執行的程式碼，能產生帶有鮮豔對角漸層的 PostScript 文件，並了解此方法相較於手寫原始 PostScript 指令更易維護的原因。

## 如何在 Java PostScript 中添加漸層
添加漸層看似只屬於圖形處理的工作，但使用 Aspose.Page，您可以在純 Java 環境下同時掌控底層的 PostScript 指令。本節說明此方法的原理以及相較於手寫原始 PostScript 可獲得的好處。

## 快速答覆
- **需要哪個函式庫？** Aspose.Page for Java。  
- **哪個類別負責建立漸層？** `LinearGradientPaint`。  
- **可以更改顏色嗎？** 可以 – 只要修改 `Color[]` 陣列。  
- **正式環境需要授權嗎？** 需要商業授權；亦提供免費試用版。  
- **實作大約需要多久？** 基本漸層約 10 分鐘即可完成。

## 什麼是 Aspose.Page Java？
Aspose.Page Java 是一套功能完整的 API，讓開發者在不依賴任何外部軟體的情況下，產生、編輯與轉換 PostScript 與 PDF 檔案。此函式庫支援 **超過 50 種輸入與輸出格式**，且可處理 **超過 500 頁** 的文件，同時將記憶體使用量控制在 100 MB 以下。

## 為什麼使用對角漸層？
對角漸層能為圖表、橫幅或任何需要現代感的圖形元素增添深度與視覺趣味。由於漸層從一個角落延伸至對角的另一個角落，它非常適合作為背景、按鈕外觀或裝飾形狀，提供專業的完成度而不需額外的影像資源。

## 前置條件
在開始之前，請確保您已具備：

- Java Development Kit (JDK) 8 或更新版本。  
- 如 Eclipse、IntelliJ IDEA 或 VS Code 等開發環境。  
- **Aspose.Page for Java** 函式庫 – 從[官方下載頁面](https://releases.aspose.com/page/java/)取得最新版本。

## 匯入套件
`java.awt` 套件提供核心圖形類別，而 `com.aspose.page` 套件則讓您存取 PostScript 專屬的 API。

`LinearGradientPaint` 類別是 Aspose.Page 與 Java 2D 漸層功能的橋樑。  
`AffineTransform` 則用於旋轉與縮放漸層，使其呈對角方向。

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

## 步驟 1：為 PostScript 文件建立輸出串流
首先，定義檔案要儲存的資料夾，並開啟 `FileOutputStream`。此串流負責接收產生的 PostScript 資料。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## 步驟 2：使用 A4 大小建立儲存選項
`PsSaveOptions` 讓您指定頁面尺寸、解析度與其他輸出設定。此處使用預設的 A4 大小，對應 595 × 842 點，解析度為 72 dpi。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## 步驟 3：建立新 PS 文件
`PsDocument` 類別代表一個 PostScript 文件，提供建立頁面與繪製圖形的方法。  
使用輸出串流與儲存選項實例化 `PsDocument`。`false` 參數表示建構子不會自動開啟新頁面 – 我們稍後自行開啟。

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 4：建立矩形
定義將接受漸層填色的矩形。矩形位置為 (200, 100)，尺寸為 (200 × 100)，以確保漸層清晰可見。

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## 步驟 5：建立漸層變換
`AffineTransform` 讓我們旋轉、縮放與平移漸層，使其對角跨越矩形。以下數學計算斜邊長並相應調整縮放比例。

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## 步驟 6：建立對角線性漸層畫筆
`LinearGradientPaint` 是產生顏色過渡的核心類別。它從矩形左上角延伸至右下角，並使用先前定義的變換。`MultipleGradientPaint.CycleMethod.NO_CYCLE` 確保漸層不會重複。

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## 步驟 7：設定畫筆並填滿矩形
將漸層畫筆套用至文件，並填滿矩形形狀。此步驟會在 PostScript 頁面上繪製出對角色彩過渡。

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## 步驟 8：關閉當前頁面並儲存文件
最後，關閉頁面、刷新串流，並儲存檔案。產生的 `DiagonalGradient_outPS.ps` 檔案可使用任何 PostScript 檢視器開啟。

```java
// Close current page and save the document
document.closePage();
document.save();
```

## 常見問題與技巧
- **漸層呈現平坦** – 再次確認旋轉角度；45° 旋轉才能產生真正的對角。  
- **顏色顯得黯淡** – 請使用 `MultipleGradientPaint.ColorSpaceType.SRGB` 以確保顏色正確渲染。  
- **找不到檔案錯誤** – 確認 `dataDir` 指向已存在的資料夾，且應用程式具備寫入權限。  
- **大型文件導致記憶體激增** – 使用 `PsSaveOptions.setCompress(true)` 以降低記憶體佔用。

## 常見問答

**Q: 我可以使用此函式庫在 Java 中執行其他圖形操作嗎？**  
A: 可以，Aspose.Page for Java 提供完整的繪圖基元、文字渲染與影像處理功能。

**Q: Aspose.Page Java 有免費試用版嗎？**  
A: 當然有。您可以從[Aspose 免費試用頁面](https://releases.aspose.com/)下載功能完整的試用版。

**Q: 哪裡可以找到 Aspose.Page Java 的文件？**  
A: 官方 API 參考文件位於[ Aspose.Page Java API 參考](https://reference.aspose.com/page/java/)。

**Q: 我要如何購買 Aspose.Page Java 的授權？**  
A: 可直接於[ Aspose 購買入口](https://purchase.aspose.com/buy)取得授權。

**Q: 需要協助或有其他問題？**  
A: 前往社群驅動的[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)尋求 Aspose 工程師與其他開發者的協助。

---

**最後更新：** 2026-09-04  
**測試環境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose

## 相關教學

- [在 PostScript 中使用 Aspose.Page for Java 建立徑向漸層](/page/java/postscript-gradient-addition/)
- [使用 Linear Gradient Paint 在 Java PostScript 中添加漸層](/page/java/postscript-gradient-addition/horizontal/)
- [在 Java 中建立 PostScript 漸層 – 添加垂直漸層](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}