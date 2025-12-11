---
date: 2025-12-09
description: 學習如何使用 Java 建立 PostScript 文件，並使用 Aspose.Page 進行影像的平移與旋轉，以實現無縫的影像處理。
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: 使用 Java 建立 PostScript 文件 – 在 Java PostScript 中加入圖像
url: /zh-hant/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 PostScript 文件（Java） – 在 Java PostScript 中加入圖像

## Introduction
在本教學中，您將學習如何 **建立 PostScript 文件（Java）**，並使用 Aspose.Page for Java 函式庫嵌入圖像。我們將逐步說明，從設定文件到套用 **平移與旋轉圖像** 的轉換操作。完成後，您將能以程式方式產生豐富的 PostScript 檔案，並自訂圖像位置以符合精確的版面需求。

## Quick Answers
- **需要的函式庫是什麼？** Aspose.Page for Java  
- **可以加入多張圖像嗎？** 可以 – 重複轉換與繪製步驟  
- **開發時需要授權嗎？** 免費試用可用於測試；正式環境需購買授權  
- **支援哪個 Java 版本？** Java 8 及以上  
- **支援圖像旋轉嗎？** 當然可以 – 使用 `AffineTransform.rotate()`  

## What is creating a PostScript document in Java?
在 Java 中建立 PostScript 文件是指產生一種頁面描述語言檔案，用於描述文字、圖形與圖像。透過 Aspose.Page，您可以在 Java 中以程式方式生成此類檔案，完整掌控版面、圖形狀態與圖像處理，無需 PostScript 直譯器。

## Why use Aspose.Page for image manipulation?
- **高階 API：** 簡化複雜的 PostScript 指令。  
- **跨平台：** 可在任何支援 Java 的作業系統上執行。  
- **完整圖形狀態控制：** 輕鬆儲存、還原、平移、縮放與旋轉圖形。  
- **無外部相依性：** 內部處理圖像載入與轉換。

## Prerequisites
在開始之前，請確保您已具備以下項目：

- 已在系統上安裝 Java Development Kit (JDK)。  
- Aspose.Page for Java 函式庫。您可在[此處](https://releases.aspose.com/page/java/)下載。  
- 具備基本的 Java 程式設計知識。  

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
接著，平移文件並從圖像檔案建立 `BufferedImage` 物件。使用 `AffineTransform` 套用一系列的縮放與旋轉等轉換。此即為 **平移與旋轉圖像** 的操作所在。

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
現在，將已轉換的圖像加入文件中。

```java
document.drawImage(image, transform, null);
```

## Step 4: Write Graphics Restore
加入圖像後，寫入圖形還原指令以完成變更。

```java
document.writeGraphicsRestore();
```

## Step 5: Close Current Page and Save
關閉目前的頁面並儲存文件。

```java
document.closePage();
document.save();
```

您可以重複上述步驟以加入多張圖像，或依需求自訂轉換參數。

## Common Issues and Solutions
- **FileNotFoundException：** 確認 `dataDir` 路徑以檔案分隔符 (`/` 或 `\\`) 結尾，且圖像檔名完全相符。  
- **ImageIO.read 回傳 null：** 檢查圖像格式是否受支援（如 JPEG、PNG）。  
- **旋轉角度不正確：** `AffineTransform.rotate` 需要弧度。若使用角度，請先轉換為弧度（`Math.toRadians(degrees)`）。

## Frequently Asked Questions

**Q: 我可以在其他程式語言中使用 Aspose.Page for Java 嗎？**  
A: Aspose.Page 主要支援 Java，但也提供其他程式語言的版本。

**Q: Aspose.Page for Java 有免費試用嗎？**  
A: 有，您可於[此處](https://releases.aspose.com/)取得免費試用。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 您可於[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

**Q: 哪裡可以找到 Aspose.Page for Java 的社群支援與討論？**  
A: 請前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得社群支援。

**Q: 有關購買 Aspose.Page for Java 的其他資源嗎？**  
A: 您可於[此處](https://purchase.aspose.com/buy)購買此函式庫。

## Conclusion
恭喜！您已成功學會如何 **建立 PostScript 文件（Java）**，並使用 Aspose.Page for Java 嵌入圖像。請參考 [文件說明](https://reference.aspose.com/page/java/) 以探索更進階的功能，例如向量圖形、文字渲染與自訂頁面尺寸。

---

**最後更新：** 2025-12-09  
**測試環境：** Aspose.Page for Java 23.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}