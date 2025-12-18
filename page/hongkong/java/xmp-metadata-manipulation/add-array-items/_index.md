---
date: 2025-12-18
description: 學習如何使用 Aspose.Page for Java，透過將陣列項目插入 EPS 檔案的 XMP 中繼資料來新增中繼資料。請跟隨我們的逐步指南。
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: 如何新增元資料 – 在 XMP 中新增陣列項目 (Java)
url: /zh-hant/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP Metadata 中新增陣列項目

## 如何新增 Metadata
歡迎閱讀我們的分步指南，說明 **如何新增 metadata** 至使用 Aspose.Page for Java 的 EPS 檔案。此教學將帶您了解在 XMP metadata 中新增陣列項目的方法——當您需要為文件資訊（例如標題或作者）增添更多內容時，這是一項常見需求。完成後，您將了解 XMP 的價值、如何以程式方式操作它，以及如何儲存已更新的 EPS 檔案。

## 快速解答
- **使用哪個函式庫？** Aspose.Page for Java  
- **目標檔案格式為何？** EPS（Encapsulated PostScript）  
- **可以新增多個標題嗎？** 可以，重複使用 `xmp.addArrayItem("dc:title", ...)` 即可  
- **正式環境需要授權嗎？** 需要，有效的 Aspose.Page 授權是必須的  
- **程式碼相容於 Java 8+ 嗎？** 完全相容，支援所有現代 Java 版本  

## 先決條件
在開始本教學之前，請確保您具備以下條件：
- 已安裝 Aspose.Page for Java 函式庫。  
- 具備基本的 Java 程式設計知識。  
- 手頭有包含現有 XMP metadata 或 PS metadata 註解的有效 EPS 檔案。  

## 匯入套件
要開始使用 Aspose.Page，您需要匯入相關套件。請在 Java 檔案的開頭加入以下程式碼：
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 步驟 1：取得 XMP Metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
在此步驟中，我們會從 EPS 檔案中取得現有的 XMP metadata。若 EPS 檔案尚未包含 XMP metadata，Aspose.Page 會自動產生新 metadata，並從 PS metadata 註解中填入相應值。

## 步驟 2：新增 "dc:title" 陣列項目
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
現在，我們在 XMP metadata 的 **dc:title** 屬性中加入新的陣列項目。請將 `"NewTitle"` 替換為您想要的標題。

## 步驟 3：新增 "dc:creator" 陣列項目
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
同理，我們在 XMP metadata 的 **dc:creator** 屬性中加入新的陣列項目。請將 `"NewCreator"` 替換為您想要的作者資訊。

## 步驟 4：初始化輸出 EPS 檔案串流
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
準備好輸出 EPS 檔案的串流，之後會將已修改 XMP metadata 的文件寫入此檔案。

## 步驟 5：以變更的 XMP Metadata 儲存文件
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
將帶有更新後 XMP metadata 的文件儲存至輸出 EPS 檔案。

## 結論
恭喜！您已成功學會 **如何新增 metadata**，透過在 XMP metadata 中插入陣列項目，使用 Aspose.Page for Java 完成此操作。此強大的函式庫簡化了 EPS 檔案的操作，並提供豐富的文件處理功能。

## 常見問題

### 我可以將 Aspose.Page for Java 與其他文件格式一起使用嗎？
是的，Aspose.Page 支援多種文件格式，包括 EPS、PDF 和 XPS。

### 是否提供 Aspose.Page for Java 的免費試用？
是的，您可以在此取得免費試用 [here](https://releases.aspose.com/)。

### 我可以在哪裡找到 Aspose.Page for Java 的文件？
文件可於此取得 [here](https://reference.aspose.com/page/java/)。

### 我該如何購買 Aspose.Page for Java？
您可以在此購買產品 [here](https://purchase.aspose.com/buy)。

### 是否提供 Aspose.Page for Java 的臨時授權？
是的，您可以在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

## 其他常見問題

**問：我可以在同一屬性中新增多個陣列項目嗎？**  
**答：當然可以。對同一屬性多次呼叫 `xmp.addArrayItem` 即可建立值的清單。**

**問：此方法是否適用於除 Dublin Core 之外的現有 XMP 架構？**  
**答：是的，只要正確引用命名空間，即可在任何 XMP 屬性中新增陣列項目。**

**問：我該如何驗證 metadata 是否正確新增？**  
**答：在支援 XMP 的檢視器（例如 Adobe Bridge）中開啟產生的 EPS 檔案，或使用 `XmpMetadata` 方法以程式方式提取 metadata 進行驗證。**

---

**最後更新：** 2025-12-18  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}