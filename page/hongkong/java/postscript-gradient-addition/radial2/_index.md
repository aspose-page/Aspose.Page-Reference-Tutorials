---
date: 2025-12-08
description: 學習如何使用 Aspose.Page 在 Java PostScript 中建立徑向漸層範例。一步一步的指南，附完整程式碼與故障排除。
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 徑向漸層範例：Java PostScript 與 Aspose.Page
url: /zh-hant/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 徑向漸層範例：使用 Aspose.Page 的 Java PostScript

## 介紹
在本教學中，您將使用 Aspose.Page for Java 建立一個 **徑向漸層範例** 的 PostScript 文件。我們會一步步說明——從專案設定到渲染填滿平滑徑向漸層的圓形——讓您能立即在 Java 應用程式中加入吸睛的圖形。

## 快速回答
- **本教學會產生什麼？** 一個包含徑向漸層圓形的 PostScript 檔 (`.ps`)。  
- **需要哪個函式庫？** Aspose.Page for Java（最新版本）。  
- **實作需要多久？** 約 10‑15 分鐘即可完成可執行範例。  
- **需要授權嗎？** 正式使用時需有臨時或完整授權；開發階段可使用免費試用版。  
- **可以把程式碼重用於 PDF 或 SVG 嗎？** 可以——Aspose.Page 支援多種輸出格式，只需少量調整。

## 什麼是徑向漸層？
徑向漸層從中心點向外過渡顏色，形成平滑的圓形混合。它非常適合用於高光、按鈕背景或任何需要自然「發光」效果的視覺元素。

## 為什麼選擇 Aspose.Page 來製作徑向漸層？
- **裝置無關的渲染** ─ 在 PostScript、PDF、SVG 等格式上表現一致。  
- **完整的 Java 整合** ─ 無需原生程式碼，僅使用純 Java API。  
- **高品質輸出** ─ 支援抗鋸齒與色彩空間控制。

## 前置條件
在開始之前，請確保您已具備：

- 基本的 Java 程式開發經驗。  
- 已在電腦上安裝 JDK 8 或更新版本。  
- Aspose.Page for Java 函式庫（可從 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) 下載）。

## 匯入套件
首先，匯入我們將會使用的類別。這些類別包括標準的 AWT 圖形類型以及 Aspose.Page API。

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
定義產生的 PostScript 檔案要儲存的資料夾。請將佔位符替換為您系統中的實際路徑。

```java
String dataDir = "Your Document Directory";
```

## 步驟 2：建立輸出串流
開啟指向目標 `.ps` 檔案的 `FileOutputStream`。此串流負責寫入 Aspose.Page 產生的二進位資料。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## 步驟 3：建立儲存選項
實例化 `PsSaveOptions`。您可以自訂頁面大小、壓縮方式等，但本範例使用預設值即可。

```java
PsSaveOptions options = new PsSaveOptions();
```

## 步驟 4：建立 PS 文件
建立 `PsDocument` 物件，傳入輸出串流與儲存選項。`false` 參數表示 Aspose.Page 不會自動開啟頁面（我們會手動處理）。

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 5：建立圓形
使用 `Ellipse2D.Float` 繪製圓形。參數為 `(x, y, width, height)`。將 width = height 即可得到完美圓形。

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## 步驟 6：定義漸層顏色
準備兩個陣列：一個存放漸層中使用的顏色，另一個存放對應的比例位置（0 = 中心，1 = 邊緣）。

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## 步驟 7：建立 AffineTransform
`AffineTransform` 用來縮放與平移漸層，使其符合圓形。矩陣 `(scaleX, 0, 0, scaleY, translateX, translateY)` 完成此工作。

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## 步驟 8：建立徑向漸層 Paint
現在建立 `RadialGradientPaint` 物件。它接受中心點、半徑、焦點、顏色比例、顏色陣列、循環方式、色彩空間以及剛才定義的變換。

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
將漸層 Paint 套用到文件，並填滿先前定義的圓形。這就是我們 **徑向漸層範例** 的核心。

```java
document.setPaint(paint);
document.fill(circle);
```

## 步驟 10：關閉頁面並儲存文件
結束頁面、將內容寫入磁碟，最後關閉串流。您的 PostScript 檔案即可使用任何 PS 檢視器開啟。

```java
document.closePage();
document.save();
```

恭喜！您已成功使用 Aspose.Page 在 Java PostScript 中建立徑向漸層範例。

## 常見問題與解決方案
| 問題 | 解決方案 |
|------|----------|
| **FileNotFoundException** 在開啟輸出串流時發生 | 確認 `dataDir` 指向已存在的資料夾，且您具有寫入權限。 |
| 漸層顯示平坦或缺失 | 確認 `fractions` 陣列長度與 `colors` 陣列相同，且 `AffineTransform` 的縮放正確。 |
| 顏色顛倒 | 交換 `colors` 陣列中的順序，或調整 `focus` 點座標。 |

## 常見問答

**Q: 在哪裡可以找到 Aspose.Page for Java 的文件？**  
A: 完整的 API 參考位於 [here](https://reference.aspose.com/page/java/)。

**Q: 我要如何下載 Aspose.Page for Java？**  
A: 從 [releases page](https://releases.aspose.com/page/java/) 取得最新的 JAR。

**Q: 有免費試用版嗎？**  
A: 有——可在 [here](https://releases.aspose.com/) 下載試用版。

**Q: 可以取得測試用的臨時授權嗎？**  
A: 當然，請向 [temporary license page](https://purchase.aspose.com/temporary-license/) 申請。

**Q: 哪裡可以得到社群支援？**  
A: 加入 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 參與討論。

## 結論
本指南示範了如何使用 Aspose.Page for Java 為 PostScript 文件建立完整的 **徑向漸層範例**。依循上述步驟，您現在擁有一套可重複使用的模式，能夠製作高階漸層，並可輕鬆移植至 PDF、SVG 或其他支援格式。請嘗試不同的顏色、半徑與形狀，為您的 Java 圖形專案增添更多色彩。

---

**最後更新：** 2025-12-08  
**測試環境：** Aspose.Page for Java 24.11（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}