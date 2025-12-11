---
date: 2025-12-11
description: 學習如何在 Java PostScript 中使用 Aspose.Page 繪製矩形形狀。本分步指南展示如何設定畫筆、設定矩形顏色（Java），並創建充滿活力的圖形。
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: 如何在 Java PostScript 中使用 Aspose.Page 繪製矩形
url: /zh-hant/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用 Aspose.Page 繪製矩形

## 簡介
如果您需要在 Java PostScript 檔案中 **how to draw rectangle** 繪製矩形形狀，您來對地方了。在本教學中，我們將示範如何使用 Aspose.Page for Java 新增彩色矩形、控制填充與描邊，並將結果儲存為 PostScript 文件。您將會看到 **how to set paint** 的具體做法、如何定義矩形的幾何形狀，以及為何此方法適合以程式方式產生可列印的圖形。

## 快速回答
- **What library is required?** Aspose.Page for Java  
- **Can I change rectangle colors?** Yes – use `setPaint` with any `java.awt.Color`  
- **Do I need a license for development?** A free trial works for testing; a license is required for production  
- **Which page size is used in the example?** A4 (default `PsSaveOptions`)  
- **Is the code compatible with Java 8+?** Absolutely – it uses standard AWT classes  

## 先決條件
在開始本教學之前，請確保您已具備以下條件：
- 具備基本的 Java 程式設計概念。  
- 已安裝 Aspose.Page for Java 函式庫。若尚未安裝，請從 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) 下載。  
- 在您的機器上已設定 Java 開發環境。

## 匯入套件
在您的 Java 專案中，先匯入必要的套件：

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 如何在 Java PostScript 中繪製矩形
以下是完整的工作流程，分為清晰的步驟說明。每個步驟皆包含簡短說明，並附上原始程式碼區塊（保持不變）。

### 步驟 1：設定矩形填充的 Paint  
**How to set paint** – 我們為第一個矩形選擇橙色作為填充顏色。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### 步驟 2：設定矩形描邊的 Paint  
**Set rectangle color java** – 接著將 Paint 改為紅色，並定義描邊寬度。

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### 步驟 3：關閉當前頁面並儲存文件  
繪製完成後，我們關閉頁面並將檔案寫入磁碟。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 為什麼使用 Aspose.Page 繪製矩形圖形？
- **Cross‑platform**：產生符合標準的 PostScript，可在任何印表機上使用。  
- **Fine‑grained control**：可分別設定填充顏色、描邊顏色與線寬。  
- **No external dependencies**：僅使用內建的 AWT 幾何類別。  

## 常見問題與技巧
- **File path errors** – 請確保 `dataDir` 以檔案分隔符結尾（`/` 或 `\\`）。  
- **License exceptions** – 試用版會加入浮水印；正式使用時請取得完整授權。  
- **Color visibility** – 某些印表機可能對特定 RGB 值的呈現不同，建議先測試簡單的黑色矩形。

## 結論
本指南示範了 **how to draw rectangle** 在 Java PostScript 文件中的實作方式，說明了 **how to set paint** 的步驟，並展示了如何 **set rectangle color java**。歡迎自行嘗試不同的形狀、顏色與線條樣式，為報表、發票或自訂列印建立豐富的可列印圖形。

## 常見問答

### 我可以在其他程式語言中使用 Aspose.Page for Java 嗎？
Aspose.Page 主要支援 Java，但其他語言亦有類似的函式庫可供使用。

### 是否提供 Aspose.Page for Java 的試用版？
是的，您可以透過 [free trial version](https://releases.aspose.com/) 體驗 Aspose.Page for Java 的功能。

### 我可以在哪裡找到更多協助與討論？
請前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 與社群互動並取得協助。

### 如何取得 Aspose.Page for Java 的臨時授權？
請至 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### 我該從哪裡購買 Aspose.Page for Java 的授權版本？
請至 [here](https://purchase.aspose.com/buy) 購買授權版本。

**Additional Q&A**

**Q:** *我可以動態變更矩形的大小嗎？*  
**A:** 可以 – 只要在呼叫 `fill` 或 `draw` 前，修改 `Rectangle2D.Float(x, y, width, height)` 的參數即可。

**Q:** *能否在矩形內加入文字？*  
**A:** 當然可以。繪製矩形後，使用 `document.drawString(...)` 並指定字型與位置即可。

**Q:** *Aspose.Page 是否支援其他形狀，如圓形或多邊形？*  
**A:** 支援，API 提供 `drawEllipse`、`drawPolygon` 等方法，可繪製各種向量圖形。

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}