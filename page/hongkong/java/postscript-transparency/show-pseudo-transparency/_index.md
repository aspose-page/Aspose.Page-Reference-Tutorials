---
date: 2026-10-04
description: 了解如何使用 Aspose.Page 在 Java 中建立偽透明效果。按照我們的逐步指南，在 PostScript 檔案中加入鮮豔的圖形。
keywords:
- create pseudo transparency java
- Aspose.Page Java
- PostScript pseudo transparency
lastmod: 2026-10-04
linktitle: 在 Java PostScript 中顯示偽透明效果
og_description: 使用 Aspose.Page 在 Java 中建立偽透明效果，以產生鮮豔的 PostScript 圖形。本指南在數分鐘內帶您完成設定、程式碼與除錯。
og_image_alt: Aspose.Page Java tutorial showing pseudo transparency in PostScript
og_title: 使用 Aspose.Page 在 Java 中建立偽透明效果教學
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to create pseudo transparency java using Aspose.Page. Follow
    our step‑by‑step guide to add vibrant graphics in PostScript files.
  headline: How to create pseudo transparency java with Aspose.Page
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java is available for commercial use. You can purchase
      a license **[purchase Aspose.Page license](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: Yes, you can get a free trial **[download free trial](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Detailed documentation is available **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)**.
    question: Where can I find additional documentation?
  - answer: You can obtain a temporary license **[temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for testing purposes?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**.
    question: Need help or want to discuss Aspose.Page?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- pseudo transparency
- Aspose.Page
- Java PostScript
title: 如何使用 Aspose.Page 在 Java 中建立偽透明效果
url: /zh-hant/java/postscript-transparency/show-pseudo-transparency/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript 偽透明與 Aspose.Page

## 簡介
在本完整教學中，您將使用 Aspose.Page for Java **建立偽透明 Java** 圖形。我們會一步步說明——從安裝函式庫到繪製兩個重疊的矩形，以在 PostScript 檔案中模擬透明效果。完成後，您將了解偽透明的重要性、實作方式，以及如何調整顏色與漸層以符合自己的設計。

## 快速回答
- **偽透明是什麼意思？** 它透過混合半透明漸層來模擬透明效果。  
- **需要哪個函式庫？** Aspose.Page for Java。  
- **執行範例是否需要授權？** 開發階段可使用免費試用版；正式上線則需商業授權。  
- **可以使用哪種 IDE？** 任何支援 Java 8+ 的 Java IDE（IntelliJ IDEA、Eclipse、VS Code）。  
- **實作需要多久時間？** 基本範例大約需要 10‑15 分鐘。

## 什麼是 Java PostScript 中的偽透明？
偽透明是一種使用半透明漸層填充來呈現透視效果的技術。由於傳統 PostScript 不支援真實的 alpha 通道，Aspose.Page 透過疊加半透明形狀來模擬。調整漸層的不透明度值，即可在不需要原生 alpha 支援的情況下，模擬不同程度的透明度。

## 為什麼要使用 Aspose.Page 來實作偽透明？
Aspose.Page 支援 **30+ 輸出格式**（包括 EPS、PDF、SVG 和 PNG），且能在不將整個檔案載入記憶體的情況下渲染數百頁文件。其跨平台 Java API 讓您能細緻控制顏色、不透明度與漸層方向，確保在任何印表機或檢視器上都有一致的效果。

## 先決條件
- 基本的 Java 知識。  
- 熟悉 PostScript 概念。  
- 已安裝 Aspose.Page for Java 函式庫。若尚未下載，請取得 **[download Aspose.Page for Java](https://releases.aspose.com/page/java/)**。  
- 已備妥 Java IDE 或建置工具（Maven/Gradle）。

## 匯入套件
以下的匯入讓您可以使用顏色、漸層與 PostScript 文件物件。

`PsDocument` 類別是 Aspose.Page 的頂層物件，代表記憶體中的 PostScript 檔案。  

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

## 步驟 1：建立 ps 文件
首先，我們建立輸出串流並初始化新的 `PsDocument`。此物件充當所有後續繪圖操作的畫布。

`PsDocument` 建構子接受 `OutputStream` 與 `PageSize`，用以定義繪圖表面。  

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "ShowPseudoTransparency_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 2：定義使用不透明漸層填充的矩形
我們使用完全不透明的漸層繪製第一個矩形。此矩形將作為偽透明覆蓋層的背景。

`LinearGradientBrush` 類別提供以線性顏色漸層填充形狀的方式。  
`LinearGradientBrush` 類別建立漸層筆刷；其 `Color` 參數接受 RGBA 值，第四個值（alpha）控制不透明度。  

```java
float offsetX = 50;
float offsetY = 100;
float width = 200;
float height = 100;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create opaque gradient fill
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0), new Color(40, 128, 70)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## 步驟 3：定義使用半透明漸層填充的矩形
接著，我們放置第二個使用含 alpha 值漸層的矩形。當它與第一個形狀重疊時，即產生 **偽透明** 效果。

`Color` 建構子建立包含紅、綠、藍與 alpha 成分的顏色。  
`Color` 建構子 `new Color(r, g, b, a)` 允許您指定 alpha 通道（0‑255），數值越低透明度越高。  

```java
offsetX = 350;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create translucent gradient fill
paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## 步驟 4：關閉頁面並儲存文件
最後，我們關閉目前的頁面並將 PostScript 檔案寫入磁碟。

`save` 方法將文件內容寫入提供的輸出串流。  
呼叫 `psDocument.save(outputStream)` 會完成檔案並將所有繪圖指令刷新至底層串流。  

```java
document.closePage();
document.save();
```

## 常見問題與除錯
- **FileNotFoundException** – 請確認 `dataDir` 指向已存在的資料夾，且應用程式具備寫入權限。  
- **Incorrect colors** – 請確保使用 `Color(int r, int g, int b, int a)` 建構子來建立半透明顏色；第四個參數是 alpha（0‑255）。  
- **Gradient not visible** – 檢查 `AffineTransform` 參數是否正確對應漸層至矩形尺寸。

## 常見問答

**Q: 我可以在商業專案中使用 Aspose.Page for Java 嗎？**  
A: 可以，Aspose.Page for Java 可用於商業用途。您可以購買授權 **[purchase Aspose.Page license](https://purchase.aspose.com/buy)**。

**Q: 是否提供免費試用？**  
A: 有，您可以取得免費試用 **[download free trial](https://releases.aspose.com/)**。

**Q: 我可以在哪裡找到其他文件？**  
A: 詳細文件可於 **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)** 取得。

**Q: 如何取得測試用的臨時授權？**  
A: 您可以取得臨時授權 **[temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)**。

**Q: 需要協助或想討論 Aspose.Page？**  
A: 請前往 **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**。

---

**最後更新：** 2026-10-04  
**測試環境：** Aspose.Page for Java 24.12 (latest)  
**作者：** Aspose

## 相關教學

- [在 PostScript 中使用 Aspose.Page for Java 建立徑向漸層](/page/java/postscript-gradient-addition/)
- [在 PostScript 中使用 Aspose.Page for Java 建立紋理圖案](/page/java/postscript-texture-patterns/)
- [如何使用 Aspose.Page Java API 將 PostScript 轉換為 PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}