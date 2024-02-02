---
title: 在 Java 中將 XSP 轉換為 TIFF
linktitle: 在 Java 中將 XSP 轉換為 TIFF
second_title: Aspose.Page Java API
description: 使用 Aspose.Page for Java 輕鬆將 XPS 轉換為 TIFF。請按照我們的逐步指南進行無縫整合。現在下載！
type: docs
weight: 14
url: /zh-hant/java/xps-conversion/to-tiff/
---
在當今的數位時代，文件轉換在各種應用中起著至關重要的作用。如果您是 Java 開發人員，正在尋求將 XPS（XML 紙張規格）文件轉換為 TIFF（標記影像檔案格式）的強大解決方案，那麼 Aspose.Page for Java 就是您的首選函式庫。在本逐步指南中，我們將引導您完成整個過程，透過詳細的解釋和程式碼片段確保您獲得流暢的體驗。
## 先決條件
在深入轉換過程之前，請確保滿足以下先決條件：
- 您的電腦上安裝了 Java 開發工具包 (JDK)。
-  Java 函式庫的 Aspose.Page。你可以下載它[這裡](https://releases.aspose.com/page/java/).
-  Aspose.Page for Java 的有效授權。您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)，或購買完整許可證[這裡](https://purchase.aspose.com/buy).
## 導入包
首先在 Java 專案中導入必要的包。確保您已將 Aspose.Page for Java 庫新增至您的專案。
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## 第 1 步：設定文檔目錄
定義輸入 XPS 檔案所在文件目錄的路徑。
```java
String dataDir = "Your Document Directory";
```
## 第 2 步：載入 XPS 文檔
使用 Aspose.Page 庫載入 XPS 文件。
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## 步驟 3：初始化 TiffSaveOptions
使用必要的參數初始化 TiffSaveOptions 對象，例如平滑模式、解析度和特定頁碼。
```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## 第四步：建立渲染設備
使用 ImageDevice 類別建立 TIFF 格式的渲染裝置。
```java
ImageDevice device = new ImageDevice();
```
## 步驟 5：將文件儲存為 TIFF
使用指定的選項和渲染設備將 XPS 文件儲存為 TIFF 格式。
```java
document.save(device, options);
```
## 第 6 步：迭代並儲存 TIFF 影像
迭代文件分割區和頁面，初始化影像輸出流並儲存 TIFF 影像。
```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
恭喜！您已使用 Aspose.Page 在 Java 中成功將 XPS 轉換為 TIFF。請隨意探索該庫的更多特性和功能[文件](https://reference.aspose.com/page/java/).
## 結論
在本教程中，我們介紹了在 Java 中使用 Aspose.Page 將 XPS 轉換為 TIFF 的基本步驟。文件轉換現在觸手可及，使您可以透過多功能文件格式支援來增強您的應用程式。
## 經常問的問題
### 我可以在沒有授權的情況下使用 Aspose.Page for Java 嗎？
雖然您可以獲得臨時許可證用於評估，但生產使用需要有效許可證。取得您的執照[這裡](https://purchase.aspose.com/buy).
### 用於轉換的 XPS 檔案的大小有限制嗎？
Aspose.Page for Java 可處理各種大小的文檔，但建議在您的特定環境中使用較大的文件進行測試。
### 我該如何獲得有關 Aspose.Page for Java 的支援或提出問題？
參觀[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持和討論。
### Aspose.Page for Java 是否有免費試用版？
是的，您可以透過免費試用來探索該庫。下載它[這裡](https://releases.aspose.com/).
### 在此轉換中 TIFF 影像的建議解析度是多少？
提供的範例使用 300 DPI 的分辨率，但您可以根據您的特定要求進行調整。