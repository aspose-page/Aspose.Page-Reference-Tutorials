---
date: 2026-10-20
description: 了解如何使用 Aspose.Page for Java 縮放矩形、平移形狀，並套用 Affine transform 以建立 PostScript
  文件。
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Java 頁面操作中的 Transformations
og_description: 了解如何使用 Aspose.Page for Java 縮放矩形、平移形狀，並套用 Affine transform 以有效產生 PostScript
  檔案。
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: 如何使用 Aspose.Page for Java 縮放矩形 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: 如何使用 Aspose.Page for Java 縮放矩形
url: /zh-hant/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for Java 縮放矩形

## 簡介
在本指南中，您將了解如何使用 Aspose.Page for Java **how to scale rectangle** 物件，同時學習如何平移形狀位置、旋轉圖形以及套用仿射變換操作，以產生高品質的 PostScript 輸出。這些技術讓您能在不編寫低階渲染程式碼的情況下，建立複雜且與裝置無關的圖形，提升 Java 應用程式的功能與可維護性。

## 快速解答
`scale(sx, sy)` 會依給定的水平與垂直因子縮放圖形上下文。  

- **如何在 Java 中使用 Aspose.Page 縮放矩形？** 在繪製矩形之前，於圖形上下文呼叫 `scale(sx, sy)` 方法。  
- **我可以在不影響其他圖形的情況下移動（平移）形狀嗎？** 可以——將平移操作包裹在 `writeGraphicsSave()` 與 `writeGraphicsRestore()` 呼叫之間。  
- **哪個類別用於建立 PostScript 檔案？** 使用 `PsDocument` 搭配 `PsSaveOptions`。  
- **在正式環境使用是否需要授權？** 商業部署需要有效的 Aspose.Page 授權。  
- **支援哪個 Java 版本？** Aspose.Page 支援 Java 8 及以上版本。

## 先決條件
在開始之前，請確認您具備：

- 對核心 Java 語法與物件導向概念有扎實的掌握。  
- 已安裝 Aspose.Page for Java 程式庫。您可從 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) 下載。  
- 已配置好 Java IDE（IntelliJ IDEA、Eclipse 或 VS Code），並在 classpath 中加入程式庫的 JAR 檔案。

## 匯入套件
`PsDocument` 是用於建立 PostScript 文件的主要類別，`PsSaveOptions` 則負責設定文件的儲存方式。  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 什麼是 Aspose.Page 中的 “how to scale rectangle”？
`scale(float sx, float sy)` 方法對目前的圖形狀態套用仿射縮放變換，依 `sx`（水平）與 `sy`（垂直）因子調整後續繪圖的大小。這是 **how to scale rectangle** 關鍵字背後的核心操作。於繪製之前套用此變換，任何後續的形狀（例如矩形）都會以新的尺寸呈現，同時保留其比例。

## 如何使用 Aspose.Page 平移形狀
`writeGraphicsSave()` 會儲存目前的圖形狀態，`writeGraphicsRestore()` 則會還原，確保變換僅影響目標形狀。平移會重新定位座標系的原點，而不改變物件的尺寸。將 `translate(dx, dy)` 包裹在 `writeGraphicsSave()` / `writeGraphicsRestore()` 之間，即可確保只有目標形狀移動，其他圖形保持不變，提供對單一元素的精確控制。

## 範例 1：無變換
第一個範例在未套用任何變換的情況下繪製矩形，作為之後範例視覺比較的基準。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## 範例 2：平移
在此範例中，我們在繪製第二個矩形之前，將圖形上下文向右移動 250 單位，以示範 **how to translate shape**。

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 範例 3：縮放
此處回應主要問題 **how to scale rectangle**。透過呼叫 `scale(0.5f, 0.75f)`，將矩形的寬度縮減至原始的 50%，高度縮減至原始的 75%。

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 如何在 Java 中旋轉形狀 java (rotate shape java)
`rotate(angle)` 會依指定的角度（以度為單位）旋轉座標系。載入 `PsDocument` 後，在圖形狀態上呼叫 `rotate(angle)`，繪製形狀，然後還原先前的狀態。此模式在單一可重用的區塊中實作 **rotate shape java** 與 **how to rotate rectangle**，讓您能圍繞任意點旋轉圖形。

## 為何這很重要 – 真實世界的好處
- **Device‑independent output** – Aspose.Page 能產生在任何印表機或檢視器上均一致呈現的 PostScript 與 XPS 檔案，免除平台特定的調整。  
- **Fine‑grained control** – 結合平移、縮放、剪切與旋轉，以符合精確的版面規格；API 每頁支援超過 20 種變換組合。  
- **Performance‑oriented processing** – 此函式庫在處理一般 100 頁報告時，記憶體佔用低於 10 MB，使批次作業快速且具擴充性。

## 常見使用情境
- **Printable invoices** – 使用縮放與平移精確放置標誌、條碼與表格，以符合公司品牌指南。  
- **Technical diagrams** – 產生每個元件必須按比例調整大小與定位的技術圖表。  
- **Automated multi‑page reports** – 建立需要跨頁保持一致縮放的 PostScript 報告，例如工程規格。

## 常見問題與解決方案
- **Transformation not resetting** – 必須始終將 `writeGraphicsSave()` 與 `writeGraphicsRestore()` 成對使用；否則後續繪圖會繼承不需要的變換。  
- **Unexpected colors** – 每次變換後設定繪圖顏色（paint），因為圖形狀態在還原後不會保留顏色資訊。  
- **File size too large** – 在 `PsSaveOptions` 中啟用壓縮，並限制嵌入的點陣圖解析度，以確保典型 50 頁文件的最終檔案大小保持在 5 MB 以下。

## 常見問答
### 我可以將 Aspose.Page for Java 用於其他文件格式嗎？
請前往 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) 取得完整指南、API 參考與範例專案。

### 哪裡可以找到更多 Aspose.Page for Java 的範例與文件？
是的，您可透過 **Aspose free trial download** 頁面取得免費試用： [Aspose free trial download](https://releases.aspose.com/)。

### 是否提供 Aspose.Page for Java 的免費試用？
可透過 **temporary license request page** 取得臨時授權： [temporary license request page](https://purchase.aspose.com/temporary-license/)。

### 如何取得 Aspose.Page for Java 的臨時授權？
請前往 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) 參與社群討論、取得程式碼片段與故障排除建議。

## 常見問題

**Q: `translate` 與 `scale` 有何差異？**  
A: `translate` 會移動座標系的原點，而 `scale` 則會改變繪製物件在 X 與/或 Y 軸上的大小。

**Q: 我可以在單一圖形狀態中結合多個變換嗎？**  
A: 可以——在繪製之前依序呼叫 `translate`、`scale`、`rotate` 或 `shear`，即可產生組合的仿射變換。

**Q: 繪製形狀後如何重設變換？**  
A: 使用 `writeGraphicsRestore()` 還原至先前儲存的圖形狀態。

**Q: 是否可以繞矩形中心旋轉？**  
A: 當然可以。先將矩形平移至原點，套用 `rotate(angle)`，再平移回原位置後繪製。

**Q: Aspose.Page 是否支援抗鋸齒以產生更平滑的圖形？**  
A: 支援——在 `PsSaveOptions` 中設定相應的渲染選項即可啟用抗鋸齒。

---

**最後更新:** 2026-10-20  
**測試環境:** Aspose.Page for Java 24.12  
**作者:** Aspose

## 相關教學

- [如何在 Java PostScript 中使用 Aspose.Page 繪製矩形](/page/java/postscript-shapes/add-rectangle/)
- [在 PostScript 中使用 Aspose.Page for Java 建立徑向漸層](/page/java/postscript-gradient-addition/)
- [PostScript 頁面操作](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}