---
date: 2026-05-15
description: 學習如何使用 Aspose.Page for Java 編輯 XMP 元資料，以及如何在 EPS 檔案中更改 XMP 值 – 清晰的逐步指南。
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: 使用 Java 更改 XMP 中的命名值
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何編輯 XMP – 使用 Java 更改 XMP 中的命名值
url: /zh-hant/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何編輯 XMP – 使用 Java 更改 XMP 中的命名值

## 快速解答
- **本教程涵蓋什麼？** 使用 Aspose.Page for Java 在 EPS 檔案中更改命名的 XMP 值。  
- **需要哪個版本的程式庫？** 任意近期的 Aspose.Page for Java 版本（API 已穩定多年）。  
- **需要授權嗎？** 生產環境需要臨時或正式授權；測試可使用免費試用版。  
- **實作需要多長時間？** 對熟悉 Java I/O 的開發者大約 10‑15 分鐘。  
- **可以在其他檔案格式使用嗎？** XMP API 亦支援 PDF、SVG 以及 Aspose.Page 支援的其他格式。

## 什麼是 XMP 中繼資料？
XMP（可擴充中繼資料平台）是一種標準化的 XML 為基礎格式，用於將豐富的中繼資料（例如創作者、標題和自訂屬性）直接嵌入檔案內。於 EPS 文件中，XMP 與傳統的 PostScript 註解共存，使應用程式能在不改變視覺內容的情況下讀取與修改中繼資料。

## 為何使用 Aspose.Page for Java 編輯 XMP？
Aspose.Page 為您提供 **超過 150 個 XMP 結構屬性的完整控制**，且在 EPS、PDF 與 SVG 格式間表現一致。它可處理高達 **500 MB** 的檔案而無需將整個文件載入記憶體，並內建驗證機制，確保產生的 EPS 符合標準。無需外部 XML 解析器或原生程式庫。

## 介紹
Aspose.Page for Java 是一套功能強大的程式庫，可協助操作與處理 EPS 檔案。針對這些檔案中的 XMP 中繼資料，Aspose.Page 為開發者提供完整的功能集合。本教程將重點說明如何更改 XMP 中的命名值，為希望提升文件處理能力的開發者提供清晰簡潔的指引。

## 前置條件
1. **Java 開發環境** – JDK（8 版或以上）以及 IDE 或建置工具（Maven/Gradle）。  
2. **Aspose.Page for Java 程式庫** – 下載並將 Aspose.Page for Java 程式庫整合至您的專案。您可於 [此處](https://reference.aspose.com/page/java/) 找到程式庫與詳細文件。  
3. **範例 EPS 檔案** – 準備一個 EPS 範例檔供實驗使用。若沒有，可使用提供的範例檔案 **「xmp4.eps」**。

## 匯入套件
`import` 陳述式將必要的 Aspose.Page 類別匯入作用域。

`PsDocument` 類別是 Aspose.Page 的核心物件，代表記憶體中的 EPS 文件。

`XmpMetadata` 類別提供對嵌入於 EPS 檔案中的 XMP 封包的存取。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 如何編輯 XMP 中繼資料？
載入 EPS 檔案、取得其 XMP 封包、修改目標屬性，然後儲存文件——全部只需幾行簡潔程式碼。此方法適用於任何命名的 XMP 值，無論是標準的 Dublin Core 欄位或是自訂的命名空間。

## 步驟 1：初始化輸入 EPS 檔案串流
`FileInputStream` 以唯讀模式開啟來源 EPS 檔案的串流，使 Aspose.Page 能在不鎖定檔案系統的情況下讀取文件。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## 步驟 2：初始化 PsDocument
`PsDocument` 是封裝 EPS 內容的主要物件，並提供對其中中繼資料、頁面與資源的存取。

```java
PsDocument document = new PsDocument(psStream);
```

## 步驟 3：取得 XMP 中繼資料
`XmpMetadata` 代表 EPS 檔案內的 XMP 封包，提供讀取、修改或刪除單一屬性的相關方法。

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 步驟 4：在 XMP 中設定新值
`setProperty` 用於在中繼資料封包中設定指定 XMP 屬性的值。

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## 步驟 5：初始化輸出 EPS 檔案串流
`FileOutputStream` 建立可寫入的串流，用於儲存已修改的 EPS 檔案。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## 步驟 6：以變更的 XMP 中繼資料儲存文件
`save` 將記憶體中的 PsDocument（含已更新的 XMP）寫入輸出串流。

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 步驟 7：關閉輸入 EPS 串流
`close` 釋放檔案句柄並釋放與輸入串流相關的資源。

```java
// Close input EPS stream
psStream.close();
```

## 常見問題與解決方案
- **FileNotFoundException** – 請確認 `dataDir` 指向正確的資料夾，且 `xmp4.eps` 確實存在。  
- **LicenseException** – 若出現授權錯誤，請確保在建立 `PsDocument` 前已載入有效的 Aspose.Page 授權檔案。  
- **Metadata Not Updated** – 儲存後，使用中繼資料檢視器（例如 Adobe Bridge）開啟產生的 EPS，確認新值已出現。

## 常見問答
**Q: 我可以在其他程式語言中使用 Aspose.Page for Java 嗎？**  
A: Aspose.Page 主要支援 Java，但 Aspose 亦提供 .NET、C++ 與 Python 等等等效程式庫，具備相似的 XMP 操作功能。

**Q: 是否提供 Aspose.Page for Java 的免費試用？**  
A: 有的，您可於 [此處](https://releases.aspose.com/) 取得 Aspose.Page for Java 的免費試用版。

**Q: 我可以在哪裡找到關於 Aspose.Page for Java 的其他支援與討論？**  
A: 前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得社群支援與討論。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 您可於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 在哪裡可以購買 Aspose.Page for Java？**  
A: 前往 [購買頁面](https://purchase.aspose.com/buy) 取得 Aspose.Page for Java。

---

**最後更新：** 2026-05-15  
**測試環境：** Aspose.Page for Java（最新版本）  
**作者：** Aspose

## 相關教程

- [如何使用 Java 讀取 XMP 中繼資料 – Aspose.Page 指南](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java 教程 – 為 EPS 檔案新增 XMP 中繼資料](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – 使用 Java 更改 XMP 中的值](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}