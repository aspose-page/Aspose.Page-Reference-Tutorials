---
title: 在 Java PostScript 中加入填滿圖案
linktitle: 在 Java PostScript 中加入填滿圖案
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page 將迷人的填滿圖案新增至 Java PostScript 文件。輕鬆提升您的視覺內容。
weight: 10
url: /zh-hant/java/postscript-hatch-patterns/add-hatch-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中加入填滿圖案

## 介紹
在 Java 程式設計領域，增強視覺元素是開發人員的常見要求。一個有趣的視覺增強功能是為 PostScript 文件添加填滿圖案。本教學將引導您完成使用 Aspose.Page for Java 添加填滿圖案的過程。
## 先決條件
在深入學習本教學之前，請確保您已進行以下設定：
- Java 開發環境：確保您已準備好 Java 開發環境。
-  Aspose.Page for Java 函式庫：下載並安裝 Aspose.Page for Java 函式庫。就可以找到需要的文件了[這裡](https://releases.aspose.com/page/java/).
## 導入包
首先，將所需的套件匯入到您的 Java 專案中。使用以下程式碼片段：
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
## 第1步：設定初始參數
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//為 PostScript 文件建立輸出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
//建立 A4 尺寸的儲存選項
PsSaveOptions options = new PsSaveOptions();
//開啟頁面建立新的 PS 文檔
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## 第 2 步：儲存圖形狀態並轉換
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## 第 3 步：為每個圖案建立正方形
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## 步驟 4：為圖案方形輪廓設定筆
```java
BasicStroke stroke = new BasicStroke(2);
```
## 第 5 步：迭代填滿圖案
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    //...（繼續使用提供的代碼）
}
```
## 第6步：恢復圖形狀態
```java
document.writeGraphicsRestore();
```
## 步驟7：用填滿圖案填滿文本
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## 步驟8：用剖面線圖案勾勒文字輪廓
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## 第 9 步：關閉並儲存文檔
```java
document.closePage();
document.save();
```
按照以下步驟操作，您將使用 Aspose.Page 成功地將填滿圖案新增至 Java PostScript 文件。
## 結論
合併陰影圖案等視覺元素可以顯著增強 Java 應用程式的吸引力。 Aspose.Page for Java 讓這一過程變得無縫，讓您可以輕鬆建立視覺上令人驚嘆的 PostScript 文件。
## 常見問題解答
### 我可以將 Aspose.Page for Java 與其他 Java 框架一起使用嗎？
是的，Aspose.Page for Java 旨在與各種 Java 框架無縫整合。
### Aspose.Page for Java 是否有試用版？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### 如何取得 Aspose.Page for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以找到有關 Aspose.Page for Java 的更多教學和支援？
探索[Aspose.Page for Java 論壇](https://forum.aspose.com/c/page/39)獲取教程和社區支援。
### 是否有 Aspose.Page for Java 的綜合文件資源？
是的，請參閱文檔[這裡](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
