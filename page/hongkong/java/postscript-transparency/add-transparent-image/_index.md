---
date: 2026-03-05
description: 學習如何使用 Aspose.Page for Java 設定背景顏色並將透明圖像加入 PostScript，輕鬆將 PNG 轉換為 PostScript。
linktitle: Add Transparent Image in Java PostScript
second_title: Aspose.Page Java API
title: 設定背景顏色 Java：向 PS 添加透明圖像
url: /zh-hant/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定背景顏色 Java：在 PS 中加入透明圖像

## 介紹
如果您在使用 Java PostScript 時需要 **set background color java**，加入透明圖像可以讓您的文件呈現更精緻、專業的外觀。在本教學中，我們將逐步說明設定彩色背景、將 PNG 轉換為 PostScript，以及使用 Aspose.Page for Java 函式庫繪製不透明與透明圖像的完整流程。完成後，您將能夠 **add image to postscript** 檔案，並完整掌控不透明度。

## 快速解答
- **什麼函式庫處理 Java PostScript 中的透明度？** Aspose.Page for Java.  
- **我可以在繪製圖像前設定背景顏色嗎？** Yes – use `document.setPaint()` and `fill()`.  
- **如何將 PNG 轉換為 PostScript？** Load the PNG with `ImageIO.read()` and draw it with `drawImage` or `drawTransparentImage`.  
- **圖像是否支援不透明度？** Use `drawTransparentImage` to specify an opacity value (0‑255).  
- **生產環境是否需要授權？** A valid Aspose.Page for Java license is required; a free trial is available.

## 前置條件
在開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)** – 已安裝最新版本。  
2. **Aspose.Page for Java** – 從[網站](https://releases.aspose.com/page/java/)下載。  
3. **Document Directory** – 用於寫入 PostScript 檔案的資料夾。  
4. **Translucent Image File** – 例如 `mask1.png`，我們將用它示範 **convert png to postscript** 步驟。

## 匯入套件
在您的 Java 專案中，匯入必要的類別。此區塊保持不變：

```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟 1：設定背景顏色 Java
在此我們建立文件，選擇 A4 大小，並填滿紅色矩形以示範背景對比。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Add a red rectangle under images for visual contrast
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```

## 步驟 2：平移座標
在放置圖像之前，將繪圖游標移動到頁面上的合適位置。

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

## 步驟 3：建立圖像物件
載入 PNG 檔案（我們的 **convert png to postscript** 步驟）。

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

## 步驟 4：加入不透明圖像
正常繪製圖像——此示範 **add image to postscript**（不含透明度）。

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

## 步驟 5：加入透明圖像（以不透明度繪製圖像）
現在我們使用 `drawTransparentImage` 以完整不透明度（255）呈現相同的 PNG。調整此數值即可控制透明度。

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

## 步驟 6：儲存與關閉
完成文件並釋放資源。

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## 為何這很重要
使用 Java 設定背景顏色可提供一個畫布，以突顯覆蓋的圖形。結合 **draw image with opacity**，您可以直接在 PostScript 中建立浮水印、商標或 UI 模型，而無需外部編輯工具。

## 常見問題與技巧
- **圖像未顯示透明**：確認 PNG 確實包含 alpha 通道。  
- **顏色不正確**：請記得背景矩形是在圖像之前繪製的；調整 `Color` 值以符合您的設計。  
- **效能**：對於大型文件，重複使用單一 `AffineTransform` 實例以減少物件建立的開銷。

## 常見問答

**問：我可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？**  
答：可以，Aspose.Page for Java 能無縫整合至其他 Java 函式庫，以增強文件處理功能。

**問：Aspose.Page for Java 是否提供免費試用？**  
答：是的，您可從[此處](https://releases.aspose.com/)取得 Aspose.Page for Java 的免費試用。

**問：如何取得 Aspose.Page for Java 的臨時授權？**  
答：您可透過[此連結](https://purchase.aspose.com/temporary-license/)取得臨時授權。

**問：是否有 Aspose.Page for Java 的支援論壇？**  
答：有，請前往 [Aspose.Page for Java 論壇](https://forum.aspose.com/c/page/39) 獲取社群支援與討論。

**問：在哪裡可以找到 Aspose.Page for Java 的文件？**  
答：請參考完整的[文件](https://reference.aspose.com/page/java/)，以取得 Aspose.Page for Java 的詳細資訊。

---

**最後更新：** 2026-03-05  
**測試環境：** Aspose.Page for Java 24.11 (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}