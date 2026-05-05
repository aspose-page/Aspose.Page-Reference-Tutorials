---
date: 2026-05-05
description: 學習如何使用 Aspose.Page for Java 為 EPS 檔案新增 XMP 命名值——一步一步的指南，附程式碼範例。
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: 使用 Java 在 XMP 中新增具名值
second_title: Aspose.Page Java API
title: 如何使用 Java 在 EPS 檔案中加入 XMP 命名值
url: /zh-hant/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP Metadata 中新增命名值

## 介紹
在現代 Java 開發中，學習 **如何在 EPS 檔案中加入 XMP** Metadata 對於保存文件來源資訊與提升可搜尋性至關重要。使用 **asp**（Aspose.Page for Java），您可以輕鬆將自訂命名值注入 XMP 封包。本教學將逐步說明完整步驟，並提供程式碼範例，讓您立即開始在 EPS 文件中加入 XMP Metadata。

## 快速回答
- **需要的函式庫？** Aspose.Page for Java (asp)  
- **目標檔案類型？** 包含 XMP Metadata 的 EPS 檔案  
- **主要使用情境？** 在 XMP 中加入自訂命名值（例如頁面大小限制）  
- **前置條件？** JDK 8+ 以及 Aspose.Page for Java 函式庫  
- **預計實作時間？** 設定好函式庫後約 5–10 分鐘  

## asp 是什麼？
*asp* 是 **Aspose** 的簡稱，Aspose 是一系列 .NET 與 Java API，簡化文件處理。Aspose.Page for Java 元件讓您能建立、編輯與轉換 PostScript 與 EPS 檔案，並提供對其 Metadata（包括 XMP）的完整程式化存取。

## 為什麼要在 XMP Metadata 中新增命名值？
- **提升搜尋引擎友善度：** 自訂標籤可增進文件的可發現性。  
- **工作流程自動化：** 後續工具可讀取您的自訂值以作決策。  
- **合規性：** 可將法規資訊直接嵌入文件套件中。  

## 為何此議題重要
在 XMP 中新增命名值可讓您儲存任意的鍵值對，且無需解析整個 EPS 檔案即可讀取。此功能在自動化出版流程、數位資產管理系統以及以合規為導向的工作流程中尤為重要，因為這些情境的後續動作皆由 Metadata 驅動。

## 前置條件
在開始之前，請確保您已具備以下項目：

- **Java Development Kit (JDK)：** 在您的機器上安裝了近期版本的 JDK（8 或以上）。  
- **Aspose.Page for Java 函式庫：** 從官方 [download link](https://releases.aspose.com/page/java/) 下載，並將 JAR 加入專案的 classpath。  
- **EPS 檔案**：該檔案可已包含 XMP Metadata，或可自動產生。

## 匯入套件
首先匯入所需的 Java 套件。這些匯入讓您能存取檔案串流、EPS 文件模型以及 XMP 處理類別。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 使用 Java 在 EPS 檔案中新增 XMP 命名值
以下是一個簡潔的編號步驟說明，精確展示 **如何在 EPS 文件中加入 XMP** 命名值。

### 步驟 1：初始化輸入 EPS 檔案串流
將來源 EPS 檔案載入 `FileInputStream`。此串流將文件傳遞給 Aspose 的 API。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **專業提示：** 讓 `dataDir` 變數保持可配置，以便相同程式碼在不同環境下皆可運作。

### 步驟 2：取得 XMP Metadata
取得現有的 XMP 封包。若 EPS 檔案沒有 XMP，Aspose 會根據 PS 註解建立全新的 XMP 物件。

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### 步驟 3：新增命名值
在 XMP 結構中插入自訂命名值。在此範例中，我們於 `xmpTPg:MaxPageSize` 命名空間下新增一個鍵。

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **為何重要：** 命名值允許您儲存任意的鍵值對，後續應用程式可在不解析整份文件的情況下讀取。

### 步驟 4：初始化輸出 EPS 檔案串流
準備一個 `FileOutputStream`，用於儲存已修改的 EPS。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### 步驟 5：儲存文件
持久化變更。`save` 呼叫會將更新後的 XMP 封包寫回 EPS 檔案。

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### 步驟 6：關閉輸入 EPS 串流
釋放原始檔案的句柄，以避免資源泄漏。

```java
psStream.close();
```

透過上述六個步驟，您已成功使用 **asp**（Aspose.Page for Java）**在 XMP Metadata 中新增命名值**。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|-------|-------|-----|
| `NullPointerException` on `xmp` | EPS 檔案沒有 XMP，且 Aspose 未能產生 | 確保 EPS 至少包含一個 PS 註解，或手動建立新的 `XmpMetadata` 實例。 |
| 輸出檔案為空 | 輸出串流未刷新/關閉 | 確認在 `finally` 區塊中呼叫 `outPsStream.close()`（如範例所示）。 |
| 鍵值重複錯誤 | 同一命名值被加入兩次 | 在加入前使用 `xmp.containsNamedValue(...)` 檢查鍵是否已存在。 |

## 常見問答

**Q: 我可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Page for Java 設計能與其他 Java 函式庫無縫協作，提供開發環境的彈性。

**Q: 是否提供 Aspose.Page for Java 的免費試用？**  
A: 有，您可在此取得 Aspose.Page for Java 的免費試用 [here](https://releases.aspose.com/).

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 請前往 [this link](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 在哪裡可以找到更多 Aspose.Page for Java 的教學與範例？**  
A: 請參閱 [documentation](https://reference.aspose.com/page/java/) 以取得完整的教學與範例。

**Q: Aspose.Page for Java 是否適用於大型專案？**  
A: 絕對適用，Aspose.Page for Java 專為有效處理大型專案而設計，提供強大的文件操作功能。

## 結論
本指南示範了 **asp**（Aspose.Page for Java）如何輕鬆 **在 EPS 檔案的 XMP Metadata 中新增命名值**。透過上述步驟，您可以為文件加入自訂 Metadata，提升可搜尋性，並啟用更智慧的後續處理。

**最後更新：** 2026-05-05  
**測試環境：** Aspose.Page for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}