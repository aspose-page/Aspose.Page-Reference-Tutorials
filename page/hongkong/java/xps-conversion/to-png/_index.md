---
date: 2025-12-23
description: 在 Java 中使用 Aspose.Page 輕鬆將 XPS 轉換為 PNG。本指南示範如何以可靠、開發者友善的方案將 XPS 渲染成圖像檔案。
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: 在 Java 中將 XPS 轉換為 PNG
url: /zh-hant/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中將 XPS 轉換為 PNG

## 介紹
在快速變化的軟件開發領域，**將 XPS 轉換為 PNG**（XML Paper Specification 轉 Portable Network Graphics）的需求屢見不鮮。為了在 Java 中順利完成此任務，Aspose.Page 提供了一個強大的解決方案。本教學將逐步說明如何使用 Aspose.Page for Java 將 XPS 轉換為 PNG。

## 快速回答
- **哪個函式庫負責轉換？** Aspose.Page for Java  
- **涉及哪些格式？** XPS（來源）→ PNG（輸出）  
- **生產環境需要授權嗎？** 需要，必須購買商業授權  
- **可以設定影像解析度嗎？** 可以，使用 `PngSaveOptions.setResolution()`  
- **能否只選擇特定頁面？** 當然可以——在選項物件中提供頁碼即可  

## 為什麼要將 XPS 轉換為 PNG？
將 XPS 渲染成影像檔案在需要在網頁上顯示文件、嵌入報告或產生預覽縮圖時非常實用。PNG 提供無損壓縮且支援度廣，適合作為 XPS 內容的高品質視覺呈現。

## 前置條件
在開始本教學之前，請確保已完成以下設定：
1. **Java Development Kit (JDK)：** 確認系統已安裝 JDK。  
2. **Aspose.Page for Java：** 下載並安裝 Aspose.Page 函式庫。下載連結請參考[此處](https://releases.aspose.com/page/java/)。  
3. **整合開發環境 (IDE)：** 建議使用 IntelliJ IDEA 或 Eclipse 等支援 Java 的 IDE。  

## 如何在 Java 中將 XPS 轉換為 PNG
以下提供逐步說明，說明**如何將 XPS 文件**轉換為 PNG 影像，並附上可直接複製到專案中的程式碼片段。

### 匯入套件
在 Java 專案中匯入使用 Aspose.Page 所需的套件。於 Java 檔案開頭加入以下 import 陳述式：

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### 步驟 1：設定文件目錄
定義存放來源 XPS 檔案以及 PNG 輸出檔案的資料夾路徑。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步驟 2：載入 XPS 文件
建立 `XpsDocument` 例項以載入來源 XPS 檔案。

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### 步驟 3：初始化選項
設定 PNG 輸出選項，可在此調整平滑度、解析度，並指定要渲染的頁面。

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### 步驟 4：建立渲染裝置
建立一個 `ImageDevice` 以保存渲染後的影像資料。

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### 步驟 5：儲存與迭代
渲染 XPS 文件，然後將每個產生的 PNG 位元組陣列寫入磁碟檔案。

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

依照上述步驟，即可輕鬆使用 Aspose.Page for Java 將 XPS **渲染為 PNG** 影像檔。

## 結論
總結來說，Aspose.Page for Java 簡化了 XPS 轉 PNG 的轉換流程，為開發者提供可靠且高效的工具。將此函式庫整合至 Java 專案，可大幅提升文件處理的便利性。

## 其他常見問題

**Q: 我可以只轉換 XPS 檔案中的特定頁面嗎？**  
A: 當然可以。使用 `PngSaveOptions` 的 `setPageNumbers` 方法即可指定要渲染的頁碼。

**Q: 推薦的高品質 PNG 解析度是多少？**  
A: 300 dpi 是品質與檔案大小的良好平衡，您亦可透過 `options.setResolution()` 進行調整。

**Q: API 是否支援多執行緒轉換大型文件？**  
A: 支援，您可以在平行執行緒中呼叫轉換程式碼，讓每個執行緒處理不同的頁面或文件區段。

**Q: 轉換非常大的 XPS 檔案時，如何控制記憶體使用量？**  
A: 建議逐頁處理，並在每次寫入後釋放 `FileOutputStream`，如範例程式碼所示。

**Q: 能否在產生的 PNG 檔案中加入自訂的中繼資料？**  
A: 雖然 `PngSaveOptions` 本身未直接提供中繼資料欄位，但您可以在轉換完成後，使用標準影像函式庫對 PNG 進行後處理以嵌入中繼資料。

**最後更新：** 2025-12-23  
**測試環境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}