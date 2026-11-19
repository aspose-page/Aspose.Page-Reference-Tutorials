---
date: 2026-11-19
description: 學習如何在 Java 中建立 PostScript 檔案、設定 A4 頁面大小，並使用 Aspose.Page 添加自訂字型。立即免費試用！
keywords:
- create postscript file java
- add custom fonts java
- set a4 page size java
- aspose.page java
- postscript generation java
lastmod: 2026-11-19
linktitle: 在 Java 中使用 PostScript 建立文件
og_description: 學習如何在 Java 中建立 PostScript 檔案、設定 A4 頁面大小，並使用 Aspose.Page 添加自訂字型。開發人員快速入門指南。
og_image_alt: Screenshot of Java code generating an A4 PostScript file with custom
  fonts using Aspose.Page
og_title: 使用 Aspose.Page 在 Java 中建立 A4 大小的 PostScript 檔案
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size
  steps:
  - name: set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` defines how the PostScript document is saved, including
      page size, margins, and compression. **Definition:** `PsPageSize` is an enumeration
      that contains standard page‑size constants such as A4, Letter, and Legal. Setting
      `options.setPageSize(PsPageSize.A4)` configures the document f'
  - name: set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: create a multipaged or single‑paged PS document
    text: '`PsDocument` represents a PostScript document that can contain one or many
      pages. Instantiating it with `new PsDocument(outputStream, options)` creates
      the document object. Set `multiPaged` to `true` for multi‑page output, then
      call `document.newPage()` for each additional page you need.'
  - name: close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create postscript
- Aspose.Page
- Java document processing
- custom fonts
- A4 page size
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size using Aspose.Page
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size using Aspose.Page
  steps:
  - name: Set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create save options with A4 size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a multipaged or single‑paged PS document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
title: 如何在 Java 中使用 A4 大小建立 PostScript 檔案
url: /zh-hant/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 A4 大小建立 PostScript 檔案

## 簡介
如果您需要在設定標準 A4 頁面尺寸的同時 **create PostScript file Java**，Aspose.Page for Java 為您提供簡潔且高效能的 API，抽象化低階的 PostScript 語法。在本教學中，我們將逐步說明——從載入函式庫與設定 `PsSaveOptions` 到嵌入您自己的 TrueType 或 OpenType 字型。完成後，您將擁有一段可直接放入任何 Java 專案的即用程式碼片段。

## 快速回答
- **哪個函式庫可以在 Java 中產生 PostScript？** Aspose.Page for Java.  
- **本指南的目標頁面尺寸是什麼？** A4 (210 mm × 297 mm).  
- **我可以嵌入自己的字型嗎？** Yes – set the additional fonts folder in the save options.  
- **生產環境需要授權嗎？** A commercial license is required; a free trial is available.  
- **支援哪些 Java 版本？** Java 8, 11, and 17 are fully supported.

## 如何在 Java 中設定 A4 頁面大小並建立 PostScript？
載入 Aspose.Page 函式庫，使用 A4 常數設定 `PsSaveOptions`，並將文件寫入檔案——全部程式碼不超過十行。此方法確保正確的頁面尺寸，且可在不需額外設定的情況下加入自訂字型。

## 什麼是 PostScript A4 大小？
PostScript A4 大小是以 PostScript 頁面描述語言表示的 ISO 216 標準（210 mm × 297 mm）。它定義了印表機與檢視器所解讀的可列印區域，確保跨平台版面配置的一致性。由於 PostScript 以與裝置無關的方式描述頁面內容，使用 A4 大小可保證文件在全球任何支援 A4 的印表機或檢視器上呈現相同。

## 為什麼使用 Aspose.Page 來設定 PostScript 頁面大小？
Aspose.Page 支援超過 30 種 PostScript 運算子，且可在不將整個文件載入記憶體的情況下產生高達 500 MB 的檔案。它能在 2 秒內處理 200 頁的文件，提供對頁面尺寸的精確控制，同時有效處理大量工作負載。此函式庫亦抽象化複雜的 PostScript 語法，並自動管理資源，讓它既適用於簡單的傳單，也適用於複雜的多頁報告。

## 如何在 Java 中加入自訂字型
嵌入您自己的字型可確保產生的文件在任何印表機或檢視器上皆呈現與設計完全相同的外觀，且 Aspose.Page 會自動偵測放置於指定資料夾中的字型。透過註冊額外的字型資料夾，您可以使用任何 TrueType 或 OpenType 字型，避免備用字型的替換，並在所有輸出裝置上維持品牌一致性。

## 先決條件
在開始之前，請確保您已具備：

- 具備 Java 程式設計的基礎知識。  
- 已安裝 Aspose.Page for Java。您可以下載它 [Aspose.Page Java 下載頁面](https://releases.aspose.com/page/java/)。  
- 一個名為 `necessary_fonts`（或您自行命名）的資料夾，內含您想嵌入的任何自訂字型。

## 匯入套件
在您的 Java 專案中，匯入所需的 Aspose.Page 類別：

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

現在讓我們將範例分解為清晰的編號步驟。

### 步驟 1：設定文件目錄
`OUTPUT_DIR` 常數告訴函式庫要將產生的檔案寫入哪個位置。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### 步驟 2：定義字型資料夾
`FONTS_FOLDER` 指向存放您自訂 TrueType 或 OpenType 字型的目錄。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步驟 3：為 PostScript 文件建立輸出串流
`FileOutputStream` 開啟一個串流，用於接收最終的 PostScript A4 輸出。

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### 步驟 4：建立具有 A4 大小的儲存選項
`PsSaveOptions` 定義了 PostScript 文件的儲存方式，包括頁面大小、邊距與壓縮。  
**定義：** `PsPageSize` 是一個列舉，包含標準頁面大小常數，如 A4、Letter 與 Legal。  
設定 `options.setPageSize(PsPageSize.A4)` 會將文件配置為標準的 A4 尺寸。

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### 步驟 5：設定頁面邊距並加入自訂字型資料夾
`options.setMargins(0, 0, 0, 0)` 會移除所有邊距以獲得全幅頁面，`options.setAdditionalFontsFolder(FONTS_FOLDER)` 則註冊您的自訂字型。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### 步驟 6：建立多頁或單頁的 PS 文件
`PsDocument` 代表一個可以包含一頁或多頁的 PostScript 文件。使用 `new PsDocument(outputStream, options)` 來實例化它，即可建立文件物件。將 `multiPaged` 設為 `true` 以產生多頁輸出，然後對每個需要的額外頁面呼叫 `document.newPage()`。

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### 步驟 7：關閉當前頁面並儲存文件
呼叫 `document.close()` 會完成檔案並將 **PostScript A4 大小** 的輸出寫入磁碟。

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## 常見問題與技巧
- **字型未顯示？** 請確認字型檔案為支援的 TrueType 或 OpenType 格式，且 `FONTS_FOLDER` 以斜線 (`/`) 結尾。  
- **邊距仍然顯示？** 在建立 `PsDocument` **之前** 呼叫 `options.setMargins(...)`。  
- **多頁輸出顯示空白？** 請記得對每個需要的額外頁面呼叫 `document.newPage()`。  
- **大型檔案導致記憶體不足錯誤？** Aspose.Page 以串流方式處理資料，因此您可以安全產生高達 500 MB 的檔案；只需確保 JVM 堆積至少 1 GB，以應付非常大的工作負載。

## 常見問與答

**Q: 我可以在我的 PostScript 文件中使用自訂字型嗎？**  
A: 可以，請在儲存選項中設定額外的字型資料夾（參見步驟 5），Aspose.Page 會自動嵌入字型。

**Q: 是否提供 Aspose.Page for Java 的試用版？**  
A: 有，您可以取得免費試用 [Aspose.Page 免費試用頁面](https://releases.aspose.com/)。

**Q: 我該如何取得完整的 API 參考文件？**  
A: 請參考文件 [API 參考文件](https://reference.aspose.com/page/java/)。

**Q: 我該從哪裡購買 Aspose.Page for Java 的授權？**  
A: 您可以在 [授權購買頁面](https://purchase.aspose.com/buy) 購買授權。

**Q: 我可以在哪裡向社群尋求協助？**  
A: 前往 Aspose.Page 社群論壇 [Aspose.Page 社群論壇](https://forum.aspose.com/c/page/39)。

**Q: 我可以產生多頁的 PostScript 檔案嗎？**  
A: 當然可以——在第 6 步將 `multiPaged` 設為 `true`，並對每個額外頁面呼叫 `document.newPage()`。

## 結論
透過遵循上述步驟，您現在已了解 **how to create PostScript file Java** 並使用 Aspose.Page 設定 **A4 page size**，同時能夠 **add custom fonts java** 並控制頁面大小選項。Aspose.Page 會處理繁重的工作，讓您專注於文件內容，而不必關注 PostScript 語言的細節。

---

**最後更新日期:** 2026-11-19  
**測試環境:** Aspose.Page for Java 24.11  
**作者:** Aspose  

## 相關教學

- [Aspose.Page Java 教學 – 在 PostScript 中設定自訂頁面大小並新增頁面](/page/java/postscript-page-manipulation/add-pages2/)
- [如何在 PostScript 中使用 Aspose.Page for Java 新增文字](/page/java/postscript-text-manipulation/)
- [Aspose Page Java 教學 - 將 PostScript 轉換為 PDF](/page/java/postscript-conversion/to-pdf/)

```java
document.closePage();
document.save();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}