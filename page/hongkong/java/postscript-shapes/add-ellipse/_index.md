---
date: 2025-12-11
description: 學習如何使用 Aspose.Page 在 Java 中建立 PostScript 橢圓。此一步一步的指南會向您展示如何在 Java 中為橢圓填充顏色及繪製橢圓。
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page 建立 PostScript 橢圓
url: /zh-hant/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 建立 PostScript ellipse

## 簡介
以程式方式建立 **PostScript ellipse** 可讓您對報告、發票或任何可列印文件中的向量圖形進行精細控制。在本教學中，您將學習如何使用 Aspose.Page for Java 函式庫 **建立 PostScript ellipse** 形狀、以顏色填充橢圓以及繪製橢圓輪廓。完成後，您即可直接將自訂圖形嵌入 PostScript 輸出中。

## 快速答覆
- **哪個函式庫最適合在 Java 中繪製 PostScript 圖形？** Aspose.Page for Java。  
- **我可以用純色填充橢圓嗎？** 可以 – 在 `fill` 之前使用 `document.setPaint(Color.YOUR_COLOR)`。  
- **如何只繪製橢圓的輪廓？** 設定 paint 與 stroke，然後呼叫 `document.draw(...)`。  
- **正式使用是否需要授權？** 需要商業授權；測試可使用臨時授權。  
- **支援哪個 Java 版本？** 任何 Java 8 以上的執行環境皆可與目前的 Aspose.Page 版本相容。

## 什麼是 PostScript ellipse？
PostScript ellipse 是以邊界矩形定義的向量形狀。與點陣圖不同，它可在不失真的情況下放大縮小，因而非常適合高解析度列印與 PDF 轉換。

## 為何使用 Aspose.Page 來建立 PostScript ellipse？
- **完整控制** 繪圖基元（線條、曲線、橢圓）。  
- **跨平台** – 可在 Windows、Linux 與 macOS 上執行。  
- **無外部相依性** – 純 Java API，無原生程式碼。  
- **易於整合** 至現有的 Java 應用程式與建置工具。

## 先決條件
在開始之前，請確保您已具備：

1. 可正常運作的 Java 開發環境（JDK 8 或更新版本）。  
2. 已將 Aspose.Page for Java 函式庫加入專案。您可於 **[此處](https://releases.aspose.com/page/java/)** 下載。

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

## 逐步指南

### 步驟 1：設定 PostScript 文件
建立輸出串流、設定頁面大小，並實例化 `PsDocument`。

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

### 步驟 2：以顏色填充橢圓
將 paint 設為所需的填充顏色，然後使用 `Ellipse2D` 實例呼叫 `fill`。

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 步驟 3：以筆畫描繪橢圓輪廓
將 paint 切換為筆畫顏色，定義 `BasicStroke` 以設定線寬，然後繪製橢圓輪廓。

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 步驟 4：關閉並儲存文件
完成頁面並將 PostScript 檔寫入磁碟。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

現在您已擁有一個包含兩個橢圓的 PostScript 檔案——一個以橙色填充，另一個以紅色描邊。歡迎自行嘗試不同的座標、尺寸與顏色，以符合您的設計需求。

## 常見問題與故障排除
- **檔案路徑不正確** – 確認 `dataDir` 以符合作業系統的分隔符 (`/` 或 `\\`) 結尾。  
- **缺少授權** – 若未持有有效授權，函式庫將以評估模式執行，可能會加上浮水印。  
- **顏色未套用** – 記得在每次 `fill` 或 `draw` 呼叫 *之前* 設定 `document.setPaint(...)`；paint 設定不會自動在不同操作間保留。

## 常見問答

**Q: 我可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Page for Java 設計上能無縫整合其他 Java 函式庫。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權以供測試使用。

**Q: Aspose.Page 適合商業專案嗎？**  
A: 當然！請前往 **[此處](https://purchase.aspose.com/buy)** 了解商業使用的授權方案。

**Q: 我可以在哪裡尋求協助或討論 Aspose.Page 相關問題？**  
A: 加入 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 社群，進行討論與取得協助。

**Q: 有哪些免費資源可深入了解 Aspose.Page for Java？**  
A: 可使用 **[免費試用](https://releases.aspose.com/)**，並在文件中探索範例。

## 結論
Aspose.Page for Java 讓 **建立 PostScript ellipse** 圖形變得相當簡單，無論您需要簡單的填充形狀或複雜的筆畫輪廓。依照上述步驟，即可快速為任何可列印文件加入專業等級的向量圖形。若想更深入探索，例如結合多個形狀、套用漸層或轉換為 PDF，請參考官方 **[文件](https://reference.aspose.com/page/java/)**。

---

**最後更新：** 2025-12-11  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
