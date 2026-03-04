---
date: 2025-12-21
description: 學習如何使用 Java 透過 Aspose.Page 修改 EPS 文件中的 XMP。使用 Aspose.Page for Java 快速增強元資料。
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page 修改 XMP – 使用 Java 更改 XMP 中的值
url: /zh-hant/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 更改 XMP 值

## 介紹
如果您需要在 EPS 檔案中 **aspose.page modify xmp** 資料，您來對地方了。在本教學中，我們將逐步說明如何使用 Aspose.Page for Java 套件讀取、更新並儲存 XMP（可擴充元資料平台）值。完成後，您即可依專案需求自訂文件的中繼資料，例如建立者、標題與修改日期。

## 快速解答
- **「aspose.page modify xmp」的功能是什麼？** 它讓您透過 Aspose.Page Java API 讀寫 EPS 檔案中的 XMP 中繼資料。  
- **需要哪個版本的程式庫？** 任意近期的 Aspose.Page for Java 版本皆可（API 在各版本間保持穩定）。  
- **執行範例是否需要授權？** 可使用免費試用版進行評估；正式上線則需商業授權。  
- **能一次變更多個 XMP 欄位嗎？** 可以——在儲存文件前，對每個欄位呼叫 `put` 即可。  
- **需要處理時區嗎？** 設定預設時區（例如 UTC）可確保日期值的一致性。

## 什麼是 XMP 以及為何要修改它？
XMP（可擴充元資料平台）是一種標準化的方式，可將豐富的中繼資料直接嵌入 EPS、PDF 及影像等檔案中。更新 XMP 可讓您掌控文件的索引、顯示與搜尋方式，對於品牌形象、合規性以及工作流程自動化皆相當重要。

## 為何使用 Aspose.Page for Java？
- **完整功能的 API** – 無需外部工具，所有操作皆在程式內部完成。  
- **跨平台** – 可在任何支援 Java 的作業系統上執行。  
- **無原生相依性** – 純 Java 實作簡化部署。  
- **強韌支援** – 能處理既有的 XMP 區塊，若缺少則可從 PS 註解自動建立新區塊。

## 前置條件
在開始本教學之前，請先確認已具備以下前置條件：

1. **Java 開發環境** – JDK（8 版或以上）以及您選擇的 IDE 或建置工具。  
2. **Aspose.Page for Java 程式庫** – 下載並安裝 Aspose.Page for Java 程式庫。您可於 [此處](https://releases.aspose.com/page/java/) 取得所需套件。

## 匯入套件
首先在您的 Java 專案中匯入所需的套件。這些套件對於與 EPS 文件互動與操作至關重要。

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

## 步驟 1：取得 XMP 中繼資料
從 EPS 文件中取得 XMP 中繼資料。若 EPS 檔案未包含 XMP 中繼資料，系統會根據 PS 中的中繼資料註解（如 %%Creator、%%CreateDate、%%Title）建立新的 XMP。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## 步驟 2：變更「ModifyDate」值
修改 XMP 中的「ModifyDate」值，以符合所需的日期。

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## 步驟 3：變更「Creator」值
更新 XMP 中的「Creator」值，以指定文件的建立者。

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## 步驟 4：變更「Title」值
修改 XMP 中的「Title」值，為文件設定適當的標題。

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## 步驟 5：以變更後的 XMP 中繼資料儲存文件
將更新後的 XMP 中繼資料儲存至新的 EPS 檔案中。

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
- **缺少 XMP 區塊** – API 會自動從 PS 註解建立區塊，必要時亦可手動實例化 `XmpMetadata`。  
- **時區不匹配** – 在建立 `Date` 物件前，務必先呼叫 `TimeZone.setDefault` 以避免意外的時差。  
- **檔案存取錯誤** – 確認輸入與輸出路徑正確，且應用程式具備讀寫權限。

## 常見問答

**Q: 如何在修改 XMP 值時處理時區問題？**  
A: 使用 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` 以確保時區設定的一致性。

**Q: 能在一次操作中變更多個 XMP 值嗎？**  
A: 可以，對每個欲變更的值使用 `put` 方法，即可同時修改多個 XMP 值。

**Q: 在哪裡可以找到 Aspose.Page for Java 的其他文件說明？**  
A: 請前往完整文件說明 [此處](https://reference.aspose.com/page/java/)。

**Q: 是否提供 Aspose.Page for Java 的免費試用？**  
A: 有，您可在 [此處](https://releases.aspose.com/) 取得免費試用。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 可於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 修改 XMP 會影響 EPS 的視覺內容嗎？**  
A: 不會。XMP 變更僅屬於中繼資料，並不會改變 EPS 檔案的圖形元素。

**Q: 我能以程式方式讀回更新後的值以驗證變更嗎？**  
A: 當然可以——在儲存且關閉文件前，直接呼叫 `xmp.get("dc:creator")`（或相應的鍵）即可。

## 結論
恭喜！您已成功使用 Aspose.Page for Java 完成在 EPS 文件中 **aspose.page modify xmp** 的流程。本教學讓您掌握修改中繼資料的技巧，確保文件能無縫符合您的特定需求。

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.Page for Java（最新版本）  
**作者：** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
