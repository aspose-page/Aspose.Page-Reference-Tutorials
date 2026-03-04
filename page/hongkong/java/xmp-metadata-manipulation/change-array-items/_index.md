---
date: 2025-12-20
description: 學習如何使用 Aspose.Page for Java（aspose.page xmp java）更改 XMP 中的陣列項目。透過我們的逐步指南輕鬆修改中繼資料，立即提升您的
  EPS 文件。
linktitle: Change Array Items in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page xmp java - 使用 Java 更改 XMP 中的陣列項目
url: /zh-hant/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp java: 使用 Java 更改 XMP 陣列項目

## 簡介
歡迎閱讀我們關於 **使用 Aspose.Page for Java 更改 XMP 陣列項目** 的完整指南。**aspose.page xmp java** 函式庫讓您能完整掌控 EPS 檔案內的 XMP 中繼資料，輕鬆自訂標題、作者及其他屬性。在本教學中，我們將逐步說明如何修改陣列項目，讓您自信地增強與個人化 EPS 文件。

## 快速解答
- **aspose.page xmp java 的功能是什麼？** 它讓您能在 Java 中讀寫 EPS 檔案的 XMP 中繼資料。  
- **試用需要授權嗎？** 需要。提供免費試用版，但正式使用必須購買授權。  
- **支援哪個版本的 JDK？** Java 8 或更新版本。  
- **可以修改其他中繼資料欄位嗎？** 當然可以——任何 XMP 屬性皆可讀取或更新。  
- **API 是否具備執行緒安全性？** 大多數讀寫操作在不同文件實例上使用時是安全的。

## 什麼是 aspose.page xmp java？
`aspose.page xmp java` 是 Aspose.Page for Java 套件的一部分，專注於 XMP（可擴充中繼資料平台）的處理。它將低階的 XMP 結構抽象為簡易的 Java 物件，讓您能在不直接操作原始 XML 的情況下，處理陣列、集合與結構化屬性。

## 為什麼要使用 aspose.page xmp java 處理 EPS 元資料？
- **精準度：** 直接定位特定的 XMP 陣列項目（例如 title、creator）。  
- **自動化：** 可將中繼資料更新整合至建置管線或批次處理程序。  
- **相容性：** 支援符合 XMP 標準的任何 EPS 檔案。  

## 前提條件
在開始撰寫程式碼之前，請確保您已具備以下條件：

- 已在系統上安裝 Java Development Kit (JDK)。  
- 已取得 Aspose.Page for Java 函式庫。您可從 [here](https://releases.aspose.com/page/java/) 下載。

## 導入包
開始之前，請將必要的類別匯入您的 Java 專案，並確保已將 Aspose.Page 的 JAR 加入專案的 classpath。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 如何使用 aspose.page xmp java 修改陣列項

### 第一步：取得 XMP 元數據
首先，從 EPS 檔案中取得 XMP 中繼資料。如果檔案本身沒有 XMP 資料，Aspose.Page 會根據現有的 PS 註解（例如 %%Creator、%%Title）建立新的 XMP 區塊。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### 步驟 2：設定「dc:title」陣列項
接著，將 **dc:title** 陣列的第一個元素替換為新的標題字串。

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### 步驟 3：設定「dc:creator」陣列項
同理，更新 **dc:creator** 陣列的第一個元素。

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### 步驟 4：初始化輸出 EPS 檔案流
為輸出 EPS 檔案建立串流，以便儲存已修改的中繼資料。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

### 步驟 5：儲存已變更 XMP 元資料的文檔
最後，將文件保存，將變更寫入 EPS 檔案。

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 常見陷阱和技巧
- **索引超出範圍：** 請確保您提供的索引已存在，否則 Aspose 會拋出例外。  
- **串流管理：** 請務必在 `finally` 區塊中關閉串流，以避免檔案被鎖定。  
- **授權啟用：** 若忘記設定有效授權，試用模式下會產生帶有水印的輸出。

## 結論
恭喜您！您已成功學會如何使用 **aspose.page xmp java** 變更 XMP 陣列項目。此步驟教學讓您能以程式方式修改 EPS 中繼資料，為自動化文件工作流程與更豐富的內容管理開啟大門。

## 其他常見問題

**問：我可以在一次呼叫中更新多個數組項嗎？ **
 
A: 您需要針對每個欲修改的索引分別呼叫 `setArrayItem`，目前沒有批次更新的方法。  

**問：Aspose.Page XMP Java 是否支援自訂命名空間？ **

A: 支援，您可以使用完整前綴（例如 `myNS:customProp`）操作任何已註冊的 XMP 命名空間。  

**問：如何驗證元資料是否已正確更新？ **
 
A: 重新以 `PsDocument` 載入 EPS 檔案，呼叫 `getXmpMetadata()` 讀回值，或使用 XMP 檢視器檢查檔案。  

**問：是否可以完全刪除陣列項目？ **
 
A: 可使用 `removeArrayItem(namespace, index)` 刪除 XMP 陣列中的特定項目。  

**問：這些變更會影響 EPS 的視覺效果嗎？ **
 
A: 不會。XMP 中繼資料屬於非視覺資訊，並不會改變 EPS 檔案的圖形內容。

---

**上次更新時間：** 2025-12-20
**測試版本：** Aspose.Page for Java 24.11（撰寫本文時的最新版本）
**作者：** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}