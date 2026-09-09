---
date: 2026-09-09
description: 了解如何在 Java PostScript 中建立漸層，並使用 Aspose.Page 為形狀加入漸層。請依循此一步一步的指南，內含程式碼與技巧。
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript 徑向漸層 with Aspose.Page
og_description: 了解如何在 Java PostScript 中建立漸層，並使用 Aspose.Page 為形狀加入漸層。請依循此一步一步的指南，內含程式碼與技巧。
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: 如何在 Java PostScript 中使用 radial fill 建立漸層
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: 如何在 Java PostScript 中使用 radial fill 建立漸層
url: /zh-hant/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用徑向填充建立漸層

## 介紹
在本教學中，您將學習 **如何建立漸層** 圖形於使用 Java 與 Aspose.Page 的 PostScript 文件。我們會逐步說明——從專案設定到渲染填滿平滑徑向漸層的圓形——讓您能即時 **將漸層套用於形狀** 物件，提升 Java 應用程式的視覺品質。

## 快速答案
- **本教學會產生什麼？** 一個包含徑向漸層填滿圓形的 PostScript 檔案（`.ps`）。  
- **需要哪個函式庫？** Aspose.Page for Java（最新版本）。  
- **實作需要多久？** 約 10‑15 分鐘即可完成範例。  
- **需要授權嗎？** 生產環境需使用臨時或正式授權；開發可使用免費試用版。  
- **可以將程式碼重用於 PDF 或 SVG 嗎？** 可以——Aspose.Page 支援多種輸出格式，只需少量調整。

## 如何在 PostScript 中使用漸層填充形狀
您可以透過建立 `PsDocument`、定義 `RadialGradientPaint`、將其套用至目標形狀，最後儲存文件的方式，在 PostScript 中以徑向漸層填充形狀。此簡潔工作流程讓您在不使用點陣圖的情況下產生專業級向量圖形，同樣的程式碼亦可重用於 PDF 或 SVG 輸出。流程直觀，且在所有支援的格式中表現一致。

## 什麼是徑向漸層？
徑向漸層從中心點向外過渡顏色，形成平滑的圓形混合。它非常適合用於高光、按鈕背景或任何需要自然「發光」效果的視覺元素。透過變更顏色停點與半徑，您可以在純向量形式中模擬光照、深度與材質屬性。

## 為何使用 Aspose.Page 產生徑向漸層？
Aspose.Page 讓您只需使用單一 Java API 即可產生裝置無關的向量圖形。它支援超過 50 種輸入與輸出格式——包括 PostScript、PDF 與 SVG——同時保留色彩精準度與抗鋸齒，適合高解析度輸出。函式庫亦提供易於使用的漸層類別，讓複雜的視覺效果變得簡單實作。

## 前置條件
在開始之前，請確保您已具備：

- 基本的 Java 程式開發經驗。  
- 已在機器上安裝 JDK 8 或更新版本。  
- Aspose.Page for Java 函式庫（可從 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) 下載）。  

## 匯入套件
首先，匯入我們將會使用的類別。這些類別包含標準的 AWT 圖形類型以及 Aspose.Page API。

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟 1：設定文件目錄
定義產生的 PostScript 檔案要儲存的資料夾。請將佔位符替換為您系統上的實際路徑。

```java
String dataDir = "Your Document Directory";
```

## 步驟 2：建立輸出串流
`FileOutputStream` 將原始位元組寫入檔案，允許二進位資料被儲存。開啟指向 `.ps` 檔案的串流，即可讓 Aspose.Page 直接將產生的 PostScript 資料寫入磁碟。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## 步驟 3：建立儲存選項
`PsSaveOptions` 設定 PostScript 檔案的儲存方式，包括頁面大小與壓縮。您可以自行調整這些設定，但預設值已足以完成本範例。

```java
PsSaveOptions options = new PsSaveOptions();
```

## 步驟 4：建立 ps 文件
`PsDocument` 代表記憶體中的 PostScript 文件，提供加入頁面與圖形的方法。

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 5：建立圓形
`Ellipse2D.Float` 描述橢圓形狀；當寬度 = 高度時即為完美圓形。此物件將作為我們漸層填充的畫布。

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## 如何使用漸層繪製圓形
要以徑向漸層繪製圓形，您只需將 `RadialGradientPaint` 載入圖形上下文，然後填充先前定義的橢圓。此單一步驟即可將形狀以從中心向外平滑過渡的顏色繪製，產生視覺上吸引的效果。

## 步驟 6：定義漸層顏色
準備兩個陣列：一個存放漸層中出現的顏色，另一個存放對應的分數位置（0 = 中心，1 = 邊緣）。

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## 步驟 7：建立 AffineTransform
`AffineTransform` 是一個矩陣，可用來平移、旋轉、縮放或剪切圖形物件。此處我們縮放並平移漸層，使其恰好填滿圓形。

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## 步驟 8：建立徑向漸層 Paint
`RadialGradientPaint` 依據中心點、半徑與顏色停點建立徑向顏色漸層。

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## 步驟 9：設定 Paint 並填充圓形
將漸層 Paint 套用至文件，並填充先前定義的圓形。這是我們 **徑向漸層範例** 的核心，展示了如何 **fill shape with gradient**。

```java
document.setPaint(paint);
document.fill(circle);
```

## 步驟 10：關閉頁面並儲存文件
完成頁面、將內容寫入磁碟，最後關閉串流。您的 PostScript 檔案現在可使用任何 PS 檢視器開啟。

```java
document.closePage();
document.save();
```

恭喜！您已成功在 Java PostScript 中使用 Aspose.Page 建立徑向漸層範例。您現在擁有可重複使用的 **fill shape with gradient** 模式，可套用於其他形狀與輸出格式。

## 常見問題與解決方案
| 問題 | 解決方案 |
|------|----------|
| **FileNotFoundException** 在開啟輸出串流時發生 | 驗證 `dataDir` 指向已存在的資料夾且您具有寫入權限。 |
| 漸層看起來平坦或缺失 | 確保 `fractions` 陣列與 `colors` 陣列長度相同，且 `AffineTransform` 正確縮放。 |
| 顏色顯示相反 | 交換 `colors` 陣列中的顏色順序或調整 `focus` 點座標。 |

## 常見問答

**問：在哪裡可以找到 Aspose.Page for Java 的文件？**  
**答：** 完整的 API 參考可在 [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/) 中取得。

**問：如何下載 Aspose.Page for Java？**  
**答：** 從 [releases page](https://releases.aspose.com/page/java/) 取得最新的 JAR 檔。

**問：是否提供免費試用版？**  
**答：** 有——可從 [Aspose free trial download page](https://releases.aspose.com/) 下載試用版本。

**問：我可以取得臨時授權以進行測試嗎？**  
**答：** 當然，請從 [temporary license page](https://purchase.aspose.com/temporary-license/) 申請。

**問：在哪裡可以獲得社群支援？**  
**答：** 加入 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 參與討論。

## 結論
在本指南中，我們使用 Aspose.Page for Java 為 PostScript 文件建立了完整的 **徑向漸層範例**。依循步驟後，您已掌握可重複使用的 **fill shape with gradient** 模式，並可將其套用至 PDF、SVG 或 Aspose.Page 支援的任何其他格式。請嘗試不同的顏色、半徑與形狀，為您的 Java 圖形專案增添豐富的視覺效果。

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## 相關教學

- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [Create Texture Pattern in PostScript with Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}