---
date: 2025-12-07
description: 使用 Aspose.Page Java 為您的 Java PostScript 文件增添對角漸層效果。了解如何在 Java 中使用 LinearGradientPaint
  添加漸層效果，輕鬆打造鮮豔的顏色過渡。
linktitle: Add Diagonal Gradient in Java PostScript using Aspose.Page Java
second_title: Aspose.Page Java API
title: 在 Java PostScript 中使用 Aspose.Page Java 添加對角漸層
url: /zh-hant/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Page Java 中於 Java PostScript 加入對角漸層

## 介紹
如果你想為 PostScript 檔案增添平滑的對角色彩過渡，**Aspose.Page Java** 讓這件事變得相當簡單。在本教學中，我們將一步一步說明 **如何加入漸層**，使用 Java 2D 的 `LinearGradientPaint` 類別。完成後，你將得到一段可直接執行的程式碼，能產生帶有鮮豔對角漸層的 PostScript 文件。

## 快速回答
- **需要哪個函式庫？** Aspose.Page for Java。  
- **哪個類別負責建立漸層？** `LinearGradientPaint`。  
- **可以更改顏色嗎？** 可以 – 只要修改 `Color[]` 陣列。  
- **正式環境需要授權嗎？** 需要商業授權；亦提供免費試用版。  
- **實作大約需要多久？** 基本漸層約 10 分鐘即可完成。

## 什麼是 Aspose.Page Java？
Aspose.Page Java 是一套功能強大的 API，讓開發者能在不依賴任何外部軟體的情況下，產生、編輯與轉換 PostScript 與 PDF 檔案。它以乾淨的物件導向 Java 介面，完整呈現 PostScript 語言的圖形功能。

## 為什麼使用對角漸層？
對角漸層能為圖表、橫幅或任何需要現代感的圖形元素增添深度與視覺趣味。因為漸層是從一個角落延伸到對角的另一個角落，特別適合作為背景、按鈕外觀或裝飾形狀。

## 前置條件
在開始之前，請確保你已具備：

- Java Development Kit (JDK) 8 或以上。  
- 如 Eclipse、IntelliJ IDEA 或 VS Code 等 IDE。  
- **Aspose.Page for Java** 函式庫 – 從[官方下載頁面](https://releases.aspose.com/page/java/)取得最新版本。

## 匯入套件
首先，匯入 Java 2D 與 Aspose 所需的類別。這些匯入讓你能使用顏色定義、幾何形狀、漸層繪製以及 PostScript 文件 API。

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

## 步驟 1：為 PostScript 文件建立輸出串流
先定義要儲存檔案的資料夾，並開啟 `FileOutputStream`。此串流將接收產生的 PostScript 資料。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## 步驟 2：使用 A4 大小建立儲存選項
`PsSaveOptions` 讓你設定頁面尺寸、解析度與其他輸出參數。這裡使用預設的 A4 大小。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## 步驟 3：建立新的 PS 文件
以輸出串流與儲存選項建立 `PsDocument`。`false` 參數表示建構子不會自動開啟新頁面 – 我們稍後自行開啟。

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步驟 4：建立矩形
定義將要填入漸層的矩形。矩形位置 (200, 100) 與尺寸 (200 × 100) 讓漸層效果更易觀察。

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## 步驟 5：建立漸層變換
`AffineTransform` 讓我們旋轉、縮放與平移漸層，使其對角穿過矩形。以下數學計算斜邊長並相應調整縮放比例。

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## 步驟 6：建立對角線性漸層 Paint
這就是 **如何加入漸層** 的核心 – 我們建立一個 `LinearGradientPaint`，從矩形左上角延伸至右下角，並套用先前定義的變換。`MultipleGradientPaint.CycleMethod.NO_CYCLE` 確保漸層不會重複。

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## 步驟 7：設定 Paint 並填滿矩形
將漸層 Paint 套用到文件，並填滿矩形形狀。此步驟會在 PostScript 頁面上渲染出對角色彩過渡。

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## 步驟 8：關閉當前頁面並儲存文件
最後，關閉頁面、刷新串流，並儲存檔案。產生的 `DiagonalGradient_outPS.ps` 檔案可用任何 PostScript 檢視器開啟。

```java
// Close current page and save the document
document.closePage();
document.save();
```

依照上述八個步驟，你已成功使用 **Aspose.Page Java** 為 PostScript 文件加入對角漸層。歡迎自行嘗試不同顏色、角度與矩形大小，以打造自訂的視覺效果。

## 常見問題與技巧
- **漸層看起來平坦** – 再次確認旋轉角度；45° 旋轉才能產生真正的對角。  
- **顏色顯得淡薄** – 請確保使用 `MultipleGradientPaint.ColorSpaceType.SRGB` 以取得正確的色彩呈現。  
- **找不到檔案錯誤** – 檢查 `dataDir` 是否指向已存在的資料夾，且程式具有寫入權限。

## 常見問答

**Q: 我可以用這個函式庫在 Java 中執行其他圖形操作嗎？**  
A: 可以，Aspose.Page for Java 提供完整的繪圖基元、文字渲染與影像處理功能。

**Q: Aspose.Page Java 有免費試用版嗎？**  
A: 當然有。你可以從 [Aspose 免費試用頁面](https://releases.aspose.com/) 下載功能完整的試用版。

**Q: 哪裡可以找到 Aspose.Page Java 的文件？**  
A: 官方 API 參考文件位於 [此處](https://reference.aspose.com/page/java/)。

**Q: 我要如何購買 Aspose.Page Java 的授權？**  
A: 可直接在 [Aspose 購買入口](https://purchase.aspose.com/buy) 取得授權。

**Q: 需要協助或有其他問題嗎？**  
A: 前往社群驅動的 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 向 Aspose 工程師與其他開發者尋求協助。

---

**最後更新：** 2025-12-07  
**測試環境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}