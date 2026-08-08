---
date: 2026-05-25
description: 了解如何在 Java 中使用 Aspose.Page 讀取 XMP。本分步指南展示了提取 XMP 元資料、創建者資訊、時間戳、縮圖等。
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: 如何使用 Java 讀取 XMP 元資料
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: 使用 Aspose.Page 讀取 XMP – Java 指南
url: /zh-hant/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 從 XMP 取得中繼資料

## 如何使用 Aspose.Page（Java）讀取 XMP？

使用 `new Document("file.eps")` 載入 EPS 檔案——`Document` 類別代表已載入的檔案。呼叫 `getXmpMetadata()`，可擷取 XMP 封包，然後查詢回傳的 `XmpMetadata` 物件——一個類似映射的介面，用於 XMP 屬性，以取得所需的鍵。這就是使用 Aspose.Page 讀取 XMP 所需的全部步驟。API 抽象化了低層解析，讓您只需兩行程式碼即可取得可直接使用的屬性映射。

歡迎閱讀我們的逐步教學，展示 **如何讀取 XMP** 中繼資料，使用 Java 與 Aspose.Page 函式庫。XMP（可擴充中繼資料平台）是一項廣泛採用的標準，用於在文件中嵌入豐富的中繼資料。完成本指南後，您將能讀取文件格式的 XMP，提取創建者資訊、時間戳記、縮圖等，讓您能構建更智慧的文件分析解決方案。

## 快速解答
- **「讀取 XMP」是什麼意思？** 它表示以程式方式擷取儲存在檔案內的 XMP 封包（其中包含中繼資料）。
- **需要哪個函式庫？** Aspose.Page for Java（從官方頁面[here](https://releases.aspose.com/page/java/)下載）。
- **我需要授權嗎？** 在正式環境中需要臨時或正式授權；免費試用版可用於評估。
- **支援哪個 Java 版本？** Java 8 或更高版本。
- **我可以從其他格式讀取 XMP 嗎？** 可以——Aspose.Page 可從 EPS、PDF、JPEG、PNG 以及超過 20 種其他格式中擷取 XMP。

## 前置條件
在深入程式碼之前，請確保您已具備：

- **Java Development Kit (JDK)** – 已在您的機器上安裝並設定 Java 8+。  
- **Aspose.Page for Java** – 從官方網站[here](https://releases.aspose.com/page/java/)下載函式庫。  
- 一個包含 XMP 中繼資料的 EPS 檔案（例如 `xmp1.eps`）。  

## 匯入套件
`XmpMetadata` 類別位於 `com.aspose.page.xmp` 命名空間，而 `Document` 類別位於 `com.aspose.page`。匯入兩者以便操作 EPS 檔案及其中繼資料。  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 步驟 1：初始化輸入 EPS 檔案串流
首先設定文件目錄的路徑，並初始化輸入 EPS 檔案串流。  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## 步驟 2：取得 XMP 中繼資料
`XmpMetadata` 是 Aspose.Page 用來保存從文件擷取的 XMP 封包的物件。使用 `document.getXmpMetadata()` 取得它。如果檔案沒有 XMP，API 會根據現有的 PostScript 註解合成一個最小的封包。  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## 步驟 3：擷取 CreatorTool 資訊
`CreatorTool` 鍵位於 `xmp` 命名空間下，記錄產生檔案的應用程式。檢查其是否存在並輸出其值。  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## 步驟 4：擷取 CreateDate 資訊
`CreateDate` 保存文件最初建立的時間戳記。使用相同的 `containsKey`/`get` 模式讀取它。  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## 步驟 5：取得縮圖寬度
如果存在縮圖，`xmp:Thumbnails` 陣列會包含一個或多個條目。每個條目包含 `width`、`height` 以及二進位資料。範例會擷取第一個縮圖的寬度。  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## 步驟 6：擷取 Format 資訊
`format` 鍵告訴您原始檔案格式（例如 “application/postscript”）。在需要記錄或驗證來源類型時非常有用。  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## 步驟 7：取得 DocumentID
`DocumentID` 是由創建應用程式指派的唯一識別碼。可用於大型資產庫的去重。  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## 為何這很重要
Aspose.Page 能從 **20+** 種檔案格式讀取 XMP，且可處理高達 **500 MB** 的文件而不需將整個檔案載入記憶體，為您提供快速、低開銷的關鍵中繼資料存取。此功能對批次處理管線、數位資產管理系統以及任何依賴可搜尋、機器可讀文件屬性的解決方案皆至關重要。

## 常見陷阱與技巧
- **缺少 XMP**：某些 EPS 檔案可能不含 XMP。`getXmpMetadata()` 呼叫會根據現有的 PS 註解合成最小集合，但若未嵌入則無法取得完整中繼資料。  
- **縮圖陣列**：`xmp:Thumbnails` 鍵可以包含多個條目。範例僅擷取第一個；若需要全部縮圖，請遍歷陣列。  
- **命名空間意識**：XMP 鍵使用命名空間（例如 `xmp:`、`dc:`）。請確保引用正確的鍵名，否則 `containsKey` 會回傳 false。  

## 常見問與答
### 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？
是的，Aspose.Page 支援 Java、.NET 以及其他多種語言。請參閱 [documentation](https://reference.aspose.com/page/java/) 中的完整列表。

### Aspose.Page for Java 有提供免費試用嗎？
是的，您可在此取得免費試用版 [here](https://releases.aspose.com/)。

### 我可以在哪裡找到 Aspose.Page for Java 的支援？
請前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 取得社群協助與官方支援。

### 如何取得 Aspose.Page for Java 的臨時授權？
您可在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

### 有其他 Aspose.Page for Java 的資源嗎？
請探索完整的 [documentation](https://reference.aspose.com/page/java/) 並在此下載函式庫 [here](https://releases.aspose.com/page/java/)。

## 其他問答
**Q: 此方法適用於包含 XMP 的 PDF 檔案嗎？**  
A: 是的，Aspose.Page 可從 PDF、EPS 以及多種影像格式讀取 XMP。

**Q: 讀取後我可以修改 XMP 中繼資料嗎？**  
A: 當然可以。`XmpMetadata` 物件是可變的；您可以新增、更新或移除鍵，然後儲存文件。

**Q: 有辦法擷取所有縮圖影像，而不僅是尺寸嗎？**  
A: 您可以從每個縮圖條目的 `xmpGImg:data` 屬性取得二進位資料，並寫入檔案。

## 結論
您現在已掌握使用 Java 與 Aspose.Page **如何讀取 XMP** 中繼資料的技巧。依循這些步驟，您可以擷取創建工具、時間戳記、縮圖、格式資訊與文件 ID——讓您完整了解 EPS 檔案中嵌入的中繼資料。歡迎嘗試其他 XMP 命名空間，以獲取更豐富的資料供您的應用程式使用。

---

**最後更新：** 2026-05-25  
**測試環境：** Aspose.Page for Java 24.12 (latest)  
**作者：** Aspose

## 相關教學

- [Aspose Page Java 教學 – 為 EPS 檔案新增 XMP 中繼資料](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page XMP 教學 – 使用 Java 在 XMP 中新增命名空間](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page XMP 教學 – 使用 Java 更改 XMP 中的命名值](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}