---
date: 2026-05-30
description: 了解如何在 Java 中使用 Aspose.Page 建立 XPS 文件，並輕鬆加入平鋪圖像，透過本分步指南快速完成。快速建立 XPS 檔案的方法。
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: 在 Java XPS 中加入平鋪圖像
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何在 Java 中使用平鋪圖像建立 XPS 文件
url: /zh-hant/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用平鋪圖像建立 XPS 文件

## 介紹
以程式方式建立 XPS 文件是需要可列印、裝置無關輸出的 Java 開發人員的核心技能。**如何建立 XPS** 檔案的高效方法由 Aspose.Page for Java 提供，它抽象化了低階的 XML Paper Specification 細節，讓您專注於視覺設計。在本指南中，您將看到如何建立 XPS 文件、將平鋪圖像作為背景或圖案加入，並儲存結果——全部使用簡潔、可投入生產的程式碼。

## 快速答案
- **Aspose.Page 的功能是什麼？** 它提供高階 API 以在 Java 中產生和操作 XPS 文件。  
- **我可以平鋪圖像嗎？** 可以 – 使用 `XpsImageBrush` 搭配 `XpsTileMode.Tile`。  
- **我需要授權嗎？** 生產環境需要臨時或商業授權。  
- **支援哪個 Java 版本？** 任意 JDK 8 以上皆相容。  
- **實作需要多長時間？** 基本平鋪圖像情境大約 10–15 分鐘。

## 什麼是「建立 XPS 文件」？
`XpsDocument` 是 Aspose.Page 的頂層物件，代表記憶體中的單一 XPS 檔案。它封裝頁面、資源與中繼資料，讓您以程式方式建構文件。建立 XPS 文件即是實例化此類別、加入視覺元素，最後呼叫 `save` 將固定版面檔寫入磁碟。此方式省去手動處理 XML，並確保符合 XML Paper Specification。

## 為什麼要加入平鋪圖像？
平鋪會在定義區域內重複圖形，非常適合作為背景、水印或圖案填充。使用 `XpsTileMode.Tile` 時，圖像會自動重複，無需手動複製，節省開發時間並確保在任何裝置上渲染一致。平鋪圖像亦能降低檔案大小，因為相同的位圖資源會被重複使用，而非多次嵌入。

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 已安裝 JDK 8 或更新版本。  
2. **Aspose.Page for Java** – 從 [website](https://releases.aspose.com/page/java/) 下載。  
3. **可寫入的目錄** – 用於儲存產生的 XPS 檔案。

## 匯入套件
在您的 Java 專案中，匯入必要的類別：

`XpsDocument` 是代表 XPS 檔案的主要物件。  
`XpsImageBrush` 使用圖像來源繪製形狀。  
`XpsTileMode` 指定圖像的平鋪方式。  
`Rectangle2D` 描述用於定位的矩形區域。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 步驟指南

### 步驟 1：設定專案
將 Aspose.Page 的 JAR 檔案加入專案的 classpath，並確認匯入語句能順利編譯，無錯誤。

### 步驟 2：建立 XPS 文件
`XpsDocument` 是保存頁面、路徑與資源的核心容器。以所需的頁面尺寸實例化它，然後即可開始加入圖形元素。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 步驟 3：定義平鋪圖像路徑
將您想平鋪的圖像（例如 `R08LN_NN.jpg`）放入 `dataDir` 所指的目錄中。該圖像將作為筆刷圖案使用。

### 步驟 4：加入平鋪圖像
建立一個矩形路徑，並以 `XpsImageBrush` 填充。將平鋪模式設定為 `Tile` 後，圖像會在矩形內重複。調整來源與目標的 `Rectangle2D` 以控制平鋪大小與位置。

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### 步驟 5：儲存文件
將 XPS 檔案寫入磁碟。輸出檔案將包含您剛剛定義的平鋪圖像，且可使用任何 XPS 檢視器開啟。

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

在同一 XPS 文件的其他頁面或形狀中需要 **加入平鋪圖像** 時，請重複上述步驟。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| 圖像未顯示 | 確認檔案路徑 (`dataDir + "R08LN_NN.jpg"`) 正確且圖像可存取。 |
| 平鋪圖案顯示拉伸 | 調整來源與目標 `Rectangle2D` 的數值以控制平鋪大小。 |
| 不透明度無效 | 確保筆刷的不透明度設定在平鋪模式配置 **之後** 進行。 |

## 常見問與答

**Q:** Aspose.Page 是否相容所有 Java 版本？  
**A:** Aspose.Page 支援 Java 8 至 Java 21；完整相容性矩陣可在 [here](https://reference.aspose.com/page/java/) 找到。

**Q:** 我可以在商業專案中使用 Aspose.Page 嗎？  
**A:** 可以，生產環境需要商業授權。購買選項列於 [here](https://purchase.aspose.com/buy)。

**Q:** 有免費試用版嗎？  
**A:** 可從 Aspose 釋出頁面下載功能完整的免費試用版，網址在 [here](https://releases.aspose.com/)。

**Q:** 我可以在哪裡取得社群支援？  
**A:** 前往 Aspose.Page 社群論壇 [forum](https://forum.aspose.com/c/page/39) 提問或分享範例。

**Q:** 如何取得評估用的臨時授權？  
**A:** 臨時授權可透過 Aspose 入口網站申請，詳情請見 [here](https://purchase.aspose.com/temporary-license/)。

## 結論
您現在已掌握使用 Aspose.Page for Java 以平鋪圖像建立 **XPS 文件** 的完整、生產就緒工作流程。透過 `XpsImageBrush` 與 `XpsTileMode.Tile`，您能產生豐富且可重複的圖形，而不會增加檔案大小。可嘗試不同的平鋪尺寸、不透明度與形狀，打造更精緻的文件版面。下一步，可探索加入向量形狀或文字覆蓋，以進一步提升 XPS 檔案的效果。

---

**最後更新:** 2026-05-30  
**測試環境:** Aspose.Page for Java 24.12 (latest)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何在 Java XPS 文件中加入圖像 – Aspose.Page 簡易指南](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - 新增頁面至 XPS 教學](/page/java/xps-page-manipulation/add-page/)
- [使用 Aspose.Page Java 將 XPS 轉換為 PDF](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}