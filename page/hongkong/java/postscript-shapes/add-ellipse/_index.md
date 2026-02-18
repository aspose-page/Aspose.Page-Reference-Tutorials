---
date: 2026-02-18
description: 學習如何設定塗料顏色，並在 Java 中使用 Aspose.Page 建立 PostScript 橢圓。本指南說明如何在 Java 中填充橢圓、繪製橢圓輪廓，以及設定筆劃粗細。
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: 在 Java 中設定繪圖顏色以繪製 PostScript 橢圓
url: /zh-hant/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定繪圖顏色以在 Java 中繪製 PostScript 橢圓

## 介紹
如果您在繪製向量圖形時需要 **設定繪圖顏色**，Aspose.Page for Java 函式庫可讓您完整掌控每一次的筆畫與填色。在本教學中，您將學會如何 **設定繪圖顏色**、**在 Java 中填充橢圓**，以及 **繪製橢圓輪廓**，採用簡單的逐步方式。完成後，您即可在發票、報告或任何可列印文件中加入高品質的 PostScript 橢圓。

## 快速解答
- **什麼函式庫最適合在 Java 中繪製 PostScript 圖形？** Aspose.Page for Java.  
- **我可以用純色填充橢圓嗎？** 可以 – 在 `fill` 之前使用 `document.setPaint(Color.YOUR_COLOR)`。  
- **如何只繪製橢圓的輪廓？** 設定 paint 與 stroke，然後呼叫 `document.draw(...)`。  
- **生產環境需要授權嗎？** 需要商業授權；測試可使用臨時授權。  
- **支援哪個 Java 版本？** 任何 Java 8 以上的執行環境皆可與目前的 Aspose.Page 版本相容。  

## 什麼是 PostScript 橢圓？
PostScript 橢圓是一種由外接矩形定義的向量形狀。與點陣圖不同，它可在不失真的情況下縮放，因而非常適合高解析度列印與 PDF 轉換。

## 為什麼使用 Aspose.Page 來建立 PostScript 橢圓？
- **完整控制** 繪圖基元（線條、曲線、橢圓）。  
- **跨平台** – 可在 Windows、Linux 與 macOS 上執行。  
- **無外部相依性** – 純 Java API，無原生程式碼。  
- **輕鬆整合** 與現有的 Java 應用程式及建置工具。  

## 前置條件
在開始之前，請確保您已具備：

1. 功能完整的 Java 開發環境（JDK 8 或更新版本）。  
2. 已將 Aspose.Page for Java 函式庫加入您的專案。您可在 **[此處](https://releases.aspose.com/page/java/)** 下載。  

## 匯入套件
在您的 Java 原始檔中，匯入繪製與儲存 PostScript 內容所需的類別。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 如何為橢圓設定繪圖顏色
設定繪圖顏色是任何填充或描邊操作之前的第一步。`setPaint` 方法決定下一個繪圖指令所使用的顏色。

### 步驟 1：設定 PostScript 文件
建立輸出串流、設定頁面尺寸，並實例化 `PsDocument`。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步驟 2：如何填充橢圓 – 使用設定繪圖顏色
要 **填充橢圓**，必須先以欲填充的顏色呼叫 `setPaint`，再以 `Ellipse2D` 例項呼叫 `fill`。

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 步驟 3：繪製橢圓輪廓並設定筆畫粗細
填充完成後，您可以將繪圖顏色改為其他顏色，定義 `BasicStroke` 以控制線寬，然後繪製橢圓輪廓。

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 步驟 4：關閉並儲存文件
完成頁面後，將 PostScript 檔寫入磁碟。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

現在您已擁有一個包含兩個橢圓的 PostScript 檔案——一個以橙色填充，另一個以紅色描邊。隨意嘗試不同的座標、尺寸與顏色，以符合您的設計需求。

## 常見問題與故障排除
- **檔案路徑不正確** – 確認 `dataDir` 以適合您作業系統的分隔符（`/` 或 `\\`）結尾。  
- **缺少授權** – 若未取得有效授權，函式庫將以評估模式執行，可能會加入浮水印。  
- **顏色未套用** – 記得在每次 `fill` 或 `draw` 呼叫 *之前* 設定 `document.setPaint(...)`；繪圖顏色設定不會自動跨操作保留。  

## 常見問與答

**Q: 我可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Page for Java 設計上能無縫整合其他 Java 函式庫。

**Q: 我要如何取得 Aspose.Page for Java 的臨時授權？**  
A: 可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權，以供測試使用。

**Q: Aspose.Page 適用於商業專案嗎？**  
A: 當然！請前往 **[此處](https://purchase.aspose.com/buy)** 了解商業使用的授權方案。

**Q: 我可以在哪裡尋求協助或討論 Aspose.Page 相關問題？**  
A: 加入 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 社群，進行討論與取得協助。

**Q: 有哪些免費資源可以深入了解 Aspose.Page for Java？**  
A: 可使用 **[免費試用](https://releases.aspose.com/)**，並在文件中探索範例。

## 結論
Aspose.Page for Java 讓 **設定繪圖顏色**、**填充橢圓** 與 **繪製橢圓輪廓** 變得簡單直觀——無論您需要簡單的填充形狀或複雜的描邊圖形。依照上述步驟，您即可快速將專業等級的向量圖形加入任何可列印文件。欲深入探索，例如結合多個形狀、套用漸層或轉換為 PDF，請參考官方 **[文件](https://reference.aspose.com/page/java/)**。

---

**最後更新：** 2026-02-18  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}