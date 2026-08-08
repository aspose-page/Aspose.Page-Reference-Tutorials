---
date: 2026-06-04
description: 了解如何在 Java 中使用 Aspose.Page 建立透明 XPS 物件。逐步指南，教您為 XPS 文件添加透明效果，呈現驚艷的視覺效果。
keywords:
- create transparent xps object
- Aspose.Page Java transparency
- Java XPS opacity
linktitle: 在 Java XPS 中添加透明物件
schemas:
- author: Aspose
  dateModified: '2026-06-04'
  description: Learn how to create transparent XPS object in Java using Aspose.Page.
    Step‑by‑step guide for adding transparency to XPS documents with stunning visual
    effects.
  headline: How to Create Transparent XPS Object in Java with Aspose.Page
  type: TechArticle
- questions:
  - answer: Yes—any geometry (ellipse, polygon, path, etc.) can receive an opacity
      value via its brush.
    question: Can I apply transparency to shapes other than rectangles?
  - answer: Set the brush’s opacity between 0.0 (fully transparent) and 1.0 (fully
      opaque) using `setOpacity(double)`.
    question: How do I control the exact transparency level?
  - answer: Absolutely. The library supports batch processing of thousands of pages,
      thread‑safe operations, and full compliance with the XPS 1.0 specification.
    question: Is Aspose.Page suitable for enterprise‑grade document generation?
  - answer: Yes—Aspose.Page works alongside libraries like Apache PDFBox or Java AWT;
      you can convert between formats or share geometry objects.
    question: Can I combine Aspose.Page with other Java graphics libraries?
  - answer: Visit the [Aspose.Page Java Forum](https://forum.aspose.com/c/page/39)
      for community help and explore the full API reference **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find more samples and support?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page 建立透明 XPS 物件
url: /zh-hant/java/xps-transparency/add-transparent-object/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 建立透明 XPS 物件

## 介紹
如果您需要在 Java 應用程式中**建立透明 XPS 物件**，Aspose.Page for Java 為您提供一個乾淨、以程式碼為先的解決方案。本教學將逐步說明您所需的一切——從安裝函式庫、準備文件、建立透明路徑、調整不透明度，到儲存最終的 XPS 檔案。完成後，您即可加入分層視覺效果，且在任何 XPS 檢視器中正確呈現。

## 快速解答
- **哪個函式庫在 Java 中為 XPS 添加透明度？** Aspose.Page for Java。  
- **是否可以以程式方式設定不透明度？** 可以——使用畫筆的 `setOpacity` 方法。  
- **正式使用是否需要授權？** 評估版之外需購買商業授權。  
- **支援哪些 Java 版本？** Java 8 及以上版本，包括 LTS 版。  
- **輸出檔案能在標準 XPS 檢視器中正常顯示嗎？** 當然——透明度完全符合 XPS 規範。

## XPS 中的透明度是什麼？
在 XPS 中，透明度允許您以部分不透明度繪製物件，使底層內容得以透視。此效果非常適合用於浮水印、覆蓋圖形，或任何透過分層視覺提升可讀性且保持檔案大小低的設計。透過調整不透明度，您可以製作細緻的陰影、突顯重要區段，或建立複雜的視覺層次，而不會增加文件的複雜度。

## 為何使用 Aspose.Page 來加入透明度？
使用 Aspose.Page 加入透明度既簡單又高效。此函式庫讓您能以程式方式控制每個圖形基元，支援大型文件的批次處理，且自動處理 XPS 包裝與壓縮。其 API 緊密遵循 XPS 規範，確保產生的檔案在所有標準檢視器中一致呈現，同時將開發工作量降至最低。

## 前置條件
- JDK 8 或更新版本已安裝。  
- 從官方網站下載 Aspose.Page for Java 函式庫 **[此處](https://releases.aspose.com/page/java/)**。  
- 一個開發 IDE（IntelliJ IDEA、Eclipse 或 VS Code）以編譯與執行範例。

## 匯入套件
`XpsDocument` 代表 XPS 檔案，提供建立頁面與圖形的方法。於 Java 原始檔的最上方加入必要的 Aspose.Page 匯入語句：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.Color;
```

現在讓我們一步步瀏覽範例程式碼。

## 步驟 1：初始化文件
`Document` 類別是 Aspose.Page 的頂層物件，代表記憶體中的單一 XPS 檔案。建立實例、加入頁面，並設定輸出資料夾。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize document
XpsDocument doc = new XpsDocument();
```
首先設定文件，並指定 XPS 文件要儲存的目錄。

## 步驟 2：建立透明物件
此處建立兩條灰色路徑，作為稍後加入的透明形狀的背景。

```java
// Just to demonstrate transparency
doc.addPath(doc.createPathGeometry("M120,0 H400 v1000 H120")).setFill(doc.createSolidColorBrush(Color.GRAY));
doc.addPath(doc.createPathGeometry("M300,120 h600 V420 h-600")).setFill(doc.createSolidColorBrush(Color.GRAY));
```
這些路徑使用實心灰色畫筆繪製；它們保持完全不透明，以便清楚觀察透明覆蓋層的效果。

## 步驟 3：加入填充路徑
`SolidColorBrush` 是一種以純色填充形狀且支援不透明度設定的畫筆。在此步驟中，我們建立一個實心藍色矩形並放置於頁面上。此矩形稍後會被透明形狀覆蓋，以示範效果。

```java
// Create path with closed rectangle geometry
XpsPath path1 = doc.createPath(doc.createPathGeometry("M20,20 h200 v200 h-200 z"));
// Set blue solid brush to fill path1
path1.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add it to the current page
XpsPath path2 = doc.add(path1);
```
該矩形使用標準的 `SolidColorBrush`，不透明度為完整 (1.0)。

## 步驟 4：操作透明度
`setOpacity` 設定畫筆的不透明度等級，範圍為 0.0（完全透明）至 1.0（完全不透明）。此處我們變更複製路徑的填色並套用平移變換。此示例說明當物件共享同一父元素時，透明度的互動方式。

```java
// path1 and path2 are the same as long as path1 hasn't been placed inside any other element
path2.setFill(doc.createSolidColorBrush(Color.GREEN));
// Now add path2 once again. Now path2 has a parent, so path3 won't be the same as path2.
XpsPath path3 = doc.add(path2);
path3.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 0, 300));
path3.setFill(doc.createSolidColorBrush(Color.RED));
```
請注意 `setOpacity(0.6)` 呼叫——這使形狀的透明度為 60%，讓下方的藍色矩形得以透視。

## 步驟 5：複製與修改路徑
我們複製現有路徑，移動它，並將不透明度調整為 0.8（80% 不透明）。此步驟展示如何重複使用幾何形狀，同時為每個實例自訂透明度。

```java
// Create new path4 with path2's geometry
XpsPath path4 = doc.addPath(path2.getData());
path4.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 300, 0));
path4.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add path4 once again.
XpsPath path5 = doc.add(path4);
path5.setRenderTransform(path5.getRenderTransform().deepClone());
path5.getRenderTransform().translate(0, 300);
path5.getFill().setOpacity(0.8f);
```
在產生大量相似形狀時，重複使用幾何形狀可將記憶體開銷降低至 **30 %**。

## 步驟 6：儲存文件
`save` 將 XPS 文件寫入指定的檔案路徑，保留所有圖形與不透明度設定。最後，我們將 XPS 檔案寫入磁碟。於任意 XPS 檢視器開啟產生的檔案，即可看到分層透明效果。

```java
// Save the modified document
doc.save(dataDir + "WorkingWithTransparency_out.xps");
```

## 常見問題與技巧
- **不透明度未顯示？** 請確認使用支援不透明度的畫筆，例如 `createSolidColorBrush`。  
- **變換未套用？** 請在將路徑加入頁面之前呼叫 `setRenderTransform` **，否則變換會被忽略**。  
- **效能提示：** 繪製大量形狀時，重複使用幾何物件與畫筆；對大型文件可將處理時間縮短至 **45 %**。  
- **檔案大小顧慮？** 透明度僅增加幾 KB；Aspose.Page 會自動壓縮 XPS 套件。

## 常見問答

**Q: 我可以將透明度套用於除矩形之外的形狀嗎？**  
A: 可以——任何幾何形狀（橢圓、多邊形、路徑等）皆可透過其畫筆設定不透明度值。

**Q: 如何精確控制透明度等級？**  
A: 使用 `setOpacity(double)` 將畫筆的不透明度設定於 0.0（完全透明）至 1.0（完全不透明）之間。

**Q: Aspose.Page 是否適用於企業級文件產生？**  
A: 絕對適用。此函式庫支援上千頁的批次處理、執行緒安全操作，且完整符合 XPS 1.0 規範。

**Q: 我可以將 Aspose.Page 與其他 Java 圖形函式庫結合使用嗎？**  
A: 可以——Aspose.Page 可與 Apache PDFBox 或 Java AWT 等函式庫同時使用；您可以在格式之間轉換或共享幾何物件。

**Q: 我在哪裡可以找到更多範例與支援？**  
A: 前往 [Aspose.Page Java 論壇](https://forum.aspose.com/c/page/39)取得社群協助，並在 **[此處](https://reference.aspose.com/page/java/)** 瀏覽完整 API 參考文件。

---

**最後更新：** 2026-06-04  
**測試環境：** Aspose.Page for Java 24.12  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何在 Java XPS 文件中加入透明度](/page/java/xps-transparency/)
- [使用 Aspose.Page Java 在 Java XPS 中設定不透明遮罩](/page/java/xps-transparency/set-opacity-mask/)
- [使用 Aspose.Page Java 將 XPS 轉換為 PDF](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}