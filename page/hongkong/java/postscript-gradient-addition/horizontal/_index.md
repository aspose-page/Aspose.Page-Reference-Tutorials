---
title: 在 Java PostScript 中加入水平漸變
linktitle: 在 Java PostScript 中加入水平漸變
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page for Java 在 Java PostScript 中新增水平漸層。輕鬆創建視覺上令人驚嘆的文檔。
weight: 11
url: /zh-hant/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中加入水平漸變

## 介紹
歡迎來到這個關於使用 Aspose.Page for Java 在 Java PostScript 中加入水平漸層的綜合教學。 Aspose.Page 是一個功能強大的 Java 程式庫，允許開發人員使用 PostScript 和其他文件格式。在本教學中，我們將透過逐步範例引導您完成建立具有水平漸層的 PostScript 文件的過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- 您的電腦上安裝了 Java 開發工具包 (JDK)。
- Java 函式庫的 Aspose.Page。您可以從[Aspose.Page Java 文檔](https://reference.aspose.com/page/java/).
## 導入包
首先在 Java 專案中導入必要的包。這些套件對於使用 Aspose.Page 至關重要。
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## 第 1 步：建立一個矩形
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//為 PostScript 文件建立輸出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
//建立 A4 尺寸的儲存選項
PsSaveOptions options = new PsSaveOptions();
//開啟頁面建立新的 PS 文檔
PsDocument document = new PsDocument(outPsStream, options, false);
//建立一個矩形
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## 步驟2：創作水平線性漸層繪畫
```java
//建立水平線性漸層塗料。變換中的縮放組件必須等於矩形的寬度和高度。
//平移分量是矩形的偏移量。
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
//訂漆
document.setPaint(paint);
```
## 第三步：填滿矩形
```java
//填滿矩形
document.fill(rectangle);
```
## 第四步：用漸層填滿文本
```java
//用漸層填滿文本
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## 第 5 步：用漸層描邊文本
```java
//使用漸層描邊文本
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## 結論
恭喜！您已使用 Aspose.Page for Java 在 Java PostScript 中成功新增水平漸層。本教學課程為您提供了詳細的逐步指南，以幫助您建立具有視覺吸引力的 PostScript 文件。
## 經常問的問題
### 我可以在商業專案中使用 Aspose.Page for Java 嗎？
是的，Aspose.Page for Java可以用於商業專案。有關許可詳細信息，請訪問[Aspose.購買](https://purchase.aspose.com/buy).
### 有免費試用嗎？
是的，您可以免費試用 Aspose.Page for Java[這裡](https://releases.aspose.com/).
### 在哪裡可以找到其他文件和支援？
參觀[Aspose.Page Java 文檔](https://reference.aspose.com/page/java/)以獲得綜合資源。如需社區支持，請查看[Aspose.Page 論壇](https://forum.aspose.com/c/page/39).
### 我怎麼才能獲得臨時許可證？
您可以從以下地址取得臨時許可證[Aspose.購買](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java 有哪些系統需求？
請參閱[文件](https://reference.aspose.com/page/java/)了解詳細的系統需求。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
