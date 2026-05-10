---
date: 2026-02-13
description: 使用 Aspose.Page Java 為您的 Java PostScript 文件增添對角漸層效果。學習如何在 Java 中使用 LinearGradientPaint
  添加漸層效果，輕鬆打造生動的色彩過渡。
linktitle: 'How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page
  Java'
second_title: Aspose.Page Java API
title: 如何在 Java PostScript 中使用 Aspose.Page Java 添加對角線漸層
url: /zh-hant/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中使用 Aspose.Page Java 添加對角漸層

## Introduction
如果您想為 PostScript 檔案加入平滑的對角色彩過渡，**Aspose.Page Java** 讓這變得相當簡單。在本教學中，我們將一步一步說明**如何加入漸層**效果，使用 Java 2D 的 `LinearGradientPaint` 類別。完成後，您將擁有一段可直接執行的程式碼，能產生帶有鮮豔對角漸層的 PostScript 文件。

## How to Add Gradient in Java PostScript
在 Java PostScript 中加入漸層看似只是一個圖形處理的工作，但使用 Aspose.Page，您可以在純 Java 環境下同時掌控底層的 PostScript 指令。本節說明此方法為何可行，以及相較於手寫原始 PostScript 可獲得的優勢。

## Quick Answers
- **需要的函式庫是什麼？** Aspose.Page for Java.  
- **哪個類別用來建立漸層？** `LinearGradientPaint`.  
- **我可以更改顏色嗎？** 可以 – 修改 `Color[]` 陣列。  
- **正式環境需要授權嗎？** 需要商業授權；亦提供免費試用版。  
- **實作大約需要多久？** 基本漸層約 10 分鐘即可完成。

## What is Aspose.Page Java?
Aspose.Page Java 是一套功能強大的 API，讓開發者能在不需任何外部軟體的情況下產生、編輯與轉換 PostScript 與 PDF 檔案。它透過乾淨的物件導向 Java 介面，完整呈現 PostScript 語言的圖形功能。

## Why use a diagonal gradient?
對角漸層能為圖表、橫幅或任何需要現代感的圖形元素增添深度與視覺趣味。由於漸層從一個角落延伸至對角角落，特別適合作為背景、按鈕外觀及裝飾形狀。

## Prerequisites
Before you start, make sure you have:

- Java Development Kit (JDK) 8 或更新版本。  
- Eclipse、IntelliJ IDEA 或 VS Code 等開發環境。  
- **Aspose.Page for Java** 函式庫 – 從[官方下載頁面](https://releases.aspose.com/page/java/)取得最新版本。

## Import Packages
首先，匯入您將需要的 Java 2D 與 Aspose 類別。這些匯入讓您能使用顏色定義、幾何形狀、漸層繪製以及 PostScript 文件 API。

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

## Step 1: Create Output Stream for PostScript Document
我們先定義檔案要儲存的資料夾，並開啟 `FileOutputStream`。此串流將接收產生的 PostScript 資料。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Step 2: Create Save Options with A4 Size
`PsSaveOptions` 讓您設定頁面尺寸、解析度與其他輸出選項。此處使用預設的 A4 大小。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Step 3: Create New PS Document
使用輸出串流與儲存選項建立 `PsDocument`。`false` 參數表示建構子不會自動開啟新頁面 – 我們稍後自行開啟。

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Create a Rectangle
定義將接受漸層填色的矩形。矩形的位置 (200, 100) 與尺寸 (200 × 100) 讓漸層效果清晰可見。

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 5: Create Gradient Transform
`AffineTransform` 讓我們旋轉、縮放與平移漸層，使其沿對角線穿過矩形。以下程式碼計算斜邊長並相應調整縮放比例。

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

## Step 6: Create Diagonal Linear Gradient Paint
以下為**如何加入漸層**的核心 – 我們建立一個 `LinearGradientPaint`，從矩形左上角延伸至右下角，並套用先前定義的變換。`MultipleGradientPaint.CycleMethod.NO_CYCLE` 確保漸層不會重複。

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Step 7: Set Paint and Fill the Rectangle
將漸層繪圖設定套用至文件，並填滿矩形形狀。此步驟會在 PostScript 頁面上繪製對角色彩過渡。

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Step 8: Close the Current Page and Save the Document
最後，關閉頁面、刷新串流，並儲存檔案。產生的 `DiagonalGradient_outPS.ps` 檔案可用任何 PostScript 檢視器開啟。

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Common Issues & Tips
- **漸層看起來平坦** – 再次確認旋轉角度；45° 旋轉才能產生真正的對角線。  
- **顏色顯得淡薄** – 確認使用 `MultipleGradientPaint.ColorSpaceType.SRGB` 以獲得正確的色彩呈現。  
- **找不到檔案錯誤** – 確認 `dataDir` 指向已存在的資料夾，且應用程式具有寫入權限。

## Frequently Asked Questions

**問：我可以在 Java 中使用此函式庫執行其他圖形操作嗎？**  
答：可以，Aspose.Page for Java 提供完整的繪圖基元、文字渲染與影像處理功能。

**問：Aspose.Page Java 有提供免費試用嗎？**  
答：當然有。您可從 [Aspose 免費試用頁面](https://releases.aspose.com/) 下載完整功能的試用版。

**問：在哪裡可以找到 Aspose.Page Java 的文件？**  
答：官方 API 參考文件可在[此處](https://reference.aspose.com/page/java/)取得。

**問：如何購買 Aspose.Page Java 的授權？**  
答：授權可直接於[ Aspose 購買入口](https://purchase.aspose.com/buy)取得。

**問：需要協助或有其他問題？**  
答：請前往社群營運的 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 尋求 Aspose 工程師與其他開發者的協助。

---

**最後更新：** 2026-02-13  
**測試環境：** Aspose.Page for Java 24.12 (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}