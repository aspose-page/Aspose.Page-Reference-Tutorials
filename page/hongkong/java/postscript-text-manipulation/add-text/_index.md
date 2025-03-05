---
title: Aspose.Page Java 文字操作
linktitle: 在 Java PostScript 中加入文本
second_title: Aspose.Page Java API
description: 在我們為 PostScript 文件添加文字的教學中探索 Aspose.Page for Java 的強大功能。學習輕鬆使用系統和自訂字體。
type: docs
weight: 10
url: /zh-hant/java/postscript-text-manipulation/add-text/
---
## 介紹
歡迎閱讀我們有關使用 Aspose.Page for Java 在 Java PostScript 中新增文字的逐步指南。 Aspose.Page for Java 是一個功能強大的程式庫，可讓開發人員輕鬆操作 PostScript 文件。在本教程中，我們將引導您完成添加文字、使用系統和自訂字體、概述文字以及合併筆劃以獲得視覺上吸引人的結果的過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- Java 程式設計的基礎知識。
- 安裝了 Java 函式庫的 Aspose.Page。您可以從[Aspose.Page for Java 下載頁面](https://releases.aspose.com/page/java/).
- 指定資料夾中提供必要的字型。您可以在以下位置找到更多信息[Aspose.Page 用於 Java 文檔](https://reference.aspose.com/page/java/).
## 導入包
在您的 Java 專案中，匯入 Aspose.Page for Java 所需的套件：
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## 第 1 步：設定文檔
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
//為 PostScript 文件建立輸出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
//建立 A4 尺寸的儲存選項
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
//要寫入 PS 檔案的文本
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
//建立新的 1 頁 PS 文檔
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 步驟2：使用系統字體填滿文本
```java
//使用系統字體填充文本
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
//使用預設或已定義的顏色（黑色）填滿文本
document.fillText(str, font, 50, 100);
//用藍色填充文本
document.fillText(str, font, 50, 150, Color.BLUE);
```
## 步驟 3：使用自訂字體填滿文本
```java
//使用自訂字體填充文本
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
//使用預設或已定義的顏色（黑色）填滿文本
document.fillText(str, drFont, 50, 200);
//用藍色填充文本
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## 步驟 4：使用系統字體勾勒文字輪廓
```java
//使用系統字體來概述文本
document.outlineText(str, font, 50, 300);
//使用藍紫色 2 點寬筆勾勒文本輪廓
document.outlineText(str, font, 50, 350, strokeColor, stroke);
//用橘色填滿文字並用藍色 2 點寬筆描邊
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## 第 5 步：使用自訂字體勾畫文字輪廓
```java
//使用自訂字體來概述文本
document.outlineText(str, drFont, 50, 450);
//使用藍紫色 2 點寬筆勾勒文本輪廓
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
//用橘色填滿文字並用藍色 2 點寬筆描邊
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## 第 6 步：儲存文檔
```java
//關閉目前頁面
document.closePage();
//儲存文件
document.save();
```
## 結論
恭喜！您已經成功學習如何使用 Aspose.Page for Java 在 Java PostScript 中新增文字。嘗試不同的字體、顏色和輪廓選項，以進一步增強您的文件。
## 經常問的問題
### 我可以在 Aspose.Page for Java 中使用我自己的自訂字體嗎？
是的，您可以透過在中指定字體名稱和大小來使用自訂字體`DrFont`班級。
### 如何更改文字的顏色？
您可以使用設定所需的顏色`Color`填充或概述文字時的類別。
### 是否可以為 PostScript 文件新增多個頁面？
絕對地！您可以透過重複文件建立和儲存步驟來建立多個頁面。
### 目的是什麼`ExternalFontCache` class?
`ExternalFontCache`用於取得自訂字體，確保它們可用於文字操作。
### 我可以對輪廓文字應用不同的筆畫嗎？
是的，您可以使用以下命令自訂筆劃的寬度和顏色`Stroke`類和`Color`類，分別。