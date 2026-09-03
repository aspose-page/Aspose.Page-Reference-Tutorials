---
date: 2026-05-25
description: 了解如何使用 Aspose.Page 及 Java 在 EPS 文件中修改 XMP。快速且可靠地更新元資料。
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: 使用 Java 更改 XMP 值
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page 修改 XMP – 使用 Java 更改 XMP 值
url: /zh-hant/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 更改 XMP 值

## 介紹
如果您正在尋找 **如何修改 xmp** 於 EPS 檔案中的方法，恭喜您來對地方了。本教學將逐步說明——讀取現有的 XMP 區塊、更新如 creator、title 與 modify date 等欄位，最後將變更寫回 EPS 文件。完成後，您將擁有一段可重複使用的程式碼，能嵌入任何自動化工作流程，確保檔案攜帶正確的中繼資料以符合品牌、合規或搜尋引擎索引需求。

## 快速解答
- **「aspose.page modify xmp」是什麼功能？** 它讓您透過 Aspose.Page Java API 讀寫 EPS 檔案中的 XMP 中繼資料。  
- **需要哪個版本的函式庫？** 任意近期的 Aspose.Page for Java 版本（API 在各版本間保持穩定）。  
- **執行範例是否需要授權？** 免費試用可用於評估；正式環境需購買商業授權。  
- **可以一次變更多個 XMP 欄位嗎？** 可以——在儲存文件前對每個欄位呼叫 `put` 即可。  
- **需要處理時區嗎？** 設定預設時區（例如 UTC）可確保日期值的一致性。

## 什麼是 XMP 以及為何要修改它？
XMP（Extensible Metadata Platform）是一種基於 XML 的標準格式，用於直接嵌入 EPS、PDF 以及影像等檔案內的豐富中繼資料。更新 XMP 可控制文件的索引、顯示與搜尋方式——對於品牌一致性、法規遵循以及自動化內容管線皆相當重要。

## 為什麼使用 Aspose.Page for Java？
Aspose.Page 提供 **完整功能、純 Java API**，免除外部工具或原生函式庫的需求。它支援 **50 多種輸入與輸出格式**，且可在不將整個文件載入記憶體的情況下處理高達 **500 MB** 的 EPS 檔案，為任何執行 Java 的作業系統提供快速、低記憶體的中繼資料操作。

## 前置條件
在開始本教學前，請確保已具備以下條件：
1. **Java 開發環境** – JDK（8 版或以上）以及您慣用的 IDE 或建置工具。  
2. **Aspose.Page for Java 函式庫** – 下載並安裝 Aspose.Page for Java 函式庫。您可於 [此處](https://releases.aspose.com/page/java/) 取得所需套件。

## 匯入套件
先在您的 Java 專案中匯入必要的套件。這些套件對於與 EPS 文件互動與操作至關重要。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 如何使用 Java 修改 EPS 中的 XMP？
`Document` 是 Aspose.Page 用來表示 EPS 檔案的類別，提供存取內容與中繼資料的功能。`XmpMetadata` 代表附加於文件的 XMP 區塊，允許讀寫中繼資料欄位。`put` 用於新增或更新 `XmpMetadata` 物件中的條目。`save` 則將修改後的文件（含更新的 XMP 中繼資料）寫入檔案。

使用 `new Document("input.eps")` 載入 EPS，取得其 `XmpMetadata` 物件，透過 `put` 更新所需鍵值，最後呼叫 `save` 將變更寫回新檔案。此流程會自動處理缺少 XMP 區塊的情況，必要時會從 PostScript 註解建立，並確保日期值符合時區設定。

## 步驟 1：取得 XMP 中繼資料
`XmpMetadata` 類別代表附加於 EPS 文件的 XMP 區塊。當呼叫 `document.getXmpMetadata()` 時，API 會回傳現有區塊，或根據 PS 註解（如 `%%Creator`、`%%CreateDate`、`%%Title`）建立新區塊。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## 步驟 2：變更 "ModifyDate" 值
將 `"ModifyDate"` 條目更新為新的修改時間戳記。使用 `java.util.Date` 搭配 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` 可保證儲存的值不受時區影響。

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## 步驟 3：變更 "Creator" 值
`"Creator"` 鍵存放產生 EPS 檔案的應用程式或人員名稱。呼叫 `xmp.put("dc:creator", "Your Company Name")` 即可將現有值替換為自訂的識別字。

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## 步驟 4：變更 "Title" 值
`"Title"` 欄位會被許多資產管理系統顯示。透過 `xmp.put("dc:title", "New Document Title")` 設定，可確保文件在目錄與搜尋結果中正確呈現。

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## 步驟 5：儲存已變更 XMP 中繼資料的文件
完成所有修改後，呼叫 `document.save("output.eps")`。函式庫會將更新後的 XMP 區塊寫回 EPS 串流，同時保持原始圖形內容不變。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 常見問題與解決方案
- **Missing XMP block** – API 會自動從 PS 註解建立區塊，必要時您也可以手動實例化 `XmpMetadata`。  
- **Timezone mismatches** – 在建立 `Date` 物件前務必先設定 `TimeZone.setDefault`，以避免意外的時區偏差。  
- **File access errors** – 確認輸入與輸出路徑正確，且應用程式具備讀寫權限。

## 常見問答

**Q: 如何在修改 XMP 值時處理時區問題？**  
A: 使用 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` 以確保時區設定的一致性。

**Q: 能否在一次操作中變更多個 XMP 值？**  
A: 可以，對每個欲變更的值使用 `put` 方法，即可同時修改多個 XMP 欄位。

**Q: 在哪裡可以找到 Aspose.Page for Java 的其他文件說明？**  
A: 請前往完整文件說明 [此處](https://reference.aspose.com/page/java/)。

**Q: Aspose.Page for Java 是否提供免費試用？**  
A: 有，您可於 [此處](https://releases.aspose.com/) 取得免費試用版。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 請於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 修改 XMP 會影響 EPS 的視覺內容嗎？**  
A: 不會。XMP 變更僅屬於中繼資料，並不會改變 EPS 檔案的圖形元素。

**Q: 能否程式化讀回更新後的值以驗證變更？**  
A: 當然可以——在儲存且關閉文件前，呼叫 `xmp.get("dc:creator")`（或其他相關鍵）即可取得最新值。

## 結論
恭喜您！已掌握 **如何使用 Aspose.Page for Java 在 EPS 文件中修改 xmp** 的技巧。透過嵌入正確的 creator、title 與 modify‑date 中繼資料，確保資產可被搜尋、符合規範，且與品牌標準保持一致。歡迎將此模式整合至批次處理管線、CI/CD 步驟或任何自動化文件產生工作流程中。

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java（最新版本）  
**Author:** Aspose

## 相關教學

- [Aspose Page Java 教學 – 為 EPS 檔案新增 XMP 中繼資料](/page/java/xmp-metadata-manipulation/add-metadata/)
- [如何使用 Java 讀取 XMP 中繼資料 – Aspose.Page 指南](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - 使用 Java 變更 XMP 陣列項目](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}