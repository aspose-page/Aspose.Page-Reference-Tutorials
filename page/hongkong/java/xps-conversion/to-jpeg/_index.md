---
date: 2025-12-23
description: 學習如何在 Java 中將 XPS 轉換為 JPEG，並了解如何使用 Aspose.Page 高效轉換 XPS 檔案。這是一份提供逐步說明的完整指南，助您實現無縫整合。
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中將 XPS 轉換為 JPEG
url: /zh-hant/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中將 XPS 轉換為 JPEG

## 介紹
在本教學中，**您將學會如何使用功能強大的 Aspose.Page for Java 套件將 XPS 轉換為 JPEG**。將 XPS 檔案轉成影像格式是當您需要在 Web 或桌面應用程式中顯示、預覽或進一步處理文件頁面時的常見需求。我們會一步步說明每個步驟、解釋每行程式碼的意義，並提供實用技巧，讓您能自信地將轉換邏輯整合到自己的專案中。

## 快速答覆
- **使用哪個函式庫進行轉換？** Aspose.Page for Java  
- **可以選擇特定頁面嗎？** 可以 – 在 `JpegSaveOptions` 中使用 `setPageNumbers`  
- **可以控制哪些影像品質？** 平滑模式、解析度與 JPEG 品質設定  
- **正式環境需要授權嗎？** 需要商業授權（提供免費試用版）  
- **程式碼相容於 Java 8 嗎？** 完全相容 – API 支援 Java 8 及更新版本  

## 什麼是 XPS 以及為何要轉換成 JPEG？
XPS（XML Paper Specification）是一種固定版面文件格式，類似 PDF。將 XPS 轉換為 JPEG 在需要縮圖、電子郵件附件，或是只能接受影像檔的系統時非常有用。JPEG 在視覺品質與檔案大小之間取得良好平衡，特別適合網頁預覽。

## 前置條件
在開始撰寫程式碼之前，請確保您已具備以下項目：

- **Java 開發環境** – 已安裝並設定 JDK 8 或更新版本。  
- **Aspose.Page for Java** – 從官方網站[此處](https://releases.aspose.com/page/java/)下載最新套件。  
- **範例 XPS 文件** – 您想要轉換為 JPEG 的 XPS 檔案。  

## 匯入套件
在 Java 原始檔中匯入必要的類別：

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## 步驟 1：初始化路徑並載入 XPS 文件
設定包含來源 XPS 檔案的目錄，並建立 `XpsDocument` 實例：

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **專業提示:** 使用 `java.nio.file` 的 `Paths.get()` 以取得跨平台的路徑處理方式。

## 步驟 2：設定 JPEG 儲存選項
定義 JPEG 影像的渲染方式——解析度、平滑度以及要匯出的頁面：

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` 產生適合列印的高解析度輸出。  
- `setPageNumbers` 讓您只挑選需要的頁面，節省時間與記憶體。

## 步驟 3：建立渲染裝置
`ImageDevice` 會將渲染後的頁面捕獲為位元組陣列：

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## 步驟 4：將 XPS 文件渲染為 JPEG
呼叫 `save` 方法，傳入裝置與先前設定的選項：

```java
document.save(device, options);
```

此時 `device` 內含一個二維陣列，每個元素代表一頁已 JPEG 編碼的資料。

## 步驟 5：遍歷結果並寫入檔案
迭代渲染出的頁面，將每個位元組陣列寫入獨立的 JPEG 檔案：

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

每個檔案會以 `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg` 命名，方便辨識來源文件與頁碼。

## 常見問題與除錯
| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| **空白 JPEG 檔案** | 輸出串流未正確刷新或關閉 | 確保在內層迴圈中呼叫 `imageStream.close()`（如範例所示）。 |
| **大型 XPS 檔案產生記憶體不足** | 同時渲染所有頁面佔用過多 RAM | 分批處理頁面或增加 JVM 堆積大小 (`-Xmx`)。 |
| **缺少頁面** | `setPageNumbers` 未包含目標頁面 | 核對頁碼陣列是否與實際 XPS 頁面索引（從 1 開始）相符。 |

## 常見問答

### Q: Aspose.Page 適合商業專案嗎？
A: 適合，Aspose.Page 為商業產品，提供多種授權方案。詳情請參考[此處](https://purchase.aspose.com/buy)。

### Q: 購買前可以先試用 Aspose.Page 嗎？
A: 可以，您可於[此處](https://releases.aspose.com/)取得免費試用版。

### Q: 哪裡可以找到 Aspose.Page 的文件說明？
A: 文件說明位於[此處](https://reference.aspose.com/page/java/)。

### Q: 如何取得 Aspose.Page 的技術支援？
A: 請前往[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)尋求社群支援。

### Q: 測試時需要臨時授權嗎？
A: 需要，您可於[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

## 結論
您已掌握 **如何使用 Aspose.Page for Java 將 XPS 轉換為 JPEG**。依循本步驟指南，您可以將此轉換流程整合至任何 Java 應用程式——無論是桌面工具、Web 服務或批次處理工具。歡迎自行嘗試不同的解析度、頁面選擇與影像格式，以符合專案需求。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.Page 24.11 for Java（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}