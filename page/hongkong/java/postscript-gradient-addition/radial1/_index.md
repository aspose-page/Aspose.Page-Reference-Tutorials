---
date: 2026-02-13
description: 學習如何使用 Aspose.Page for Java 建立具有徑向顏色停止點的 PostScript 漸層。本一步一步的指南將向您展示如何在文件中加入顏色停止點漸層。
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: 建立 PostScript 漸層 – Java 中的徑向漸層
url: /zh-hant/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用 Aspose.Page 添加徑向漸層

## 介紹
如果您曾需要 **建立 PostScript 漸層**，且希望擁有平滑、吸睛的顏色過渡，那麼學習如何加入徑向漸層就是最佳起點。在本教學中，我們將逐步說明如何使用 **Aspose.Page for Java** 函式庫產生包含精美徑向漸層的 PostScript 檔案。完成後，您將了解相關 API、看到完整可執行的範例，並知道如何調整顏色、位置與半徑，以符合任何設計需求。

## 快速回答
- **哪個函式庫可以在 PostScript 中建立徑向漸層？** Aspose.Page for Java。  
- **實作大約需要多久？** 基本範例約 10‑15 分鐘即可完成。  
- **執行程式碼是否需要授權？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援哪個 Java 版本？** Java 8 或以上。  
- **可以變更漸層形狀嗎？** 可以——只要在 `RadialGradientPaint` 建構子中調整半徑與中心點即可。

## 如何使用徑向填充建立 PostScript 漸層
以下提供簡潔的逐步說明，完整展示如何 **建立 PostScript 漸層** 內容，並使用徑向填充。每一步都包含簡短說明，後接原始程式碼區塊（保持不變）。

## 什麼是徑向漸層？
徑向漸層會從中心點向外輻射顏色，逐漸向邊緣混合。與線性漸層不同，顏色過渡呈圓形（或橢圓形）模式，非常適合用於高光、聚光燈或柔和的背景填充。

## 為什麼選擇 Aspose.Page 來處理徑向漸層？
- **完整控制 PostScript 輸出**——不必手動編寫低階 PS 指令。  
- **跨平台**——只要能執行 Java，即可在任何作業系統上使用。  
- **豐富的顏色管理**——支援多個顏色停點、不同色彩空間與循環方式。  
- **即插即用**——可與 Aspose.Page 的文字、影像與向量圖形功能結合使用。

## 前置條件
在開始撰寫程式碼之前，請先確保以下項目已備妥：

- **Java Development Kit (JDK) 8+** —— 可使用 `java -version` 檢查。  
- **Aspose.Page for Java** —— 從官方 [Aspose.Page 下載頁面](https://releases.aspose.com/page/java/) 取得最新 JAR。  
- **您慣用的 IDE** —— 如 Eclipse、IntelliJ IDEA 或已安裝 Java 擴充功能的 VS Code。  
- **可寫入的資料夾** —— 用來存放產生的 `.ps` 檔案。

## 匯入套件
首先匯入所需的類別。`java.awt` 套件提供漸層繪圖物件，而 `com.aspose.eps` 則負責 PostScript 文件的處理。

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟說明

### 步驟 1：建立矩形並開啟 PS 文件
我們先建立輸出串流、設定頁面大小（預設 A4），再定義一個用來放置漸層的矩形。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **專業提示：** 調整矩形座標 (`200, 100, 200, 200`) 即可將漸層放置在頁面的任意位置。

### 步驟 2：定義顏色與比例
徑向漸層由 *顏色停點*（colors）與 *比例*（fractions）組成。此處我們建立一個包含六種顏色及其對應比例的陣列。

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **為什麼重要：** 透過調整 `fractions`，您可以控制顏色過渡的快慢，從而產生細膩或強烈的視覺效果。

### 添加顏色停點漸層至徑向填充
當需要 **添加顏色停點漸層** 時，`colors` 與 `fractions` 陣列是關鍵。您可以自由重新排序、增減項目，以符合設計需求。

### 步驟 3：建立 RadialGradientPaint
現在建立 `RadialGradientPaint` 物件。建構子接受中心點、半徑、焦點、比例、顏色、循環方式、色彩空間，以及可選的變換矩陣。

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **注意：** 若不需要額外的縮放或旋轉，`transform` 可設為 `null`。若想嘗試斜切漸層，可自行實驗 `AffineTransform`。

### 步驟 4：設定 Paint 並填滿矩形
取得 Paint 後，指示 `PsDocument` 使用它，然後填滿先前定義的矩形。

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

此時，PostScript 頁面已包含一個以徑向漸層平滑填充的矩形。

### 步驟 5：關閉並儲存文件
最後，關閉當前頁面並將檔案寫入磁碟。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

在任何支援 PostScript 的檢視器（例如 Ghostscript）中開啟 `RadialGradient1_outPS.ps`，即可看到與程式碼完全相符的漸層效果。

## 常見問題與解決方案
| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 漸層顯示為單一顏色 | `fractions` 陣列未以 `0.0f` 開頭或未以 `1.0f` 結尾 | 確認第一個比例為 `0.0f`，最後一個比例為 `1.0f`。 |
| 顏色看起來黯淡 | 使用了錯誤的 `ColorSpaceType` | 改用 `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` 以獲得更鮮豔的輸出。 |
| 未產生輸出檔案 | `FileOutputStream` 路徑無效或無寫入權限 | 檢查 `dataDir` 是否存在，且程式具有寫入權限。 |

## 常見問答

**Q: 可以在商業專案中使用 Aspose.Page for Java 嗎？**  
A: 可以。正式上線需購買商業授權。您可於 [Aspose 授權頁面](https://purchase.aspose.com/buy) 購買。

**Q: 官方 API 參考文件在哪裡？**  
A: 完整文件可在 [此處](https://reference.aspose.com/page/java/) 取得。

**Q: 有免費試用版可以測試嗎？**  
A: 當然有。請從 [Aspose.Page 釋出頁面](https://releases.aspose.com/) 下載試用版。

**Q: 如何取得臨時授權以進行評估？**  
A: 可於 [此處](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

**Q: 哪裡可以取得社群支援？**  
A: 歡迎加入 Aspose.Page 社群論壇： [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39)。

## 結論
現在您已掌握 **如何在 Java PostScript 文件中加入徑向漸層** 的技巧。只要調整矩形尺寸、顏色停點與漸層半徑，即可創造無限的視覺效果，從柔和的背景填充到醒目的聚光燈圖形皆可輕鬆實現。歡迎嘗試不同的 `AffineTransform` 參數，以旋轉或斜切漸層，並結合文字與影像，產出更豐富的 PDF 或 EPS 輸出。

---

**最後更新：** 2026-02-13  
**測試環境：** Aspose.Page for Java 最新版（撰寫時）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}