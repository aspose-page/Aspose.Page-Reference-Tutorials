---
date: 2026-05-15
description: 探索 aspose.page XMP 教程（Java 版）——學習如何在 XMP 中更改陣列項目、更新 EPS 標題、創作者等，只需幾行程式碼。
keywords:
- aspose.page xmp tutorial
- change array items java
- xmp metadata java
linktitle: 使用 Java 更改 XMP 陣列項目
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  headline: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  type: TechArticle
- description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  name: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  steps:
  - name: Get XMP Metadata
    text: Call `document.getXmpMetadata()` to retrieve the XMP metadata object associated
      with the EPS file.
  - name: Set "dc:title" Array Item
    text: Use `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` to replace the
      first title entry.
  - name: Set "dc:creator" Array Item
    text: Similarly, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` updates
      the first creator entry.
  - name: Initialize Output EPS File Stream
    text: Create a `FileOutputStream` pointing to the destination EPS file to write
      the updated document.
  - name: Save Document with Changed XMP Metadata
    text: The `PsDocument` class represents an EPS document and provides the `save`
      method to write changes to a stream.
  type: HowTo
- questions:
  - answer: No. You must invoke `setArrayItem` for each index you wish to modify;
      the API does not provide a bulk‑update method.
    question: Can I update multiple array items in one call?
  - answer: Yes. Provide the full prefix (e.g., `myNS:customProp`) when calling `setArrayItem`
      or `removeArrayItem`.
    question: Does aspose.page xmp java support custom namespaces?
  - answer: Reload the EPS with `PsDocument`, call `getXmpMetadata()`, and inspect
      the returned values, or open the file in an XMP viewer.
    question: How do I verify that the metadata was updated correctly?
  - answer: Use `removeArrayItem(namespace, index)` to delete a specific entry from
      an XMP array.
    question: Is it possible to remove an array item entirely?
  - answer: No. XMP metadata is stored separately from the graphic content and does
      not alter how the EPS renders.
    question: Will the changes affect the visual appearance of the EPS?
  type: FAQPage
second_title: Aspose.Page Java API
title: aspose.page XMP 教程：使用 Java 更改 XMP 中的陣列項目
url: /zh-hant/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page XMP 教程：使用 Java 更改陣列項目

## 介紹
Welcome to our comprehensive **aspose.page xmp tutorial**. In this guide we’ll show you step‑by‑step how to change array items in XMP metadata inside EPS files using Aspose.Page for Java. Whether you need to update the document title, author list, or any other XMP array, the process is straightforward, fully programmatic, and works with Java 8 +.

## 快速解答
- **aspose.page xmp java 的功能是什麼？** 它直接從 Java 讀寫 EPS 檔案中的 XMP 中繼資料。  
- **我需要授權才能試用嗎？** 是的，提供免費 30 天試用版；正式使用則需商業授權。  
- **支援哪個 JDK 版本？** Java 8 或更新版本（包括 Java 11、17 與 21）。  
- **我可以修改其他中繼資料欄位嗎？** 當然可以——任何 XMP 屬性，包括自訂命名空間，都可以讀取或更新。  
- **API 是否支援執行緒安全？** 大多數讀寫操作在每個執行緒使用各自的 `PsDocument` 實例時都是安全的。

## aspose.page xmp java 是什麼？
`aspose.page xmp java` 是 Aspose.Page for Java 的元件，將可擴充中繼資料平台 (XMP) 抽象為易於使用的 Java 物件。它讓您在不處理原始 XML 的情況下操作陣列、集合與結構化屬性。實務上，您可使用高階方法如 `setArrayItem` 與 `removeArrayItem` 即時編輯中繼資料。

## 為何在 EPS 中繼資料使用 aspose.page xmp java？
當您需要在大規模下精確且自動化地控制 EPS 中繼資料時，應使用此函式庫。Aspose.Page 支援 **30+ 個 XMP 結構欄位**，且可在不將整個文件載入記憶體的情況下處理高達 **500 MB** 的檔案，提供高速與低記憶體佔用。API 亦保證變更不會影響原始圖形，視覺渲染保持不變。

## 前置條件
- 已安裝 Java Development Kit (JDK) 8 或更新版本。  
- Aspose.Page for Java 函式庫。從 [here](https://releases.aspose.com/page/java/) 下載最新的 JAR。  
- 有效的 Aspose 授權檔案（或試用授權）已放置於 classpath 中。

## 如何使用 aspose.page xmp java 更改陣列項目
本節示範完整工作流程：開啟 EPS 檔案、取得其 XMP 中繼資料物件、修改特定陣列項目，最後將更新後的文件寫回磁碟。每個步驟皆以簡潔的 Java 程式碼說明，方便您整合至自己的應用程式中。

### 步驟 1：取得 XMP 中繼資料
呼叫 `document.getXmpMetadata()` 以取得與 EPS 檔案相關聯的 XMP 中繼資料物件。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

### 步驟 2：設定 "dc:title" 陣列項目
使用 `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` 來取代第一個標題項目。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### 步驟 3：設定 "dc:creator" 陣列項目
同樣地，`xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` 會更新第一個創作者項目。

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### 步驟 4：初始化輸出 EPS 檔案串流
建立指向目標 EPS 檔案的 `FileOutputStream` 以寫入更新後的文件。

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### 步驟 5：以變更的 XMP 中繼資料儲存文件
`PsDocument` 類別代表 EPS 文件，並提供 `save` 方法將變更寫入串流。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## 常見陷阱與技巧
- **索引超出範圍：** 請確認目標索引是否存在；否則 Aspose 會拋出 `ArrayIndexOutOfBoundsException`。  
- **串流管理：** 必須在 `finally` 區塊中關閉串流，或使用 try‑with‑resources 以防止檔案被鎖定。  
- **授權啟用：** 若忘記套用有效授權，試用模式下的 EPS 會出現浮水印。  
- **大型檔案：** 對於超過 200 MB 的 EPS 檔案，建議增加 JVM 堆積大小 (`-Xmx2g`) 以避免記憶體壓力。

## 常見問答

**Q: 我可以一次呼叫更新多個陣列項目嗎？**  
A: 不能。您必須針對每個欲修改的索引分別呼叫 `setArrayItem`；API 未提供批次更新方法。

**Q: aspose.page xmp java 是否支援自訂命名空間？**  
A: 支援。呼叫 `setArrayItem` 或 `removeArrayItem` 時，請提供完整前綴（例如 `myNS:customProp`）。

**Q: 我該如何驗證中繼資料已正確更新？**  
A: 使用 `PsDocument` 重新載入 EPS，呼叫 `getXmpMetadata()` 並檢查返回的值，或在 XMP 檢視器中開啟檔案。

**Q: 是否可以完全移除陣列項目？**  
A: 使用 `removeArrayItem(namespace, index)` 以刪除 XMP 陣列中的特定項目。

**Q: 變更會影響 EPS 的視覺外觀嗎？**  
A: 不會。XMP 中繼資料與圖形內容分開儲存，不會改變 EPS 的渲染方式。

## 結論
您已掌握 **aspose.page XMP 教程**（Java 版），能自信地在 EPS XMP 中繼資料裡更改陣列項目。此功能可實現自動化文件流程、大量中繼資料更新，以及在不觸及視覺資料的情況下更佳的資產管理。

---

**最後更新：** 2026-05-15  
**測試環境：** Aspose.Page for Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 相關教學

- [使用 Java 在 XMP 中繼資料新增陣列項目](/page/java/xmp-metadata-manipulation/add-array-items/)
- [aspose page XMP 教程 – 使用 Java 更改命名值](/page/java/xmp-metadata-manipulation/change-named-value/)
- [如何使用 Java 讀取 XMP 中繼資料 – Aspose.Page 指南](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}