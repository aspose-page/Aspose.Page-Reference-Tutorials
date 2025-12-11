---
date: 2025-12-08
description: 學習如何使用 Aspose.Page Java 為 Java PostScript 文件加入斜紋圖案。此一步一步的指南將向您示範如何高效地加入斜紋圖形。
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java：在 Java PostScript 中加入斜紋圖案
url: /zh-hant/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中加入交叉圖樣

## 介紹
如果您正在使用 **Aspose.Page Java**，且需要為 PostScript 輸出增添紋理圖形，交叉圖樣是一種快速且彈性的解決方案。在本教學中，我們將一步步說明 **如何在 PostScript 文件中加入交叉圖樣**，解釋其用途，並提供完整、可直接執行的程式碼範例。完成後，您只需幾行 Java 程式碼，即可建立視覺上吸引人的交叉填充形狀與文字。

## 快速答覆
- **需要哪個函式庫？** Aspose.Page for Java（即 “aspose page java” SDK）。  
- **要加入什麼視覺效果？** 交叉圖樣（例如斜線、交叉紋理）。  
- **執行範例是否需要授權？** 開發階段可使用免費試用版；正式上線需購買授權。  
- **程式碼行數大約？** 約 70 行，分為清晰的步驟。  
- **可否套用相同方式於 PDF？** 可以——Aspose.Page 支援多種輸出格式，包括 PDF。

## 前置條件
在開始之前，請確保您已具備：

- **Java 開發環境** – JDK 8 以上，並配合您慣用的 IDE。  
- **Aspose.Page for Java 函式庫** – 從官方網站下載最新 JAR [此處](https://releases.aspose.com/page/java/)。  
- **寫入權限** – 能夠將產生的 PostScript 檔案寫入指定資料夾。

## 匯入套件
首先，將所需的類別匯入專案。這些 import 提供繪圖基元、顏色處理以及 Aspose.Page API 的存取。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟 1：設定初始參數
建立輸出串流、設定頁面尺寸（A4），並定義在繪製每個交叉填充方格時會重複使用的版面變數。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## 步驟 2：儲存圖形狀態並平移
儲存圖形狀態可讓我們稍後回到原始座標系統，而 `translate` 則將原點移至方便的起始位置。

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## 步驟 3：為每種圖樣建立方格
定義一個可重複使用的矩形，代表每個交叉填充的格子。

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## 步驟 4：設定方格輪廓筆刷
使用 2 點的 `BasicStroke` 為每個方格提供清晰的外框。

```java
BasicStroke stroke = new BasicStroke(2);
```

## 步驟 5：遍歷交叉圖樣
遍歷 `HatchStyle` 列舉中的每個值，使用對應的紋理填充方格，然後繪製其外框。這是 **加入交叉圖樣** 功能的核心。

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## 步驟 6：還原圖形狀態
在完成格子網格的繪製後，回到原始座標系統。

```java
document.writeGraphicsRestore();
```

## 步驟 7：使用交叉圖樣填充文字
此範例示範如何以交叉紋理繪製文字，將字串 “ABC” 以斜交叉圖樣填滿。

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## 步驟 8：使用交叉圖樣描邊文字
接著以 70 % 的交叉樣式與較粗的筆觸為相同文字描邊。

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## 步驟 9：關閉並儲存文件
完成頁面設定、將檔案寫入磁碟，並釋放資源。

```java
document.closePage();
document.save();
```

依照上述步驟操作，即可產生一個展示完整交叉圖樣套用於形狀與文字的 PostScript 檔案——全部由 **aspose page java** 提供支援。

## 為什麼在 Aspose.Page Java 中使用交叉圖樣？
- **視覺區分度** – 即使印表機只能輸出單色，交叉填充仍能清楚呈現圖形差異。  
- **效能** – 紋理即時產生，避免使用大型影像檔。  
- **跨格式支援** – 同一段程式碼可輕鬆切換至 PDF、EPS 或 SVG，變更極少。

## 常見問題與技巧
- **檔案路徑錯誤** – 確認 `dataDir` 以正確的檔案分隔符 (`/` 或 `\`) 結尾。  
- **不支援的顏色** – 某些舊版 PostScript 直譯器可能無法處理特定色彩空間；建議使用基本 RGB 以確保相容性。  
- **授權警告** – 未使用有效授權執行範例時，輸出檔案會被加上浮水印。

## 結論
加入交叉圖樣可顯著提升技術圖紙、地圖或任何由 Java 產生的圖形之可讀性與美觀度。透過 **Aspose.Page Java**，您可使用簡潔的 API 抽象低階 PostScript 指令，專注於設計而非檔案格式的細節。

## 常見問答

**Q: 可以將 Aspose.Page Java 與其他 Java 框架一起使用嗎？**  
A: 可以，該函式庫與框架無關，支援 Spring、Jakarta EE、Android（功能有限）以及純 Java SE。

**Q: Aspose.Page Java 有提供試用版嗎？**  
A: 當然有。可在 [此處](https://releases.aspose.com/) 下載免費 30 天試用版。

**Q: 如何取得開發用的臨時授權？**  
A: 請於 [此處](https://purchase.aspose.com/temporary-license/) 申請臨時授權，可移除評估浮水印。

**Q: 哪裡可以找到更多教學與社群支援？**  
A: 前往官方論壇 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) 獲取更多範例與問答。

**Q: 是否有完整的類別與方法文件？**  
A: 有，完整的 API 參考文件可在 [此處](https://reference.aspose.com/page/java/) 取得。

---

**最後更新：** 2025-12-08  
**測試環境：** Aspose.Page for Java 24.12（撰寫時最新版本）  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
