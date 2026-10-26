---
date: 2026-10-25
description: 了解如何使用 Aspose.Page 為 Java PostScript 文件設定自訂頁面大小並新增頁面。遵循我們的逐步指南，輕鬆操作文件。
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: 在 PostScript 中新增頁面
og_description: 了解如何使用 Aspose.Page for Java 在 PostScript 中設定自訂頁面大小。遵循逐步說明，新增頁面、設定尺寸，並有效儲存文件。
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: 使用 Aspose.Page Java 在 PostScript 中設定自訂頁面大小
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Aspose.Page Java 教學 – 設定自訂頁面大小，同時在 PostScript 中新增頁面
url: /zh-hant/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java 教學 – 在 PostScript 中新增頁面時設定自訂頁面大小

## 簡介
在現代的 Java 應用程式中，常常需要為 PostScript 輸出 **set custom page size**——無論是產生發票、票券或自訂圖形。本教學將示範如何為每一頁設定自訂頁面大小、加入多頁，並產生符合精確版面需求的 PostScript 檔案。您將獲得一個完整、可直接執行的範例，可放入任何 Java 8+ 專案中。

## 快速解答
- **我可以為每一頁設定不同的頁面大小嗎？** 是——您可以使用 `document.openPage(width, height)` 以自訂尺寸開啟頁面。  
- **我需要在正式環境中使用授權嗎？** 必須擁有有效的 Aspose.Page 授權才能在非評估部署中使用。  
- **支援哪些 Java 版本？** 此函式庫支援 Java 8 及更新版本。  
- **API 是否為執行緒安全？** Document 實例不是執行緒安全的；請為每個執行緒建立獨立的 `PsDocument`。  
- **PostScript 檔案的大小上限是多少？** Aspose.Page 能有效處理多兆位元組的檔案；記憶體使用量隨內容而變化，而非頁數。  
- **我可以使用 openPage 的寬度/高度重載嗎？** 當然可以——`openPage(double width, double height)` 允許您以點為單位指定任意尺寸。  

## 先決條件
在開始之前，請確保您已具備：

- 具備 Java 程式設計的基本概念。  
- 已在專案中加入 Aspose.Page for Java（Maven/Gradle 或手動 JAR）。  
- 具備 Java 開發環境（IDE、JDK 8+）。  

## 匯入套件
以下類別是必要的：用於寫入檔案的 `FileOutputStream`、用於建立 PostScript 文件的 `PsDocument`，以及用於設定輸出選項的 `PsSaveOptions`。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟 1：建立多頁 PostScript 文件
`PsDocument` 是代表可包含多頁的 PostScript 文件的核心類別。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## 步驟 2：向第一頁加入內容
文件準備好後，您可以在第一頁加入任何需要的內容。完成後，關閉頁面以鎖定其內容。

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## 如何設定自訂頁面大小
您可以在繪製任何內容之前，呼叫 `document.openPage(width, height)` 並以點為單位指定所需的尺寸，以設定自訂頁面大小。`openPage(width, height)` 會以指定的寬度與高度開啟新頁面，讓您完整掌控頁面畫布。如果預設頁面大小不符合需求，您可以在開啟新頁面時 **set a custom page size**。這對於收據、標籤或任何非標準版面都很有用。

## 步驟 3：加入具有不同尺寸的第二頁
以下我們開啟第二頁，並明確提供自訂的寬度與高度（以點為單位）。此範例示範如何為單獨頁面設定自訂頁面大小，讓您能在同一文件中使用 **different page sizes**。

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## 步驟 4：儲存文件
最後，透過儲存文件來永久保存變更。所有頁面（包括自訂尺寸的頁面）都會寫入輸出檔案。

```java
// Save the document
document.save();
```

透過遵循上述步驟，您可以在 Java PostScript 文件中無縫加入頁面並 **set custom page size**，從而完整掌控每一頁的版面配置。

## 為何使用 Aspose.Page 來設定自訂頁面大小？
Aspose.Page 提供對頁面尺寸的精確控制，允許您以點為單位定義任意寬度與高度，在單一檔案中混合多種頁面大小，並高效串流內容以產生高效能的 PostScript。這使其非常適合發票、票券以及需要低記憶體使用的大規模批次處理。

Aspose.Page 讓您以點為單位定義精確的頁面尺寸，在單一檔案中混合多種尺寸，並高效串流內容，從而在產生 PostScript 時提供精確控制與高效能。  
- **Precision:** 尺寸以點為單位定義，讓您對頁面寬度與高度擁有精確的控制。  
- **Flexibility:** 在單一 PostScript 檔案中混合使用 **different page sizes**。  
- **Performance:** 此函式庫直接將內容串流至輸出檔案，能處理高達 500 MB 的檔案，同時將堆積記憶體使用量控制在 100 MB 以下，適用於大規模 **generate PostScript file** 情境。  
- **Rich API:** 支援超過 30 種圖形基元、10 種影像格式，以及每頁無限制的文字物件——同時遵守您設定的自訂尺寸。  

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **頁面尺寸顯示顛倒** | 請記得 `openPage(width, height)` 先接受寬度再接受高度（皆以點為單位）。 |
| **內容超出頁面** | 使用 `PsGraphics` 座標系統將元素定位於自訂邊界內，或縮放您的繪圖。 |
| **大型文件發生記憶體不足錯誤** | 如範例所示，直接寫入 `FileOutputStream` 以啟用串流，並避免一次將大型影像全部載入記憶體。 |

## 常見問答
### 我可以在單一 PostScript 文件中加入不同尺寸的頁面嗎？
是的，如本教學所示，您可以在多頁 PostScript 文件中加入尺寸不同的頁面。

### 我可以加入的頁面數量有任何限制嗎？
Aspose.Page 支援在文件中加入實質上無限制的頁面數量。

### 我可以在頁面上加入自訂內容，例如影像或圖形嗎？
當然可以！Aspose.Page 允許您加入各種內容，包括文字、影像以及其他圖形元素。

### Aspose.Page 適合處理大型文件嗎？
是的，Aspose.Page 專為高效處理小型與大型文件而設計。

### 我可以在哪裡找到 Aspose.Page 的其他資源與支援？
請參考 [Aspose.Page 文件](https://reference.aspose.com/page/java/)，或造訪 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得社群支援。

**其他問答**

**Q:** *在 PostScript 頁面上繪圖時支援哪些影像格式？*  
**A:** 您可以使用繪圖 API 直接嵌入 PNG、JPEG、BMP 與 GIF 影像。  

**Q:** *如何變更文件的預設 DPI？*  
**A:** 在建立 `PsDocument` 之前，設定 `PsSaveOptions.setResolution(int dpi)`。  

**Q:** *我可以使用密碼加密 PostScript 檔案嗎？*  
**A:** PostScript 本身不支援加密，但您可以將輸出包裝成 PDF，並在需要時套用安全設定。  

---

**最後更新：** 2026-10-25  
**測試環境：** Aspose.Page for Java 24.10  
**作者：** Aspose  

## 相關教學

- [如何在 Java 中使用 Aspose.Page 設定 A4 頁面大小並建立 PostScript](/page/java/document-creation/postscript/)
- [如何使用 Aspose.Page Java API 將 PostScript 轉換為 PDF](/page/java/postscript-conversion/to-pdf/)
- [如何在 Java PostScript 中使用 Aspose.Page 繪製矩形](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}