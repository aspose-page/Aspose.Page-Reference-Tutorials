---
date: 2025-12-21
description: Aspose.Page XMP 教學 – 透過 Aspose.Page for Java，清晰逐步指引，學習如何修改 EPS 檔案的 XMP
  中繼資料。
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: Aspose.Page XMP 教程 – 使用 Java 更改 XMP 中的命名值
url: /zh-hant/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose page xmp 教程 – 使用 Java 更改 XMP 中的命名值

在現代文件工作流程中，**Aspose.Page for Java** 讓讀取、編輯和寫入 EPS 檔案中的 XMP 中繼資料變得簡單。此 **aspose page xmp tutorial** 將指導您如何更改 XMP 資料包中的命名值，讓您的文件中繼資料保持準確且可搜尋。無論是更新頁面尺寸、作者資訊或自訂標籤，下列步驟都會精確說明如何在 Java 中完成。

## 快速解答
- **此教學涵蓋什麼內容？** 使用 Aspose.Page for Java 在 EPS 檔案中更改命名的 XMP 值。  
- **需要哪個版本的函式庫？** 任何近期的 Aspose.Page for Java 版本（API 多年來保持穩定）。  
- **需要授權嗎？** 生產環境需要臨時或完整授權；免費試用可用於測試。  
- **實作需要多長時間？** 對於熟悉 Java I/O 的開發者，大約 10‑15 分鐘。  
- **可以在其他檔案格式中使用嗎？** XMP API 亦支援 PDF、SVG 以及 Aspose.Page 支援的其他格式。

## XMP 中繼資料是什麼？
XMP（可擴充中繼資料平台）是一種標準化格式，用於將豐富的中繼資料（例如創建者、標題與自訂屬性）直接嵌入檔案中。在 EPS 文件中，XMP 與傳統的 PostScript 註解共存，使應用程式能在不改變視覺內容的情況下讀取與修改中繼資料。

## 為什麼使用 Aspose.Page for Java 編輯 XMP？
- **完整控制** – 可存取任何 XMP 屬性，包括自訂結構，無需自行解析原始 XML。  
- **跨格式一致性** – 同一套 API 可用於 EPS、PDF 與 SVG，簡化程式碼維護。  
- **無外部相依性** – 純 Java 函式庫，無需本機程式碼或額外解析器。  
- **健全的錯誤處理** – 內建驗證確保產生的 EPS 符合標準規範。

## 介紹
Aspose.Page for Java 是一套功能強大的 Java 函式庫，可協助操作與處理 EPS 檔案。針對這些檔案中的 XMP 中繼資料，Aspose.Page 為開發人員提供完整的功能集合。本教學將重點放在更改 XMP 中的命名值，為希望提升文件處理能力的開發者提供清晰簡潔的指引。

## 前置條件
在深入教學之前，請確保您已具備以下前置條件：
1. **Java Development Environment** – 確保您的機器已設置 Java 開發環境。  
2. **Aspose.Page for Java Library** – 下載並將 Aspose.Page for Java 函式庫整合至您的專案。您可在[此處](https://reference.aspose.com/page/java/)找到函式庫與詳細文件說明。  
3. **Sample EPS File** – 準備一個 EPS 範例檔案以供測試。若沒有，可使用提供的範例檔案 **"xmp4.eps"**。

## 匯入套件
要開始此流程，請在 Java 程式碼中匯入必要的套件。這些套件對於與 Aspose.Page for Java 互動至關重要。請在 Java 檔案的開頭加入以下程式碼行：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

現在，讓我們將使用 Aspose.Page for Java 更改 XMP 中命名值的流程分解為多個步驟：

## 步驟 1：初始化輸入 EPS 檔案串流
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## 步驟 2：初始化 PsDocument
```java
PsDocument document = new PsDocument(psStream);
```

## 步驟 3：取得 XMP 中繼資料
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 步驟 4：在 XMP 中設定新值
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## 步驟 5：初始化輸出 EPS 檔案串流
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## 步驟 6：以變更的 XMP 中繼資料儲存文件
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 步驟 7：關閉輸入 EPS 串流
```java
// Close input EPS stream
psStream.close();
```

此逐步指南確保以系統化方式使用 Aspose.Page for Java 更改 XMP 中的命名值。遵循這些步驟，即可將此功能無縫整合至您的 Java 應用程式中。

## 常見問題與解決方案
- **FileNotFoundException** – 確認 `dataDir` 指向正確的資料夾，且 `xmp4.eps` 存在。  
- **LicenseException** – 若出現授權錯誤，請確保在建立 `PsDocument` 前已載入有效的 Aspose.Page 授權檔案。  
- **Metadata Not Updated** – 儲存後，使用中繼資料檢視器（例如 Adobe Bridge）開啟產生的 EPS，確認新值已出現。

## 結論
總結來說，Aspose.Page for Java 簡化了在 EPS 檔案中處理 XMP 中繼資料的流程。本教學已提供您有效更改 XMP 中命名值的知識，提升文件處理能力。

## 常見問答
### 我可以在其他程式語言中使用 Aspose.Page for Java 嗎？
Aspose.Page 主要支援 Java，但 Aspose 亦提供其他程式語言的類似函式庫。

### 是否提供 Aspose.Page for Java 的免費試用？
是的，您可在[此處](https://releases.aspose.com/)探索 Aspose.Page for Java 的免費試用。

### 我可以在哪裡找到關於 Aspose.Page for Java 的其他支援與討論？
請前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39)取得社群支援與討論。

### 我如何取得 Aspose.Page for Java 的臨時授權？
您可在[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

### 我可以在哪裡購買 Aspose.Page for Java？
若要購買 Aspose.Page for Java，請前往[購買頁面](https://purchase.aspose.com/buy)。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.Page for Java（最新版本）  
**作者：** Aspose