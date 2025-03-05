---
title: 使用 Java 在 XMP 元資料中新增數組項
linktitle: 使用 Java 在 XMP 元資料中新增數組項
second_title: Aspose.Page Java API
description: 使用 Aspose.Page for Java 增強 EPS 檔案。了解如何輕鬆地將數組項新增至 XMP 元資料。立即按照我們的逐步指南進行操作！
type: docs
weight: 10
url: /zh-hant/java/xmp-metadata-manipulation/add-array-items/
---
## 介紹
歡迎閱讀我們有關使用 Aspose.Page for Java 在 XMP 元資料中新增陣列項目的逐步指南。 Aspose.Page 是一個功能強大的 Java 函式庫，可讓您操作和處理各種文件格式，包括 EPS 檔案。在本教程中，我們將重點放在使用 Java 在 XMP 元資料中新增數組項目的特定任務。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- 安裝了 Java 函式庫的 Aspose.Page。
- 對 Java 程式設計有基本的了解。
- 具有現有 XMP 元資料或 PS 元資料註釋的有效 EPS 檔案。
## 導入包
首先，您需要匯入使用 Aspose.Page 所需的套件。在 Java 檔案的開頭包含以下行：
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## 第 1 步：取得 XMP 元數據
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//初始化輸入 EPS 檔案流
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
//取得 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，我們會得到一個新文件，其中填入 PS 元資料註釋中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.getXmpMetadata();
```
在此步驟中，我們從 EPS 檔案中檢索現有的 XMP 元資料。如果 EPS 檔案尚不包含 XMP 元數據，Aspose.Page 會產生一個新檔案並用 PS 元資料註解中的值填滿它。
## 步驟 2：新增“dc:title”數組項
```java
//再新增一項「dc:title」數組項
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
現在，我們將一個新的陣列項目新增到 XMP 元資料中的「dc:title」屬性。將“NewTitle”替換為所需的標題。
## 步驟 3：新增「dc:creator」陣列項
```java
//再新增一項「dc:creator」陣列項
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
同樣，我們將一個新的陣列項目新增到 XMP 元資料中的「dc:creator」屬性中。將“NewCreator”替換為所需的創建者資訊。
## 步驟 4：初始化輸出 EPS 檔案流
```java
//初始化輸出 EPS 檔案流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
準備輸出 EPS 檔案流，其中將保存具有更新的 XMP 元資料的修改文件。
## 步驟 5：使用變更的 XMP 元資料儲存文檔
```java
//儲存具有變更的 XMP 元資料的文檔
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
將包含更新的 XMP 元資料的文件儲存到輸出 EPS 檔案。
## 結論
恭喜！您已經成功學習如何使用 Aspose.Page for Java 在 XMP 元資料中新增陣列項目。這個強大的程式庫簡化了 EPS 檔案的操作過程，並提供了廣泛的文檔處理功能。
## 經常問的問題

### 我可以將 Aspose.Page for Java 與其他文件格式一起使用嗎？
是的，Aspose.Page 支援各種文件格式，包括 EPS、PDF 和 XPS。
### Aspose.Page for Java 是否有免費試用版？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Page for Java 的文檔？
文件可用[這裡](https://reference.aspose.com/page/java/).
### 如何購買 Aspose.Page for Java？
您可以購買該產品[這裡](https://purchase.aspose.com/buy).
### Aspose.Page for Java 是否有臨時授權？
是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).