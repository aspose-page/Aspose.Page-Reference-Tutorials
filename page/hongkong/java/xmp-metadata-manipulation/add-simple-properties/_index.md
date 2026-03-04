---
date: 2025-12-20
description: 學習如何使用 Aspose.Page for Java 在 EPS 檔案中建立 XMP 中繼資料。逐步指南，透過程式碼加入簡單的 XMP
  屬性。
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: 如何使用 Java 建立 XMP 元資料 EPS
url: /zh-hant/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP 中新增簡單屬性

## 介紹
在現代文件工作流程中，能夠以程式方式 **create XMP metadata EPS** 檔案，可讓您完整掌控圖形的描述、搜尋與保存方式。使用 Aspose.Page for Java，您可以在不離開 Java 生態系統的情況下讀取、修改與寫入 EPS 文件內的 XMP 封包。本教學將逐步說明如何在 EPS 檔案中加入簡單的 XMP 屬性，讓您快速且可靠地為圖形添加自訂中繼資料。

## 快速解答
- **「create xmp metadata eps」是什麼意思？** 在 EPS 檔案中加入 XMP 封包（基於 XML 的中繼資料）。  
- **需要哪個函式庫？** Aspose.Page for Java（可從 Aspose 官方網站下載）。  
- **測試時需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **程式碼行數多少？** 少於 30 行 Java 程式碼，加上少量 import 陳述式。  
- **可以加入其他資料類型嗎？** 可以——支援日期、整數、雙精度、字串，甚至陣列。

## 什麼是 create xmp metadata eps？
XMP（Extensible Metadata Platform）是一種在檔案內嵌入豐富中繼資料的標準。當您 **create XMP metadata EPS** 時，即是將 XML 封包嵌入 EPS（Encapsulated PostScript）文件中，讓後續應用程式能讀取作者、建立日期、自訂標籤等資訊。

## 為什麼要在 EPS 檔案中加入 XMP 中繼資料？
- **可搜尋性：** 讓 DAM 系統自動索引。  
- **合規性：** 將法律或授權資訊直接存於檔案內。  
- **自動化：** 後續流程可根據嵌入的資料做決策。  
- **可攜性：** 中繼資料隨 EPS 一起傳遞，確保跨平台一致性。

## 前置條件
在開始之前，請確保您已具備：

- 基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page for Java 函式庫。您可以在 **[此處](https://releases.aspose.com/page/java/)** 下載。  
- 一個包含中繼資料的範例 EPS 檔案。若沒有，可使用提供的 **`xmp3.eps`** 檔案。

## 匯入套件
首先匯入所需的類別。匯入語句與原範例完全相同：

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

## 步驟 1：載入 EPS 文件並取得 XMP 中繼資料
我們開啟 EPS 檔案，建立 `PsDocument` 實例，並取得（或建立）XMP 封包。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 步驟 2：新增日期屬性
新增日期非常簡單，只需建立 `Date` 物件並放入 XMP 地圖中。

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## 步驟 3：新增整數屬性
您可以使用整數值儲存編號或版本號等資訊。

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## 步驟 4：新增雙精度屬性
浮點數適用於測量值或評分等情境。

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## 步驟 5：新增字串屬性
自訂文字標籤（例如專案代碼）以字串形式儲存。

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## 步驟 6：儲存更新後的 EPS 檔案
所有屬性加入完成後，將文件寫回磁碟。

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

## 步驟 7：清理資源
務必關閉輸入串流，以避免檔案句柄洩漏。

```java
// Close input EPS stream
psStream.close();
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **Null XMP metadata** | EPS 檔案未包含 XMP 封包，且函式庫無法推斷 PS 註解。 | 確認來源 EPS 至少包含一個 PS 註解（例如 `%%Creator`），函式庫會自動產生最小的 XMP 封包。 |
| **Time zone mismatch** | 日期在其他應用程式開啟時出現時區偏移。 | 如步驟 2 所示，在建立 `Date` 物件前先執行 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`。 |
| **License exception** | 執行時拋出 `LicenseException`。 | 在使用 API 前套用有效的 Aspose.Page 授權，或以試用模式執行以進行評估。 |

## 結論
依照上述步驟，您現在已掌握如何使用 Aspose.Page for Java **create XMP metadata EPS** 檔案。新增日期、整數、雙精度與字串等簡單屬性相當直接，且產生的 EPS 檔案會帶有豐富且可搜尋的中繼資料，對任何後續工作流程皆有助益。

## 常見問答
### 我可以在其他程式語言中使用 Aspose.Page for Java 嗎？
Aspose.Page 主要支援 Java，但也提供 .NET 等其他語言的版本。

### Aspose.Page for Java 有提供免費試用嗎？
有，您可以在 [此處](https://releases.aspose.com/) 取得免費試用。

### 我在哪裡可以找到 Aspose.Page for Java 的詳細文件？
文件可於 [此處](https://reference.aspose.com/page/java/) 取得。

### 我該如何取得 Aspose.Page for Java 的臨時授權？
臨時授權可在 [此處](https://purchase.aspose.com/temporary-license/) 申請。

### 我該從哪裡購買 Aspose.Page for Java？
您可以在 [此處](https://purchase.aspose.com/buy) 購買此產品。

**最後更新：** 2025-12-20  
**測試環境：** Aspose.Page for Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}