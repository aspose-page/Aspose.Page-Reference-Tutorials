---
date: 2026-10-31
description: 了解如何在 Java PostScript 中使用 Aspose.Page 設定 paint color 並填充 ellipse。本指南示範如何填充
  ellipse、繪製 ellipse 輪廓，以及使用清晰的程式碼步驟設定 stroke thickness。
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: 在 Java PostScript 中加入 ellipse
og_description: 了解如何在 Java PostScript 中使用 Aspose.Page 填充 ellipse 並設定 paint color。遵循一步一步的程式碼，即可在數秒內繪製填充及輪廓
  ellipse。
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: 如何在 Java PostScript 中填充 ellipse 並設定 paint color
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: 如何在 Java PostScript 中填充 ellipse 並設定 paint color
url: /zh-hant/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中填滿橢圓並設定繪圖顏色

## 介紹
如果您在繪製向量圖形時需要 **設定繪圖顏色**，Aspose.Page for Java 函式庫可讓您完整掌控每一次的筆畫與填色。在本教學中，您將學會如何 **設定繪圖顏色**、**填滿橢圓**，以及 **繪製橢圓輪廓**，採用簡單的逐步方式。完成後，您即可在發票、報告或任何可列印文件中加入高品質的 PostScript 橢圓。

## 快速回答
- **哪個函式庫最適合在 Java 中繪製 PostScript 圖形？** Aspose.Page for Java。  
- **我可以使用純色填滿橢圓嗎？** 可以 – 在 `fill` 之前使用 `document.setPaint(Color.YOUR_COLOR)`。  
- **如何只繪製橢圓的輪廓？** 設定繪圖顏色與筆畫，然後呼叫 `document.draw(...)`。  
- **正式使用是否需要授權？** 需要商業授權；測試時可使用臨時授權。  
- **支援哪個 Java 版本？** 任何 Java 8 以上的執行環境皆可與目前的 Aspose.Page 版本相容。

## 什麼是 PostScript 橢圓？
PostScript 橢圓是一種以邊界矩形定義的向量形狀。與點陣圖不同，它可在不失真的情況下自由縮放，非常適合高解析度列印與 PDF 轉換。由於形狀以數學方式描述，無論以何種尺寸或解析度渲染，都能保持清晰的邊緣與平滑的曲線。

## 為何使用 Aspose.Page 來建立 PostScript 橢圓？
Aspose.Page 為您提供對每個繪圖基元的確定性控制。它支援 **3 大作業系統（Windows、Linux、macOS）**、**0 個原生相依性**，且在一般伺服器上每秒可渲染 **50+ 個向量基元**。此函式庫純粹以 Java 實作，您可在任何 Java 8 以上的應用程式中嵌入，無需額外的原生函式庫。

## 前置條件
在開始之前，請確保您已具備：

1. 可正常運作的 Java 開發環境（JDK 8 或更新版本）。  
2. 已將 Aspose.Page for Java 函式庫加入您的專案。您可從 **[Aspose.Page for Java 釋出頁面](https://releases.aspose.com/page/java/)** 下載。

## 匯入套件
在您的 Java 原始碼檔案中，匯入繪製與儲存 PostScript 內容所需的類別。

`java.awt` 套件提供基本的圖形類型，如 `Color`、`Ellipse2D` 與 `BasicStroke`。`com.aspose.page` 套件則提供負責寫入 PostScript 輸出的 `PsDocument` 類別。

- **`Color`** – 代表用於繪圖的 sRGB 顏色。  
- **`Ellipse2D`** – 描述以邊界矩形定義的橢圓形狀。  
- **`BasicStroke`** – 指定繪製輪廓的線寬、虛線樣式與端點樣式。  
- **`PsDocument`** – 代表 PostScript 文件，提供繪圖與頁面管理的方法。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 如何為橢圓設定繪圖顏色
第一步是告訴文件下一個繪圖操作要使用哪種顏色。`setPaint` 方法會設定一個純色，之後的填色或筆畫都會套用此顏色，視後續的呼叫而定。

### 步驟 1：設定 PostScript 文件
建立輸出串流、設定頁面尺寸，並實例化 `PsDocument`。

`PsDocument` 是代表記憶體中 PostScript 檔案的核心類別。所有繪圖指令皆透過此物件傳遞，它負責頁面版面配置、資源管理與最終檔案產生。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步驟 2：填滿橢圓 – 使用設定繪圖顏色
若要 **填滿橢圓**，必須先以欲填充的顏色呼叫 `setPaint`，再以 `Ellipse2D` 例項呼叫 `fill`。

`setPaint` 設定後續填色或筆畫所使用的目前繪圖顏色。  
`Ellipse2D` 定義橢圓的幾何邊界；其建構子接受左上角的 X、Y 座標以及寬度與高度。

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 步驟 3：繪製橢圓輪廓並設定筆畫粗細
填色完成後，您可以將繪圖顏色改為其他顏色，定義 `BasicStroke` 以控制線寬，然後繪製橢圓輪廓。

`BasicStroke` 指定繪製輪廓的線寬、虛線樣式與端點樣式。透過調整其 `width` 屬性，即可控制橢圓邊框的粗細程度。

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 步驟 4：關閉並儲存文件
完成頁面並將 PostScript 檔寫入磁碟。

呼叫 `document.close()` 會將所有待處理的繪圖指令寫入，並釋放資源。產生的 `.ps` 檔可使用任何 PostScript 檢視器開啟，或轉換為 PDF。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

現在您已擁有一個包含兩個橢圓的 PostScript 檔——一個以橙色填滿，另一個以紅色描邊。隨意嘗試不同的座標、尺寸與顏色，以符合您的設計需求。

## 常見問題與除錯
- **檔案路徑不正確** – 確認 `dataDir` 以適合您作業系統的分隔符（`/` 或 `\\`）結尾。  
- **缺少授權** – 若未取得有效授權，函式庫會以評估模式執行，可能會加入浮水印。  
- **顏色未套用** – 記得在每次 `fill` 或 `draw` 呼叫之前設定 `document.setPaint(...)`；繪圖顏色設定不會自動跨不同操作保留。

## 常見問答

**Q: 我可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Page for Java 設計上能與其他 Java 函式庫無縫整合。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 可從 **[Aspose 臨時授權頁面](https://purchase.aspose.com/temporary-license/)** 取得臨時授權，以供測試使用。

**Q: Aspose.Page 適用於商業專案嗎？**  
A: 絕對適用！請前往 **[Aspose 購買頁面](https://purchase.aspose.com/buy)** 了解商業使用的授權方案。

**Q: 我可以在哪裡尋求協助或討論 Aspose.Page 相關問題？**  
A: 加入 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 社群，參與討論與取得協助。

**Q: 有哪些免費資源可深入了解 Aspose.Page for Java？**  
A: 可使用 **[Aspose 免費試用頁面](https://releases.aspose.com/)**，並在文件中探索範例。

## 結論
Aspose.Page for Java 讓 **設定繪圖顏色**、**填滿橢圓** 與 **繪製橢圓輪廓** 變得相當簡單——無論您需要簡單的填色形狀或複雜的筆畫圖形。依照上述步驟，您即可快速將專業等級的向量圖形加入任何可列印文件。若想深入探索，例如結合多個形狀、套用漸層或轉換為 PDF，請參考官方的 **[Aspose.Page Java 文件](https://reference.aspose.com/page/java/)**。

**最後更新：** 2026-10-31  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose

## 相關教學

- [如何在 Java PostScript 中使用 Aspose.Page 繪製矩形](/page/java/postscript-shapes/add-rectangle/)
- [如何在 Java PostScript 中使用 Aspose.Page 新增 Unicode 文字](/page/java/postscript-text-manipulation/add-text-unicode/)
- [如何在 PostScript 中使用 Aspose.Page for Java 建立徑向漸層](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}