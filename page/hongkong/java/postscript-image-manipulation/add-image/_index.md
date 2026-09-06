---
date: 2026-08-23
description: 了解如何使用 aspose.page image manipulation java 在 PostScript 檔案中嵌入及旋轉圖像，並提供清晰的
  Java 範例。
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: 在 Java PostScript 中添加圖像
og_description: 了解如何使用 aspose.page image manipulation java 在 PostScript 檔案中嵌入及旋轉圖像，並提供逐步的
  Java 程式碼範例。
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: 如何使用 aspose.page image manipulation java 添加圖像
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: 如何使用 aspose.page image manipulation java 添加圖像
url: /zh-hant/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 aspose.page 圖像操作 java 添加圖像

## 介紹
在本教學中，您將學習如何 **使用 aspose.page 圖像操作 java** 來建立 PostScript 檔案、嵌入點陣圖，並套用平移與旋轉變換。完成本指南後，您將能從 Java 產生像素完美的 PostScript 輸出——非常適合自動化報表、列印流程或任何需要在 PostScript 文件中精確放置圖像的工作流程。

## 快速答案
- **需要的函式庫是什麼？** Aspose.Page for Java  
- **可以加入多張圖像嗎？** 可以——對每張圖像重複變換與繪製步驟  
- **開發時需要授權嗎？** 免費試用可用於測試；正式環境需購買授權  
- **支援哪個 Java 版本？** Java 8 及以上版本  
- **支援圖像旋轉嗎？** 當然可以——使用 `AffineTransform.rotate()`  

## 什麼是 aspose.page 圖像操作 java？
`aspose.page 圖像操作 java` 是 Aspose.Page API，讓您能以 Java 程式碼程式化地建立、編輯與渲染 PostScript 文件，完整控制圖像的放置、縮放與旋轉。使用此 API，您不必直接編寫低階的 PostScript 語法，庫會在內部處理格式轉換與嵌入。

## 為什麼使用 aspose.page 進行圖像操作？
Aspose.Page 提供 **超過 50 種圖像格式**（包括 JPEG、PNG、BMP、TIFF），且能在不將整個文件載入記憶體的情況下嵌入圖像，讓您即使處理上百頁的檔案，記憶體使用仍能維持在一般伺服器的 100 MB 以下。高階 API 抽象了複雜的 PostScript 指令，讓您撰寫簡潔的 Java 程式碼，而不必直接使用原始 PS 操作符。

## 前置條件
- 安裝 Java Development Kit (JDK) 8 或更新版本。  
- Aspose.Page for Java 函式庫 ─ 下載 **[Aspose.Page for Java 下載頁面](https://releases.aspose.com/page/java/)**。  
- 具備基本的 Java 語法與物件導向程式設計知識。

## 什麼是 create postscript java？
從 Java 建立 PostScript 檔案即是以程式方式產生 `.ps` 文件，描述頁面版面配置、向量圖形與點陣圖像。Aspose.Page 會將您的 Java 呼叫轉換為有效的 PostScript 指令，讓您在不需要額外的 PostScript 直譯器的情況下產生可直接列印的檔案。

## 如何逐步添加帶平移和旋轉的圖像

載入圖像、套用 `AffineTransform`，再將其繪製到頁面上。以下步驟說明了完整的操作順序。

### 步驟 1：寫入圖形保存
保存圖形狀態可將您的變換隔離，之後可以還原。這相當於原始 PostScript 中的 `gsave` 操作符。

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### 步驟 2：平移與變換（平移與旋轉圖像）
首先，從來源檔案建立 `BufferedImage`，然後建立一個 `AffineTransform`，將圖像平移至目標座標並繞其中心旋轉。`AffineTransform.rotate` 需要以弧度為單位的角度，請使用 `Math.toRadians(degrees)` 進行度數轉換。

**AffineTransform** 是 Java 中表示二維仿射變換（如平移、旋轉、縮放或剪切）的類別。  
**BufferedImage** 是 Java 中將圖像以像素光柵方式儲存在記憶體的類別。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### 步驟 3：將圖像添加到文件
配置好變換後，將圖像繪製到當前頁面。函式庫會自動將 `BufferedImage` 轉換為相應的 PostScript 圖像串流。

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### 步驟 4：寫入圖形還原
呼叫還原（`grestore`）會將圖形狀態恢復到保存前的狀態，確保後續的繪圖指令不受先前變換影響。

```java
document.drawImage(image, transform, null);
```

### 步驟 5：關閉當前頁面並保存
結束頁面、關閉文件，並將輸出檔案寫入磁碟。

```java
document.writeGraphicsRestore();
```

您可以重複上述流程以嵌入更多圖像，每次只需調整平移座標與旋轉角度。

## 常見問題與解決方案
- **FileNotFoundException：** 請確認 `dataDir` 以檔案分隔符（`/` 或 `\\`）結尾，且圖像檔名完全相符。  
- **ImageIO.read 回傳 null：** 請確保圖像格式屬於支援清單（JPEG、PNG、BMP、GIF、TIFF）。  
- **旋轉角度不正確：** `AffineTransform.rotate` 使用弧度；請使用 `Math.toRadians(degrees)` 從度數轉換。  
- **大型頁面記憶體激增：** 使用 `Document.save` 並設定 `saveOptions.setCompress(true)` 以降低記憶體佔用。

## 常見問答

**Q: 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？**  
A: 核心函式庫僅支援 Java，但 Aspose 亦提供 .NET、C++、Python 等等等效 API，分別針對各自平台設計。

**Q: 是否提供 Aspose.Page for Java 的免費試用？**  
A: 有，您可以前往 **[Aspose.Page 免費試用頁面](https://releases.aspose.com/)** 取得。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 您可在 **[臨時授權申請頁面](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 哪裡可以找到 Aspose.Page for Java 的社群支援與討論？**  
A: 請造訪 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 取得社群協助。

**Q: 有關購買 Aspose.Page for Java 的其他資源嗎？**  
A: 您可以在 **[Aspose.Page 購買頁面](https://purchase.aspose.com/buy)** 直接購買。

## 結論
現在您已掌握完整的 **aspose.page 圖像操作 java** 範例，能建立 PostScript 檔案、平移與旋轉圖像，並將結果保存。請參閱完整的 **[文件說明](https://reference.aspose.com/page/java/)**，探索向量圖形、自訂頁面尺寸、文字渲染等進階功能。

---

**最後更新：** 2026-08-23  
**測試環境：** Aspose.Page for Java 23.11  
**作者：** Aspose  








```java
document.closePage();
document.save();
```

## 相關教學

- [如何使用 Aspose.Page Java API 將 PostScript 轉換為 PDF](/page/java/postscript-conversion/to-pdf/)
- [如何在 Java PostScript 中使用 Aspose.Page Java 添加對角漸層](/page/java/postscript-gradient-addition/diagonal/)
- [如何在 Java PostScript 中使用 Aspose.Page 添加交叉圖案](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}