---
date: 2026-05-20
description: 了解如何使用 Aspose.Page for Java 為 EPS 檔案新增 XMP 中繼資料。一步一步的指南，教您以程式方式嵌入簡單的
  XMP 屬性。
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: 使用 Java 在 XMP 中新增簡單屬性
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: 使用 Java 為 EPS 檔案新增 XMP 中繼資料
url: /zh-hant/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 為 EPS 檔案新增 XMP 中繼資料

## 介紹
在現代圖形流水線中，能夠 **新增 XMP 中繼資料** 到 EPS 檔案的程式化操作，讓您完整掌控插圖的描述、搜尋與歸檔方式。使用 Aspose.Page for Java，您可以在不離開 Java 生態系的情況下讀取、修改與寫入 EPS 文件內的 XMP 封包。在本教學中，我們將逐步說明如何為 EPS 檔案新增簡單的 XMP 屬性，讓您快速且可靠地為圖形加入自訂中繼資料。

## 快速解答
- **「add XMP metadata to EPS」是什麼意思？** 在 EPS 檔案中嵌入 XMP 封包（基於 XML 的中繼資料）。  
- **需要哪個函式庫？** Aspose.Page for Java（可從 Aspose 網站下載）。  
- **測試時需要授權嗎？** 免費試用可用於開發；正式環境需購買商業授權。  
- **程式碼行數多少？** 少於 30 行 Java 程式碼，加上少量 import 陳述式。  
- **可以加入其他資料類型嗎？** 可以——支援日期、整數、雙精度、字串，甚至陣列。

## 如何使用 Java 為 EPS 檔案新增 XMP 中繼資料？
使用 `new PsDocument("input.eps")` 載入 EPS 檔案，取得或建立其 XMP 封包，插入所需屬性，然後將文件儲存回磁碟——全部在不到十行的 Java 程式碼內完成。此方法讓您在不手動編輯 EPS 原始檔的情況下，嵌入可搜尋、符合標準的中繼資料。

## EPS 中的 XMP 中繼資料是什麼？
EPS 中的 XMP 中繼資料是一個位於 EPS 檔案內的 XML 封包，用於儲存作者、建立日期及自訂標籤等資訊。嵌入此封包可讓後續工具直接讀取並使用這些資料，無需額外的附屬檔案。

## 為什麼要為 EPS 檔案新增 XMP 中繼資料？
嵌入 XMP 中繼資料可讓 EPS 資產即時可搜尋，透過在檔案內儲存授權資訊確保合規，讓自動化流程能根據嵌入的標籤做出決策，並保證中繼資料隨圖形在所有平台上一起傳遞。Aspose.Page 可在不將整個文件載入記憶體的情況下處理高達 500 MB 的檔案，為大規模工作負載提供快速效能。

## 前置條件
在開始之前，請確保您已具備：

- 具備 Java 程式設計的基本知識。  
- 已安裝 Aspose.Page for Java 函式庫。您可於 **[here](https://releases.aspose.com/page/java/)** 下載。  
- 一個包含中繼資料的 EPS 範例檔案。若沒有，可使用提供的 **`xmp3.eps`** 檔案。

## 匯入套件
首先，匯入您需要的類別。匯入語句與原始範例完全相同：

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
`PsDocument` 類別代表 EPS 檔案，提供存取其內容與中繼資料的方法。  
`XmpMetadata` 物件保存與文件相關聯的 XMP 封包。

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
`Date` 類別代表特定的時間點，具備毫秒精度。

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## 步驟 3：新增整數屬性
`Integer` 類別將原始的 `int` 值包裝為物件。

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## 步驟 4：新增雙精度屬性
`Double` 類別將原始的 `double` 值包裝為物件。

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## 步驟 5：新增字串屬性
`String` 類別代表字元序列。

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## 步驟 6：儲存更新後的 EPS 檔案
`save` 方法將修改後的文件寫回磁碟，保留 EPS 結構。

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
務必關閉串流以避免檔案句柄洩漏，並確保所有緩衝區已刷新。

```java
// Close input EPS stream
psStream.close();
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| **Null XMP 中繼資料** | EPS 檔案沒有 XMP 封包，且函式庫無法推斷 PS 註解。 | 確保來源 EPS 至少包含一個 PS 註解（例如 `%%Creator`）。函式庫將自動產生最小的 XMP 封包。 |
| **時區不匹配** | 在其他應用程式開啟時，日期會出現偏移。 | 在建立 `Date` 物件之前，先設定 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`，如 Step 2 所示。 |
| **授權例外** | 執行時拋出 `LicenseException`。 | 在使用 API 前套用有效的 Aspose.Page 授權，或以試用模式執行以進行評估。 |

## 常見問答
**Q: 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？**  
**A:** Aspose.Page 主要支援 Java，但亦提供 .NET、C++ 與 Python 的等效函式庫。

**Q: Aspose.Page for Java 有提供免費試用嗎？**  
**A:** 有，您可透過取得免費試用 **[here](https://releases.aspose.com/)** 來體驗 Aspose.Page 的功能。

**Q: 在哪裡可以找到 Aspose.Page for Java 的詳細文件？**  
**A:** 文件可於 **[here](https://reference.aspose.com/page/java/)** 取得。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
**A:** 可於 **[here](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 在哪裡可以購買 Aspose.Page for Java？**  
**A:** 您可於 **[here](https://purchase.aspose.com/buy)** 購買此產品。

---

**最後更新：** 2026-05-20  
**測試環境：** Aspose.Page for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Java 讀取 XMP 中繼資料 – Aspose.Page 指南](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page XMP 教學 – 使用 Java 新增 XMP 命名空間](/page/java/xmp-metadata-manipulation/add-namespace/)
- [使用 Java 為 XMP 中繼資料新增陣列項目](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}