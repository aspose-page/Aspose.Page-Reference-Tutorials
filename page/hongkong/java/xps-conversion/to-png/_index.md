---
title: 在 Java 中將 XPS 轉換為 PNG
linktitle: 在 Java 中將 XPS 轉換為 PNG
second_title: Aspose.Page Java API
description: 使用 Aspose.Page 在 Java 中輕鬆將 XPS 轉換為 PNG。透過這種可靠且對開發人員友好的解決方案簡化文件任務。
type: docs
weight: 13
url: /zh-hant/java/xps-conversion/to-png/
---
## 介紹
在軟體開發的動態世界中，經常需要將 XPS（XML 紙張規格）文件轉換為 PNG（便攜式網路圖形）影像。為了用 Java 無縫地完成這項任務，Aspose.Page 提供了一個強大的解決方案。在本教學中，我們將逐步介紹使用 Aspose.Page for Java 將 XPS 轉換為 PNG 的過程。
## 先決條件
在我們深入學習本教學之前，請確保您已設定以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Page for Java：下載並安裝 Aspose.Page 函式庫。你可以找到下載鏈接[這裡](https://releases.aspose.com/page/java/).
3. 整合開發環境 (IDE)：選擇與 Java 相容的 IDE，例如 IntelliJ IDEA 或 Eclipse。
## 導入包
在您的 Java 專案中，匯入必要的套件以利用 Aspose.Page 功能。在 Java 檔案的開頭加入以下導入語句：
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## 步驟1：設定文檔目錄
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
```
## 第 2 步：載入 XPS 文檔
```java
//載入XPS文檔
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## 第 3 步：初始化選項
```java
//使用必要的參數初始化選項物件。
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## 第四步：建立渲染設備
```java
//建立PDF格式的渲染設備
ImageDevice device = new ImageDevice();
```
## 第 5 步：儲存並迭代
```java
//使用選項和設備將 XPS 文件儲存為 PNG
document.save(device, options);
//迭代文檔分區（固定文檔，用 XPS 術語來說）
for (int i = 0; i < device.getResult().length; i++) {
    //遍歷分區頁
    for (int j = 0; j < device.getResult()[i].length; j++) {
        //初始化影像輸出流
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        //寫入影像
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //關閉流
        imageStream.close();
    }
}
```
透過執行下列步驟，您可以使用 Aspose.Page for Java 輕鬆將 XPS 文件轉換為 PNG 映像。
## 結論
總之，Aspose.Page for Java 簡化了 XPS 到 PNG 的轉換過程，為開發人員提供了可靠且高效的工具。將此程式庫合併到您的 Java 專案中以簡化文件操作任務。
## 常見問題解答
### 我可以在商業專案中使用 Aspose.Page for Java 嗎？
是的，Aspose.Page 是一個商業產品。您可以找到許可信息[這裡](https://purchase.aspose.com/buy).
### 有免費試用嗎？
是的，您可以探索免費試用[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Page for Java 的文檔？
提供全面的文檔[這裡](https://reference.aspose.com/page/java/).
### 如何獲得用於測試目的的臨時許可證？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 是否有用於 Aspose.Page 討論的社群論壇？
是的，請造訪社區論壇[這裡](https://forum.aspose.com/c/page/39).