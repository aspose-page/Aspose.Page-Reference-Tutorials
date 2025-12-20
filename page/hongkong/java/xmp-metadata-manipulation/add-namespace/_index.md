---
date: 2025-12-20
description: 在本全面的 aspose.page XMP 教程中，學習如何使用 Aspose.Page for Java 為 EPS 檔案添加 XMP
  命名空間。
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page XMP 教學 – 使用 Java 在 XMP 中添加命名空間
url: /zh-hant/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp 教學 – 使用 Java 在 XMP 中新增 Namespace

## 介紹

如果您需要修改或豐富 EPS 檔案的中繼資料，**aspose.page xmp 教學** 會向您展示 **如何使用 Java 新增 XMP namespace**。本指南將逐步說明——從載入 EPS 文件、註冊自訂 namespace、插入新屬性，到最後儲存更新後的檔案。完成後，您將掌握一套可在任何 Aspose.Page‑支援的 Java 專案中重複使用的 XMP 中繼資料操作模式。

## 快速回答
- **主要目標是什麼？** 為 EPS 檔案新增自訂 XMP namespace 與屬性。  
- **需要哪個函式庫？** Aspose.Page for Java。  
- **測試需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **需要多少段程式碼變更？** 只需五段簡短程式碼——每個步驟各一段。  
- **此模式能否套用到其他 namespace？** 可以，只要在 `registerNamespaceURI` 呼叫中更改前綴與 URI 即可。

## 什麼是 XMP Namespace？

XMP（Extensible Metadata Platform）namespace 是一個唯一的識別碼，用於將相關的中繼資料屬性以共同的 URI 分組。註冊 namespace 後，您即可儲存自訂資料（例如專屬標籤），而不會與既有標準衝突。

## 為什麼使用 Aspose.Page 進行 XMP 操作？

- **完整控制** EPS 與 PDF 中繼資料，無需 Adobe 工具。  
- **自動建立** XMP 區塊（若原檔案不存在），根據 PS 註解生成。  
- **跨平台 Java 支援**，方便整合至現有工作流程。

## 前置條件

- Aspose.Page for Java：請確保已安裝此函式庫。您可以在[此處](https://releases.aspose.com/page/java/)下載。  
- Java 開發環境：在您的系統上設定好 Java 開發環境。  
- 文件檔案：準備一個含有 XMP 中繼資料的 EPS 檔案。若檔案未包含 XMP 中繼資料，函式庫會根據 PS 註解自動建立。

## 匯入套件

開始之前，先將必要的套件匯入您的 Java 專案：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 步驟 1：取得 XMP 中繼資料

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### 為什麼這很重要
取得 `XmpMetadata` 物件後，您即可即時操作文件的中繼資料，進行讀取、修改或擴充，然後再儲存。

## 步驟 2：註冊新 Namespace *(如何新增 xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### 說明
`registerNamespaceURI` 方法會將簡短前綴（`tmp`）對應到完整的 URI。此步驟對於後續操作至關重要，因為 XMP 屬性必須以已註冊的 namespace 為前綴。

## 步驟 3：新增屬性

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### 發生了什麼？
此處我們建立一個名為 `tmp:newKey` 的自訂屬性，並賦予值 `"NewValue"`。您可以依需求自行更換鍵名與值。

## 步驟 4：儲存文件

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### 小技巧
務必將 `save` 呼叫包在 `try/finally` 區塊（或使用 try‑with‑resources）中，以確保即使發生例外，輸出串流也能正確關閉。

## 步驟 5：關閉串流

```java
// Close input EPS stream
psStream.close();
```

### 最佳實踐
關閉輸入串流可即時釋放檔案句柄，避免 Windows 系統出現檔案鎖定問題。

## 常見問題與解決方案

| 問題 | 可能原因 | 解決方式 |
|------|----------|----------|
| 儲存後未出現 XMP 區塊 | 原始 EPS 未含 XMP，且註解不足 | 確認 EPS 包含標準 PS 註解（`%%Creator`、`%%Title` 等），或在註冊 namespace 前手動建立空的 `XmpMetadata` 物件。 |
| `registerNamespaceURI` 拋出例外 | 前綴已被使用 | 改用唯一的前綴，或透過 `xmp.getRegisteredNamespaces()` 檢查現有 namespace。 |
| 儲存的檔案損毀 | 輸出串流未刷新 | 使用 try‑with‑resources，或在關閉前明確呼叫 `outPsStream.flush()`。 |

## 結論

透過本 **aspose.page xmp 教學**，您現在掌握了一套可重複使用的方式，能在 EPS 檔案中使用 Aspose.Page for Java 新增自訂 namespace 與屬性。此功能為更豐富的中繼資料策略鋪路——無論是嵌入工作流程識別碼、專屬標籤，或是供下游系統使用的整合資料。

## 常見問答

### 我可以在其他程式語言中使用 Aspose.Page for Java 嗎？
Aspose.Page 主要支援 Java，但亦提供 .NET 等其他語言的版本。

### 有免費試用版嗎？
有，您可以在[此處](https://releases.aspose.com/)取得免費試用。

### 哪裡可以找到完整文件？
請參考[此處](https://reference.aspose.com/page/java/)的文件說明。

### 如何取得臨時授權？
您可以在[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

### 有 Aspose.Page 的社群論壇嗎？
有，您可以前往[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)與社群交流。

---

**最後更新：** 2025-12-20  
**測試環境：** Aspose.Page for Java 23.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}