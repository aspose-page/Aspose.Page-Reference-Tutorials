---
title: 在 Java PostScript 中加入紋理平鋪模式
linktitle: 在 Java PostScript 中加入紋理平鋪模式
second_title: Aspose.Page Java API
description: 使用 Aspose.Page for Java 輕鬆地將紋理平鋪圖案新增至 PostScript 文件。探索我們的無縫整合指南，以實現創造性的可能性。
weight: 10
url: /zh-hant/java/postscript-texture-patterns/add-texture-tiling-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中加入紋理平鋪模式

## 介紹
在 Java 開發領域，在 PostScript 文件中創建複雜的圖案和紋理是一種常見的需求。 Aspose.Page for Java 被證明是輕鬆完成此任務的一個有價值的工具。在本教學中，我們將引導您完成使用 Aspose.Page 在 Java PostScript 文件中新增紋理平鋪圖案的過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- 對 Java 程式語言有基本的了解。
- 熟悉 PostScript 文件結構。
- 安裝了 Java 函式庫的 Aspose.Page。你可以下載它[這裡](https://releases.aspose.com/page/java/).
## 導入包
首先導入 Java 專案所需的套件：
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 步驟 1：建立 PostScript 文檔
首先建立一個新的 PostScript 文檔，指定輸出流和儲存選項。確保您已配置必要的路徑。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//為 PostScript 文件建立輸出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
//建立 A4 尺寸的儲存選項
PsSaveOptions options = new PsSaveOptions();
//開啟頁面建立新的 PS 文檔
PsDocument document = new PsDocument(outPsStream, options, false);
//開啟頁面建立新的 PS 文檔
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 第2步：設定圖形環境
透過平移原點並從紋理影像檔案建立 BufferedImage 來設定圖形環境。
```java
document.writeGraphicsSave();
document.translate(200, 100);
//從圖像檔案建立 BufferedImage 對象
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```
## 步驟3：創造紋理畫筆
從影像定義紋理畫筆，指定紋理要覆蓋的區域。
```java
//創建寬度加倍的圖像區域
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
//從圖像創建紋理畫筆
TexturePaint paint = new TexturePaint(image, imageArea);
```
## 第四步：繪製並填滿形狀
建立一個矩形並用定義的紋理畫筆填滿它。此外，繪製並勾勒出形狀以增加視覺吸引力。
```java
//建立矩形
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
//將此紋理畫筆設定為目前繪畫
document.setPaint(paint);
//填滿矩形
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```
## 步驟5：新增帶有紋理圖案的文本
將文字新增至文件並使用紋理圖案填滿/描邊它。根據需要自訂字體、位置和其他參數。
```java
//以紋理圖案填滿文本
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
//以紋理圖案勾勒出文字輪廓
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## 第 6 步：儲存並關閉
透過關閉當前頁面、儲存文件並確保無縫執行來結束流程。
```java
//關閉目前頁面
document.closePage();
//儲存文件
document.save();
```
## 結論
恭喜！您已使用 Aspose.Page for Java 成功將紋理平鋪圖案新增至 Java PostScript 文件。請隨意探索更多自訂選項並釋放這個強大庫的全部潛力。

## 常見問題解答
### Aspose.Page for Java適合初學者嗎？
絕對地！ Aspose.Page for Java 提供了全面的文檔，使所有技能水平的開發人員都可以使用它。
### 我可以將 Aspose.Page for Java 整合到我現有的 Java 專案中嗎？
是的，您可以按照提供的文件輕鬆將 Aspose.Page for Java 整合到您的專案中[這裡](https://reference.aspose.com/page/java/).
### 我可以在哪裡找到支援或討論與 Aspose.Page 相關的查詢？
參觀[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)與社區互動並尋求協助。
### Aspose.Page for Java 是否有免費試用版？
是的，您可以探索免費試用[這裡](https://releases.aspose.com/).
### 如何取得 Aspose.Page for Java 的臨時授權？
訪問[這個連結](https://purchase.aspose.com/temporary-license/)獲得臨時許可證。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
