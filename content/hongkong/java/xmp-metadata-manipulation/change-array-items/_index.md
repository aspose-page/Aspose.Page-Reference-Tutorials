---
title: 使用 Java 更改 XMP 中的陣列項
linktitle: 使用 Java 更改 XMP 中的陣列項
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page for Java 變更 XMP 中的陣列項目。使用我們的逐步指南輕鬆修改元資料。立即增強您的 EPS 文件！
type: docs
weight: 15
url: /zh-hant/java/xmp-metadata-manipulation/change-array-items/
---
## 介紹
歡迎來到我們關於使用 Aspose.Page for Java 更改 XMP 中的陣列項目的綜合指南！ Aspose.Page 是一個功能強大的 Java 函式庫，可讓您無縫地使用 EPS 檔案中的 XMP 元資料。在本教程中，我們將引導您完成修改 XMP 元資料中的陣列項目的過程，幫助您增強和自訂 EPS 文件。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- 您的系統上安裝了 Java 開發工具包 (JDK)。
-  Java 的 Aspose.Page 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/page/java/).
## 導入包
首先，讓我們在 Java 專案中導入必要的套件。確保您的專案中包含 Aspose.Page 庫。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## 第 1 步：取得 XMP 元數據
首先，從 EPS 檔案中檢索 XMP 元資料。如果 EPS 檔案尚未包含 XMP 元數據，則會使用 PS 元資料註釋中的值（例如 %%Creator、%%CreateDate、%%Title 等）建立新檔案。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//初始化輸入 EPS 檔案流
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
//取得 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，則新檔案將填入 PS 元資料註釋中的值。
XmpMetadata xmp = document.getXmpMetadata();
```
## 步驟 2：設定“dc:title”數組項
現在，讓我們使用新值來設定索引 0 處的「dc:title」陣列項目。
```java
//按索引 0 設定「dc:title」數組項
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## 步驟 3：設定「dc:creator」陣列項
同樣，使用新的建立者值設定索引 0 處的「dc:creator」陣列項目。
```java
//依索引 0 設定「dc:creator」陣列項
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## 步驟 4：初始化輸出 EPS 檔案流
準備將儲存修改後的文件的輸出 EPS 檔案流。
```java
//初始化輸出 EPS 檔案流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## 步驟 5：使用變更的 XMP 元資料儲存文檔
使用更新的 XMP 元資料儲存文件。
```java
//儲存具有變更的 XMP 元資料的文檔
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 結論
恭喜！您已經成功學習如何使用 Aspose.Page for Java 來變更 XMP 中的陣列項目。本教學提供了逐步指導，確保您可以使用自訂元資料輕鬆增強 EPS 文件。

## 常見問題解答
### 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？
Aspose.Page 主要是為 Java 設計的，但 Aspose 也為其他語言提供了類似的函式庫。
### 在哪裡可以找到 Aspose.Page for Java 的詳細文件？
文件可用[這裡](https://reference.aspose.com/page/java/).
### Aspose.Page for Java 是否有免費試用版？
是的，您可以獲得免費試用[這裡](https://releases.aspose.com/).
### 如何取得 Aspose.Page for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以購買完整版的 Aspose.Page for Java？
您可以購買完整版[這裡](https://purchase.aspose.com/buy).