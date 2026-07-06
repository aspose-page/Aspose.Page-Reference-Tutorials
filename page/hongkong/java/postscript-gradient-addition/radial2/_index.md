---
date: 2026-02-13
description: 學習如何在 Java PostScript 中使用 Aspose.Page 以漸層填充形狀及繪製漸層圓形。一步一步的指南，附上程式碼與技巧。
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 使用漸層填充形狀：Java PostScript 徑向範例
url: /zh-hant/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用漸層填充形狀：Java PostScript 徑向範例

## 介紹
在本教學中，您將學習如何透過使用 Aspose.Page for Java 為 PostScript 文件建立徑向漸層範例，來 **填充形狀以漸層**。我們將逐步說明每個步驟——從設定專案到繪製填滿平滑徑向漸層的圓形——讓您能即時為 Java 應用程式加入吸睛的圖形。

## 快速解答
- **本教學會產生什麼？** 一個包含徑向漸層填充圓形的 PostScript 檔案（`.ps`）。  
- **需要哪個函式庫？** Aspose.Page for Java（最新版本）。  
- **實作需要多長時間？** 大約 10‑15 分鐘即可完成可運作的範例。  
- **需要授權嗎？** 生產環境需要臨時或正式授權；開發時可使用免費試用版。  
- **程式碼能否重用於 PDF 或 SVG？** 可以——Aspose.Page 支援多種輸出格式，只需少量修改。

## 如何在 PostScript 中使用漸層填充形狀
在深入程式碼之前，我們先說明為何「使用漸層填充形狀」很重要。使用漸層能讓圖形呈現專業且具立體感，而不必依賴點陣圖。透過 Aspose.Page，您可以將相同的漸層邏輯套用於任何向量形狀——圓形、矩形或自訂路徑——並支援所有支援的輸出格式（PostScript、PDF、SVG）。

## 什麼是徑向漸層？
徑向漸層從中心點向外過渡顏色，形成平滑的圓形混合。它非常適合用於高光、按鈕背景或任何需要自然「發光」效果的視覺元素。

## 為何使用 Aspose.Page 進行徑向漸層？
- **裝置無關的渲染** – 在 PostScript、PDF、SVG 等平台上表現一致。  
- **完整的 Java 整合** – 無需原生程式碼，只使用純 Java API。  
- **高品質輸出** – 支援抗鋸齒與色彩空間控制。

## 前置條件
在開始之前，請確保您已具備以下條件：

- 基本的 Java 程式設計知識。  
- 已在電腦上安裝 JDK 8 或更新版本。  
- Aspose.Page for Java 函式庫（可從 [Aspose.Page Java 文件](https://reference.aspose.com/page/java/) 下載）。

## 匯入套件
首先，匯入我們需要的類別。這些包括標準的 AWT 圖形類型以及 Aspose.Page API。

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟 1：設定文件目錄
定義生成的 PostScript 檔案要儲存的資料夾。請將佔位符替換為您系統中的實際路徑。

```java
String dataDir = "Your Document Directory";
```

## 步驟 2：建立輸出串流
開啟指向目標 `.ps` 檔案的 `FileOutputStream`。此串流負責輸出 Aspose.Page 產生的二進位資料。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## 步驟 3：建立儲存選項
實例化 `PsSaveOptions`。您可以自訂頁面大小、壓縮等設定，但此範例使用預設值即可。

```java
PsSaveOptions options = new PsSaveOptions();
```

## 步驟 4：建立 PS 文件
建立 `PsDocument` 物件，傳入輸出串流與儲存選項。`false` 旗標表示 Aspose.Page 不會自動開啟頁面（我們會手動開啟）。

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 5：建立圓形
我們將使用 `Ellipse2D.Float` 繪製圓形。參數為 `(x, y, width, height)`。將 width = height 即可產生完美的圓形。

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## 如何以漸層繪製圓形
現在已有形狀，接下來的步驟是 **以漸層繪製圓形**。將 `RadialGradientPaint` 套用到圓形後，填充操作會自動使用我們定義的漸層。

## 步驟 6：定義漸層顏色
準備兩個陣列：一個存放漸層中使用的顏色，另一個存放對應的比例位置（0 = 中心，1 = 邊緣）。

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## 步驟 7：建立 AffineTransform
`AffineTransform` 會縮放並平移漸層，使其適配我們的圓形。矩陣 `(scaleX, 0, 0, scaleY, translateX, translateY)` 完成此工作。

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## 步驟 8：建立徑向漸層 Paint
現在建立 `RadialGradientPaint` 物件。它需要中心點、半徑、焦點、顏色比例、顏色陣列、循環方式、色彩空間，以及剛才定義的變換。

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## 步驟 9：設定 Paint 並填充圓形
將漸層 Paint 套用至文件，並填充先前定義的圓形。這是我們 **徑向漸層範例** 的核心，示範了如何 **使用漸層填充形狀**。

```java
document.setPaint(paint);
document.fill(circle);
```

## 步驟 10：關閉頁面並儲存文件
完成頁面，將內容寫入磁碟，並關閉串流。您的 PostScript 檔案現在可使用任何 PS 檢視器開啟。

```java
document.closePage();
document.save();
```

恭喜！您已成功使用 Aspose.Page 在 Java PostScript 中建立徑向漸層範例。現在您擁有一個可重複使用的 **使用漸層填充形狀** 模式，能夠套用於其他形狀與輸出格式。

## 常見問題與解決方案
| 問題 | 解決方案 |
|---------|----------|
| **FileNotFoundException** 發生於開啟輸出串流時 | 請確認 `dataDir` 指向已存在的資料夾且您具有寫入權限。 |
| 漸層看起來平坦或缺失 | 確保 `fractions` 陣列與 `colors` 陣列長度相同，且 `AffineTransform` 正確縮放。 |
| 顏色顯示相反 | 交換 `colors` 陣列中的顏色順序，或調整 `focus` 點座標。 |

## 常見問答

**問：在哪裡可以找到 Aspose.Page for Java 的文件？**  
答：完整的 API 參考可在[此處](https://reference.aspose.com/page/java/)取得。

**問：如何下載 Aspose.Page for Java？**  
答：從[發行頁面](https://releases.aspose.com/page/java/)取得最新的 JAR。

**問：是否提供免費試用？**  
答：有——可在[此處](https://releases.aspose.com/)下載試用版。

**問：我可以取得測試用的臨時授權嗎？**  
答：當然，請從[臨時授權頁面](https://purchase.aspose.com/temporary-license/)申請。

**問：在哪裡可以獲得社群支援？**  
答：加入[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)的討論。

## 結論
在本指南中，我們使用 Aspose.Page for Java 為 PostScript 文件建立了完整的 **徑向漸層範例**。依照步驟操作後，您已擁有可重複使用的 **使用漸層填充形狀** 模式，能夠套用至 PDF、SVG 或 Aspose.Page 支援的任何其他格式。請嘗試不同的顏色、半徑與形狀，以豐富您的 Java 圖形專案。

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}