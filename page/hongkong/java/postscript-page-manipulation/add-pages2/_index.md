---
date: 2026-02-18
description: 學習如何使用 Aspose.Page 設定自訂頁面大小並向 Java PostScript 文件新增頁面。請遵循我們的逐步指南，輕鬆完成文件操作。
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java 教程 – 在 PostScript 中加入頁面時設定自訂頁面大小
url: /zh-hant/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java 教學 – 在 PostScript 中新增頁面時設定自訂頁面大小

## 介紹
在現代的 Java 應用程式中，**設定自訂頁面大小** 以產生 PostScript 輸出往往是必須的——無論是產生發票、票券或自訂圖形。本教學將教您如何為每一頁 **設定自訂頁面大小**、加入多頁，最後 **產生符合精確版面需求的 PostScript 檔案**。我們會一步一步說明程式碼，讓您能快速在自己的專案中套用此技巧。

## 快速答覆
- **我可以為每一頁設定不同的頁面大小嗎？** 可以，使用 `document.openPage(width, height)` 以自訂尺寸開啟頁面。  
- **正式環境需要授權嗎？** 需要有效的 Aspose.Page 授權才能在非評估環境中使用。  
- **支援哪些 Java 版本？** 此函式庫支援 Java 8 及更新版本。  
- **API 是否為執行緒安全？** Document 實例本身不是執行緒安全的；請為每個執行緒建立獨立的 `PsDocument`。  
- **PostScript 檔案的大小上限是多少？** Aspose.Page 能有效處理多 MB 級別的檔案；記憶體使用量會隨內容而變，與頁數無關。  
- **可以使用 openPage 的寬度/高度重載嗎？** 當然可以——`openPage(double width, double height)` 允許您以點 (points) 為單位指定任意尺寸。  

## 前置條件
在開始之前，請確保您已具備：

- 基本的 Java 程式設計概念。  
- 已將 Aspose.Page for Java 加入專案（Maven/Gradle 或手動 JAR）。  
- Java 開發環境 (IDE、JDK 8 以上)。  

## 匯入套件
首先，匯入 Aspose.Page 函式庫中所需的類別。

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步驟 1：建立多頁 PostScript 文件
先建立一個支援多頁的 `PsDocument`，此動作會設定輸出串流，並告訴函式庫我們將處理多頁檔案。

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
如果預設的頁面大小不符合需求，您可以在開啟新頁面時 **設定自訂頁面大小**。這對收據、標籤或任何非標準版面都非常有用。

## 步驟 3：加入尺寸不同的第二頁
以下示範如何開啟第二頁，並以點為單位明確提供自訂寬度與高度。此範例展示了在同一文件中為個別頁面 **設定自訂頁面大小**，讓您能使用 **不同的頁面大小**。

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## 步驟 4：儲存文件
最後，將變更寫入檔案。所有頁面（包括自訂尺寸的頁面）都會被寫入輸出檔。

```java
// Save the document
document.save();
```

依照上述步驟，您即可在 Java PostScript 文件中無縫加入頁面並 **設定自訂頁面大小**，完整掌控每一頁的版面配置。

## 為何使用 Aspose.Page 來設定自訂頁面大小？
- **精準度：** 尺寸以點為單位定義，讓您對頁寬與頁高擁有絕對控制。  
- **彈性：** 可在同一 PostScript 檔案中混合使用 **不同的頁面大小**。  
- **效能：** 函式庫直接將內容串流至輸出檔，適合大規模 **產生 PostScript 檔案** 的情境。  
- **豐富 API：** 支援繪製圖形、嵌入影像與加入文字，同時遵守您設定的自訂尺寸。  

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **頁面尺寸顯示顛倒** | 記得 `openPage(width, height)` 的參數順序是先寬度後高度（皆以點為單位）。 |
| **內容超出頁面範圍** | 使用 `PsGraphics` 座標系統將元素定位於自訂邊界內，或對繪圖進行縮放。 |
| **大型文件導致記憶體不足** | 如範例所示，直接寫入 `FileOutputStream` 以啟用串流，並避免一次載入大量影像至記憶體。 |

## 常見問答
### 我可以在單一 PostScript 文件中加入不同尺寸的頁面嗎？
可以，正如本教學所示，您可以在多頁 PostScript 文件中加入尺寸各異的頁面。  

### 加入的頁面數量有沒有上限？
Aspose.Page 支援在文件中加入實質上無限制的頁面數量。  

### 我可以在頁面上加入自訂內容，例如影像或圖形嗎？
當然可以！Aspose.Page 允許您加入各種內容，包括文字、影像與其他圖形元素。  

### Aspose.Page 能否處理大型文件？
可以，Aspose.Page 設計上能有效處理小型與大型文件。  

### 我在哪裡可以找到更多 Aspose.Page 的資源與支援？
請參考 [Aspose.Page 文件](https://reference.aspose.com/page/java/)，或前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得社群支援。  

**其他問答**

**Q:** *在 PostScript 頁面上繪圖時支援哪些影像格式？*  
**A:** 您可以直接使用繪圖 API 嵌入 PNG、JPEG、BMP 與 GIF 影像。  

**Q:** *如何變更文件的預設 DPI？*  
**A:** 在建立 `PsDocument` 前，呼叫 `PsSaveOptions.setResolution(int dpi)` 設定解析度。  

**Q:** *我可以為 PostScript 檔案設定密碼保護嗎？*  
**A:** PostScript 本身不支援加密，但您可以將輸出包裝成 PDF，並在 PDF 中套用安全設定。  

---

**最後更新：** 2026-02-18  
**測試環境：** Aspose.Page for Java 24.10  
**作者：** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}