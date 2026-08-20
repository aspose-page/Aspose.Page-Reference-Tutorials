---
date: 2026-03-13
description: 學習如何在 Java 中使用 Aspose.Page Java 將 XPS 轉換為 JPEG。本分步指南將向您展示如何使用 Aspose.Page
  Java 函式庫高效地將 XPS 轉換為 JPEG。
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page Java 將 XPS 轉換為 JPEG
url: /zh-hant/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page Java 將 XPS 轉換為 JPEG

## Introduction to Aspose.Page Java
在本教學中 **您將學會如何使用 Aspose.Page Java 函式庫將 XPS 轉換為 JPEG**。將 XPS 檔案轉換成 JPEG 圖片是常見需求，尤其在需要於網站入口、桌面檢視器或電子郵件附件中以點陣圖方式顯示文件頁面時。我們會逐行說明程式碼、解釋每個設定的意義，並分享實用技巧，讓您能自信地將此轉換流程嵌入自己的 Java 應用程式。

## Quick Answers
- **哪個函式庫負責轉換？** Aspose.Page Java  
- **可以選擇特定頁面嗎？** 可以 – 在 `JpegSaveOptions` 中使用 `setPageNumbers`  
- **可以控制哪些影像品質？** 平滑模式、解析度與 JPEG 品質設定  
- **正式環境需要授權嗎？** 需要商業授權（提供免費試用版）  
- **程式碼是否相容 Java 8？** 完全相容 – API 支援 Java 8 及以上版本  

## What is XPS and Why Convert XPS to JPEG?
XPS（XML Paper Specification）是一種固定版面文件格式，類似 PDF。將 XPS 轉換為 JPEG 在需要縮圖、電子郵件附件，或與僅接受影像檔案的系統整合時非常有用。JPEG 在視覺品質與檔案大小之間取得良好平衡，適合作為網路預覽圖。

## Prerequisites
在開始撰寫程式碼之前，請先確保具備以下條件：

- **Java 開發環境** – 已安裝並設定 JDK 8 或更新版本。  
- **Aspose.Page for Java** – 從官方網站[此處](https://releases.aspose.com/page/java/)下載最新函式庫。  
- **範例 XPS 文件** – 您欲轉換為 JPEG 的 XPS 檔案。  

## Import Packages
開始於 Java 原始檔中匯入必要的類別：

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Step 1: Initialize Paths and Load the XPS Document
設定包含來源 XPS 檔案的目錄，並建立 `XpsDocument` 實例：

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **專業提示：** 使用 `java.nio.file` 的 `Paths.get()` 以取得跨平台的路徑處理方式。

## Step 2: Configure JPEG Save Options
定義 JPEG 圖片的渲染方式——解析度、平滑度以及要匯出的頁面：

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` 產生適合列印的高解析度輸出。  
- `setPageNumbers` 讓您只挑選需要的頁面，節省時間與記憶體。

## Step 3: Create the Rendering Device
`ImageDevice` 會將渲染後的頁面捕獲為位元組陣列：

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Step 4: Render the XPS Document to JPEG
呼叫 `save` 方法，傳入裝置與先前設定的選項：

```java
document.save(device, options);
```

此時 `device` 內部保存的是一個二維陣列，每個元素皆為 JPEG 編碼的頁面。

## Step 5: Iterate Through the Result and Write Files
遍歷渲染結果，將每個位元組陣列寫入獨立的 JPEG 檔案：

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

每個檔案皆以 `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg` 命名，方便辨識來源文件與頁碼。

## Common Use Cases
- **為文件管理系統產生縮圖**。  
- **在僅支援影像格式的 Web 應用中嵌入頁面預覽**。  
- **批次處理大型 XPS 檔案庫**，將其轉為 JPEG 以作存檔或報表用途。  

## Common Issues & Troubleshooting
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| **Blank JPEG files** | 輸出串流未正確刷新或關閉 | 確保在內層迴圈中呼叫 `imageStream.close()`（如範例所示）。 |
| **Out‑of‑memory errors** on large XPS files | 同時渲染所有頁面佔用過多記憶體 | 改為分批處理頁面或增大 JVM 堆積大小 (`-Xmx`)。 |
| **Missing pages** | `setPageNumbers` 未包含目標頁面 | 核對頁碼陣列是否與實際 XPS 頁面索引（從 1 開始）相符。 |

## Frequently Asked Questions

### Q: Is Aspose.Page suitable for commercial projects?
A: Yes, Aspose.Page is a commercial product with licensing options available. Check [here](https://purchase.aspose.com/buy) for details.

### Q: Can I try Aspose.Page before purchasing?
A: Yes, you can obtain a free trial [here](https://releases.aspose.com/).

### Q: Where can I find Aspose.Page documentation?
A: The documentation is available [here](https://reference.aspose.com/page/java/).

### Q: How can I get support for Aspose.Page?
A: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) for community‑based support.

### Q: Do I need a temporary license for testing?
A: Yes, you can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
您現在已掌握 **如何使用 Aspose.Page Java 將 XPS 轉換為 JPEG**。依循本步驟指南，即可將此轉換流程整合至任何 Java 應用程式——無論是桌面工具、Web 服務或批次處理工具。歡迎自行嘗試不同的解析度、頁面選擇與影像格式，以符合專案需求。

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Page 24.11 for Java (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}