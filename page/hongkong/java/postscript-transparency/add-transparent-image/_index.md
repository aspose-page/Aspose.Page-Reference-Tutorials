---
date: 2025-12-18
description: 學習如何使用 Aspose.Page for Java 建立 PostScript 文件並加入透明圖像。本指南示範如何輕鬆將圖像添加到 PostScript。
linktitle: Create PostScript Document Java – Add Transparent Image
second_title: Aspose.Page Java API
title: 使用 Java 建立 PostScript 文件 – 添加透明圖像
url: /zh-hant/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中加入透明圖像

## 簡介
在 Java PostScript 的世界裡，提升文件的視覺效果通常需要加入透明圖像。本教學將指導您如何在使用功能強大的 Aspose.Page for Java 函式庫的同時，完成 **create postscript document java** 的過程。您將看到如何將圖像加入 PostScript、精確定位，以及控制其不透明度，以達到專業外觀的效果。

## 快速回答
- **本教學涵蓋什麼內容？** 使用 Aspose.Page for Java 將透明 PNG 加入 PostScript 文件。  
- **需要哪個函式庫？** Aspose.Page for Java（從官方網站下載）。  
- **需要授權嗎？** 生產環境需要臨時或正式授權；亦提供免費試用。  
- **可以使用其他圖像格式嗎？** 可以，但 PNG（具備 Alpha 通道）在透明度方面表現最佳。  
- **實作需要多久時間？** 基本範例大約需要 10‑15 分鐘。

## 什麼是 Java 中的 PostScript 文件？
PostScript 文件是一種頁面描述語言（PDL）檔案，用於描述文字、圖形與影像。透過 Java，您可以以程式方式產生這些檔案，完整掌控版面配置與渲染。主要關鍵字 **create postscript document java** 正是此功能的寫照。

## 為什麼要加入透明圖像？
透明圖像可讓您在不遮蔽底層內容的情況下疊加圖形，非常適合用於浮水印、標誌或裝飾元素。將透明度與精確定位結合，可產生外觀精緻、品牌一致的文件。

## 先決條件
在開始本教學之前，請確保已具備以下先決條件：

1. Java Development Kit（JDK）：確保您的機器已安裝最新的 JDK。  
2. Aspose.Page for Java：從 [website](https://releases.aspose.com/page/java/) 下載並安裝 Aspose.Page for Java 函式庫。  
3. 文件目錄：在系統上建立一個目錄，用於儲存您的 Java PostScript 文件。  
4. 透明圖像檔案：準備一個透明圖像檔（例如「mask1.png」），於教學中使用。

## 匯入套件
在您的 Java 專案中，匯入必要的套件以利用 Aspose.Page for Java 提供的功能。以下是您需要的完整匯入區塊：

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

## 如何使用透明圖像建立 postscript document java？
以下為逐步說明。每一步皆包含簡短說明，並附上原始程式碼區塊（保持不變）。

### 步驟 1：設定背景顏色
我們先建立 PostScript 文件、開啟輸出串流，並繪製一個紅色矩形作為透明圖像的視覺參考。

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

### 步驟 2：平移座標
在繪製之前，我們將原點平移至頁面上方便的位置，使圖像顯示在預期位置。

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

### 步驟 3：建立圖像物件
載入包含 Alpha 通道的 PNG 檔案。此圖像將用於不透明與透明的渲染。

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

### 步驟 4：加入不透明圖像
首先，我們將圖像以一般的 RGB 位圖繪製。此步驟示範之後套用透明度時的差異。

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

### 步驟 5：加入透明圖像
接著，我們以完整不透明度（255）或 0‑255 之間的任意值繪製相同圖像，以控制透明度。此處使用 255 代表完全不透明，若想呈現透視效果可降低此數值。

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

### 步驟 6：儲存與關閉
最後，我們還原圖形狀態、關閉頁面，並將文件儲存至磁碟。

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## 常見問題與解決方案
- **FileNotFoundException** – 請確認 `dataDir` 指向正確的資料夾，且 `mask1.png` 已存在。  
- **ImageIO.read returns null** – 請確保 PNG 格式正確且未損壞。  
- **Transparent image appears opaque** – 調整 `drawTransparentImage` 的第三個參數（0 = 完全透明，255 = 完全不透明）。

## 常見問答
### 我可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？
可以，Aspose.Page for Java 可無縫整合其他 Java 函式庫，以增強文件處理功能。

### Aspose.Page for Java 是否提供免費試用？
可以，您可從 [here](https://releases.aspose.com/) 取得 Aspose.Page for Java 的免費試用。

### 如何取得 Aspose.Page for Java 的臨時授權？
您可從 [this link](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### 是否有 Aspose.Page for Java 的支援論壇？
有，請造訪 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) 取得社群支援與討論。

### 在哪裡可以找到 Aspose.Page for Java 的文件？
請參考完整的 [documentation](https://reference.aspose.com/page/java/) 以取得 Aspose.Page for Java 的詳細資訊。

## 結論
恭喜！您已成功學會如何 **create postscript document java**，並使用 Aspose.Page for Java 加入透明圖像。可嘗試不同的圖像、不透明度與位置，打造符合品牌需求的視覺驚豔文件。

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}