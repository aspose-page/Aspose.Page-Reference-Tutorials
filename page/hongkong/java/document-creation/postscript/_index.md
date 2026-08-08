---
date: 2026-06-20
description: 了解如何設定 A4 頁面尺寸、在 Java 中建立 PostScript 檔案，並使用 Aspose.Page 新增自訂字型。立即試用免費版！
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: 在 Java 中使用 PostScript 建立文件
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page 設定 A4 頁面尺寸並建立 PostScript
url: /zh-hant/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 設定 A4 頁面大小並建立 PostScript

## 簡介
如果您需要在 Java 中產生 PostScript 檔案時 **set a4 page size**，Aspose.Page 提供快速且可靠的 API，隱藏低階細節。在本教學中，我們將逐步說明完整工作流程——建立 PostScript 文件、設定 A4 頁面尺寸，以及在需要時 **adding custom fonts**。完成後，您將擁有可直接放入任何 Java 專案的即用程式碼片段。

## 快速回答
- **哪個程式庫可在 Java 中建立 PostScript？** Aspose.Page for Java。  
- **本指南針對哪種頁面尺寸？** A4（210 mm × 297 mm）。  
- **我可以嵌入自己的字型嗎？** 可以——在儲存選項中設定額外字型資料夾。  
- **生產環境需要授權嗎？** 需要商業授權；亦提供免費試用版。  
- **支援哪些 Java 版本？** Java 8 及以上。

## 如何在 Java 中設定 a4 頁面大小並建立 postscript
載入 Aspose.Page 程式庫，使用 A4 常數配置 `PsSaveOptions`，並將文件寫入檔案——全部在十行程式碼內完成。此直接方式保證正確的頁面尺寸，且可在不額外設定的情況下加入自訂字型。

## 什麼是 postscript a4 大小？
PostScript A4 大小是 ISO 216 標準（210 mm × 297 mm）在 PostScript 頁面描述語言中的表達方式。它定義了印表機與檢視器所解讀的可列印區域，確保跨平台版面一致。由於 PostScript 以裝置無關的方式描述頁面內容，使用 A4 大小可保證文件在任何支援 A4 的印表機或檢視器上呈現相同。

## 為何使用 Aspose.Page 設定 postscript 頁面大小？
Aspose.Page 支援 **30+ PostScript 運算子**，且可產生高達 **500 MB** 的檔案而無需將整個文件載入記憶體。這讓您在處理大型工作負載時仍能精確控制頁面尺寸。該程式庫亦抽象化複雜的 PostScript 語法，自動管理資源，提供高效能串流，適用於簡單的單頁傳單與複雜的多頁報告。

## 如何在 Java 中加入自訂字型
嵌入自訂字型可確保產生的文件在任何印表機或檢視器上皆與設計稿完全相符，且 Aspose.Page 會自動偵測指定資料夾中的字型。透過註冊額外字型資料夾，您可以使用任何 TrueType 或 OpenType 字型，避免備援替代，並在所有輸出裝置上維持品牌一致性。

## 先決條件
在開始之前，請確保您已具備：

- 具備 Java 程式開發的基礎知識。  
- 已安裝 Aspose.Page for Java。您可在此處下載 [此處](https://releases.aspose.com/page/java/)。  
- 一個名為 `necessary_fonts`（或任意您喜好的名稱）的資料夾，內含您想嵌入的自訂字型。

## 匯入套件
在您的 Java 專案中，匯入所需的 Aspose.Page 類別：

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

現在讓我們將範例拆解為清晰的編號步驟。

### 步驟 1：設定文件目錄
`OUTPUT_DIR` 常數告訴程式庫要將產生的檔案寫入哪個位置。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### 步驟 2：定義字型資料夾
`FONTS_FOLDER` 指向保存您自訂 TrueType 或 OpenType 字型的目錄。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步驟 3：為 PostScript 文件建立輸出串流
`FileOutputStream` 開啟一個串流，用於接收最終的 PostScript A4 輸出。

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### 步驟 4：使用 A4 大小建立儲存選項
`PsSaveOptions` 讓您指定目標頁面尺寸。  
**定義：** `PsPageSize` 為列舉，包含標準頁面尺寸常數，如 A4、Letter 與 Legal。  
設定 `options.setPageSize(PsPageSize.A4)` 即可將文件配置為標準 A4 尺寸。

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### 步驟 5：設定頁邊距並加入自訂字型資料夾
`options.setMargins(0, 0, 0, 0)` 移除所有邊距以實現滿版頁面，`options.setAdditionalFontsFolder(FONTS_FOLDER)` 則註冊您的自訂字型。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### 步驟 6：建立多頁或單頁 PS 文件
`PsDocument document = new PsDocument(outputStream, options)` 建立文件。`PsDocument` 代表一個可包含一頁或多頁的 PostScript 文件。將 `multiPaged` 設為 `true` 即可產生多頁輸出。

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### 步驟 7：關閉目前頁面並儲存文件
呼叫 `document.close()` 會完成檔案寫入，將 **PostScript A4 size** 輸出至磁碟。

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## 常見問題與技巧
- **字型未顯示？** 請確認字型檔為支援的 TrueType 或 OpenType 格式，且 `FONTS_FOLDER` 以斜線 (`/`) 結尾。  
- **仍顯示邊距？** 請在建立 `PsDocument` 之前呼叫 `options.setMargins(...)`。  
- **多頁輸出呈現空白？** 記得對每個額外頁面呼叫 `document.newPage()`。

## 常見問答

**Q: 我可以在我的 PostScript 文件中使用自訂字型嗎？**  
A: 可以，於儲存選項中設定額外字型資料夾（參見步驟 5），Aspose.Page 會自動嵌入字型。

**Q: Aspose.Page for Java 有提供試用版嗎？**  
A: 有，您可在此處取得免費試用版 [此處](https://releases.aspose.com/)。  

**Q: 我該如何取得完整的 API 參考文件？**  
A: 請參考文件說明 [此處](https://reference.aspose.com/page/java/)。  

**Q: 我該從哪裡購買 Aspose.Page for Java 的授權？**  
A: 您可在此處購買授權 [此處](https://purchase.aspose.com/buy)。  

**Q: 我可以在哪裡向社群尋求協助？**  
A: 前往 Aspose.Page 論壇 [forum](https://forum.aspose.com/c/page/39)。  

**Q: 我能產生多頁的 PostScript 檔案嗎？**  
A: 當然可以——在步驟 6 中將 `multiPaged` 設為 `true`，並於每個額外頁面呼叫 `document.newPage()`。

## 結論
透過上述步驟，您現在已掌握 **如何在 Java 中使用 Aspose.Page 設定 a4 頁面大小並建立 PostScript**，同時也能 **add custom fonts java** 並控制頁面尺寸選項。Aspose.Page 會處理繁重的底層工作，讓您專注於文件內容本身。

---

**最後更新：** 2026-06-20  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Aspose.Page Java 教學 – 設定自訂頁面大小並在 PostScript 中新增頁面](/page/java/postscript-page-manipulation/add-pages2/)
- [如何在 PostScript 中使用 Aspose.Page for Java 新增文字](/page/java/postscript-text-manipulation/)
- [Aspose Page Java 教學 - 將 PostScript 轉換為 PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```