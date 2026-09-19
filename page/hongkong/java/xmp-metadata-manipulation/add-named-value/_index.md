---
date: 2026-09-19
description: 了解如何使用 Aspose.Page for Java 為 EPS 檔案加入 XMP 命名值——一步一步的指南，附有程式碼範例。
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: 使用 Java 在 XMP 中加入命名值
og_description: 如何使用 Aspose.Page for Java 為 EPS 檔案加入 XMP 命名值。遵循此簡明指南，即可在數分鐘內注入自訂中繼資料。
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: 如何使用 Java 在 EPS 檔案中加入 XMP 命名值
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: 如何使用 Java 在 EPS 檔案中加入 XMP 命名值
url: /zh-hant/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP 中新增具名值

## 介紹
在現代 Java 開發中，學習 **如何在 EPS 檔案中加入 XMP** 中繼資料對於保存文件來源與提升可搜尋性至關重要。透過 **Aspose.Page for Java**，您可以輕鬆將自訂具名值注入 XMP 封包。本教學將逐步說明完整流程，並提供程式碼範例，讓您立即在 EPS 文件中加入 XMP 中繼資料。

## 快速答覆
- **需要的函式庫？** Aspose.Page for Java (Aspose)  
- **目標檔案類型？** 包含 XMP 中繼資料的 EPS 檔案  
- **主要使用情境？** 將自訂具名值（例如頁面尺寸上限）加入 XMP  
- **前置條件？** JDK 8+ 以及 Aspose.Page for Java 函式庫  
- **一般實作時間？** 設定好函式庫後約 5–10 分鐘  

## 什麼是 asp？
Aspose 是 Aspose 的簡稱，提供一套 API 讓開發者能在不依賴外部軟體的情況下，建立、編輯、轉換與渲染各種文件格式。Aspose.Page for Java 專注於 PostScript 與 EPS 處理，提供對頁面內容、圖形與 XMP 等中繼資料的程式化存取。

## 為什麼要在 XMP 中加入具名值？
具名值允許您直接在 XMP 封包內儲存任意的鍵值對，讓下游工具能即時讀取。這可提升搜尋引擎友善度、啟用工作流程自動化，並透過嵌入法規資訊而不改變視覺內容，滿足合規需求。

## 為什麼這很重要
在 XMP 中加入具名值可讓您儲存任意鍵值對，且無需解析整個 EPS 檔案即可讀取。此功能在自動化出版管線、數位資產管理系統以及以合規為導向的工作流程中尤為寶貴，因為中繼資料會驅動下游動作。

## 前置條件
在開始之前，請確保您具備以下項目：

- **Java Development Kit (JDK)：** 已在您的機器上安裝 8 版或以上的最新 JDK。  
- **Aspose.Page for Java 函式庫：** 從官方 [Aspose.Page for Java download](https://releases.aspose.com/page/java/) 下載，並將 JAR 加入專案的 classpath。  
- **EPS 檔案：** 已包含 XMP 中繼資料或會自動產生 XMP 的 EPS 檔案。

## 匯入套件
先匯入必要的 Java 套件。這些匯入讓您能存取檔案串流、EPS 文件模型以及 XMP 處理類別。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 如何使用 Java 在 EPS 檔案中加入 XMP 具名值
要加入具名值，先以 `FileInputStream` 讀取 EPS 檔案，取得或建立其 `XmpMetadata` 物件，將目標 `NamedValue` 插入相應的命名空間，最後使用 `FileOutputStream` 寫回修改後的文件。Aspose.Page 會在缺少 XMP 封包時自動建立，確保新中繼資料正確嵌入。

### 步驟 1：初始化輸入 EPS 檔案串流
**FileInputStream** 是 Java I/O 類別，用於從檔案讀取原始位元組。將來源 EPS 檔案載入 `FileInputStream`，此串流會將文件傳遞給 Aspose 的 API。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **專業提示：** 讓 `dataDir` 變數保持可設定，這樣相同程式碼即可在不同環境中使用。

### 步驟 2：取得 XMP 中繼資料
**XmpMetadata** 代表與 EPS 文件關聯的 XMP 封包。取得現有的 XMP 封包；若 EPS 檔案沒有，Aspose 會根據 PS 註解自動建立新的 XMP 物件。

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### 步驟 3：加入具名值
**NamedValue** 是儲存在 XMP 中繼資料命名空間內的鍵值對。將自訂具名值插入 XMP 結構。本例在 `xmpTPg:MaxPageSize` 命名空間下新增一個鍵。

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **為什麼重要：** 具名值讓您儲存任意鍵值對，下游應用程式可在不解析整個文件的情況下讀取。

### 步驟 4：初始化輸出 EPS 檔案串流
**FileOutputStream** 是 Java I/O 類別，用於將原始位元組寫入檔案。準備一個 `FileOutputStream` 以保存修改後的 EPS。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### 步驟 5：儲存文件
`save` 方法會將變更寫入檔案。它會把更新後的 XMP 封包寫回 EPS，確保新具名值成為文件中繼資料的一部份。

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### 步驟 6：關閉輸入 EPS 串流
關閉原始檔案的串流可防止資源洩漏，並確保檔案不會被鎖定以供後續操作使用。

```java
psStream.close();
```

完成上述六個步驟後，您已成功使用 **Aspose.Page for Java** **在 XMP 中加入具名值**。

## 常見問題與解決方案
| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `xmp` | EPS 檔案沒有 XMP，且 Aspose 未能產生 | 確認 EPS 至少包含一個 PS 註解，或手動建立新的 `XmpMetadata` 實例。 |
| Output file is empty | 輸出串流未刷新/關閉 | 確認在 `finally` 區塊中呼叫 `outPsStream.close()`（如範例所示）。 |
| Duplicate key error | 同一具名值被加入兩次 | 在加入前使用 `xmp.containsNamedValue(...)` 檢查鍵是否已存在。 |

## 常見問答

**Q: 可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Page for Java 設計為可與其他 Java 函式庫無縫整合，提供開發環境的彈性。

**Q: Aspose.Page for Java 有免費試用版嗎？**  
A: 有，您可在 [Aspose releases page](https://releases.aspose.com/) 取得 Aspose.Page for Java 的免費試用版。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 前往 [temporary license page](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 哪裡可以找到更多 Aspose.Page for Java 的教學與範例？**  
A: 請參考 [documentation](https://reference.aspose.com/page/java/) 內的完整教學與範例。

**Q: Aspose.Page for Java 適合大型專案嗎？**  
A: 絕對適合，Aspose.Page for Java 專為大型專案設計，提供高效能且穩定的文件操作功能。

## 結論
本指南示範了 **Aspose.Page for Java** 如何簡單地 **在 EPS 檔案的 XMP 中加入具名值**。依照上述步驟，您即可為文件加入自訂中繼資料，提升可搜尋性，並支援更智慧的下游處理。

---

**最後更新：** 2026-09-19  
**測試環境：** Aspose.Page for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose

## 相關教學

- [How to Add XMP Namespace in EPS Files Using Aspose.Page – Java Tutorial](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Add XMP Metadata to EPS Files Using Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Read XMP using Aspose.Page – Java Guide](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}