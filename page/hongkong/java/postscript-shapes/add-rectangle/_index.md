---
date: 2026-02-18
description: 學習如何使用 Aspose.Page 在 Java PostScript 中繪製矩形形狀。本分步指南將示範如何設定畫筆、設定矩形顏色（Java），以及如何創建生動的圖形，同時說明如何高效繪製矩形。
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: 如何在 Java PostScript 中使用 Aspose.Page 繪製矩形
url: /zh-hant/java/postscript-shapes/add-rectangle/
weight: 11
---

 Chinese. Eg "Aspose.Page for Java 文件說明". Keep link.

Similarly other links.

Also bullet list items.

Let's produce final content.

Be careful with "Quick Answers" section bullet items.

Translate accordingly.

Also "Common Use Cases for Rectangle Drawing" etc.

Make sure to preserve markdown formatting.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用 Aspose.Page 繪製矩形

## 介紹
如果您需要在 Java PostScript 檔案中 **繪製矩形**，您來對地方了。在本教學中，我們將示範如何使用 Aspose.Page for Java 新增彩色矩形、控制填色與描邊，並將結果儲存為 PostScript 文件。您將會看到 **如何設定 Paint**、如何定義矩形的幾何形狀，以及為什麼此方法非常適合以程式方式產生可列印的圖形。完成本指南後，您也會了解 **draw rectangle java** 技術的更廣泛應用，以及它在 **java awt rectangle drawing** 工作流程中的角色。

## 快速回答
- **需要哪個函式庫？** Aspose.Page for Java  
- **可以更改矩形顏色嗎？** 可以 – 使用 `setPaint` 搭配任意 `java.awt.Color`  
- **開發階段需要授權嗎？** 免費試用版可用於測試；正式上線需購買授權  
- **範例使用哪種頁面尺寸？** A4（`PsSaveOptions` 的預設值）  
- **程式碼支援 Java 8+ 嗎？** 完全支援 – 使用標準 AWT 類別  

## 什麼是 PostScript 中的「繪製矩形」？
在 PostScript 文件中繪製矩形意味著定義一個矩形區域，然後填色、描邊或同時執行兩者。使用 Aspose.Page 時，您可以透過熟悉的 **java awt rectangle drawing** 類別來完成，讓程式碼易於閱讀與維護。

## 為什麼選擇 Aspose.Page 來處理矩形圖形？
- **跨平台**：產生符合標準的 PostScript，可在任何印表機上使用。  
- **細緻控制**：可分別設定填色、描邊顏色與線寬。  
- **無外部相依**：僅使用內建的 AWT 幾何類別，無需額外圖形函式庫。  

## 前置條件
在開始教學之前，請確保您已具備以下條件：
- 基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page for Java 函式庫。若尚未安裝，請從 [Aspose.Page for Java 文件說明](https://reference.aspose.com/page/java/) 下載。  
- 在您的機器上已設定好 Java 開發環境。

## 匯入套件
在 Java 專案中，先匯入必要的套件。這些匯入讓您可以使用 AWT 的 `Color`、`BasicStroke`、`Rectangle2D` 類別，以及 Aspose.Page 的核心文件處理類別。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟說明：在 Java PostScript 中繪製矩形

### 步驟 1：設定填充矩形的 Paint  
**如何設定 Paint** – 我們為第一個矩形選擇橙色填充，示範 **set rectangle color java** 的功能。

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

### 步驟 2：設定描邊矩形的 Paint  
**set rectangle color java** – 接著將 Paint 改為紅色，並定義描邊寬度。此範例說明如何使用自訂線寬 **draw rectangle java**。

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### 步驟 3：關閉當前頁面並儲存文件  
繪製完成後，我們關閉頁面並將檔案寫入磁碟。關閉頁面可確保所有繪圖指令都已寫入 PostScript 串流。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 矩形繪製的常見應用情境
- **發票或收據產生** – 矩形作為邊框或突顯區塊。  
- **標籤製作** – 繪製彩色方框以區分商品資訊。  
- **簡易圖表** – 使用填充矩形作為長條圖元素。  
- **自訂可列印表單** – 結合矩形與文字建立表單欄位。  

## 常見問題與技巧
- **檔案路徑錯誤** – 確認 `dataDir` 以檔案分隔符 (`/` 或 `\\`) 結尾。  
- **授權例外** – 試用版會加上浮水印，正式使用請取得完整授權。  
- **顏色可見度** – 部分印表機對某些 RGB 值的解讀不同，建議先測試黑色矩形。  
- **記憶體使用** – 大型文件建議在每頁結束後呼叫 `document.closePage()` 以釋放資源。  

## 常見問答

**Q:** *我可以在其他程式語言中使用 Aspose.Page for Java 嗎？*  
A: Aspose.Page 主要支援 Java，但其他語言也有類似的函式庫可供選擇。

**Q:** *是否有 Aspose.Page for Java 的試用版？*  
A: 有，您可以透過 [免費試用版](https://releases.aspose.com/) 了解功能。

**Q:** *哪裡可以找到更多協助與討論？*  
A: 前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 與社群互動取得協助。

**Q:** *如何取得 Aspose.Page for Java 的臨時授權？*  
A: 請至 [此處](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

**Q:** *哪裡可以購買 Aspose.Page for Java 的正式授權？*  
A: 前往 [此處](https://purchase.aspose.com/buy) 購買授權版本。

**其他問答**

**Q:** *我可以動態調整矩形大小嗎？*  
A: 可以 – 在呼叫 `fill` 或 `draw` 前，只需修改 `Rectangle2D.Float(x, y, width, height)` 的參數。

**Q:** *能否在矩形內加入文字？*  
A: 完全可以。繪製矩形後，使用 `document.drawString(...)` 並指定字型與位置即可。

**Q:** *Aspose.Page 是否支援其他形狀，例如圓形或多邊形？*  
A: 支援，API 提供 `drawEllipse`、`drawPolygon` 等方法，可繪製各種向量圖形。

## 結論
本指南示範了 **如何在 Java PostScript 文件中繪製矩形**，說明了 **如何設定 Paint**，並展示了 **set rectangle color java** 的用法。現在您已具備建立多彩可列印圖形的基礎，無論是發票、標籤或自訂表單，都能輕鬆上手。歡迎嘗試不同的顏色、線條樣式以及其他 AWT 形狀，讓輸出更加豐富。

---

**最後更新：** 2026-02-18  
**測試環境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}