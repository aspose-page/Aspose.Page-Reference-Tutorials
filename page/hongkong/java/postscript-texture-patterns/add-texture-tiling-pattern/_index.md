---
date: 2026-05-05
description: 學習如何使用 Aspose.Page for Java 為 PostScript 文件添加紋理平鋪圖案。本指南示範如何高效加入紋理，並探索創意的可能性。
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: 在 Java PostScript 中新增紋理平鋪圖案
second_title: Aspose.Page Java API
title: 如何在 Java PostScript 中加入紋理平鋪圖樣
url: /zh-hant/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中加入紋理平鋪圖案

## 介紹
在 Java 開發領域，學習 **如何加入紋理** 到 PostScript 文件是一項常見需求。Aspose.Page for Java 讓此工作變得簡單，讓您專注於設計而非低階的 PostScript 語法。在本教學中，我們將逐步說明如何新增紋理平鋪圖案、填充形狀，甚至在 Java PostScript 文件中為文字加入紋理。

## 快速回答
- **需要的程式庫是什麼？** Aspose.Page for Java  
- **本指南的主要關鍵字是什麼？** *how to add texture*  
- **測試是否需要授權？** A free trial is available; a license is required for production.  
- **支援的 Java 版本是？** Java 8 or higher.  
- **我可以在多個形狀上重複使用紋理筆刷嗎？** Yes – create the `TexturePaint` once and apply it to any shape.  
- **如何使用紋理填滿矩形？** Use `document.fill(shape)` after setting the `TexturePaint` as the current paint.

## 什麼是紋理平鋪圖案？
紋理平鋪圖案會在較大的區域內重複小圖像（圖塊），讓您能夠 **以紋理填滿形狀**，而無需手動繪製每個圖塊。此技術非常適合用於 PostScript 中的背景、填充以及裝飾性文字效果。

## 為什麼使用 Aspose.Page for Java？
- **零依賴渲染** – no need for external PostScript interpreters.  
- **完整的圖形控制** – combine vector shapes, text, and bitmap textures.  
- **跨平台** – works on any OS that supports Java.  

## 前置條件
在開始本教學之前，請確保已具備以下前置條件：

- 具備 Java 程式語言的基本了解。  
- 熟悉 PostScript 文件結構。  
- 已安裝 Aspose.Page for Java 程式庫。您可以在此處下載 [此處](https://releases.aspose.com/page/java/)。  

## 匯入套件
首先為您的 Java 專案匯入必要的套件：

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 如何在 Java PostScript 中加入紋理平鋪圖案
以下是一個逐步指南。每個步驟都包含簡短說明，並附上您需要複製的完整程式碼。

### 步驟 1：建立 PostScript 文件
首先建立新的 PostScript 文件，指定輸出串流與儲存選項。確保已正確設定所需的路徑。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步驟 2：設定圖形環境
將原點平移至方便的位置，並載入作為紋理圖塊的位圖。

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### 步驟 3：建立紋理筆刷
定義一個會在形狀區域內重複位圖的 `TexturePaint`。如果想讓圖塊顯示得更大或更小，請調整矩形大小。

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### 步驟 4：繪製與填充形狀
建立一個矩形，並使用筆刷 **以紋理填滿矩形**。然後描邊形狀，使結果在視覺上更為明顯。

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### 步驟 5：使用紋理圖案加入文字
您也可以將相同的紋理套用於文字字形。這示範了 **如何在字元上填入紋理**，同時仍能對其描邊。

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### 步驟 6：儲存與關閉
最後，關閉頁面、儲存文件，並釋放資源。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 常見問題與技巧
- **缺少紋理檔案** – Verify the path to `TestTexture.bmp` is correct and the file is accessible.  
- **圖像尺寸不正確** – If the texture appears stretched, adjust `imageArea` to match the original image size.  
- **效能** – Reuse the same `TexturePaint` instance for multiple shapes to avoid unnecessary object creation.  
- **專業提示：** Use a high‑resolution bitmap for the tile to keep the texture crisp when scaled.  

## 常見問答

**Q: Aspose.Page for Java 適合初學者嗎？**  
A: 絕對適合！Aspose.Page for Java 提供完整的文件，使各種技術程度的開發者都能輕鬆使用。

**Q: 我可以將 Aspose.Page for Java 整合到現有的 Java 專案中嗎？**  
A: 可以，您只要依照提供的文件說明即可輕鬆將 Aspose.Page for Java 整合至您的專案，文件位於 [此處](https://reference.aspose.com/page/java/)。  

**Q: 我可以在哪裡取得支援或討論 Aspose.Page 相關問題？**  
A: 前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 與社群互動並尋求協助。  

**Q: 是否提供 Aspose.Page for Java 的免費試用？**  
A: 有，您可以在此處探索免費試用 [此處](https://releases.aspose.com/)。  

**Q: 我該如何取得 Aspose.Page for Java 的臨時授權？**  
A: 前往 [此連結](https://purchase.aspose.com/temporary-license/) 取得臨時授權。  

## 結論
恭喜！您已成功學會使用 Aspose.Page for Java 在 Java PostScript 文件中加入 **紋理平鋪圖案**。隨時嘗試不同的位圖圖塊、縮放比例與合成操作，盡情發揮紋理填充的創意潛力。

---

**Last Updated:** 2026-05-05  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}