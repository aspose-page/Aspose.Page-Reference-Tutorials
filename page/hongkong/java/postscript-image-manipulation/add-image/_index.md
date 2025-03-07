---
title: 在 Java PostScript 中新增圖像
linktitle: 在 Java PostScript 中新增圖像
second_title: Aspose.Page Java API
description: 在本教程中探索 Aspose.Page Java 的無縫集成，為 PostScript 文件添加圖像。提升您的文件處理能力。
weight: 10
url: /zh-hant/java/postscript-image-manipulation/add-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中新增圖像

## 介紹
在本教學中，我們將探討如何使用 Aspose.Page for Java 函式庫將圖片新增至 Java PostScript 文件。 Aspose.Page 是一個功能強大的程式庫，提供了處理 PostScript 檔案的各種功能，使開發人員能夠無縫地操作和增強他們的文件。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- 您的系統上安裝了 Java 開發工具包 (JDK)。
-  Java 函式庫的 Aspose.Page。你可以下載它[這裡](https://releases.aspose.com/page/java/).
- 對 Java 程式設計有基本的了解。
## 導入包
首先，在您的 Java 專案中匯入必要的套件。使用以下程式碼片段作為參考：
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 步驟1：編寫圖形保存
第一步是將圖形儲存到文件中。這確保了以後進行的任何轉換或修改都可以在需要時回滾。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//為 PostScript 文件建立輸出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
//建立 A4 尺寸的儲存選項
PsSaveOptions options = new PsSaveOptions();
//開啟頁面建立新的 PS 文檔
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## 第 2 步：翻譯與變換
接下來，翻譯文件並從圖像文件建立 BufferedImage 物件。使用 AffineTransform 應用一系列變換，例如縮放和旋轉。
```java
document.translate(100, 100);
//從圖像檔案建立 BufferedImage 對象
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
//建立影像變換
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## 第 3 步：將圖像新增至文件中
現在，將轉換後的圖像新增至文件。
```java
document.drawImage(image, transform, null);
```
## 第四步：編寫圖形恢復
添加圖像後，編寫圖形恢復以完成所做的更改。
```java
document.writeGraphicsRestore();
```
## 步驟5：關閉目前頁面並儲存
關閉目前頁面並儲存文件。
```java
document.closePage();
document.save();
```
重複這些步驟以新增多個影像或根據您的要求自訂轉換。
## 結論
恭喜！您已經成功學習如何使用 Aspose.Page for Java 將圖像新增至 Java PostScript 文件。探索[文件](https://reference.aspose.com/page/java/)以獲得更高級的特性和功能。
## 常見問題解答
### 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？
Aspose.Page 主要支援 Java，但也有適用於其他程式語言的版本。
### Aspose.Page for Java 是否有免費試用版？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### 如何取得 Aspose.Page for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以找到與 Aspose.Page for Java 相關的社群支援和討論？
參觀[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持。
### 是否有其他資源可用於購買 Aspose.Page for Java？
你可以購買圖書館[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
