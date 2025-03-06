---
title: 在 Java 中將 XPS 轉換為 JPEG
linktitle: 在 Java 中將 XPS 轉換為 JPEG
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page 在 Java 中將 XPS 轉換為 JPEG。包含無縫集成分步說明的綜合指南。
weight: 11
url: /zh-hant/java/xps-conversion/to-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中將 XPS 轉換為 JPEG

## 介紹
在本教學中，我們將探討如何使用 Aspose.Page for Java 將 XPS（XML 紙張規格）檔案轉換為 JPEG 影像。 Aspose.Page 是一個功能強大的 Java 程式庫，可讓開發人員無縫地使用 XPS 和其他文件格式。本逐步指南將幫助您了解該過程並在 Java 應用程式中實現它。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- Java 開發環境：確保您的電腦上設定了 Java 開發環境。
-  Aspose.Page for Java 函式庫：下載並安裝 Aspose.Page for Java 函式庫。你可以找到圖書館[這裡](https://releases.aspose.com/page/java/).
- 範例 XPS 文件：有一個要轉換為 JPEG 的範例 XPS 文件。
## 導入包
首先將必要的套件匯入到您的 Java 類別：
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## 第 1 步：初始化路徑和 XPS 文檔
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//初始化XPS輸入流
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## 步驟2：設定JpegSaveOptions
```java
//使用必要的參數初始化選項物件。
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## 第三步：建立渲染設備
```java
//建立PDF格式的渲染設備
ImageDevice device = new ImageDevice();
```
## 步驟 4：將 XPS 儲存為 JPEG
```java
document.save(device, options);
```
## 第 5 步：迭代並儲存 JPEG 頁面
```java
//迭代文檔分區（固定文檔，用 XPS 術語來說）
for (int i = 0; i < device.getResult().length; i++) {
    //遍歷分區頁
    for (int j = 0; j < device.getResult()[i].length; j++) {
        //初始化影像輸出流
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        //寫入影像
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //關閉流
        imageStream.close();
    }
}
```
這一系列步驟將有效地將您的 XPS 文件轉換為 JPEG 影像，每個影像單獨保存。
## 結論
恭喜！您已經成功學習如何使用 Aspose.Page 在 Java 中將 XPS 轉換為 JPEG。對於在 Java 應用程式中進行文件轉換的開發人員來說，此過程非常寶貴。
## 經常問的問題

### Q：Aspose.Page 適合商業項目嗎？
答：是的，Aspose.Page 是一個商業產品，具有可用的授權選項。查看[這裡](https://purchase.aspose.com/buy)了解詳情。
### Q：我可以在購買前試用 Aspose.Page 嗎？
答：是的，您可以獲得免費試用[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到 Aspose.Page 文件？
答：文檔已提供[這裡](https://reference.aspose.com/page/java/).
### Q：如何獲得 Aspose.Page 的支援？
答：訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得基於社區的支持。
### Q：我需要臨時許可證才能進行測試嗎？
答： 是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
