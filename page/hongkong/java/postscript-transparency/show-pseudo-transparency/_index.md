---
date: 2025-12-17
description: 了解如何使用 Aspose.Page 在 Java 中創建偽透明效果。請依照我們的逐步指南，在 PostScript 檔案中加入鮮豔圖形。
linktitle: Show Pseudo-Transparency in Java PostScript
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page 在 Java 中創建偽透明
url: /zh-hant/java/postscript-transparency/show-pseudo-transparency/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript 偽透明與 Aspose.Page

## 介紹
在本完整教學中，您將使用 Aspose.Page for Java **建立偽透明的 Java 圖形**。我們將逐步說明——從環境設定到繪製兩個重疊的矩形，產生在 PostScript 檔案中呈現透明效果的假象。完成後，您將了解偽透明的用途、如何實作，以及如何調整參數以符合自己的設計需求。

## 快速解答
- **偽透明是什麼意思？** 它透過混合半透明漸層來模擬透明效果。
- **需要哪個函式庫？** Aspose.Page for Java。
- **執行範例是否需要授權？** 免費試用版可用於開發；商業授權則需於正式環境使用。
- **可以使用哪種 IDE？** 任何支援 Java 8+ 的 Java IDE（如 IntelliJ IDEA、Eclipse、VS Code）。
- **實作大約需要多久？** 基本範例約需 10‑15 分鐘。

## 什麼是 Java PostScript 中的偽透明？
偽透明是一種利用半透明漸層填充來產生透視物件視覺效果的技術。由於傳統 PostScript 不支援真實的 alpha 通道，Aspose.Page 透過疊加半透明形狀來模擬此效果。

## 為何使用 Aspose.Page 來實作偽透明？
- **跨平台** – 在任何作業系統上產生有效的 PostScript。
- **無外部相依性** – 純 Java API。
- **細緻控制** – 可程式化調整顏色、不透明度與漸層方向。
- **一致的輸出** – 在印表機與檢視器上皆呈現相同結果。

## 前置條件
在開始之前，請確保您已具備以下條件：
- 基本的 Java 知識。
- 熟悉 PostScript 概念。
- 已安裝 Aspose.Page for Java 函式庫。若尚未下載，請前往 **[此處](https://releases.aspose.com/page/java/)** 取得。
- 已備妥 Java IDE 或建置工具（Maven/Gradle）。

## 匯入套件
首先匯入必要的類別，以便操作顏色、漸層以及 PostScript 文件物件。

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟 1：建立 PS 文件
首先，我們建立輸出串流並初始化新的 `PsDocument`。此步驟會設定繪圖畫布，以便繪製形狀。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "ShowPseudoTransparency_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 2：使用不透明漸層填充定義矩形
我們使用完全不透明的漸層繪製第一個矩形，作為偽透明覆蓋層的背景。

```java
float offsetX = 50;
float offsetY = 100;
float width = 200;
float height = 100;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create opaque gradient fill
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0), new Color(40, 128, 70)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## 步驟 3：使用半透明漸層填充定義矩形
接著，我們放置第二個矩形，使用帶有 alpha 值的漸層。當它與第一個形狀重疊時，即產生 **偽透明** 效果。

```java
offsetX = 350;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create translucent gradient fill
paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## 步驟 4：關閉頁面並儲存文件
最後，我們關閉目前的頁面，並將 PostScript 檔案寫入磁碟。

```java
document.closePage();
document.save();
```

## 常見問題與除錯
- **FileNotFoundException** – 請確認 `dataDir` 指向已存在的資料夾，且應用程式具備寫入權限。
- **顏色不正確** – 請確保使用 `Color(int r, int g, int b, int a)` 建構子來建立半透明顏色；第四個參數為 alpha（0‑255）。
- **漸層未顯示** – 檢查 `AffineTransform` 參數是否正確對應至矩形尺寸。

## 常見問答
### 我可以在商業專案中使用 Aspose.Page for Java 嗎？
可以，Aspose.Page for Java 可用於商業用途。您可於 **[此處](https://purchase.aspose.com/buy)** 購買授權。

### 是否提供免費試用？
可以，您可在 **[此處](https://releases.aspose.com/)** 取得免費試用版。

### 我可以在哪裡找到更多文件？
詳細文件可於 **[此處](https://reference.aspose.com/page/java/)** 取得。

### 如何取得測試用的臨時授權？
您可在 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

### 需要協助或想討論 Aspose.Page？
請前往 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)**。

---

**最後更新：** 2025-12-17  
**測試環境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}