---
date: 2026-02-15
description: 學習如何使用 Aspose.Page for Java 建立 PostScript Java 文件，並產生具備圖像平移與旋轉功能的 PostScript
  文件檔案。
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: 建立 PostScript Java – 在 Java PostScript 中加入圖像
url: /zh-hant/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 PostScript Java – 在 Java PostScript 中加入圖像

## Introduction
在本教學中，您將學習如何使用 Aspose.Page for Java 函式庫 **create postscript java** 文件並嵌入圖像。我們將逐步說明，從初始化新的 PostScript 檔案到套用 **translate and rotate image** 轉換。完成後，您將能以程式方式產生 PostScript 檔案，並以像素精準度控制圖像位置——非常適合自動化報表、列印工作流程，或任何需要從 Java **generate postscript document** 輸出的情境。

## Quick Answers
- **What library is required?** Aspose.Page for Java  
- **Can I add multiple images?** Yes – repeat the transform and draw steps  
- **Do I need a license for development?** A free trial works for testing; a license is required for production  
- **Which Java version is supported?** Java 8 and later  
- **Is image rotation supported?** Absolutely – use `AffineTransform.rotate()`

## What is create postscript java?
**create postscript java** 操作會產生一個 PostScript 頁面描述檔，內含文字、向量圖形與點陣圖。使用 Aspose.Page，您可以直接從 Java 程式碼建立這些檔案，完整掌控版面配置、縮放與旋轉，且不需額外的 PostScript 直譯器。

## Why use Aspose.Page for image manipulation?
- **High‑level API:** 抽象低階 PostScript 指令為簡單的 Java 方法。  
- **Cross‑platform:** 可在任何支援 Java 的作業系統上執行。  
- **Full graphics‑state control:** 可隨意儲存、還原、平移、縮放與旋轉圖形。  
- **No external dependencies:** 內部處理圖像載入、格式轉換與嵌入。

## Prerequisites
在開始撰寫程式碼之前，請確保您已具備：

- 已在系統上安裝 Java Development Kit (JDK)。  
- Aspose.Page for Java 函式庫。您可於[此處](https://releases.aspose.com/page/java/)下載。  
- 基本的 Java 程式設計知識。  

## Import Packages
要開始使用，請在 Java 專案中匯入必要的套件。以下程式碼片段可作為參考：

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Write Graphics Save
第一步是將圖形儲存指令寫入文件。這可確保之後的任何轉換或修改在需要時能夠回復。

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

## Step 2: Translate and Transform (translate and rotate image)
接著平移文件，並從圖像檔案建立 `BufferedImage` 物件。使用 `AffineTransform` 套用一系列的縮放與旋轉等轉換。此處即執行 **translate and rotate image** 操作。

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

## Step 3: Add Image to Document
現在，將已轉換的圖像加入文件。

```java
document.drawImage(image, transform, null);
```

## Step 4: Write Graphics Restore
加入圖像後，寫入圖形還原指令以完成變更。

```java
document.writeGraphicsRestore();
```

## Step 5: Close Current Page and Save
關閉當前頁面並儲存文件。

```java
document.closePage();
document.save();
```

您可以重複上述步驟以加入多張圖像，或依需求自訂轉換參數。

## Common Issues and Solutions
- **FileNotFoundException:** 確保 `dataDir` 路徑以檔案分隔符 (`/` 或 `\\`) 結尾，且圖像檔名完全相符。  
- **ImageIO.read returns null:** 確認圖像格式受支援（例如 JPEG、PNG）。  
- **Incorrect rotation angle:** `AffineTransform.rotate` 需要弧度。若使用度數，請先轉換為弧度（`Math.toRadians(degrees)`）。

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java with other programming languages?**  
A: Aspose.Page 主要支援 Java，但也提供其他程式語言的版本。

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: 有，您可於[此處](https://releases.aspose.com/)取得免費試用。

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: 您可於[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

**Q: Where can I find community support and discussions related to Aspose.Page for Java?**  
A: 請造訪 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 取得社群支援。

**Q: Are there any additional resources for purchasing Aspose.Page for Java?**  
A: 您可於[此處](https://purchase.aspose.com/buy)購買此函式庫。

## Conclusion
恭喜！您已成功學會如何使用 Aspose.Page for Java **create postscript java** 文件並嵌入圖像。請探索[文件說明](https://reference.aspose.com/page/java/)以了解更多進階功能，如向量圖形、文字渲染與自訂頁面尺寸。

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}