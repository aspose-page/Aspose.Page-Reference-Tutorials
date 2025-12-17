---
date: 2025-12-17
description: 學習如何使用 Aspose.Page for Java 為 PostScript 文件添加紋理平鋪圖案。本指南展示如何高效添加紋理並探索創意可能性。
linktitle: Add Texture Tiling Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 如何在 Java PostScript 中加入紋理平鋪圖案
url: /zh-hant/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中加入紋理平鋪圖案

## 簡介
在 Java 開發領域，學習 **如何加入紋理** 到 PostScript 文件是一項常見需求。Aspose.Page for Java 是實現此任務的得力工具。本教學將指導您如何使用 Aspose.Page 在 Java PostScript 文件中加入紋理平鋪圖案。

## 快速解答
- **需要的函式庫是什麼？** Aspose.Page for Java  
- **本指南的主要關鍵字是什麼？** *how to add texture*  
- **測試是否需要授權？** 提供免費試用版；正式環境需購買授權。  
- **支援的 Java 版本為何？** Java 8 或以上。  
- **可以重複使用同一個紋理筆刷繪製多個形狀嗎？** 可以 – 只需建立一次 `TexturePaint`，即可套用於任何形狀。

## 什麼是紋理平鋪圖案？
紋理平鋪圖案會將小圖像（圖塊）在較大區域內重複排列，讓您 **以紋理填充形狀**，而不必手動繪製每一塊圖塊。此技術非常適合用於背景、填充以及 PostScript 中的裝飾文字效果。

## 為何使用 Aspose.Page for Java？
- **零相依性渲染** – 無需外部 PostScript 直譯器。  
- **完整的圖形控制** – 可結合向量形狀、文字與點陣圖紋理。  
- **跨平台** – 只要支援 Java 的作業系統皆可執行。  

## 前置條件
在開始教學之前，請確保您已具備以下前置條件：
- 具備 Java 程式語言的基礎知識。  
- 熟悉 PostScript 文件結構。  
- 已安裝 Aspose.Page for Java 函式庫。您可以在此處下載 [here](https://releases.aspose.com/page/java/)。

## 匯入套件
先為您的 Java 專案匯入必要的套件：

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

## 步驟 1：建立 PostScript 文件
建立新的 PostScript 文件，指定輸出串流與儲存選項。請確保已正確設定相關路徑。

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

## 步驟 2：設定圖形環境
透過平移座標原點並從紋理圖檔建立 `BufferedImage`，來設定圖形環境。

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

## 步驟 3：建立紋理筆刷
從圖像建立紋理筆刷，並指定要被紋理覆蓋的區域。

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

## 步驟 4：繪製與填充形狀
建立矩形，並使用先前定義的筆刷 **以紋理填充形狀**。此外，還會繪製輪廓以提升視覺效果。

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

## 步驟 5：加入帶有紋理圖案的文字
在文件中加入文字，示範 **如何填充紋理** 在字形上。可依需求自訂字型、位置與其他參數。

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## 步驟 6：儲存與關閉
完成後關閉目前頁面，儲存文件，確保執行流程順暢。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 常見問題與提示
- **找不到紋理檔案** – 請確認 `TestTexture.bmp` 的路徑正確且檔案可存取。  
- **圖像尺寸不正確** – 若紋理被拉伸，請調整 `imageArea` 以符合原始圖像大小。  
- **效能考量** – 為多個形狀重複使用同一個 `TexturePaint` 實例，以避免不必要的物件建立。

## 常見問答

**Q: Aspose.Page for Java 適合初學者嗎？**  
A: 絕對適合！Aspose.Page for Java 提供完整文件，讓各層級開發者都能輕鬆上手。

**Q: 我可以將 Aspose.Page for Java 整合到現有的 Java 專案嗎？**  
A: 可以，只要依照此處提供的文件說明 [here](https://reference.aspose.com/page/java/) 即可輕鬆整合。

**Q: 哪裡可以取得支援或討論 Aspose.Page 相關問題？**  
A: 前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 與社群互動並尋求協助。

**Q: 是否有免費試用版可供 Aspose.Page for Java 使用？**  
A: 有，您可以在此處取得免費試用版 [here](https://releases.aspose.com/)。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 請前往此連結 [this link](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

## 結論
恭喜您！您已成功學會 **如何加入紋理** 平鋪圖案至 Java PostScript 文件，並使用 Aspose.Page for Java 完成操作。歡迎進一步探索自訂選項——嘗試不同的點陣圖圖塊、縮放比例與合成方式，釋放紋理填充的全部創意潛力。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-17  
**測試環境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

---