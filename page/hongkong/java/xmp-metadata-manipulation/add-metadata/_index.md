---
date: 2026-03-08
description: 學習如何使用 Aspose Page Java 教程將 XMP 元資料加入 EPS 檔案。請跟隨此一步一步的指南，以提升您的文件管理。
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java 教程 – 向 EPS 檔案添加 XMP 中繼資料
url: /zh-hant/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP 中添加元資料

## 介紹
在本 **aspose page java tutorial** 中，您將學習如何使用 Java 為文件的元資料加入 XMP 資訊。此步驟說明指南會帶您閱讀現有的 EPS 檔案、擷取其 XMP 元資料，並使用 Aspose.Page for Java 函式庫將變更儲存回磁碟。完成教學後，您將擁有一套可在任何 EPS 工作流程中重複使用的 XMP 操作模式。

## 快速答覆
- **需要哪個函式庫？** Aspose.Page for Java  
- **可以為任何 EPS 檔案加入 XMP 嗎？** 可以 – 若檔案尚未有 XMP 區塊，API 會自動建立新區塊。  
- **開發時需要授權嗎？** 免費試用可用於評估；正式上線需購買商業授權。  
- **支援哪個 Java 版本？** Java 8 及以上版本。  
- **實作需要多長時間？** 基本的元資料更新通常在 10 分鐘以內完成。

## Aspose Page Java 是什麼？
Aspose.Page for Java（亦稱 **aspose page java**）是一套高效能 API，讓開發者在不需 Adobe 軟體的情況下，建立、編輯與轉換 PostScript 與 EPS 檔案。它同時提供完整的 XMP 元資料存取功能，讓您能直接在圖形檔案中嵌入可搜尋的資訊。

## 為什麼要在 EPS 檔案中加入 XMP 元資料？
嵌入 XMP 元資料可提升資產管理、可搜尋性，並符合 IPTC、Dublin Core 等業界標準。當您加入創作者、標題或建立日期等欄位時，下游系統（如 DAM、搜尋引擎或列印工作流程）即可自動索引與整理您的 EPS 資產。

## Aspose Page Java 教學概覽
本教學示範在 EPS 檔案中操作 XMP 元資料的核心步驟。了解這些步驟後，您即可將元資料處理整合至更大的文件處理管線，提升可搜尋性，並符合數位資產管理的業界標準。

## 前置條件
在開始教學之前，請確保您具備以下條件：
- 具備基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page for Java 函式庫。您可於 [此處](https://releases.aspose.com/page/java/) 下載。  
- 一個您想要修改的 EPS 檔案。

## 匯入套件
首先，將必要的套件匯入您的 Java 程式中：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## 步驟 1：取得 XMP 元資料
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

將 `"Your Document Directory"` 替換為實際存放文件的路徑。

## 步驟 2：取得 CreatorTool 值
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## 步驟 3：取得 CreateDate 值
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## 步驟 4：取得 Title 值
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## 步驟 5：取得 Format 值
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## 步驟 6：取得 Creator 值
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## 步驟 7：取得 MetadataDate 值
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## 步驟 8：以新 XMP 元資料儲存文件
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

最後，別忘了關閉輸入的 EPS 串流：

```java
// Close input EPS stream
psStream.close();
```

現在，您已成功使用 Aspose.Page for Java 為 EPS 檔案加入元資料！

## 常見問題與解決方案
- **Missing XMP block** – API 會自動建立區塊，但請確保 EPS 檔案未受損。  
- **Unsupported characters** – XMP 值必須為 UTF‑8，請避免在元資料欄位中使用非標準符號。  
- **Large EPS files** – 如範例所示使用串流處理檔案，以降低記憶體使用量，並務必在 `finally` 區塊中關閉串流。

## 結論
在本 **aspose page java tutorial** 中，我們探討了如何使用 Aspose.Page for Java 函式庫為 EPS 檔案加入 XMP 元資料。這套強大的 API 讓您能以程式方式操作文件元資料，協助資產保持有序且易於搜尋。

## 常見問答

**Q: Aspose.Page for Java 可以免費使用嗎？**  
A: Aspose.Page for Java 為商業產品。您可透過免費試用 [此處](https://releases.aspose.com/) 了解其功能。

**Q: 哪裡可以找到 Aspose.Page for Java 的文件說明？**  
A: 文件說明可於 [此處](https://reference.aspose.com/page/java/) 取得。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 您可在 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: Aspose.Page for Java 支援哪些檔案格式？**  
A: Aspose.Page for Java 支援多種格式，包括 EPS、PDF 與 XPS。

**Q: 我可以購買 Aspose.Page for Java 嗎？**  
A: 可以，請於 [此處](https://purchase.aspose.com/buy) 購買。

**Q: 在加入元資料時，如何處理大型 EPS 檔案？**  
A: 請以串流方式處理檔案（如範例所示），以降低記憶體使用，並及時關閉串流。

**Q: 我可以修改既有的 XMP 欄位，而不只是讀取它們嗎？**  
A: 當然可以 – 您可使用 `xmp.put(key, value)` 於儲存前更新或新增條目。

---

**最後更新：** 2026-03-08  
**測試環境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}