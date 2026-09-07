---
date: 2026-08-29
description: 了解如何在 Java 中使用 Aspose.Page 進行 EPS 向量尺寸調整。本分步指南將示範如何使用點、英吋、毫米或百分比來調整 EPS
  大小。
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: 在 Java 中調整 EPS 檔案尺寸
og_description: Java 向量尺寸調整讓您直接在 Java 中調整 EPS 檔案尺寸。使用 Aspose.Page，您可以透過點、英吋、毫米或百分比進行調整，同時保留向量品質。
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: Java 向量尺寸調整：使用 Aspose.Page 變更 EPS 尺寸
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: 如何使用 Aspose.Page 在 Java 中調整 EPS 向量檔案尺寸
url: /zh-hant/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 向量調整 EPS 檔案大小

## 介紹
如果您需要以程式方式 **java vector resize** EPS 檔案，您來對地方了。本教學將帶您使用 Aspose.Page 函式庫在 Java 中調整 EPS 圖片的大小。無論您想將尺寸加倍、縮小至特定測量值，或是使用百分比，以下步驟都能讓您完整掌控輸出尺寸。熟悉 EPS 調整大小的技巧對於在不同列印版面、螢幕解析度或品牌指引下調整圖形至關重要。

## 快速回答
- **需要的函式庫是什麼？** Aspose.Page for Java  
- **我可以使用點、英吋或毫米調整大小嗎？** 可以 — API 支援這三種單位以及百分比。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式環境需購買授權。  
- **需要哪個 Java 版本？** Java 8 或更新版本。  
- **程式碼是執行緒安全的嗎？** 每個 `PsDocument` 實例彼此獨立，您可以平行處理檔案。  

## EPS 是什麼以及為何要調整大小？
Encapsulated PostScript (EPS) 是廣泛用於列印與出版的向量圖形格式。有時原始 EPS 檔的尺寸與目標輸出不符 — 例如，設計為 72 pts 的商標可能需要在較大的手冊中使用 144 pts。了解 **how to resize eps** 能讓您在保持向量品質的同時，依工作流程調整尺寸。

## 為什麼使用 Aspose.Page 來調整 EPS 大小？
Aspose.Page 提供直觀的 API，讓您以任何支援的單位指定目標尺寸，同時自動保留向量結構。函式庫在內部處理單位轉換，讓您無需手動計算即可專注於所需尺寸。

- **支援四種測量單位** — Points、Inches、Millimeters 與 Percent。  
- **無外部相依性** — 純 Java API，無需本機函式庫。  
- **高效能處理** — 在標準 8 核心伺服器上每分鐘可處理高達 500 個 EPS 檔案。  
- **保留向量忠實度** — 輸出保持完整可縮放，無需點陣化。  

## 前置條件
在進入程式碼之前，請確保您具備以下條件：

- 已在機器上安裝 Java Development Kit (JDK)。  
- Aspose.Page for Java 函式庫。您可以在 **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)** 下載。  
- 基本的 Java 程式設計概念。  

## 匯入套件
在您的 Java 專案中，加入必要的匯入，以便使用 Aspose.Page 物件與標準 I/O 串流。

`PsDocument` 代表已載入記憶體的 EPS 文件。  
`Units` 是一個列舉，定義 API 所接受的測量單位。

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## 如何使用不同單位變更 EPS 尺寸
您可以透過呼叫 `resizeEps` 方法，傳入欲設定的寬度、高度以及 `Units` 列舉值，來變更 EPS 尺寸；此方式支援點、英吋、毫米或百分比。相同的五步驟模式適用於所有單位，使 API 可預測且易於整合。

`resizeEps` 會在保持內部向量資料的同時，將 EPS 畫布調整至指定尺寸。

## 如何使用點 (points) 調整 EPS 大小
載入您的 EPS，使用點 (points) 指定新尺寸，然後儲存結果。此方法會將原始尺寸加倍，同時保留長寬比。使用點能讓您精確控制列印就緒的尺寸，對於排版與高解析度輸出尤為有用。

### 步驟 1：設定輸入串流
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 步驟 2：初始化 `PsDocument` 物件
`PsDocument` 載入來源 EPS 檔案並提供操作方法。  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### 步驟 3：取得 EPS 圖片的目前尺寸
```java
Dimension oldSize = doc.extractEpsSize();
```

### 步驟 4：為調整大小的檔案建立輸出串流
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 步驟 5：使用點 (points) 調整大小並儲存 EPS
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## 如何使用英吋 (inches) 調整 EPS 大小
使用英吋 (inches) 調整大小可讓您符合以英制單位定義的規格，例如手冊版面或美國列印標準。提供目標寬度與高度（英吋），API 會在套用變換前將其轉換為相應的內部單位。

## 如何使用毫米 (millimeters) 調整 EPS 大小
在使用公制工作流程時，以毫米 (millimeters) 指定尺寸可確保與美國以外的紙張尺寸與印刷設備保持一致。函式庫會自動將毫米轉換為內部座標系統。

## 如何使用百分比調整 EPS 大小
以百分比調整大小會按比例縮放原始尺寸，方便在不計算絕對值的情況下快速調整。例如，係數 `0.5` 會將寬度與高度同時縮小 50 %。

## 常見陷阱與技巧
- **務必關閉串流** — 在正式程式碼中，使用 try‑with‑resources 包裝串流以避免檔案鎖定。  
- **保留長寬比** — 除非刻意想要變形，否則寬度與高度應以相同係數相乘。  
- **檢查 DPI** — 調整大小不會改變 DPI；若需不同 DPI，請在調整後另行設定。  
- **執行緒安全** — 每個執行緒建立新的 `PsDocument`；共享同一實例可能導致預期外結果。  

## 常見問答

**Q: 我可以將此函式庫用於其他影像格式嗎？**  
A: 不行，Aspose.Page 僅專門支援 PostScript 與 EPS 檔案。

**Q: Aspose.Page for Java 有提供免費試用嗎？**  
A: 有，您可以在 **[Aspose free trial page](https://releases.aspose.com/)** 探索免費試用。

**Q: 我可以在哪裡找到更多協助與討論？**  
A: 前往 **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** 取得社群支援。

**Q: 我要如何取得臨時授權？**  
A: 您可在 **[temporary license request page](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 有提供範例專案嗎？**  
A: 有，請參考文件 **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**。

---

**最後更新：** 2026-08-29  
**測試環境：** Aspose.Page for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Page 調整 EPS 大小 – Java EPS 操作](/page/java/manipulation-eps/)
- [如何在 Java 中裁剪 EPS 檔案 – Aspose.Page 指南](/page/java/manipulation-eps/crop/)
- [如何使用 Aspose.Page for Java 縮放矩形](/page/java/page-manipulation/transformations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}