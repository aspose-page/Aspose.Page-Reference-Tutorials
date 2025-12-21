---
date: 2025-12-21
description: 學習如何使用 Java 透過 Aspose.Page 讀取 XMP 中繼資料。本分步指南示範如何讀取文件格式 XMP 並提取關鍵屬性。
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: 使用 Java 讀取 XMP 元資料 – Aspose.Page 指南
url: /zh-hant/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 從 XMP 取得中繼資料

## 如何使用 Java 讀取 XMP 中繼資料

歡迎閱讀我們的逐步教學，說明如何使用 Java 以及 Aspose.Page 程式庫 **讀取 XMP** 中繼資料。XMP（Extensible Metadata Platform）是一項廣泛採用的標準，用於在文件中嵌入豐富的中繼資料。完成本指南後，您將能夠讀取文件格式的 XMP、提取創建者資訊、時間戳記、縮圖等，讓您能夠構建更智慧的文件分析解決方案。

## 快速解答
- **「如何讀取 XMP」是什麼意思？** 它指的是以程式方式從檔案中提取 XMP 中繼資料。  
- **需要哪個程式庫？** Aspose.Page for Java（可從 Aspose 下載頁面取得）。  
- **需要授權嗎？** 生產環境需要臨時或正式授權；亦提供免費試用版。  
- **支援哪個 Java 版本？** Java 8 以上。  
- **可以從其他格式讀取 XMP 嗎？** 可以，Aspose.Page 能處理 EPS、PDF 以及多種嵌入 XMP 的影像格式。

## 前置條件
在開始編寫程式碼之前，請確保您已具備以下條件：

- **Java Development Kit (JDK)** – 已在您的機器上安裝並設定 Java 8 以上。  
- **Aspose.Page for Java** – 從官方網站[此處](https://releases.aspose.com/page/java/)下載程式庫。  
- 一個包含 XMP 中繼資料的 EPS 檔案（例如 `xmp1.eps`）。

## 匯入套件
在您的 Java 專案中，匯入必要的套件：

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
從 EPS 檔案取得 XMP 中繼資料。若檔案未包含 XMP 中繼資料，系統會根據 PS 中繼資料註解產生新的 XMP。

```java
XmpMetadata xmp = document.getXmpMetadata();
```

## 步驟 3：擷取 CreatorTool 資訊
檢查並輸出 XMP 中繼資料的 "CreatorTool" 值。

```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## 步驟 4：擷取 CreateDate 資訊
檢查並輸出 XMP 中繼資料的 "CreateDate" 值。

```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## 步驟 5：取得縮圖寬度
若存在縮圖，擷取並輸出第一個縮圖的寬度。

```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## 步驟 6：擷取格式資訊
檢查並輸出 XMP 中繼資料的 "format" 值。

```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## 步驟 7：取得 DocumentID
檢查並輸出 XMP 中繼資料的 "DocumentID" 值。

```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## 為何這很重要
讀取 XMP 中繼資料可讓您以程式方式發現文件的來源、建立日期及其他關鍵屬性，無需在檢視器中開啟文件。此功能對於批次處理、內容管理系統以及以中繼資料驅動索引與搜尋的數位資產流程尤為有用。

## 常見陷阱與技巧
- **缺少 XMP**：某些 EPS 檔案可能不含 XMP。`getXmpMetadata()` 會根據現有的 PS 註解合成最小集合，但若未嵌入完整的中繼資料，將無法取得全部資訊。  
- **縮圖陣列**：`xmp:Thumbnails` 鍵可包含多個條目。範例僅擷取第一個；若需要全部縮圖，請遍歷陣列。  
- **命名空間意識**：XMP 鍵使用命名空間（例如 `xmp:`、`dc:`）。請確保引用正確的鍵名，否則 `containsKey` 會回傳 false。

## 常見問與答
### 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？
是的，Aspose.Page 支援多種語言，包括 Java、.NET 等。請參閱[文件說明](https://reference.aspose.com/page/java/)了解詳情。

### Aspose.Page for Java 是否提供免費試用？
是的，您可在[此處](https://releases.aspose.com/)取得免費試用。

### 我可以在哪裡取得 Aspose.Page for Java 的支援？
請前往[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)取得社群支援。

### 如何取得 Aspose.Page for Java 的臨時授權？
您可在[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

### 有其他 Aspose.Page for Java 的資源嗎？
請探索完整的[文件說明](https://reference.aspose.com/page/java/)並在[此處](https://releases.aspose.com/page/java/)下載程式庫。

## 其他問答
**Q: 這種方法能用於包含 XMP 的 PDF 檔案嗎？**  
A: 是的，Aspose.Page 能從 PDF、EPS 以及多種影像格式讀取 XMP。

**Q: 讀取後我可以修改 XMP 中繼資料嗎？**  
A: 當然可以。`XmpMetadata` 物件是可變的，您可以新增、更新或移除鍵，之後再儲存文件。

**Q: 有方法擷取所有縮圖影像，而不僅是尺寸嗎？**  
A: 您可以從每個縮圖條目的 `xmpGImg:data` 屬性取得二進位資料，並寫入檔案。

## 結論
您現在已掌握使用 Java 與 Aspose.Page **讀取 XMP** 中繼資料的方法。依循上述步驟，即可擷取創建工具、時間戳記、縮圖、格式資訊與文件 ID，完整了解 EPS 檔案中嵌入的中繼資料。歡迎嘗試其他 XMP 命名空間，以取得更豐富的資料供您的應用程式使用。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose