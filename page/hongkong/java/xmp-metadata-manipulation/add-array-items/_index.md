---
date: 2026-03-05
description: 學習如何使用 Aspose.Page for Java 在 EPS 檔案的 XMP 中加入 dc:title 陣列項目。請遵循此一步一步的指南，即可快速取得成果。
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: 如何使用 Java 在 XMP 中繼資料中新增 dc:title 陣列項目
url: /zh-hant/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP Metadata 中新增陣列項目

## 介紹
在本教學中，您將了解 **如何新增 dc:title**（以及其他陣列項目）到 EPS 檔案中的 XMP metadata，使用 Aspose.Page for Java。更新 XMP metadata 在需要將可搜尋資訊（例如標題、創作者或關鍵字）直接嵌入圖形檔案時非常有用。我們將逐步說明每一步，解釋每行程式碼的意義，並示範如何驗證變更。

## 快速解答
- **“dc:title” 代表什麼？** 它是以 XMP 陣列形式儲存的 Dublin Core 標題屬性。  
- **為什麼要修改 XMP metadata？** 它能提升資產管理、可搜尋性，並符合標準要求。  
- **是否需要已有的 XMP 區塊？** 不需要 — 若缺少，Aspose.Page 會從 PS 註解自動產生。  
- **需要哪個版本的函式庫？** 任意近期的 Aspose.Page for Java 版本（已在最新 2026 版測試）。  
- **我可以新增其他陣列屬性嗎？** 可以 — 使用相同的 `addArrayItem` 方法，針對如 `dc:creator` 等屬性。

## 前置條件
在開始之前，請確保您已具備以下條件：

- 已安裝 Aspose.Page for Java 函式庫（將 JAR 加入專案的 classpath）。  
- 基本的 Java 開發經驗（建議使用 JDK 8 以上）。  
- 一個已包含 XMP metadata 或至少包含 PS metadata 註解（例如 `%%Title`、`%%Creator`）的 EPS 檔案。  

## 匯入套件
首先，匯入用於讀取、操作與儲存 EPS 檔案所需的類別：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 步驟 1：載入 EPS 文件並取得 XMP Metadata
此處我們開啟 EPS 檔案並向 Aspose.Page 取得其 XMP 區塊。若檔案缺少 XMP，函式庫會使用現有的 PS 註解自動建立，確保您始終擁有可供操作的 metadata 容器。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 步驟 2：新增 **dc:title** 陣列項目  
此行示範 **如何新增 dc:title**。將 `"NewTitle"` 替換為您想嵌入的實際標題。此方法會將值附加到現有的 title 陣列中，保留先前的所有標題。

```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

## 步驟 3：新增 **dc:creator** 陣列項目  
同樣地，您可以豐富 `dc:creator` 屬性。可儲存多位創作者；每次呼叫都會新增一筆條目。

```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

## 步驟 4：準備輸出串流  
我們為修改後的 EPS 檔案建立串流。使用不同的檔名（`xmp3_changed.eps`）可避免改動原始檔案。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## 步驟 5：以更新的 XMP Metadata 儲存文件  
`save` 呼叫會將 EPS 資料與更新後的 XMP 區塊一起寫入。`finally` 區塊確保即使發生例外，檔案句柄也會被釋放。

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 為何這很重要
嵌入正確的 `dc:title` 與 `dc:creator` 值可提升：

- **可搜尋性** 在數位資產管理（DAM）系統中。  
- **合規性** 符合需要 metadata 的出版標準。  
- **協作**，團隊成員可快速辨識檔案內容，無需開啟 EPS。  

## 常見陷阱與技巧
- **陷阱：** 無意間覆寫現有的陣列項目。  
  **技巧：** 使用 `xmp.getArrayItems("dc:title")` 檢查目前的值，再決定是否新增。  
- **陷阱：** 忘記關閉串流，導致檔案被鎖定。  
  **技巧：** 如範例所示，始終將 I/O 包於 try‑with‑resources 或 `finally` 區塊中。  
- **技巧：** 您可以串接多個 `addArrayItem` 呼叫，一次新增多個標題或創作者。  

## 常見問答

### 我可以將 Aspose.Page for Java 用於其他文件格式嗎？
是的，Aspose.Page 支援多種文件格式，包括 EPS、PDF 與 XPS。

### 是否提供 Aspose.Page for Java 的免費試用？
是的，您可在此取得免費試用 [此處](https://releases.aspose.com/)。

### 我在哪裡可以找到 Aspose.Page for Java 的文件說明？
文件說明可於 [此處](https://reference.aspose.com/page/java/) 取得。

### 我要如何購買 Aspose.Page for Java？
您可在此購買產品 [此處](https://purchase.aspose.com/buy)。

### 是否提供 Aspose.Page for Java 的臨時授權？
是的，您可於此取得臨時授權 [此處](https://purchase.aspose.com/temporary-license/)。

---

**最後更新：** 2026-03-05  
**測試環境：** Aspose.Page for Java（最新 2026 版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}