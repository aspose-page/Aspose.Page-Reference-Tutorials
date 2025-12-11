---
date: 2025-12-11
description: 學習如何使用 Aspose.Page 設定自訂頁面大小並向 Java PostScript 文件新增頁面。請遵循我們的一步一步指引，以實現無縫的文件操作。
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java 教程 – 在 PostScript 中添加頁面時設定自訂頁面大小
url: /zh-hant/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java 教學 – 在 PostScript 中新增頁面時設定自訂頁面大小

## 介紹
在現代的 Java 應用程式中，**設定自訂頁面大小** 以產生 PostScript 輸出往往是必須的——無論您是在產生發票、票券或是自訂圖形。Aspose.Page for Java 讓這項工作變得簡單。在本教學中，您將一步步學會如何在 PostScript 文件中新增頁面並設定自訂頁面大小，讓您每次都能產出恰到好處的版面配置。

## 快速回答
- **我可以為每一頁設定不同的頁面大小嗎？** 是的，您可以使用 `document.openPage(width, height)` 以自訂尺寸開啟頁面。  
- **正式環境使用需要授權嗎？** 非評估部署需要有效的 Aspose.Page 授權。  
- **支援哪些 Java 版本？** 此函式庫支援 Java 8 及以上版本。  
- **API 是否為執行緒安全？** Document 實例不是執行緒安全的；每個執行緒請建立獨立的 `PsDocument`。  
- **PostScript 檔案的大小上限是多少？** Aspose.Page 能有效處理多 MB 檔案；記憶體使用量隨內容而非頁數成長。

## 前置條件
在開始之前，請確保您已具備：

- 具備 Java 程式設計的基礎知識。  
- 已在專案中加入 Aspose.Page for Java（Maven/Gradle 或手動 JAR）。  
- Java 開發環境（IDE、JDK 8 以上）。  

## 匯入套件
要開始使用，先從 Aspose.Page 函式庫匯入必要的類別。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟 1：建立多頁 PostScript 文件
首先，建立一個已設定為多頁的 `PsDocument`。此步驟會設定輸出串流，並告訴函式庫我們將處理多頁檔案。

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

## 步驟 2：在第一頁加入內容
文件準備好後，您可以在第一頁加入任何需要的內容。完成後，關閉頁面以鎖定其內容。

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## 如何設定自訂頁面大小
如果預設的頁面大小不符合需求，您可以在開啟新頁面時**設定自訂頁面大小**。這對收據、標籤或任何非標準版面都非常有用。

## 步驟 3：以不同尺寸新增第二頁
以下示範如何開啟第二頁，並明確提供自訂的寬度與高度（單位為點）。這說明了如何為個別頁面設定自訂頁面大小。

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## 步驟 4：儲存文件
最後，將變更寫入檔案。所有頁面——包括自訂尺寸的頁面——都會寫入輸出檔。

```java
// Save the document
document.save();
```

依照上述步驟，您即可使用 Aspose.Page 在 Java PostScript 文件中無縫新增頁面並**設定自訂頁面大小**，完全掌控每一頁的版面配置。

## 結論
Aspose.Page for Java 提供了功能強大且友善的 API 來處理 PostScript 文件。現在您已了解如何新增多頁、套用自訂尺寸並儲存結果，讓您能為任何基於 Java 的解決方案產生精確排版的輸出。

## 常見問題
### 我可以在單一 PostScript 文件中加入不同尺寸的頁面嗎？
可以，如本教學所示，您可以在多頁 PostScript 文件中加入尺寸各異的頁面。  
### 新增頁面的數量有任何限制嗎？
Aspose.Page 支援在文件中加入實質上無限制的頁數。  
### 我可以在頁面上加入自訂內容，例如影像或圖形嗎？
當然可以！Aspose.Page 允許您加入各種內容，包括文字、影像與其他圖形元素。  
### Aspose.Page 適合處理大型文件嗎？
是的，Aspose.Page 設計上能有效處理小型與大型文件。  
### 我可以在哪裡找到 Aspose.Page 的其他資源與支援？
探索 [Aspose.Page documentation](https://reference.aspose.com/page/java/)，或前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 取得社群支援。  

**其他問答**

**問：** *在 PostScript 頁面上繪圖時支援哪些影像格式？*  
**答：** 您可以使用繪圖 API 直接嵌入 PNG、JPEG、BMP 與 GIF 影像。  

**問：** *如何變更文件的預設 DPI？*  
**答：** 在建立 `PsDocument` 前，設定 `PsSaveOptions.setResolution(int dpi)`。  

**問：** *我可以使用密碼加密 PostScript 檔案嗎？*  
**答：** PostScript 本身不支援加密，但您可以將輸出包裝成 PDF，並在需要時套用安全設定。

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
