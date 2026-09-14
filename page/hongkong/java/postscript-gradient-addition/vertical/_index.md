---
date: 2026-09-14
description: 了解如何使用 Aspose.Page 建立 PostScript 漸層 Java。本分步指南將向您展示如何僅用幾行 Java 程式碼在 PostScript
  檔案中加入垂直漸層。
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: 在 Java PostScript 中加入垂直漸層
og_description: 了解如何使用 Aspose.Page 建立 PostScript 漸層 Java。本分步指南將向您展示如何僅用幾行 Java 程式碼在
  PostScript 檔案中加入垂直漸層。
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: 建立 PostScript 漸層 Java – 垂直漸層
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: 建立 PostScript 漸層 Java – 垂直漸層
url: /zh-hant/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 PostScript 漸層 Java – 垂直漸層

## 介紹
Aspose.Page for Java 是一個可程式化建立與操作 PostScript 與 PDF 檔案的函式庫。在本完整教學中，您將學習如何使用該函式庫 **create postscript gradient java**。加入垂直漸層可以讓文件看起來更鮮明且專業，只需幾行程式碼即可實現驚豔的視覺效果。我們會逐步帶領您，說明每個步驟的原因，並提供實用技巧以避免常見陷阱。完成本指南後，您將能產生具有平滑、吸睛垂直顏色過渡的 PostScript 檔案。

## 快速回答
- **需要哪個函式庫？** Aspose.Page for Java  
- **我可以自訂顏色嗎？** 是的，任何 `java.awt.Color` 都可以使用  
- **支援旋轉嗎？** 是的，您可以使用 `AffineTransform` 旋轉漸層  
- **產生的輸出格式為何？** 標準的 PostScript (.ps) 檔案  
- **商業使用是否需要授權？** 是的，需要商業授權  

## 為何在 PostScript 文件中加入垂直漸層？
加入垂直漸層能為頁面增添深度、提升視覺層次，且因為漸層以向量形式定義而非點陣圖，檔案大小也能保持低。此技巧非常適合報告標題、技術手冊，或任何需要現代感且不犧牲可伸縮性的傳單。

## 前置條件
在深入教學之前，請確保您已具備以下前置條件：
- 已在機器上安裝 Java Development Kit (JDK)。  
- Aspose.Page for Java 函式庫。您可以從 [Aspose.Page for Java release page](https://releases.aspose.com/page/java/) 下載。

## 匯入套件
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

現在，讓我們一步一步走過加入垂直漸層的過程。

## 如何建立 PostScript 漸層 Java
載入您的 Java 環境，建立 `PsSaveOptions` 實例，並呼叫 `Document.save` —— 這是產生帶有垂直漸層的 PostScript 檔案的核心流程。API 會為您處理顏色插值、座標變換與頁面刷新，您只需專注於定義矩形與漸層參數。

### 步驟 1：設定文件目錄
`File` 物件代表輸出將寫入的資料夾。必須先建立目錄，否則在開啟串流時會拋出 `IOException`。
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步驟 2：建立 PostScript 文件的輸出串流
`FileOutputStream` 將二進位 PostScript 資料寫入磁碟。使用 `try‑with‑resources` 區塊可確保即使發生例外，串流也會被關閉。
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### 步驟 3：建立 A4 大小的儲存選項
`PsSaveOptions` 讓您指定頁面尺寸、DPI 以及是否嵌入字型。將尺寸設定為 A4（595 × 842 點）符合大多數可列印文件。
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### 步驟 4：建立新的 PS 文件
`Document` 是代表記憶體中單一 PostScript 檔案的最高層物件。所有繪圖指令皆對此物件發出。
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步驟 5：建立矩形
`Rectangle2D.Double` 定義將被漸層填滿的區域。矩形的座標以點為單位（1 點 = 1/72 英吋）。
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### 步驟 6：設定漸層的顏色與比例
`float[]` 陣列定義每個顏色停點的位置（0.0 到 1.0）。`Color` 物件保存實際的 RGB 值。您可以使用任何想要的 `java.awt.Color`。
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### 步驟 7：建立漸層變換
`AffineTransform` 會對漸層進行縮放與旋轉。對於純垂直漸層，只需縮放 Y 軸；若需要，可稍後再加入旋轉。
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### 步驟 8：建立垂直線性漸層 Paint
`LinearGradientPaint` 將矩形、顏色停點與變換結合。此物件稍後會傳遞給圖形上下文。
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### 步驟 9：設定 Paint 並填滿矩形
`Graphics2D.setPaint` 套用漸層，`fill` 則在先前定義的矩形內繪製。
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### 步驟 10：關閉當前頁面並儲存文件
呼叫 `document.save` 會將整個 PostScript 串流寫入輸出檔案，並釋放所有本機資源。
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

恭喜！您已成功使用 Aspose.Page for Java 為 Java PostScript 文件加入垂直漸層。

## 常見問題與解決方案
- **漸層看起來平坦**：請確保 `AffineTransform` 的縮放與矩形尺寸相符。  
- **顏色顯得黯淡**：請確認使用正確的 `ColorSpaceType`（SRGB），且 fractions 陣列的順序為 0.0 到 1.0。  
- **檔案未產生**：請檢查輸出目錄 (`dataDir`) 是否存在，且應用程式具有寫入權限。  

## 常見問答

**Q: 我可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？**  
A: 是的，Aspose.Page for Java 設計上能與其他 Java 函式庫（如 Apache Commons 或 Spring）無縫協作。

**Q: 是否提供 Aspose.Page for Java 的免費試用？**  
A: 是的，您可以取得免費試用 [free trial download page](https://releases.aspose.com/).

**Q: 我可以在哪裡找到更多文件？**  
A: 詳細文件可在 [Aspose.Page Java API reference](https://reference.aspose.com/page/java/) 取得。

**Q: 我要如何購買 Aspose.Page for Java？**  
A: 您可以在 [Aspose.Page purchase page](https://purchase.aspose.com/buy) 購買。

**Q: 是否有 Aspose.Page 討論論壇？**  
A: 是的，您可以加入社群論壇 [Aspose.Page community forum](https://forum.aspose.com/c/page/39)。

## 其他常見問答

**Q: 我可以建立其他方向的漸層（水平、對角線）嗎？**  
A: 當然可以。調整 `LinearGradientPaint` 的起點與終點，並在 `AffineTransform` 中修改旋轉角度。

**Q: 這也適用於 PDF 輸出嗎？**  
A: 相同的漸層邏輯可在儲存為 PDF 時使用 `PdfSaveOptions` 取代 `PsSaveOptions` 來套用。

**Q: 如何動態變更漸層大小？**  
A: 在執行時計算矩形尺寸，並將這些值傳遞給 `Rectangle2D` 與 `AffineTransform` 的建構子。

---

**最後更新：** 2026-09-14  
**測試環境：** Aspose.Page for Java 24.11（最新）  
**作者：** Aspose

## 相關教學

- [在 PostScript 中使用 Aspose.Page for Java 建立徑向漸層](/page/java/postscript-gradient-addition/)
- [如何使用 Aspose.Page Java API 將 PostScript 轉換為 PDF](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page 透明度教學 – 在 Java PostScript 中加入透明度](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}