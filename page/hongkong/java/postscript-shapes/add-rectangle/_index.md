---
title: 自訂 Java PostScript - 使用 Aspose.Page 新增矩形
linktitle: 在 Java PostScript 中新增矩形
second_title: Aspose.Page Java API
description: 探索使用 Aspose.Page for Java 將鮮豔的矩形新增至 Java PostScript 文件的逐步指南。輕鬆增強您的文件自訂！
type: docs
weight: 11
url: /zh-hant/java/postscript-shapes/add-rectangle/
---
## 介紹
您是否希望使用充滿活力的矩形來增強您的 Java PostScript 文件？別再猶豫了！在本逐步指南中，我們將探討如何使用 Aspose.Page for Java 將矩形新增至 PostScript 文件。 Aspose.Page 是一個功能強大的程式庫，提供了處理 PostScript 檔案的強大功能，使其成為尋求操作和自訂文件的開發人員的理想選擇。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- 對 Java 程式設計有基本的了解。
- 安裝了 Java 函式庫的 Aspose.Page。如果沒有，請從以下位置下載[Aspose.Page 用於 Java 文檔](https://reference.aspose.com/page/java/).
- 在您的電腦上設定 Java 開發環境。
## 導入包
在您的 Java 專案中，首先匯入必要的套件：
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 教學課程：在 Java PostScript 中新增矩形
## 步驟1：設定填滿矩形的油漆
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//為 PostScript 文件建立輸出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
//建立 A4 尺寸的儲存選項
PsSaveOptions options = new PsSaveOptions();
//開啟頁面建立新的 PS 文檔
PsDocument document = new PsDocument(outPsStream, options, false);
//設定填充矩形的油漆
document.setPaint(Color.ORANGE);        
//填滿第一個矩形
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## 步驟 2： 設定描邊矩形的繪製
```java
//設定描邊矩形的油漆
document.setPaint(Color.RED);
//設定行程
document.setStroke(new BasicStroke(3));
//描邊（輪廓）第二個矩形
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## 步驟 3：關閉目前頁面並儲存文檔
```java
//關閉目前頁面
document.closePage();
//儲存文件
document.save();
```
恭喜！您已經使用 Aspose.Page 成功地將充滿活力的矩形新增至 Java PostScript 文件。
## 結論
在本教學中，我們探索了使用 Aspose.Page for Java 透過矩形增強 Java PostScript 文件的過程。這個強大的程式庫為尋求輕鬆自訂和操作文件的開發人員打開了一個充滿可能性的世界。
嘗試不同的形狀和顏色，讓您的文件在視覺上更具吸引力！
## 經常問的問題

### 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？
Aspose.Page 主要支援 Java，但類似的程式庫也可用於其他語言。
### 是否有 Aspose.Page for Java 的試用版？
是的，您可以透過以下方式探索 Aspose.Page for Java 的功能：[免費試用版](https://releases.aspose.com/).
### 我可以在哪裡找到更多幫助和討論？
參觀[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)與社區互動並獲得協助。
### 如何取得 Aspose.Page for Java 的臨時授權？
獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以購買 Aspose.Page for Java 的授權版本？
購買授權版本[這裡](https://purchase.aspose.com/buy).