---
date: 2026-03-08
description: 學習如何使用 Aspose.Page for Java 在 EPS 檔案中加入 XMP 命名空間 ─ 一步一步的 XMP 與 XMP 命名空間添加教學
  Java 指南。
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: 使用 Aspose.Page 在 EPS 檔案中新增 XMP 命名空間 – Java 教學
url: /zh-hant/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

-03-08  
**Tested With:** Aspose.Page for Java 24.10 (latest)  
**Author:** Aspose  

Translate labels but keep dates unchanged.

**最後更新：** 2026-03-08  
**測試環境：** Aspose.Page for Java 24.10（最新）  
**作者：** Aspose  

Now close shortcodes.

We must keep the shortcodes exactly.

Thus final output includes all content with translations.

Make sure to keep markdown formatting, tables, etc.

Let's construct final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page – Java 在 EPS 檔案中新增 XMP 命名空間 教學

如果您需要修改或豐富 EPS 檔案的中繼資料，這篇 **how to add xmp** 教學將會完整示範如何使用 Java 及 Aspose.Page 新增 XMP 命名空間。完成本指南後，您將擁有一套可重複使用的模式，將自訂中繼資料注入任何 EPS 文件。

## 快速解答
- **主要目標是什麼？** 在 EPS 檔案中新增自訂的 XMP 命名空間與屬性。  
- **需要哪個函式庫？** Aspose.Page for Java。  
- **測試需要授權嗎？** 免費試用版可用於開發；正式上線則需商業授權。  
- **需要多少段程式碼變更？** 只需五段簡短程式碼片段——每一步各一段。  
- **此模式可否用於其他命名空間？** 可以，只需在 `registerNamespaceURI` 呼叫中更改前綴與 URI。  

## 什麼是 XMP 命名空間？

XMP（Extensible Metadata Platform）命名空間是一個唯一的識別碼，用於將相關的中繼資料屬性依據共同的 URI 分組。註冊命名空間可讓您儲存自訂資料（例如專有標籤），而不會與現有標準衝突。

## 為何使用 Aspose.Page 進行 XMP 操作？

- **完整控制** EPS 與 PDF 中繼資料，無需 Adobe 工具。  
- **自動建立** XMP 區塊（若不存在），根據 PS 註解產生。  
- **跨平台 Java 支援**，讓您輕鬆整合至現有工作流程。  

## 前置條件

- Aspose.Page for Java：確保已安裝此函式庫。您可於 [here](https://releases.aspose.com/page/java/) 下載。  
- Java 開發環境：在您的系統上設定 Java 環境。  
- 文件檔案：準備一個含有 XMP 中繼資料的 EPS 檔案。若檔案未包含 XMP 中繼資料，函式庫會根據 PS 註解自動建立。  

## 匯入套件

要開始，請在 Java 專案中匯入必要的套件：

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

### 為何重要
取得 `XmpMetadata` 物件可讓您即時操作文件的中繼資料，從而在儲存前讀取、修改或擴充它。

## 步驟 2：註冊新命名空間 *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### 說明
`registerNamespaceURI` 方法將短前綴（`tmp`）映射至完整的 URI。此步驟對於後續操作至關重要，因為 XMP 屬性必須以已註冊的命名空間作為限定。

## 步驟 3：新增屬性

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### 發生了什麼？
此處我們建立名為 `tmp:newKey` 的自訂屬性，並賦予值 `"NewValue"`。您可以依業務需求自行替換鍵名與值。

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
請務必將 `save` 呼叫包在 `try/finally` 區塊（或使用 try‑with‑resources），以確保即使發生例外，輸出串流亦能正確關閉。

## 步驟 5：關閉串流

```java
// Close input EPS stream
psStream.close();
```

### 最佳實踐
關閉輸入串流可即時釋放檔案句柄，避免在 Windows 系統上出現檔案鎖定問題。

## 常見問題與解決方案

| 問題 | 可能原因 | 解決方法 |
|------|----------|----------|
| 儲存後未出現 XMP 區塊 | 原始 EPS 未包含 XMP，且註解不足 | 確保 EPS 包含標準 PS 註解（`%%Creator`、`%%Title` 等），或在註冊命名空間前手動建立空的 `XmpMetadata` 物件。 |
| `registerNamespaceURI` 拋出例外 | 前綴已被使用 | 選擇唯一的前綴，或透過 `xmp.getRegisteredNamespaces()` 檢查現有命名空間。 |
| 儲存的檔案損壞 | 輸出串流未刷新 | 使用 `try‑with‑resources`，或在關閉前明確呼叫 `outPsStream.flush()`。 |

## 結論

透過遵循此 **how to add xmp** 教學，您現在已掌握在 EPS 檔案中使用 Aspose.Page for Java 新增自訂命名空間與屬性的可重複方法。此功能為更豐富的中繼資料策略開啟大門——無論是嵌入工作流程識別碼、專有標籤，或是為下游系統提供整合資料。

## 常見問答

### 我可以在其他程式語言中使用 Aspose.Page for Java 嗎？
Aspose.Page 主要支援 Java，但亦提供 .NET 等其他語言的版本。

### 是否提供免費試用？
是的，您可於 [here](https://releases.aspose.com/) 取得免費試用。

### 在哪裡可以找到完整的文件說明？
請參考文件說明 [here](https://reference.aspose.com/page/java/)。

### 如何取得臨時授權？
您可於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### 是否有 Aspose.Page 的社群論壇？
是的，您可在 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 與社群互動。

---

**最後更新：** 2026-03-08  
**測試環境：** Aspose.Page for Java 24.10（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}